---
date: 2011-02-13 13:11:27
layout: post
published: false
title: 'Sysstat: un paquet bien utile'
description: "Monitorer votre ordinateur comme si c'était un serveur!"
categories:
- Conseil
tags:
- astuce
- sar
- sysstat
---

Si comme moi, vous êtes quelqu'un qui aime "benchmarker" votre système, afin de trouver la moindre petite optimisation, je vous conseille d'installer un paquet appelé sysstat. Ce dernier est plus que complet, puisqu'il intègre tout un tas de commande utile comme sar (que j'utilise principalement), iostat ou encore mpstat. Je suppose qu'il est destiné aux serveurs.

<!-- more -->

Je vais vous expliquer quel est l'utilisation de ces commandes:

sar: Permet d'afficher et de comparer la consommation de CPU globale. La commande:

	sar -u 1 10

affiche l'utilisation du CPU toutes les secondes et pendant 10 fois dans votre shell. La première valeur est l'intervalle de temps et la deuxième le nombre de relevés. La consommation est affiché sous la forme: %user, %nice, %system, %iowait, %steal et %idle.

<img class="imgcenter" alt="sar" src="http://linuxien.legtux.org/uploads/images/2011/02/sar.png">

Vraiment pratique lorsque l'on démarre un logiciel en plein écran pour faire ses relevés.

iostat: Permet d'afficher l'utilisation CPU depuis le dernier redémarrage et les périphériques/partitions connectés.

	iostat

Vous pouvez aussi l'utiliser comme ceci afin de lancer la commande:

	iostat -tc 2 3

<img class="imgcenter" alt="iostat" src="http://linuxien.legtux.org/uploads/images/2011/02/iostat.png">

mpstat: Permet d'afficher l'activité du processeur. La commande

	mpstat -P ALL

affiche les infos pour chaque coeur (ou noyau) du CPU en commençant par 0.

<img class="imgcenter" alt="mpstat" src="http://linuxien.legtux.org/uploads/images/2011/02/mpstat.png">

Voilà quelques outils pour "jouer" avec votre ordi.
