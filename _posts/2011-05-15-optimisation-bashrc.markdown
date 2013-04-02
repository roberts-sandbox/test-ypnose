---
date: 2011-05-15 10:46:42
layout: post
title: Optimisation .bashrc
description: "Changer son PS1 pour améliorer la lisibilité du prompt."
categories:
- Astuce
- Personnalisation
tags:
- archlinux
- astuce
- bashrc
- terminal
- urxvt
---

Ayant toujours quelque chose à optimiser ou à améliorer sous Archlinux, j'ai décidé de personnaliser mon terminal (à savoir URxvt), via le bashrc. Si vous êtes un lecteur de ce blog, vous devriez vous souvenir d'un précédent article, où j'avais parlé de changer la couleur en fonction de l'user ou du super-user dans le terminal.
Dans ce fichier, j'ai entre autres définit la variable $BROWSER afin de déclarer que cette dernière vaut Chromium. Les possibilités sont quasi infinies avec ce fichier. Vous pouvez aussi définir des alias, c'est-à-dire que vous pouvez définir des abréviations pour une commande donnée. Par exemple, avec:

<!-- more -->

	alias pacman='sudo pacman'

lorsque vous lancer "pacman", cela reviendra à lancer "sudo pacman". Plutôt pratique non?

Je ne définit pas beaucoup d'alias pour la simple et bonne raison, que je lance rarement des commandes longues et fastidieuses même si j'utilise beaucoup le terminal.

J'ai surtout concentré mon optimisation, autour de la "forme" du prompt. En me baladant sur [Deviantart.com](http://www.deviantart.com/), j'ai vu de jolies choses et cela ma inspiré. J'ai donc réalisé un prompt avec de la couleur, parce que je n'aime pas quelque chose qui est monochrome.
Voici les images:

De base:

<img class="imgcenter" alt="base" src="http://linuxien.legtux.org/uploads/images/2011/05/termbase.png">

Modifié (Normal User):

<img class="imgcenter" alt="modif" src="http://linuxien.legtux.org/uploads/images/2011/05/termmodif.png">

Modifié (Root):

<img class="imgcenter" alt="root" src="http://linuxien.legtux.org/uploads/images/2011/05/termmodifroot.png">

Je trouve ça plus agréable avec de la couleur ! Le dossier dans lequel on se trouve, est en jaune, l'user en vert, le root en rouge et l'host en bleu.

Voici le code à rentrer dans le .bashrc (je vous conseille de commenter, votre code actuel afin de ne pas se retrouver ennuyé, en cas de problème).

[Par ici](https://github.com/Ypnose/Madfiles/blob/master/.bashrc) (#user) Ligne PS1

Si vous voulez, avoir aussi ce système pour le root, créer un .bashrc dans /root et remplissez-le avec le code, que vous pourrez modifier.

[Par ici](https://github.com/Ypnose/Madfiles/blob/master/.bashrc_root) (#root) Ligne PS1

Comme toujours, si vous voulez avoir un bon aperçu des fonctionnalités, vous pouvez vous rendre [ici](https://wiki.archlinux.org/index.php/Bashrc#Configuration) et [là](https://wiki.archlinux.org/index.php/Color_Bash_Prompt). Il y a les couleurs possibles et les optimisations possibles pour le .bashrc.
