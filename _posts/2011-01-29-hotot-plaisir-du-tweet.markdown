---
date: 2011-01-29 19:04:11
layout: post
published: false
title: 'Hotot: Plaisir du tweet'
description: "Un client Twitter multi-compte bien utile."
categories:
- News
tags:
- hotot
- twitter
---

Certains d'entres vous possèdent certainement un compte Twitter pour suivre des projets ou tout simplement pour le boulot. On peut se contenter du site web lui-même, pour ajouter de nouveaux tweets ou alors utiliser des extensions sur le navigateur fétiche. Mais il existe aussi des logiciels (comme [choqok](http://choqok.org/) pour KDE) qui permettent à l'utilisateur, de consulter son profil Twitter. J'ai récemment découvert un logiciel qui s’appelle [Hotot](http://hotot.org/) et qui semble extrêmement prometteur (il n'y pas encore de paquets dans les dépôts). Le logiciel est en python et nécessite des dépendances telle que python-webkit par exemple.

<!-- more -->

<img class="imgcenter" alt="Python" src="http://linuxien.legtux.org/uploads/images/2011/01/pythonlogo.png">

Ce dernier est très intuitif. Il suffit de cliquer sur un bouton pour ajouter un nouveau compte, se loguer sous son profil pour récupérer un code PIN, le coller sous Hotot et le tour est joué. Facile non?

Mais ce que j'ai vraiment aimé, c'est l'interface très propre avec de belles "transitions", quand on veux consulter ses messages ou chercher un profil. J'ai crû comprendre que l'interface est gérée en CSS sou-poudrée de javascript. Je ne l'utilise pas encore à plein temps, mais il y a des chances que je lâche mon "Chromed Bird" bientôt.

<img class="imgcenter" alt="Window" src="http://linuxien.legtux.org/uploads/images/2011/01/hototdesk.png">

Par exemple, lorsque vous recevez un nouveau tweet, une notification s'affiche en haut de votre écran.

Il est difficile pour moi de décrire ce qu'est le logiciel. Voilà pourquoi, je vous conseille vivement de l'essayer si vous disposer d'un compte.

Pour les Ubunteros:

	sudo add-apt-repository ppa:hotot-team
	sudo apt-get update && sudo apt-get install hotot

Pour les Archers ([AUR](https://aur.archlinux.org/packages.php?ID=40692)):

	yaourt -S hotot

J'espère que cette news aura titillé votre curiosité.
