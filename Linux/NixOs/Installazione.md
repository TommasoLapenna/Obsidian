                                                                                                                                                                                                      Accesso superuser (senza password).
```
sudo -i
```

Per connettersi alla rete, occorre avviare il wpa_supplicant. Il supplicant è un estremo di una connessione LAN e il suo compito è quello di ottenere l'autenticazione da un autenticatore dall'altra parte della connessione.
```
systemctl start wpa_supplicant
```
e poi
```
wpa_cli
```
Dentro wpa_cli:
```
add_network 
set_network 0 ssid "lapennahouse 5 Ghz"
set_network 0 psk "caterina1"
enable_network 0
```

Occorre adesso partizionare i dischi, siccome il sistema è UEFI, si utilizza GPT (Guid Partition Table)
```
parted /dev/nvme0n1 -- mklabel gpt
parted /dev/nvme0n1 -- mkpart root ext4 512MB 100%
parted /dev/nvme0n1 -- mkpart ESP fat32 1MB 512MB 
parted /dev/nvme0n1 -- set 2 esp on
```

Adesso si passa alla formattazione, si fa utilizzo dei label per rendere indipendente la configurazione del file system da i cambiamenti del sistema

```
mkfs.ext4 -L nixos /dev/nvme0n1p1
mkfs.fat -F 32 -n boot /dev/nvme0n1p2
```

Implementazione del sistema RAID 1 con mdamd e gestitone con LVM: md si occupa della parte raid, mentre LVM si occupa di creare partizioni virtuali e flessibili. La swap verrà implementata come file a livello LVM (quindi non è presente la partizione fisica per essa in nessuno dei due dischi). Per il RAID si partiziona il secondo disco esattamente come il primo.
Si creano i raid md0 per root e md1 per il boot, con lsblk si vede sotto alle partizioni fisiche a che array appartengono
```
mdamd --create /dev/md0 --level=1 --raid-devices=2 /dev/nvme0n1p1 /dev/nvme1n1
mdamd --create /dev/md1 --level=1 --raid-devices=2 /dev/nvme0n1p2 /dev/nvme1n2
//per monitorare la scinronizzazione che avviene dopo la creazioned dell'array:
watch -n .1 cat /proc/mdstat
mdadm --misc --detail /dev/md0
mdadm --misc --detail /dev/md1
```
E' buona pratica fare regolarmente scrubbing.
Per la configurazione di LVM  si creano inizialmente i volumi fisici
```
pvcreate /dev/md0
pvcreate /dev/md1
pvdisplay
```
Successivamente si creano i volume group
```
vgcreate vgmd0 /dev/md0
vgcreate vgmd1 /dev/md1
vgdisplay
```
Si creano infine i volumi logici (tra la quale la swap)
```
lvcreate -L 200G vgmd0 -n lvroot
lvcreate -C y -L 8G vgmd0 -n lvswap
lvcreate -l 100%free vgmd1 -n lvboot
```
Si risvolgono le operazioni fatte con parted precedentemente su questi volumi logici.
E si crea no i file system in questi volume logico
```
mkfs.ext4 -L nixos /dev/vgmd0/lvroot
mkswap -L swap /dev/vgmd0/lvswap
mkfs.fat -F 32 -n boot /dev/vgmd1/lvboot
```
Si aggiorna la configurazione RAID
```
mdadm --examine --scan >> /etc/mdadm.conf
```
Si passa finalmente all'istallazione vera e propria
```
mount /dev/vgmd0/lvroot /mnt
mkdir -p /mnt/boot
mount -o umask=077 /dev/vgmd1/lvboot /mnt/boot
```
In nixos, è necessario creare un file di configurazione /mnt/etc/nixos/configuration.nix (in nix, e quindi dichiarativo) della desiderata configurazione del sistema
```
nixos-generate-config --root /mnt
nano /mnt/etc/nixos/configuration.nix
```
Poi, in base alla configurazione fornita
```
nixos-install
```

Allora, installazione non è andata come previsto: ci sono stati problemi con la partizione logica lvboot, che non veniva riconosciuta effetivamente come una partizione bootabile non essendo di tipo efi. 
Con tante bestemmie sono state allora cancellati gli array raid:
```
lvremove /dev/vgmd[01]/lv[boot|swap|root]
mdadm --stop(anche --fail) /dev/md[01]
mdadm --remove /dev/md[01]
mdadm --zero-superblock /dev/nvme[01]n1p[12]
```
Si verifica con 
```
cat /proc/mdstat
```
se gli array sono stati effettivamente cancellati, inoltre va cancellato il file di configurazione /etc/mdadm.conf che penso debba addirittura essere /etc/mdadm/mdadm.conf (non so perché solo sulla guida di arch non crea la subdirectory).
Inoltre prima non ho azzerato tutti i dischi e infatti appena riavviato il computer l'array si è ricomposto perché a quanto pare se rimane l'informazione nel disco, anche se l'array viene cancellato, viene ricomposto.
Per dare infine il colpo di grazia a questa shalata si riempono i dischi di dati random
```
dd if=/dev/urandom bs=4096 of=/dev/nvme[01]n1
```
 A questo giro la partizione md1 di RAID per il boot deve avere i metadati versione 1.0, per essere leggibile dal bootloader
 ```
 mdamd --create /dev/md1 --level=1 --raid-devices=2 --metadata=1.0 /dev/nvme0n1p2 /dev/nvme1n2
 ```

 per poter montare md0 serve un file system
 ```
 mkfs.ext4 /dev/md0
 ```

Per il warning dell'installer sull'uso di RAID, si aggiungr  
```
boot.swraid.enable = true;
```
che a quanto pare è disattivato di default nella nuove versioni. A quanto pare il problema dello warning mdadm: Neither MAILADDR nor PROGRAM has been set. This will cause the `mdmon` service to crash è dato dal fatto che mdmon dee notificare un indirizzo email o chaiamre un programma se uno dei dischi si rompe de quindi
```
  boot.swraid.mdadmConf = ''
    MAILADDR=nobody@nowhere
  '';
```

de allora
Cambio di programma
Prima si installa tutto su nvme01n1 e poi si fa il raid dopo. Quindi si ritolgono tutti gli array coi passaggi prima.
Dopo l'istallazione manca un cazzo di modo per connettersi e quindi si aggiunge iwd ai pacchetti da installare.

https://github.com/titanknis/Nixos-Installation-Guide?tab=readme-ov-file#generate-nixos-configuration-and-install

creati quindi volumi logici, da configurare poi il RAID

Nella configurazione iniziale sono montati così le partizioni:
```
mount /dev/vg0/nixos-root /mnt
mount /dev/vg0/nixos-home /mnt/home
mount /dev/nvme0n1p2 /mnt/boot
```

Per connettersi visto che per qualche motivo wpa_cli non funziona
```
wpa_passphrase "SSID">wifi.conf (che si trova nella directory home, da sistemare)
wpa_supplicant -i wlp0s20f3 -c wifi.conf -B
dhcpcd???
```
