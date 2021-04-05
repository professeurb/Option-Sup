# Installation des programmes

Comme on l'a vu, il est possible d'utiliser OCaml en ligne sur le site [Try OCaml](https://try.ocamlpro.com). Néanmoins, pour pouvoir travailler de façon plus efficace, il est intéressant d'installer chez soi OCaml (avec quelques bibliothèques, et la possibilité d'en installer d'autres) ainsi qu'un éditeur performant, comme Emacs qui propose un ensemble de fonctionnalités très intéressantes pour OCaml.

Nous allons détailler dans la suite comment installer cela, les diverses procédures sont regroupées par systèmes d'exploitation.

## Linux

Les procédures d'installation sous les différents distributions de Linux sont similaires, seules diffèrents les commandes à utiliser.

### Emacs

```shell
apt install emacs # Ubuntu, Debian, Mint
pacman -S emacs   # ArchLinux, Mangaro
```

### OCaml

On poursuit avec l'installation d'[opam](https://opam.ocaml.org), le _package manager_ d'Ocaml.

```shell
apt install opam  # Ubuntu, Debian, Mint
pacman -S opam    # ArchLinux, Mangaro
```

Pour finir, reportez-vous plus bas aux instructions d'installation d'OCaml par opam.

## macOS

Voici une procédure d'installation qui repose sur [Homebrew](https://brew.sh), un gestionnaire de programmes basé sur le terminal.

### Homebrew

Recopiez la ligne suivante et exécutez-la dans le terminal&nbsp;:
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
S'il y a un problème, il est possible que vous deviez installer auparavant un certain nombre de programmes pour faire du développement, en exécutant&nbsp;:
```shell
xcode-select --install
```
### Emacs

```shell
brew install emacs
```

### OCaml

On installe ensuite [opam](https://opam.ocaml.org), le _package manager_ d'Ocaml.

```shell
brew install gpatch opam
```

Pour finir, reportez-vous plus bas aux instructions d'installation d'OCaml par opam.


## Windows

Il n'est pas facile d'installer directement Emacs comme OCaml sous Windows qui n'est pas un système d'exploitation de type [UNIX](https://fr.wikipedia.org/wiki/Unix) (contrairement à Linux et macOS).

La procédure que je vous propose d'essayer (mais que je n'ai pas testée) repose sur l'installation de [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/).

### WSL et Emacs

Voici une page détaillée pour installer WSL puis Emacs&nbsp;: [Emacs-WSL](https://github.com/hubisan/emacs-wsl)

### OCaml

Une fois que vous avez installé WSL et Ubuntu, vous pouvez installer OCaml comme expliqué précédemment pour Linux/Ubuntu.

## Initialisation d'OCaml par opam

Les instructions s'appliquent à une installation via `opam`. Ce sont des commandes à taper dans le terminal.

On commence par initialiser `opam` et installer OCaml.
```shell
opam init --yes
```

Ensuite, nous allons installer quelques bibliothèques.
```shell
opam install --yes tuareg merlin utop graphics
```
Parmi ces bibliothèques, on trouve
* [tuareg](https://github.com/ocaml/tuareg), un mode d'édition spécial pour Emacs
* [utop](https://github.com/ocaml-community/utop), un interpréteur amélioré,
* [graphics](https://github.com/ocaml/graphics), pour tracer des figures,

Installons maintenant un [plugin](https://github.com/ocaml-opam/opam-user-setup) permettant de faciliter la configuration des éditeurs, dont Emacs.
```shell
opam user-setup install
```

Pour finir, on 
```shell
eval `opam env`
```