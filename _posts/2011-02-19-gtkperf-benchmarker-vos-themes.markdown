---
date: 2011-02-19 12:26:46
layout: post
title: 'GtkPerf: Benchmarker vos thèmes!'
description: "Mesurer la vitesse d'affichage de vos thèmes GTK2."
categories:
- Personnalisation
tags:
- gtkperf
- openbox
- theme
---

Dans ma quête du système parfaitement parfait, j'ai fait la découverte du logiciel appelé GtkPerf. En parcourant Gnome-Look ou autre Box-Look, je me suis aperçu d'une chose: la plupart des thèmes GTK esthétiques, nécessitent plusieurs "engines" ou moteurs. Sous Gnome, rien de bien choquant mais lorsque l'on souhaite les utiliser sous Openbox, il n'est pas pratique d'installer tout un tas de moteurs.

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/02/auroraengine.png">

Je me suis alors posé quelques questions: un thème utilisant plusieurs moteurs devrait être moins "rapide" et performant qu'un thème sans fioritures. Parfois cela se vérifie mais pas toujours. C'est là que GtkPerf entre en scène, il permet de faire toutes une série de tests, avec votre thème courant (déroulement d'un menu, remplissage d'un champ avec des mots, scroll de ce champ, etc...) et au final, il vous affiche une valeur de temps. Sans surprise, plus elle est basse, plus votre thème est "performant".

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/02/gtkperf.png">

Afin d'obtenir une référence pour mes tests, j'ai utilisé comme base le thème GTK par défaut "Raleigh" qui est assez moche (12.61 avec Test Rounds=200). GtkPerf permet de faire toute la série de tests, ou un seul test bien précis. Vous pouvez aussi paramétrer le "Test Rounds", en saisissant une valeur. Un nombre élevé rend les tests plus longs. Pratique pour vraiment comparer les temps.

Ce qui est surprenant et qui m'a vraiment bluffé, c'est que j'utilisais un thème plutôt simpliste et les valeurs lors du benchmark étaient très élevées. Ce dernier nécessitait un moteur voire deux. Et d'autres thèmes assez beaux, ont eu des scores honorables.

Le moteur qui passe tout avec brio mais qui est un peu trop simpliste à mon goût: gtk-xfce-engine. J'ai obtenu tout simplement des valeurs extrêmement basses.

Ce paquet devrait se trouver dans vos dépôts quelque soit votre distribution.

BONUS: Mon [bureau actuel](http://forum.ubuntu-fr.org/viewtopic.php?pid=4003393#p4003393).
