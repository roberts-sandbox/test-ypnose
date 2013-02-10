---
date: 2011-01-23 17:06:38
layout: post
title: "Jouer à Quake 3"
description: "Le guide pour bien installer Quake3 sous GNU/Linux, avant de fragger!"
categories:
- Idée
tags:
- openarena
- quake
---

Lassé de Call of Duty ou autre Battefield? je précise que je ne joue pas à ces jeux, et bien je pense avoir trouvé votre reconversion.

En temps que fanboy [Id Software](http://www.idsoftware.com/) (avouons-le, tous leurs titres sont des hits), j'ai eu l'idée de ressortir et (re)découvrir Quake 3 Arena en regardant de nombreuses vidéos de joueurs. En plus, comme le moteur a été libéré, un moteur graphique amélioré a vu le jour: [ioquake3](http://ioquake3.org/) avec de nouvelles fonctionnalités comme openAL pour le son (5.1 ou 7.1), support de Mumble ou version 64 bits. Tout est bien sûr disponible sous notre système.

Avant de commencer, je rappelle qu'il est impératif d'avoir acheté le jeu.

<!-- more -->

Trêve de bavardages, il est temps de l'installer. Rendez-vous sur cette [page](http://ioquake3.org/get-it/) et télécharger le moteur pour Linux (Engine) et les "datas" incluant le dernier patch d'ID (Data Installer). Une fois que vous avez fini, rendez vous dans votre dossier de téléchargements et avec le terminal, rentrer ces commandes:

	chmod +x ioquake3-1.36-7.1.i386.run
	./ioquake3-1.36-7.1.i386.run


Remplissez les champs nécessaires et lancez l'installation du moteur. Ensuite, vous devez installer les "datas":

	chmod +x ioquake3-q3a-1.32-9.run
	./ioquake3-q3a-1.32-9.run

Quand la procédure est effectué, lancer votre cd "Quake3 Arena" et récupérer sur ce dernier le fichier pak0.pk3 et copier le dans ~/ioquake3/baseq3 (endroit que j'ai défini lors de l'install). Les autres .pk3 sont inutiles car le Data Installer les a installé. C'est parti vous pouvez jouer!

Cependant, ce n'est pas terminé. Je vais vous donner quelques conseils de mon cru (j'ai passé 2 jours pour tester avec htop, top et un script fourni par l'ami [Rolinh](http://rolinh.gw-computing.net/)). Je veux préciser que les consos de CPU ont été constaté sur mon système. Il est possible que cela marche différemment chez vous.

* Quake 3 n'inclut pas de réglage pour les résolutions élevées (comme 1920x1080), l'astuce consiste donc à éditer votre q3config.cfg et à modifier les lignes suivantes:

	seta r_mode "-1"
	seta r_customwidth "votre_largeur"
	seta r_customheight "votre_hauteur"

Lors de l'installation, un lien symbolique est créé pour lancer le jeu. Lorsque je clique sur ce lien, le jeu fonctionne bien mais j'ai une surconsommation de CPU. Et quand je vais dans le dossier ~/.ioquake3 et que je lance ``` ./ioquake3.i386 ``` dans un shell, je consomme en moyenne 20%.

* Si les textures de Quake vous semblent un peu "vieillottes", voilà un [pack de textures](http://ioquake3.org/2010/08/24/high-resolution-creative-commons-texture-replacement-pack/) qui transforme le jeu. Elles sont juste magnifiques.

* Autre option très importante, modifier ``` seta com_maxfps "xx" ``` par la valeur de fréquence de votre écran (chez moi 60 Hz donc 60 FPS max). N'ayant pas réglé cette option auparavant (réglé a 85 de base), j'avais une consommation CPU très élevée (~60%).

* Pour le menu OpenBox, j'ai écris un petit script qui lance Quake dans un shell:

	#!/bin/bash
	cd /home/foo/.ioquake3/
	xterm -e ./ioquake3.i386

Quake 3 est de base sans filtrage anisotropique , je crois avoir trouvé l'option à rajouter dans q3.config:

	seta r_ext_texture_filter_anisotropic "1"_
	seta r_ext_max_anisotropy "x" (2, 4, 6 ou 8 )

Aimant certaines skins d'OpenArena, il suffit de copier "pak2-players.pk3" et/ou "pak2-players-mature.pk3" dans le dossier ~/ioquake3/baseq3 et vous pourrez ainsi bénéficier des skins OpenArena dans Quake.

J'espère que ça vous permettra de mieux profiter du jeu. Et OpenArena m'aura bien aidé.

NOTE: Ces paramètres fonctionnent aussi sous OpenArena et certainement Urban Terror car ils tournent avec ioquake.
