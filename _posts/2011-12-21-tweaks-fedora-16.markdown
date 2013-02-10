---
date: 2011-12-21 16:22:38
layout: post
title: "Tweaks sous Fedora 16"
description: "Beaucoup d'optimisations avec ma Fedora pour gagner en autonomie."
categories:
- Astuce
- Conseil
tags:
- cpu
- fedora
---

Bonjour,

J'en ai pas mal parlé sur mon profil [Twitter](https://twitter.com/#!/tetedulinuxien/), il n'y a pas si longtemps, mais je pense avoir enfin trouvé la distrib pour mon laptop. C'est bel et bien Fedora 16.

Elle fonctionne parfaitement "out-of-the-box" mais chez moi certains réglages semblent nécessaires, car par exemple l'autonomie à subi un sacré coup. Sous Windows Vista, mon laptop tient dans les 3h15 et sous Fedora (non-réglée) je passe à un petit 2h. Il y aussi quelques ajustements au niveau de l'interface.

<!-- more -->

Pour moi ces "tweaks" sont donc incontournables. Je vais donc vous faire un récapitulatif.

Pour commencer, petite parenthèse, lors de l'installation j'applique ce partitionnement (comme sur chaque distrib): une partition 10-12 Go pour la racine en ext4, 2Go pour la swap (remplir une partition du double de la RAM est inutile, je dispose déjà de 4Go sous tout mes ordis) et le reste pour ma /home en ext4 aussi.

*** Gestion de la fréquence CPU ***

Pour installer une version améliorée de cpufrequtils appelée cpupowerutils, qui comporte quelques nouvelles fonctionnalités, on passe par le paquet kernel-tools:

	sudo yum install kernel-tools

En effet, le paquet cpufrequtils est déprécie et est remplacé par kernel-tools. A ce moment là, j'ai eu quelques difficultés pour paramétrer le nécessaire. En fait, il n'y a pas grand chose de compliqué.

Avec 'nano', on édite la fichier /etc/sysconfig/cpupower comme ceci:

	sudo nano /etc/sysconfig/cpupower

et on a ça:

	# See 'cpupower help' and cpupower(1) for more info
	CPUPOWER_START_OPTS="frequency-set -g performance"
	CPUPOWER_STOP_OPTS="frequency-set -g ondemand"

Modifier la ligne  CPUPOWER_START_OPTS en remplaçant "performance" par le "governor" désiré. J'ai moi-même remplacé "performance" par "ondemand". Vous pouvez ajouter aussi une fréquence minimale avec l'argument -d et une fréquence maximale avec l'argument -u.

Ex: "frequency-set -g ondemand -d 800MHz -u 2GHz". Je vous invite à lire le man pour plus d'options:

	man cpupower-frequency-set

Pour vous éviter de relancer le service cpupower à chaque (re)démarrage, procédez comme ceci:

	sudo systemctl enable cpupower

Et voilà votre "governor" réglé automatiquement à chaque démarrage. Vous pouvez contrôler avec

	cat /proc/cpuinfo | grep "cpu MHz"

et voir la fréquence minimale gérée par votre CPU.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/12/cpu.png">

*** Gestion du GPU ***

Mon laptop comporte un GPU ATI HD3450. Je souhaite me passer du driver proprio et utiliser l'alternative libre. Utiliser GNOME3 fonctionne sans problème avec le radeon libre. Cependant, pour gagner quelques minutes et aussi parce que les effets Compiz ne n'importent guère, je suis passé sur GNOME Fallback. J'ai déjà un gain mais je ne vais pas m’arrêter là.

Beaucoup se plaignent du ventilateur qui se met à "chanter" assez tôt, pour ne plus cesser. J'ai failli passer sur le proprio juste à cause de ce phénomène mais finalement non. J'ai trouvé le Saint-Graal. En tombant sur cette [doc](http://www.x.org/wiki/RadeonFeature), j'ai donc encore affiné mes réglages et baissé significativement la vitesse du ventilateur (et aussi la dissipation thermique).

Pour modifier les fichiers suivants, vous ne DEVEZ pas avoir l'option "nomodeset" dans GRUB. Vérifiez avec:

	cat /etc/default/grub

Je vais retenir les points de la doc dont nous avons besoin. Il faudra regarder/modifier uniquement deux fichiers. AVANT TOUT, CES PROCÉDURES SONT À VOS RISQUES ET PÉRILS, FAITES BIEN ATTENTION.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/12/gpu.png">

Lancez

	cat /sys/class/drm/card0/device/power_method

Si vous obtenez "profile" (sans les guillemets), c'est OK, rien à modifier donc. Vous pouvez passer à la suite.

Ensuite, rentrez

	sudo nano /sys/class/drm/card0/device/power_profile

et remplacer "default" (sans les guillemets) soit par mid soit par autre chose. Il est écrit sur la doc qu'il ne faut pas rentrer low, mais je suis quand même en train d'essayer ce paramètre. Allez [ici](http://www.x.org/wiki/RadeonFeature#KMS_Power_Management_Options) pour une liste complète. En modifiant le fichier de "default" à "mid", j'ai pu entendre le ventilo baisser sa vitesse en temps réel.

Sachant qu'à chaque redémarrage, le paramètre du fichier "power_profile" revient sur default, il faut automatiser la commande. De base, Fedora 16 ne comporte pas de "rc.local". Il faut donc créer le fichier "/etc/rc.d/rc.local" et ajouter votre commande:

	#!/bin/bash
	echo mid > /sys/class/drm/card0/device/power_profile

Vous pouvez remplacer mid par 'low', ''auto' et 'high'. N'oubliez pas de le rendre exécutable avec:

	chmod +x /etc/rc.d/rc.local

Le fichier sera lu au boot de Fedora sans aucun autre réglage.


*** Réduire la consommation d'énergie avant le noyau 3.2 ***

Je vous invite à lire l'[article](http://blog.rolinh.ch/linux/palier-au-probleme-de-consommation-denergie-des-noyaux-linux-2-6-38-a-3-2/) de mon blog ami sur Rolin.ch ici, mais un autre tweak consiste à ajouter une option à GRUB, en attendant la correction dans le noyau du problème du surconsommation sur certains processeurs Intel depuis la version 2.6.38.

L'option à rajouter est "pcie_aspm=force". Pour ceci, rentrez:

	sudo nano /etc/default/grub

et ajouter "pcie_aspm=force" (sans les guillemets) à la fin de la ligne GRUB_CMDLINE_LINUX et recharger le grub.cfg avec:

	sudo grub2-mkconfig -o /boot/grub2/grub.cfg

Redémarrez l'ordi et vous aurez certainement une bonne surprise.

Je suis passé maintenant à 2h50 d'autonomie, ce qui est plutôt important.

*** Autre réglages ***

Sachant que mon chipset wifi est un Broadcom 4312 et que le driver free ne permet pas de faire fonctionner mon modèle, j'ai dû ajouter le dépôt RPMfusion qui comporte un driver non-libre.

J'ai ajouté les dépôts "Free" et "Non-free":

	sudo rpm -Uvh http://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-stable.noarch.rpm

et

	sudo rpm -Uvh http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-stable.noarch.rpm

Il faut ensuite rafraîchir la liste des paquets:

	sudo yum update

et j'ai installé le paquet kmod-wl avec:

	sudo yum install kmod-wl

-------------------------------------------------------

Je trouve que de base Fedora 16 consomme beaucoup de RAM, donc il faut désactiver pas mal d'applications au démarrage. J'ai désactivé les applis suivantes et je suis passé de 650 Mo à environ 350 Mo:

  * Caribou
  
  * Démarrer la méthode de saisie

  * Dépôt Tracker

  * Extracteur du système de fichiers Tracker

  * Extracteur Tracker pour Flickr

  * Files

  * Gestionnaire Bluetooth

  * GNOME Login Sound

  * Notificateur de sauvegarde

  * Orca screen reader

  * Partage de bureau

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/12/applis.png">

Pour modifier ces programmes, lancez:

	gnome-session-properties

-------------------------------------------------------

J'ai effectué quelques ajustements au niveau de l'interface car avoir une barre en haut et une en bas, c'est un peu trop pour moi. J'ai tout rassemblé sur une barre en haut de l'écran.

Elle rassemble:

  * Menu principal

  * Mes applications souvent utilisées

  * Liste des fenêtres

  * Sélecteur d'espaces de travail

  * Heure

  * Zone de notification

  * Menu personnel


Voilà le résultat:

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/12/bar.png">

Vous serez peut-être surpris que cet article ne soit pas en rapport avec Archlinux, mais j'essaie aussi de parler d'autre chose qui soit en rapport avec GNU/Linux.

PS: Il est bien écrit power_profile (ou method) dans les balises. L"underscore" est juste mal affiché dans ces balises.

EDIT: Corrigé une petite erreur au niveau du rc.local.
