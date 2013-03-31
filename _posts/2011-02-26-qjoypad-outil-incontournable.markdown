---
date: 2011-02-26 12:20:28
layout: post
published: false
title: 'QJoypad: Outil incontournable'
description: "Utiliser son pad pour les jeux ou les applications qui ne les supporte pas."
categories:
- Astuce
tags:
- qjoypad
- qt
---

En me baladant sur la toile, j'ai fait la découverte d'un logiciel appelé [QJoypad](http://qjoypad.sourceforge.net/), codé en Qt et qui permet d'utiliser votre manette dans des applications (dans X) ne supportant pas ces périphériques. Le logiciel fonctionne de la manière suivante: vous assigner les touches de votre manette à des touches du clavier. Par exemple, lorsque vous appuyer sur la touche "3" de la manette, c'est comme si vous appuyer sur le A du clavier.

<!-- more -->

<img class="imgcenter" alt="logo" src="http://qjoypad.sourceforge.net/logo.gif">

Cependant, je pense qu'il est impératif que votre manette soit détectée par le noyau (/dev/input/js0) sinon je ne garanti pas la prise en charge du périphérique. Quand vous le démarrez, une icone s'affiche dans le systray et vous pouvez afficher la fenêtre du logiciel. Il est possible de créer plusieurs profils (un profil par logiciel) et quand vous appuyer sur une touche, QJoypad vous le signale. Il est même possible de définir qu'un joystick remplace la souris.

<img class="imgcenter" alt="exemple" src="http://linuxien.legtux.org/uploads/images/2011/02/joypad.png">

Depuis qu'il se trouve sur mon PC, je l'utilise beaucoup, en particulier sur [XBMC](http://www.xbmc.fr/) qui supportait bizarrement ma manette (seulement 2 touches fonctionnait). Le plaisir de naviguer, dans les menus avec une manette est immense. Vous pouvez aussi le mettre à contribution pour vos jeux, comme [M.A.R.S.](http://mars-game.sourceforge.net/) (ne supporte pas encore les joysticks sauf pour le SVN).

Je vous conseille fortement de le compiler (version récente datant de début février). Il existe des paquets .deb ou .rpm mais il semble que les versions soient assez vieillottes. Sous Arch, j'ai utilisé AUR et sous OpenSUSE, je l'ai compilé; tout marche nikel.
