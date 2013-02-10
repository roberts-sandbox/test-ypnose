---
date: 2011-03-24 12:09:14
layout: post
title: 'urxvt: le terminal ultime'
description: "Rxvt-unicode où comment utiliser le meilleur terminal actuel."
categories:
- Avis
tags:
- terminal
- urxvt
- xterm
---

Ça y est, j'ai officiellement abandonné mon xterm, que je trouvais plutôt pratique. Après avoir lu une tonne d'article comme quoi rxvt-unicode c'est fabuleux, j'ai décidé de tenter l'expérience. Et je n'ai pas été déçu. D'ailleurs, je suppose qu'il y a pas mal de lecteurs, qui l'utilisent sur leurs systèmes.
Vous pourriez me demandez pourquoi j'ai changé. Tout simplement parce que urxvt comporte certaines fonctionnalités très prometteuse. En effet, il est possible de lancer un daemon lorsque le système démarre, ce qui a pour but de partager les ressources et de lancer tout les terminaux dans un processus. Je trouve l'idée des daemons très bonnes (cf thunar --daemon). Ainsi les applications concernés, répondent au quart de tour. Il est aussi réputé pour être très léger (donc parfais sur Openbox).

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/03/urxvt.png">

Afin de lancer le daemon dès l'initialisation du système, j'ai ajouté à mon ~/.xinitrc (avant exec openbox-session), l'option:

	urxvtd -q -o -f

Rendez vous sur cette [page](http://linux.die.net/man/1/urxvtd), pour voir les options disponibles. Dorénavant, si vous souhaitez utiliser le daemon, lancer "urxvtc" (au lieu de urxvt) pour démarrer les terminaux clients.

J'ai bindé la touche F1 dans le rc.xml pour lancer un terminal. Le résultat, c'est instantané et c'est d'une praticité incroyable pour mon "pacman -Syu" quotidien. J'ai même l'impression que l'affichage est sensiblement plus rapide que xterm. Depuis que je l'utilise, je ne peux plus m'en passer et dès que je lance mes applis dans des terms, je trouve ça ultime.

Je n'en ai pas parlé précédemment, mais il supporte la vrai transparence (je ne m'en sert pas). Pour connaître la procédure, la [doc](https://wiki.archlinux.org/index.php/Urxvt#True_transparency) vous l'explique. Pour avoir un joli terminal qui correspond a vos goûts, vous devrez certainement, mettre un minimum les mains dans le cambouis (~/.Xdefaults). Cependant, je ne pense pas que cela fasse peur à des Archers.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/03/rxvt.gif">

Les options disponibles sont innombrables. Comme la taille et la police utilisée, le type et le style de scrollbar, la taille par défaut de la fenêtre, etc... A vous de vous renseigner. Par ailleurs, vous trouverez des configs qui vous aideront, sur la toile.
