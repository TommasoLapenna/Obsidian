## TODO
Cambiare /dev/nvme... a disk by-id con il comando import?

## Installazione
https://wiki.gentoo.org/wiki/User:Ali3nx/Installing_Gentoo_Linux_EFISTUB_On_ZFS
Per connettersi:
```
net-setup wlp0s20f3
```
Il setup prevede entrambi i dischi partizionati allo stesso modo:
```
partizione 1: boot, 1 G
partizione 2: 16 G, swap
partizione 3: root, resto del disco
```
La partizione boot starà fuori da ogni tipo di mirroring, mentre la swap sarà in un mdadm raid1 e la root in una pool zfs in mirroring (raid 1). La swap è fuori dalla partizione di zfs perché se gestita da guest'ultimo si possono avere crash e blocchi dell'os.
Si partizionano quindi i dischi nel seguente modo:
```
parted -a optimal /dev/nvme[01]n1
mklabel gpt
mkpart esp 1 1001
mkpart swap 1001 17001
mkpart rootfs 17001 100%
set 1 boot on
```
E poi si crea un file system vfat per le due partizioni di boot
```
mkfs.vfat -F32 /dev/nvmen[01]n1p1
```
Setup per zfs:
```
zgenhostid -f
modprobe zfs
```
Per evitare eventuali problematiche, si usa l'id dei dischi per non creare ambiguità
```
ls -l /dev/disk/by-id
```
Con questi identificatori individuati si può adesso creare la zpool col mirror:
```
zpool create -f -o ashift=12 -o autotrim=on -o cachefile=/etc/zfs/zpoo.lcache -O compression=lz4 -O xattr=sa -O relatime=on -O acltype=posixacl -O dedup=off -m none -R /mnt/gentoo rpool mirror /dev/disk/by-id/... /dev/disk/by-id/...
```
Si creano ora tutti i necessari dataset:
```
zfs create -o mountpoint=none -o canmount=off rpool/root
zfs create -o mountpoint=/ rpool/root/gentoo
zpool set bootfs=rpool/root/gentoo rpool
```
Creazione dei seguenti container dataset:
```
zfs create -o canmount=off rpool/usr
zfs create -o canmount=off rpool/var
zfs create -o canmount=off rpool/var/lib
zfs create -o canmount=off rpool/home
```
Si crea poi la user home directory dataset
```
zfs create -o mountpoint=/home/tommaso rpool/home/username
```
 E poi si aggiornano i device symbolics links:
 ```
 udevadm trigger
 ```
Si può adesso procedere con l'istallazione vera e propria di gentoo: si controlla la data con `date`.ù
Si monta la partizione di boot nella directory del chroot
```
cd /mnt/gentoo
mkdir boot
mount /dev/nvme0n1p1 boot
```
Si scarica adesso lo stage file, meglio versione desktop in quanto sembra che in quella non si possono creare delle dipendenze circolari e si compila più velocemente
```
wget https://distfiles.gentoo.org/releases/amd64/autobuilds/20250921T170345Z/stage3-amd64-desktop-openrc-20250921T170345Z.tar.xz
tar xpvf stage3-...-.tar.xz --xattrs-include='*.*' --numeric-owner -C /mnt/gentoo
```
Si copia la zpool cache
```
mkdir etc/zfs
cp /etc/zfs/zpool.cache etc/zfs
```
e le impostazioni di network
```
cp /etc/resolv.conf etc/
```
Si montano i device richiesti
```
mount --rbind /dev dev
mount --types /proc proc
mount --rbind /sys sys
mount --make-rslave dev
mount --make-rslave proc
mount --make-rslave sys
```
Si può adesso fare chroot
```
chroot /mnt/gentoo /bin/bash
source /etc/profile
export PS1="(chroot) $(PS1)"
```