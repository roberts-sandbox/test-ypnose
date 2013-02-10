---
date: 2011-01-26 13:00:22
layout: post
title: Petit script Openbox
description: "Afficher la température de votre GPU Nvidia, dans le menu Openbox."
categories:
- Personnalisation
tags:
- gpu
- nvidia
---

Récemment, j'ai cherché un petit script qui affiche la température de mon GPU Nvidia dans le Menu Openbox. Effectivement, c'est un peu contraignant de démarrer à chaque fois Nvidia X Server Settings. Mais je n'ai pas réussi à trouver cette fonction.

Grâce à la [documentation](http://openbox.org/wiki/Main_Page) Openbox, j'ai réussi à écrire un script qui affiche la version du driver installé et la température de ce dernier. Voici une image:

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/01/gpuscript.png">

Pour le mettre en place, vous devez:

  * le [télécharger](http://linuxien.legtux.org/uploads/images/2011/01/nvidiatemp.sh)

  * le placer dans votre dossier personnel

  * exécuter "chmod +x .nvidiatemp.sh" dans votre terminal favori (afin de le rendre exécutable)

  * le renommer en .nvidiatemp.sh par exemple (il sera en caché)

Lorsque vous avez effectué ces procédures, il vous suffit d'ajouter cette ligne à votre menu.xml:

	<menu execute="/home/xxx/.nvidiatemp.sh" id="pipe-temp" label="GPUTemp"/>

Il devrait fonctionner pour les GPU Nvidia récents, car j'utilise la commande "nvidia-settings -q gpucoretemp -t" qui est la même que dans Nvidia X server. N'hésitez pas à me contacter pour me tenir au courant.
