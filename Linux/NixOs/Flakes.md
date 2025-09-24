https://www.youtube.com/watch?v=JCeYq72Sko0
## Introduzione
I flake fanno parte delle funzionalità (per ora) sperimentali del nix package manager, servono a fornire una struttura uniforme per i progetti nix: tutto ciò bloccando le dipendenze in un lock file che rende riproducibili le espressioni nix.

![[Pasted image 20250914172801.png|center|600]]

![[Pasted image 20250914172853.png|center|600]]
## Utilizzo
Un file flake.nix è strutturato nel seguente modo
```nix
{
	description = "basic flake";

	inputs = {
		nixpgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
	};

	outputs = { self, nixpkgx }: {
		packages.x86-linux.hello = nixpkgs.legacyPackages.x86_64-linux.hello;

		packages.x86_64-linux.default = self.packages.x86_64-linux.hello;
	};
}
```

con `nix run` scarica i file e crea un file di lock, successivamente si avrà di output nel terminale `hello`.

| Comandi Principali | Utilizzo                    | Output                                  |
| ------------------ | --------------------------- | --------------------------------------- |
| `nix run`          | runs a packaged binary      | `outputs.packages."SYSTEM".default`     |
| `nix build`        | builds a package            | `outputs.packages."SYSTEM".default`     |
| `nix develop`      | activates a dev shell       | `outputs.devShells."SYSTEM.default`     |
| `nixos-rebuild`    | builds a nixos system       | `outputs.nixosConfigurations."HOSTNAME` |
| `home-manager`     | builds a home configuration | `outputs.homeConfiguration."USERNAME`   |

> [!info]
> Questi comandi andranno a cercare nel flake lo specifico output relativo (ovviamente nel flake non è esplicitato output.)

Con `nix flake show` si può osservare l'output del flake:
![[Pasted image 20250914173852.png|center|]]
 Se si guarda infatti il flake, si può osservare che all'output `packages.x86-linux.hello` è assegnato il valore `nixpkgs.legacyPackages.x86_64-linux.hello`, stessa cosa per `packages.x86_64-linux.default = self.packages.x86_64-linux.hello;`.

 L'attributo output di un flake è una funzione:
- Ha parametri `{ self, nixpkgx }`, entrambi i quali sono a loro volta flake, con *self* il flake stesso e *nixpkgs* proveniente dall'input. Quindi il flake scarica il contenuto dell'URL specificato, lo chiama *nixpkgs* e passa all'output tutti i contenuti scaricati.
- Quando si dichiare il `default` packages, ci si riferisce a quello di *self* al quale si assegna il valore di *nixpkgs*.

 ![[Pasted image 20250914174811.png|center|600]]
Si riprende adesso il flake

 ```nix
{
	description = "basic flake";

	inputs = {
		nixpgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
	};

	outputs = { self, nixpkgx }: {
		packages.x86-linux.hello = nixpkgs.legacyPackages.x86_64-linux.hello;

		packages.x86_64-linux.default = nixpkgs.packages.x86_64-linux.hello;
	};
}
```

e si introducono delle variabili per semplificare la lettura e si aggiunge un altro input
 ```nix
{
	description = "basic flake";

	inputs = {
		nixpgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
		nixpkgsveryold.url = "github:nixos/nixpkgs?ref=nixos-21.11"
	};
	outputs = { self, nixpkgx, nixpkgsveryold }: 
	let
		pkgs = nixpkgs.legacyPackages.x86_64-linux;
		pkgsold = nixpkgsveryold.legacyPackages.x86_64-linux;
	in
	{
		packages.x86-linux.hello = pkgs.hello;

		packages.x86_64-linux.default = pkgs.hello;

		devShells.x86_64-linux-default = pkgs.mkShell {
			buildInputs = [ pkgs.neovim pkgsold.vim ];
		};
	};
}
```

Output:
![[Pasted image 20250914182038.png|center]]

Per compattare la scrittura si può riscrivere l'output in questo modo:
 ```nix
{
	description = "basic flake";

	inputs = {
		nixpgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
		nixpkgsveryold.url = "github:nixos/nixpkgs?ref=nixos-21.11"
	};
	outputs = inputs
	let
		pkgs = inputs.nixpkgs.legacyPackages.x86_64-linux;
		pkgsold = inputs.nixpkgsveryold.legacyPackages.x86_64-linux;
	in
	{
		packages.x86-linux.hello = pkgs.hello;

		packages.x86_64-linux.default = pkgs.hello;

		devShells.x86_64-linux-default = pkgs.mkShell {
			buildInputs = [ pkgs.neovim pkgsold.vim ];
		};
	};
}
```

oppure
 ```nix
{
	description = "basic flake";

	inputs = {
		nixpgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
		nixpkgsveryold.url = "github:nixos/nixpkgs?ref=nixos-21.11"
	};
	outputs = { nixpkgx, ... } @ inputs: 
	let
		pkgs = nixpkgs.legacyPackages.x86_64-linux;
		pkgsold = inputs.nixpkgsveryold.legacyPackages.x86_64-linux;
	in
	{
		packages.x86-linux.hello = pkgs.hello;

		packages.x86_64-linux.default = pkgs.hello;

		devShells.x86_64-linux-default = pkgs.mkShell {
			buildInputs = [ pkgs.neovim pkgsold.vim ];
		};
	};
}
```
Quindi per riferirsi a *nixpkgs* si scrive il nome stesso, mentre gli altri input sono sotto *inputs.*.

Con `nix flake metadata` si ottiene
![[Pasted image 20250914182604.png|center|600]]

Per ridurre le grandezze dei download quando si usano gli stessi pacchetti, ma di diverse versioni ì, si può scrivere:

![[Pasted image 20250914182802.png|center]]

## Configurazione del Sistema
`nixos-rebuild` cerca l'output `outputs.nixosConfigurations."HOSTNAME"`, quindi 
```nix
{
	description = "basic flake";

	inputs = {
		nixpkgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
		home-manager.url = "github:nix-community/home-manager";
		home-manager.inputs.nixpkgs.follows = "nixpkgs";
	};

	outputs = { nixpkgs, ... } @ inputs:
	{

		nixosConfigurations."HOSTNAME"= nixpkgs.lib.nixosSystem {
			moduels = [
				./configuration.nix
				# ./hardware-configuration.nix non necessario, è già in configuration.nix
				({ pkgs, ...}: {
					programs.vim.defaultEditor = true;
				})
			];
		};
		
	};
}
```

e poi

![[Pasted image 20250914183505.png|center|600]]

   Si possono passare gli input alla configurazione nel seguente modo
   ```nix
{
	description = "basic flake";

	inputs = {
		nixpkgs.url = "github:nixos/nixpkgs?ref=nixos-unstable";
		home-manager.url = "github:nix-community/home-manager";
		home-manager.inputs.nixpkgs.follows = "nixpkgs";
	};

	outputs = { nixpkgs, ... } @ inputs:
	{

		nixosConfigurations."HOSTNAME"= nixpkgs.lib.nixosSystem {
			specialArgs = { inherit inputs; };
			moduels = [
				./configuration.nix
			];
		};
		
	};
}
```

*inherit* sta per *inputs = inputs*. In *configuration.nix* si avrà poi
```nix
{ pkgs, lib, inputsi ... }: {
	
	imports = [
		./hardware-configuration.nix
	];

	environment.systemPackages = with pkgs; [
		vim
		inputs.nixpkgsveryold.legacyPackages.${pkgs.system}.neovim
	];

	system.stateVersion = "..."
}
```
