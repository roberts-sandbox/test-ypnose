---
date: 2011-10-24 17:18:30
layout: post
title: Profiter de VVVVVV sous GNU/Linux.
description: "Un bon jeu 8bits sous GNU/Linux, ça fait plaisir."
categories:
- Astuce
tags:
- astuce
- jeux
---

VVVVVV? Étrange nom pour un jeu. Et bien, sachez que sous ce nom curieux, il se cache une vraie perle.

Ce jeu a été créé début 2010 en Flash et a été porté en C++ à l'occasion du [Humble Indie Bunble 3](http://fr.wikipedia.org/wiki/Humble_Indie_Bundle#Troisi.C3.A8me_.C3.A9dition) (version 2.0). Cela a donc permis d'avoir une version native sous notre cher OS, qui était vendue dans le bundle #3.

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/10/game.png">

Le principal objectif, est de retrouver les membres d'équipage, qui sont perdus dans un vaisseau. Je ne vais pas trop parler de l'histoire, pour ne pas révéler le scénario. Les graphismes sont rétros et les musiques 8 bits (qui sont fabuleuses) rappellent l'ère des jeux old-school. La particularité de ce jeu, est de pouvoir marcher sur le plafond. Vous avancez donc dans des puzzles / plate-formes de plus en plus durs, et c'est même assez addictif.

Le but de cette article est de vous donnez quelques astuces, pour profiter du jeu.

Pour commencer, télécharger votre jeu légalement, et vérifier la somme MD5 de votre archive (pour le paquet provenant du Humble Indie Bundle).

MD5: 54d3679da69d92adb65fe9633f3c67d7

	md5sum VVVVVV_2.01_Linux.tar.gz

Ensuite, il faut extraire le contenu de l'archive avec votre logiciel favori. Après, rendez vous [ici](http://distractionware.com/forum/index.php?topic=693.0) et téléchargez un patch beta qui permettra de corriger quelques bugs, mais surtout d'ajouter le support OpenGL.

Pourquoi cela est important? Tout simplement, parce que le jeu gagne en performances. Sans ce support, tout est calculé par le processeur et les performances sont donc moins bonnes.

L'archive "Linux_Patch_2_2" comporte un nouvel exécutable patché. Je vous conseille quand même, de garder une backup de l'ancien exécutable (réflexe d'Archer). Placez vous dans le dossier contenant le jeu.

	mv VVVVVV_32 VVVVVV_32.bak

ou

	mv VVVVVV_64 VVVVVV_64.bak

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/10/gpu.png">

Vous pouvez maintenant extraire l'archive dans le dossier du jeu. De nouvelles dépendances sont au rendez-vous, comme libtiff, aalib, libcaca et [libjpeg6](http://aur.archlinux.org/packages.php?ID=49446) (sur AUR).

	sudo pacman -S libtiff aalib libcaca sdl_image sdl_mixer

Il y aussi une seconde archive contenant les niveaux corrigés (levels.zip). Placez le contenu de cette archive dans "[VVVVVV directory]/data/levels/".

Lancez le jeu avec:

	./VVVVVV ou ./VVVVVV_64

Si vous obtenez une erreur du type:

	/usr/lib/libjpeg.so.62: no version information available

essayer de modifier le fichier VVVVVV (avec votre éditeur de texte) comme sur ce [lien](https://raw.github.com/gist/1108439/fa9e2ec1293985b7de1dcaf5a934bb6522583150/vvvvvv).

C'est bon! Assurez-vous d'avoir activé l'option 'Enable OpenGL" dans le menu "Graphics". Profitez bien de ce jeu fabuleux.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/10/screen.png">
