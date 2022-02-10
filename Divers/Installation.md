# Installation des programmes

Pour utiliser OCaml chez vous, plusieurs possibilités&nbsp;: soit utiliser une version en ligne, soit installer OCaml directement chez vous, sur votre ordinateur.

## Versions en ligne

### Try OCaml

Une des sociétés s'occupant du développement du langage, [OcamlPro](https://www.ocamlpro.com), propose un éditeur et une console en ligne sur le site [Try OCaml](https://try.ocamlpro.com).

### Basthon

Le site [Basthon](https://basthon.fr) qui, originellement, offrait simplement une console Python, a vu ses fonctionnalités se développer. Il est possible maintenant d'utiliser plusieurs langages (dont OCaml) en deux modes&nbsp;: soit avec deux fenêtres éditeur/console, soit à l'aide d'un mode _notebook_.

## Installation sur son ordinateur

Pour faire du OCaml dans des conditions optimales, vous pouvez envisager d'installer le langage sur votre ordinateur. Voici, suivant les systèmes d'exploitation, la procédure à suivre.


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

Une fois _Homebrew_ installé, vous pouvez installer les programmes nécessaires.

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

Il est assez compliqué d'installer _à la main_ OCaml sous Windows. La première solution que je propose est d'utiliser [WinCaml](https://jean-mouric.pagesperso-orange.fr/index.html), programme proposé par un collègue enseignant en classe préparatoire. Cependant, n'ayant d'ordinateur sous Windows, je ne peux l'essayer. Mais les instructions semblent claires (il faut les lire attentivement, et installer une distribution OCaml comme indiqué).

Pour les plus ambitieux, une autre possibilité est d'installer, sur un Windows récent, le programme [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/). Cela fournit un environnement type Linux (comme ce que vous utilisez en salle 404). 

Vous pourrez alors installer Emacs (en suivant les instructions détaillées ici&nbsp;: [Emacs-WSL](https://github.com/hubisan/emacs-wsl)) puis `opam` (le gestionnaire d'installation d'OCaml), en suivant les instructions de Linux/Ubuntu.

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

Pour finir, on exécute la commande
```shell
eval `opam env`
```