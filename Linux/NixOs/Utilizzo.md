## Introduzione
In Nixos, tutto è controllato in un unico file di configurazione, ed è quindi replicabile. Nixos è un sistema operativo immutable (diverso da distribuzioni quindi come arch, simile a qualcosa come fedora),  quindi il core del sistema operativo (insieme a programmi, servizi e impostazioni) non possono essere modificati direttamente. Quindi quando si effettua un aggiornamento quindi non si prendono in considerazione le modifiche dell'utente, in quanto separate.

![[Pasted image 20250914135124.png|center|500]]

Questo sistema di aggiornamenti si chiama *Atomic Upgrades*, dove il sistema viene aggiornato completamente, in quanto non è possibile applicare aggiornamenti parziali.
## Snapshot e Rollback
Ogni volta che si aggiorna il sistema, viene effettuato uno snapshot, attraverso i quali è possibile effettuare rollback a configurazioni precedenti (direttamente dal bootloader). A differenza degli altri immutable systems, dove lo snapshot viene effettuato all'aggiornamento rilasciato dal mantainer, in Nixos lo snapshot viene effettuato alla modifica di `configuration.nix`.
Gli snapshot in Nixos si chiamano *generations*, e la loro dimensione è pari a quella dei cambiamenti rispetto a quella precedente.
## Configurazione
  Nell'istallazione di Nixos sono presenti due file di configurazione:
  - `configuration.nix`: contiene impostazioni come quelle di sistema, desktop environment, programmi istallati ecc.
  - `hardware-configuration.nix`: contiene impostazioni come partizioni del disco, swap, moduli kernel ecc.

   I file di configurazione sono collocati in 
   ```
   # cd /etc/nixos
   # ls
	   configuration.nix    hardware-configuration.nix
   ```

   I file sono tutti scritti nel linguaggio nix.

   Nel parametro
   ```
   environment.systemPackages = with pkgs; [
	   ...
   ];
   ```

sono presenti tutti i programmi installati sul sistema.
Per creare una nuova generazione, dopo una modifica della configurazione, si usa il comando
```
sudo nixos-rebuild switch
```
Che si occuperà di scaricare i file necessari e poi buildare.
Quando si ha un programma come impostazione di sistema, come ad esempio
```
programs.firefox.enable = true;
```
verrà aggiunto il programma normalmente a `environment.systemPackages`, e verranno poi aggiunte delle configurazioni per il programma, come ad esempio nel caso di firefox
```
programs.firefox = {
	enable = true;
	package = pkgs.firefox-beta:
	policies.Homepage.StartPage = "https://nixos.org"
	policies.DisableTelemetry = true;
}
```
Altri esempi di programmi:
```
programs.git = {
	enable = true;
	config = {
		user.name = "...";
		user.email= "...";
		init.defaultBranch = "...";
		pull.rebase = true;
	}
}

programs.neovim = {
	enable = true;
	defaultEditor = true;

	extraPackages = [
		pkgs.vimPlugins.gruvbox-nvim
	];
}
```

Se si attivano dei  servizi come ssh nel seguente modo
```
services.openssh = {
	enable = true;
	settings.PermitRootLogin = false;
	settings.PasswordAutentication = false;
	ports = [22]
}
```
verrà attivato pure il relativo servizio *systemd*

## Altre Opzioni di Rebuild
![[Pasted image 20250914142124.png]]
## Ricerca
Tutte i possibili pacchetti e possibili impostazioni si possono trovare in https://search.nixos.org/packages

## Channel
Ci sono due channel
- *nixpkgs*
- *nixpgs-unstable*:  rolling release
Per scegliere il channel:
```
sudo nix-channel --add https://nixos.org/channels/nixos... nixos
```
Per aggiornare il channel:
```
sudo nix-channel --upgrade
```
![[Pasted image 20250914144443.png|center]]
I pacchetti per gli aggiornamenti successivi saranno quindi poi quelli più recenti.

> [!warning]
> In questo modo però la versione dei pacchetti rimane specifica al sistema, non rendendolo così  riproducibile su altre macchine che potrebbero avere il channel impostato ad un'altra versione.

La soluzione è quella di combinare la versione di nixpkgs con la configurazione stessa, per fare ciò si utilizzano i *flake*.
## Flakes
Per ovviare quindi al problema del punto precedente, si attivano i flake nella directory delle configurazioni:
```
# cd /etc/nixos
# sudo nix --extra-experimental-features...?
```
Il risultato è la creazione di un file `flake.nix`, che indica quali dipendenze seguire e quali versioni (di output) scaricare.
![[Pasted image 20250914145143.png|center|600]]
Successivamente si riutilizza il comando di rebuild e apparirà un file *flake.lock* (se non funziona va specificata la posizione del flake).

> [!info] Lock File
> Un file di lock è un file che non va letto, indica le versioni e le dipendenze per assicurare la riproducibilità. Di base questo file, in un caso minimale, conterrà solo la versione di nixpkgs.

Se si utilizzano i flake il comando per fare l'update diventa
```
sudo nix flake update
```
