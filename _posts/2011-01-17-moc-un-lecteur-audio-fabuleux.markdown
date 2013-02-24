---
date: 2011-01-17 23:01:39
layout: post
title: "Moc, un lecteur audio fabuleux"
description: "Le meilleur lecteur audio CLI pour moi. Un must-have."
categories:
- Avis
tags:
- lecteur
- moc
---

N'avez-vous jamais cherché le lecteur audio avec un grand "L". Effectivement, il existe un nombre assez conséquent de lecteurs, dont certains sont même des références comme [Amarok](http://amarok.kde.org/), [Rhythmbox](http://projects.gnome.org/rhythmbox/) ou [SongBird](http://www.getsongbird.com/). Il y a donc beaucoup de chances de trouver chaussure à son pied. Le problème, c'est que lorsqu'on utilise un WM léger comme OpenBox, et bien il devient difficile d'obtenir un lecteur, sans une tripotée de dépendances et qui soit léger. Nombre d'entres vous penseront à [mpd](http://fr.wikipedia.org/wiki/Music_Player_Daemon) avec un client comme [Sonata](http://sonata.berlios.de/) ou autres mais je cherchais la pure simplicité.

<!-- more -->

Je suis donc tombé sur un logiciel qui s’appelle [moc](http://moc.daper.net/) et qui est basé sur [ncurses](http://fr.wikipedia.org/wiki/Ncurses) (Music On Console). Il m'a vraiment étonné. A part libmad, jack et deux ou trois autres paquets, on a très peu de dépendances. Autre bon point, il ne consomme rien (en RAM et CPU) ce qui est plutôt un bon point pour les "vieux ordinateurs".

<img class="imgcenter" alt="Moc window" src="http://linuxien.legtux.org/uploads/images/2011/01/2011-01-17-232848_1920x1080_scrot.png">

L'utilisation est assez simple, tout est commandé grâce au clavier: S pour stop, Q pour quit, P pour pause et play, N pour piste suivante et B pour piste précédente. Vous pouvez naviguer dans l'arborescence pour trouver vos morceaux. Lorsque vous ouvrez une playlist, (format des radios web en général), cette dernière s'affiche à droite de la fenêtre. Il vous suffit d'appuyer sur TAB pour y accéder et Entrée pour la lancer. Le coté "minimaliste" (c'est à dire l'essentiel: écouter de la musique) me plait et le logiciel n'intègre pas les des fonctions, que je n'utilise pas comme les tags ou gestion de la bibliothèque. Dés que vous quittez ce lecteur, la musique tourne encore, car il utilise un serveur (comme mpd). Lorsqu'on a terminé, on fait S et Q, et le lecteur est stoppé. Si vous voulez stopper le serveur, tapez "mocp -x".

Cela peut vous paraître un peu rébarbatif mais je vous assure que ce lecteur est très agréable. D'ailleurs je n'utilise plus que lui.
