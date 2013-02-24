---
date: 2011-05-31 16:16:17
layout: post
title: Script moc pour Openbox
description: "Intégration de moc dans le menu d'Openbox."
categories:
- Personnalisation
tags:
- archlinux
- moc
- openbox
---

Sachant que je suis un utilisateur conquis de Moc (Music On Console), j'ai eu l'idée de créer un petit script, qui affiche le morceau joué dans le menu Openbox.

Si vous n'avez pas lancé Moc, le script vous affiche un message et n'affiche pas la section "Controls":

<!-- more -->

<img class="imgcenter" alt="nomoc" src="http://linuxien.legtux.org/uploads/images/2011/05/turnoff.png">

Si Moc est lancé mais ne joue pas de musique, le script affiche un message "Not Playing Music" mais la section "Controls" s'affiche.

<img class="imgcenter" alt="mocstop" src="http://linuxien.legtux.org/uploads/images/2011/05/musicstop.png">

Lorsqu'une chanson est en cours de lecture, le titre est affiché et grâce à la section "Controls", vous pouvez mettre Pause, Chanson suivante et précédente, L'option "Quit" permet de fermer le lecteur et le daemon (cela reviens à un "killall mocp").

<img class="imgcenter" alt="mocplay" src="http://linuxien.legtux.org/uploads/images/2011/05/playing.png">

Je prévoie de rajouter d'autres fonctions mais je suis plutôt content du résultat. N'hésitez pas à donnez vos avis et/ou conseils.

Les instructions pour l'installer sont dans le [script](https://raw.github.com/Ypnose/Madfiles/master/NEWmocinfo.sh). Tchuss!
