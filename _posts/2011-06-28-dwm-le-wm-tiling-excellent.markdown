---
date: 2011-06-28 14:51:37
layout: post
title: 'Dwm: Le WM Tiling excellent'
description: "Le tiling, le vrai, avec un WM extrèmement KISS."
categories:
- Avis
- Personnalisation
tags:
- archlinux
- dwm
- urxvt
---

Ces derniers temps, j'ai essayé beaucoup de WM Tiling, dans le but de profiter pleinement de mon écran, qui dispose d'une résolution 1920x1080. Le but du tiling est de redimensionner automatiquement, les fenêtres afin d'occuper tout l'espace disponible. Par exemple, lorsque vous ouvrez une fenêtre, elle occupe tout l'écran; avec deux fenêtres, chacune occupe la moitié de l'écran, etc... L'autre avantage est d'utiliser au maximum de la navigation au clavier. Ainsi, vous vous déplacez dans les tags et fenêtres, grâce à des combinaisons de touches et cela vous fait gagner énormément de temps.

<!-- more -->

Les candidats sont nombreux: WMFS, WMII, Awesome et Subtle (pas dynamique mais manuel) mais aucun de m'a satisfait comme Dwm. Pourquoi j'ai choisi Dwm par rapport aux autres? J'ai effectué des périodes d'essais, et j'ai été dérangé par des inconvénients (je précise que je ne critique pas les autres WM).

Pour WMFS, il m'a semblé qu'il était gourmand, en particulier sur le CPU. Subtle est assez dur à régler et a utiliser, malgré les possibilités immenses. Pour Awesome, j'ai un peu eu peur de voir la syntaxe évoluer dans le temps, et par conséquent, devoir mettre mes configs à jour après telle ou telle update, ne me plait pas.

<img class="imgcenter" alt="dwmkiss" src="http://linuxien.legtux.org/uploads/images/2011/06/dwm-logo.png">

La particularité de Dwm est sa légèreté. Le soft est codé en C, ne comporte que 2000 lignes de codes et dispose de nombreux patchs pour ajouter des fonctionnalités. Il ne lit pas de fichier de config, pour les options (au contraire de WMFS ou Awesome), il faut directement modifier les sources du logiciel pour personnaliser les options. Et par conséquent, il faut tout recompiler par la suite (0.25s chez moi). Cela pourrait sembler être une tâche contraignante, mais ce n'est pas le cas.

C'est un avantage, car comme il ne lit pas de fichier, et que tout est directement intégré au code, on a un gain de performance non négligeable. Je suis impressionné par la consommation et la réactivité de ce dernier, qui est respectivement très basse et très rapide.

Sous certains WM, la config n'est pas aisée et on ne comprend pas tout de suite (je pense à Subtle, que je trouve assez chaud à paramétrer), cependant sous Dwm, tout est parfaitement clair, on sait très bien ce qu'il faut modifier.

Les fonctionnalités sont fournies: jusqu'à 9 tags différents, 3 layouts par défaut (en plus des autres dans les patchs), possibilité de lancer une application précise sur un tag, un layout différent sur chaque tags (avec patch), un espace entre les fenêtres, etc... Par contre, il ne comporte pas de menu ou de zone de notification. Il faudra installer des programmes externes.

Je me sens très bien sous Dwm et de jours en jours, je m'habitue pleinement au tiling et aux raccourcis. C'est très plaisant à utiliser.

<img class="imgcenter" alt="arch" src="http://linuxien.legtux.org/uploads/images/2011/06/arch-linux.png">

Pour l'installer sous Archlinux, on passe donc par [ABS](https://wiki.archlinux.org/index.php/ABS), avec:

	# abs community/dwm
	$ cp -r /var/abs/community/dwm ~/dwm

Après, on doit évidemment modifier ce que l'on veux et éventuellement ajouter des patchs. Lorsque vous avez rentré vos changements, on effectue le bon vieux:

	makepkg

Dans le cas où, vous avez déjà compilé le bouzin une première fois avec makepkg, et que vous avez fait de nouveaux changements, on peux utiliser:

	makepkg -ef

ce qui forcera à utiliser les sources déjà téléchargées et écrasera les fichiers générés par la précédente compilation.

Si vous souhaitez tenter l'aventure, vous devez absolument utiliser[ ce patch](http://dwm.suckless.org/patches/frenchkey) qui a pour but de pouvoir utiliser les raccourcis sur un clavier FR.

Pour appliquer un patch, allez dans le répertoire /src/dwm-5.x.x et utilisez cette commande:

	patch -p1 < patch_de_votre_choix.diff

Pour lancer le WM, on applique toujours la méthode du exec dwm dans le .xinitrc.

Je ne rentrerai pas plus dans le détail, car ce billet n'est pas un tutorial, mais une découverte. Par contre, les curieux devront faire un tour sur la [doc Arch](https://wiki.archlinux.org/index.php/Dwm) ou le [site officiel](http://dwm.suckless.org/).

Bien sûr, je partagerai mes configs personnelles via [Github](https://github.com/Ypnose/Madfiles/tree/master/Dwm).

Je rentrerai dans le détail de la config et personnalisation dans un autre billet.

Tchao et BONNES VACANCES!
