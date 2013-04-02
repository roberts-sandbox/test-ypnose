---
date: 2011-01-06 16:27:51
layout: post
title: "Personnaliser le terminal"
description: "Un petit PS1, qui sort de l'ordinaire."
categories:
- Personnalisation
tags:
- archlinux
---

Avouons le, le terminal est un outil extrêmement performant (parfois même addictif) et très utile mais vous le savez déjà. Sous Archlinux, [xterm](http://fr.wikipedia.org/wiki/Xterm) est installé par défaut et je trouve cet émulateur parfais pour mon utilisation. Il m'arrive parfois d'avoir une dizaines de terminals ouvert en même temps lorsque j'utilise nano pour éditer mes fichiers, pacman pour installer, ou compiler des logiciels. Cependant par erreur, j'ai déjà ouvert des logiciels en root, ce qui est plutôt déconseillé.

<!-- more -->

Après avoir cherché sur la toile, un moyen de colorier "votre_pseudo@localhost" comme sous OpenSuse lorsqu'on est en root, j'ai enfin trouvé.

Cette "customisation" a été testé uniquement sous Archlinux (cela doit aussi fonctionner sous d'autres distributions mais je ne promets rien).

__Colorier votre prompt pour l'utilisateur régulier:__

  * Faites une backup de votre ~/.bashrc

  * Vous devez éditer votre ~/.bashrc avec un éditeur de texte comme nano par exemple

  * Si vous avez la ligne ``` _PS1='[\u@\h \W]\$ ' ``` , commentez la avec un #

  * Ajoutez la ligne: ``` _PS1='\[\e[0;36m\][\u@\h \W]\$\[\e[0m\] ' ``` (cela correspond au prompt couleur cyan)

  * Pour changer la couleur ou mettre le prompt en gras, ou souligné; remplacez ``` \e[0;36m ``` par le code correspondant (reportez vous au codes couleurs au bas de cet article.)

  * Sauvegardez et fermez l'éditeur

__Colorier votre prompt pour l'utilisateur root:__

  * Éditez le bashrc de l'utilisateur root: _nano /root/.bashrc _(Si ce fichier est absent, copiez le bashrc qui se trouve dans /etc/skel)

  * Ajouter la ligne ``` PS1='\[\e[1;31m\][\u@\h \W]\$\[\e[0m\] ``` (correspond au prompt couleur rouge et gras)

  * Remplacer ``` \e[1;31m ``` par le code correspondant à la couleur et à la forme du texte que vous désirez.

  * Sauvegardez et quittez

Afin de tester, lancer votre terminal, regardez si le prompt est de la couleur choisie en utilisateur normal et en root.

Codes couleurs

    txtblk='\e[0;30m' # Black - Normal
    txtred='\e[0;31m' # Red
    txtgrn='\e[0;32m' # Green
    txtylw='\e[0;33m' # Yellow
    txtblu='\e[0;34m' # Blue
    txtpur='\e[0;35m' # Purple
    txtcyn='\e[0;36m' # Cyan
    txtwht='\e[0;37m' # White
    bldblk='\e[1;30m' # Black - Gras
    bldred='\e[1;31m' # Red
    bldgrn='\e[1;32m' # Green
    bldylw='\e[1;33m' # Yellow
    bldblu='\e[1;34m' # Blue
    bldpur='\e[1;35m' # Purple
    bldcyn='\e[1;36m' # Cyan
    bldwht='\e[1;37m' # White
    unkblk='\e[4;30m' # Black - Souligné
    undred='\e[4;31m' # Red
    undgrn='\e[4;32m' # Green
    undylw='\e[4;33m' # Yellow
    undblu='\e[4;34m' # Blue
    undpur='\e[4;35m' # Purple
    undcyn='\e[4;36m' # Cyan
    undwht='\e[4;37m' # White
    bakblk='\e[40m'   # Black - Arrière-plan
    bakred='\e[41m'   # Red
    badgrn='\e[42m'   # Green
    bakylw='\e[43m'   # Yellow
    bakblu='\e[44m'   # Blue
    bakpur='\e[45m'   # Purple
    bakcyn='\e[46m'   # Cyan
    bakwht='\e[47m'   # White
    txtrst='\e[0m'    # Text Reset

[Source](https://wiki.archlinux.org/index.php/Color_Bash_Prompt#Basic_prompts)
