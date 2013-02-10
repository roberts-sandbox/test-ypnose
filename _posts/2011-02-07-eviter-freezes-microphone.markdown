---
date: 2011-02-07 20:36:23
layout: post
title: Eviter les "freezes" à cause du microphone
description: "Comment éviter un bug bien ennuyeux à cause du microphone."
categories:
- Astuce
tags:
- alsa
- micro
---

Subissant quelques mésaventures sous Archlinux (et OpenSUSE il y a quelques temps), j'ai noté quelque chose d'étrange. Je précise que cet article est destiné à ceux qui ont un micro externe qui se banche en USB et qui comporte une carte son intégré (en gros, qui ne se branche pas dans la jack de la carte mère). Voilà un [exemple](http://www.materiel.net/microphone/logitech-usb-desktop-14518.html).

Et oui aussi bizarre que cela puisse paraître, j'ai rencontré des freezes d'applications comme sous Mumble ou Heroes of Newerth, lorsqu'ils sont démarrés pour la première fois et que les réglages sont ceux par défaut. Effectivement, l'application pouvant utiliser un micro, va vérifier qu'un micro est branché dans la jack et qu'il capture le son. Si il n'y en a pas, ou que vous n'avez pas réglé dans Alsamixer "Capture", vous aurez des freezes et ne pourrez rien faire sauf fermer le programme.

<!-- more -->

L'astuce consiste donc à paramétrer Alsamixer comme l'image ci-dessous:

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/02/alsa.png">

Comme vous pouvez le constater, on a déclaré que "Capture" doit enregistrer le son alors même qu'aucun microphone n'est branché. Par la suite, pour utiliser le bon périphérique, il vous suffit de choisir celui que vous désirez, lors des réglages du logiciel.
