---
date: 2011-01-08 11:45:34
layout: post
published: false
title: "Intégrer les applis Qt dans GTK"
description: "Avoir un thème graphique uniforme entre Qt et GTK."
categories:
- Personnalisation
tags:
- astuce
- qt
---

Sous ma OpenBox, il m'arrive d'utiliser quelques applications Qt comme Mumble (et je ne peux pas le remplacer) et dans un environnement à base de GTK (WM léger) ça fait un peu tâche. Il existe une petite astuce qui consiste a faire utiliser par Qt, le thème GTK. Je suppose que vous avez déjà choisit un thème GTK avec [Lxappearance](https://wiki.archlinux.org/index.php/Openbox) ou autre utilitaire.

<!-- more -->

<img class="imgcenter" alt="Qt" src="http://linuxien.legtux.org/uploads/images/2011/01/qt-logo.png">

L'astuce consiste à rajouter dans votre ~/.xinitrc , la ligne ``` export GTK2_RC_FILES="$HOME/.gtkrc-2.0" ``` . Vous pouvez éditer votre fichier avec nano ou Gedit. Si vous utiliser OpenBox ou PekWM, assurez vous que cette ligne soit avant "exec openbox-session" (pour OpenBox) ou avant "exec pekwm" (pour PekWM). Ayant, par erreur ajouté cette ligne après, l'astuce ne fonctionnait pas.

Quand vous avez modifié votre ~/.xinitrc , lancer "qtconfig" dans votre terminal, et au niveau de l'option "GUI Style", choisissez GTK+. A vous de belles applications Qt uniformisées avec le reste du système!
