---
date: 2011-06-17 11:39:36
layout: post
title: 'Funtoo: Compilez!'
description: "Ma découverte de Funtoo avec ses heures de compilations."
categories:
- Test
tags:
- archlinux
- distrib
- funtoo
- kernel
---

Bonjour,

En appliquant ma curiosité légendaire, j'ai par conséquent décidé de me constituer un dualboot, sur mon nouvel ordi. Dans un article plus ancien, j'avais expliqué que je souhaitais essayer une Gentoo. J'ai entendu beaucoup de bien d'une distrib appelé Funtoo, qui a été crée par le grand manitou de Gentoo. Il a quitté le navire en 2008, à cause de problèmes de licences. Attention, ce n'est pas un fork mais une autre variante de Gentoo.

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/06/gentoologo.png">

Je précise que je reste fidèle à ma Arch, qui me satisfait pleinement. Comme je l'ai dit souvent, c'est ma meilleure expérience GNU/Linux. J'utiliserai surtout cette Funtoo à un but expérimental.

Avant tout, il faut être sûr d'avoir des partitions disponibles. Le schéma habituel, à savoir: une racine /, un /home séparé et un /boot de quelques Mo. Funtoo ne s'installe qu'avec [chroot](http://lea-linux.org/documentations/index.php/Admin-admin_env-chroot). Une occasion pour moi, de tester cette méthode que je n'utilise pas. Pour ma Arch, j'utilise l'iso sur une clé USB. L'installation en elle même, est un tantinet plus compliquée que pour une Archlinux. Vous aurez besoin d'une connexion Internet, sans quoi, l’installation doit être encore plus hardue. Vous avez deux choix: utiliser la branche stable ou current, avec beaucoup de softs récents mais peut-être moins fonctionnels. J'ai opté pour la branche "Stable" car je souhaite avoir un système exploitable. En fonction de votre choix (branche, 32 ou 64 bits et processeur), vous télécharger ce que l'on appelle stage3 et l'arbre Portage. Ils comportent le système de base (racine) et les librairies.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/06/funtoo.jpg">

Après l'extraction, vous devez modifier des fichiers de configs avec nano, comme le /etc/make.conf qui permet de définir le [CFLAGS](http://fr.wikipedia.org/wiki/CFLAGS) en fonction du CPU et bien d'autres options. Ce fichier est un des plus importants, car vous en aurez besoin pour toutes vos futures compilations. Il y a environ 7 fichiers à regarder.

Actuellement, vous n'avez aucun noyau d'installé sur Funtoo. Après avoir mis votre système à jour et avoir tout compilé (dans les 2h30 sur mon Phenom, aucun soucis en tout cas), vous devez prendre les sources du kernel et compiler le bouzin.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/06/tux.jpg">

Cet étape est de loin la plus intéressante de l'installation. Je connaissais déjà la procédure, sachant que je compile un noyau sur Arch. Pour ne pas faire de bêtises, il est conseillé d'appliquer la config de base préconisée par les développeurs (via make defconfig), et de l'adapter à vos besoins ensuite. Cette étape peut prendre vraiment beaucoup de temps, en particulier pour du matos un peu exotique (comme mon microphone USB). Je suis justement en train de me préparer un ".config" (configuration des options du kernel) totalement adapté à mon ordinateur. J'en garderai des copies, et cela me sera utile lors de prochaines compilations de noyau. Par contre, j'avoue que j'ai eu un kernel panic, dû à une option redondante.

Une chose que j'apprécie quand on compile son kernel, c'est qu'il est possible de définir des fonctions qui rendent le tout plus simple, grâce à menuconfig. Par exemple, comme je l'ai déjà expliqué il n'y a pas si longtemps, j'utilise cpufreq parce que le profil de base du CPU, est "performance" et que je souhaite le définir sur "ondemand"; je peux désormais définir le profil de base sur "ondemand", et ainsi me passer de la mise en oeuvre de cpufreq. Autre bon point, je peux directement désactiver la prise en charge IPv6 dans le noyau, sans passer par une règle dans modprobe.conf.

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/06/gcc.png">

Par conséquent, si votre matériel est plutôt bon, je vous recommande grandement de passer par cet étape, quelque soit votre distribution. Vous découvrirez sûrement des choses intéressantes.

Comme pour Arch, lorsque l'on a fini l'installation et éventuellement modifié GRUB en cas de dualboot, on redémarre et on se retrouve sur un système minimaliste, en tty. Voici les lignes que j'ai rajouté dans GRUB 0.97, pour pouvoir booter sur Funtoo:

	title Funtoo Linux
	root (hd0,10)
	kernel /vmlinuz-2.6.38-gentoo-r6 root=/dev/sda9 quiet vga=792

Après, à nous d'installer le serveur X et un bon WM, mais tout cela sera expliqué lors d'un prochain article!

Doc: [Funtoo](http://www.funtoo.org/wiki/Welcome)
