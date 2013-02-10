---
date: 2011-06-01 10:54:11
layout: post
title: '"Moc Controller" v 1.04'
description: "Nouvelle version de mon script moc pour Openbox."
categories:
- Personnalisation
---

Yo les lecteurs;

Voici une nouvelle version du script que j'ai appelé "Moc Controller", avec pas mal de changements. Avant tout, je tiens à dire que mon travail fonctionne beaucoup mieux, avec des morceaux qui ont été tagué un minimum.

Déjà, il y avait un problème avec le caractère "&" qui a fallu remplacer par "&amp;". Le script ne fonctionnait plus à cause de ça.

<!-- more -->

Ajout de la fonction "Bitrate":

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/06/bitrate.png">

Ensuite, j'ai ajouté des messages si le fichier est un .wav (je m'occuperais du .ogg aussi). Les waves n'ont pas les tags id3. Donc, un message est affiché, si vous lisez ce type de fichier (le titre est vide). Pareil pour la section "Bitrate".

Exemple:

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/06/wave.png">

Quand le lecteur est stoppé ou que votre morceau est en "PAUSE", "Bitrate" affiche des "traits" au lieu de "Not Supported":

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/06/bitratepause.png">

Rendez-vous ici pour télécharger la nouvelle [version](https://raw.github.com/Ypnose/Madfiles/master/NEWmocinfo.sh). Bye.
