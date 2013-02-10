---
date: 2011-05-28 10:15:05
layout: post
title: 'cpufreq: votre PC va aimer'
description: "Réduire la consommation et la température de votre CPU."
categories:
- Astuce
tags:
- archlinux
- cpu
---

Io les lecteurs,

Voulant faire "joujou" et obtenir le système parfait avec mon nouvel ordinateur, je suis tombé sur la doc Archlinux de cpufreq. Ma carte mère (la M4A89GTD PRO) comporte la fonctionnalité "[Cool' n' Quiet](http://fr.wikipedia.org/wiki/Cool'n'Quiet)", qui permet de baisser la fréquence des coeurs du processeurs, lorsque votre système travaille moins. Cpufreq est un outil qui permet de jouer sur les fréquences en fonction d'un profil (performance, conservative, etc). Jusqu’à maintenant, je n'avais pas mis en place cpufreq sur mes installations, mais je me suis laissé tenter.

Depuis que j'ai ce PC, la fréquence des coeurs du Phenom X4 était au maximum, à savoir 3.2 GHz pendant tout l'uptime. Mon système tournait aux alentours de 40°C en idle.

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/05/amd-phenom-ii-x4-955.jpg">

Avant de vous expliquer, je tiens à vous dire que j'ai gagné environ 9°C en idle, ce qui est non négligeable.

La mise en oeuvre est très simple. Il y a plusieurs méthodes possibles. Je vais détailler ce que j'ai fait.

ATTENTION, JE NE SUIS PAS RESPONSABLE DES DÉGRADATIONS DU VOTRE MATÉRIEL, EN CAS DE MAUVAISES MANIPULATIONS.

Pour commencer, il faut installer cpufreq:

	# pacman -S cpufrequtils

Avant de faire une config' en dur, je vous conseille de tester si cpufreq reconnait bien le processeur. Charger donc le module correspondant à votre processeur (renseigner vous pour connaitre ce dernier). Chez moi:

	# modprobe powernow-k8

Ensuite lancer:

	$ cpufreq-info

Cette commande devrait vous retourner des infos sur votre modèle, comme les plages de fréquences, le driver utilisé, etc..

J'ai opté pour le daemon, qui permet de définir mes paramètres lors du boot. Modifiez le fichier /etc/conf.d/cpufreq en dé-commentant la ligne "governor" et en indiquant le comportement désiré. Chez moi "ondemand" (fréquence en fonction de la charge). Il faut savoir que quand vous n'installez pas cpufreq, le profil est automatiquement définit sur "Performance". Vous avez ci-dessus une liste des governors possibles.

	#configuration for cpufreq control
	
	# valid governors:
	#  ondemand, performance, powersave,
	#  conservative, userspace
	governor="ondemand"
	
	# limit frequency range (optional)
	# valid suffixes: Hz, kHz (default), MHz, GHz, THz
	#min_freq="2.25GHz"
	#max_freq="3GHz"
	
	# use freq to set up the exact cpu frequency using it with userspace governor
	#freq=

Les lignes min/max_freq permettent de choisir une valeur minimale/maximale de fréquences mais c'est OPTIONNEL. Je n'y ai pas touché. Ma fréquence minimale est définit par cpufreq et est fixée à 800MHz et la maximale à 3.2 GHz (par coeur).

La mise en oeuvre touche à sa fin. Pour finir, modifier votre rc.conf en ajoutant votre driver à charger dans MODULES() et le daemon dans DAEMONS(). L'exemple est bien-sûr pour mon ordi.

	MODULES=(powernow-k8)
	[...]
	DAEMONS=(..., cpufreq)

Redémarrez la machine et visualisez les températures via sensors (avec lm_sensors installé). Une commande bien pratique:

	watch -n 1 sensors

La commande [watch](http://en.wikipedia.org/wiki/Watch_(Unix) permet de relancer une commande et d'afficher le résultat après une plage de temps. Par défaut, 2 secondes. Incroyablement utile!

Comme toujours, pour plus d'infos, voici la [source](https://wiki.archlinux.org/index.php/Cpufreq).
