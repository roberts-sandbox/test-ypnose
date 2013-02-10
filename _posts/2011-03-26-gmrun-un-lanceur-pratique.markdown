---
date: 2011-03-26 12:21:34
layout: post
title: 'Gmrun: un lanceur pratique'
description: "Un petit lanceur tout simple, mais suffisamment pratique."
tags:
- gmrun
---

Si vous tournez avec GNOME ou KDE, il doit vous arriver d'utiliser le lanceur intégré, pour démarrer certaines de vos applications. Mais nous autres, qui sommes sous des WM, nous n'avons pas de lanceurs intégrés. Voilà pourquoi, il peut être intéressant d'installer un lanceur pour certains programmes. Je suis un ancien adepte de [bashrun](http://bashrun.sourceforge.net/), mais je suis récemment passé à [Gmrun](https://wiki.archlinux.org/index.php/Gmrun).

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/03/bashrun.jpg">

Je trouve ce dernier plus intuitif et il s'intègre mieux sous Openbox ou PekWM (il prend en compte le thème GTK). Par ailleurs, il gère l’auto complétion. Comme d'habitude, sa configuration passe par la modification d'un fichier de config. Vous pouvez donc créer un fichier appelé .gmrunrc dans votre /home, avec à l'intérieur les options nécessaires.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/03/gmrun.png">

Les options ne sont pas compliquées, voilà par exemple mon [fichier](http://tetedulinuxien.fr/wp-content/uploads/2011/03/gmrunrc.txt). Ce fichier vous permettra de fixer la taille, la position sur l'écran, le navigateur où sera lancé les URL, le terminal par défaut pour les commandes, etc...

La doc Archlinux est très claire sur les options possibles et je pense que c'est la meilleure [source](https://wiki.archlinux.org/index.php/Gmrun) d'informations pour une configuration "aux petits oignons". Vous pouvez aussi, définir une touche pour utiliser Gmrun, comme F2 ou ALT+F2, ce qui augmente la praticité du soft.

Bonne lecture!
