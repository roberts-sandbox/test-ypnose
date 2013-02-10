---
date: 2011-05-16 11:19:12
layout: post
title: 'Netcfg: simplicité et efficacité'
description: "Quand gérer son réseau n'a jamais été aussi KISS."
categories:
- Astuce
- Test
tags:
- archlinux
- reseau
---

Salut,
Même si mon [Wicd](http://wicd.sourceforge.net/) fonctionnait du tonnerre et était très simple d'utilisation, j'ai décidé de changer afin de rendre le système aussi léger qu'une plume. Je ne sais pas trop comment vous effectuez vos mises à jours, sur une Archlinux toute fraîche via le Wifi, mais je suis un adepte convaincu de [wpa_supplicant](http://hostap.epitest.fi/wpa_supplicant/) (sur d'autres distribs aussi). Ce logiciel est d'une efficacité renversante, avec le fichier de config wpa_supplicant.conf dans lequel vous rentrez les paramètres de votre connexion. Point non négligeable, il gère parfaitement WPA2 (ma connexion est en WPA2).

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/05/wifi.png">

Tellement, je trouve ce logiciel fabuleux, j'ai décidé de trouver quelque chose de similaire, qui puisse me connecter à mon réseau sans fil (j'utilise toujours le même), pendant le démarrage du système et je suis tombé sur [Netcfg](https://wiki.archlinux.org/index.php/Netcfg). Tout comme son homologue, il est plutôt simple et lorsque vous l'installez avec:

	# pacman -S netcfg

des exemples de fichiers de config sont stockés dans /etc/network.d/examples. Vous en avez pour du WEP, WPA(2) et Ethernet. J'ai trouvé dans les exemples, ce fichier qui s'appelle "wireless-wpa-config":

	CONNECTION='wireless'
	DESCRIPTION='A wpa_supplicant configuration based wireless connection'
	INTERFACE='wlan0'
	SECURITY='wpa-config'
	WPA_CONF='/etc/wpa_supplicant.conf'
	IP='dhcp'

Ce fichier va chercher les informations stockées dans mon wpa_supplicant.conf qui est parfaitement fonctionnel. Donc, rien à rajouter dans ces fichiers.

Vous devez exporter l'exemple dans le dossier /etc/network.d:

	# cp /etc/network.d/examples/fichier_désiré /etc/network.d/maison

Rajoutez ensuite à votre rc.conf, les options suivantes (qui ont été définis avant):

	NETWORKS=(maison)

et

	DAEMONS=(..., @net-profiles, ...)

Voilà vous êtes connecté en Wifi à votre Box via Netcfg. Du moment, que votre fichier wpa_supplicant.conf est adapté et utilisable pour votre réseau, tout le reste est une "lettre à la Poste".

De la lecture [ici](https://wiki.archlinux.org/index.php/Wpa_supplicant). Je suis en train de tester en long et en large mais la connection est aussi stable qu'avec Wicd. Je n'ai pas encore rencontré de problèmes.
