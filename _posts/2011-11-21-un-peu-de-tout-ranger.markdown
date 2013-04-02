---
date: 2011-11-21 12:47:09
layout: post
title: "Un peu de tout (mais surtout Ranger)!"
description: "Changer le layout de moc et ma découverte de Ranger."
categories:
- News
- Personnalisation
tags:
- archlinux
- astuce
- lecteur
- moc
- ranger
- terminal
- urxvt
---

Salut,

En ce moment, je passe une bonne partie de la journée à modifier les configs de mes logiciels préférés. J'essaie de me rapprocher d'un système le plus intuitif possible. Je vais donc vous faire profiter de mes trouvailles.

Le "layout" par défaut de Moc n'est pas très pratique, je trouve. Surtout dans un terminal peu large. Par conséquent, j'ai un peu regardé le fichier appelé "config", qui comporte tout les paramètres de Moc (exemple dans /usr/share/doc/moc). Il contient entre autres, le thème utilisé, le répertoire par défaut, le canal à moduler, etc.

<!-- more -->

<img class="imgcenter" alt="mocdef" src="http://linuxien.legtux.org/uploads/images/2011/10/mocdefaut.png">

A la fin de ce fichier, vous pouvez trouver une section qui contient différents layouts prédéfinis. Comme par exemple:

	Layout1 = "directory:0,0,50%,100% playlist:50%,0,50%,100%"

Cette ligne vous permet d'afficher un layout adapté à votre utilisation. Voici mon nouveau résultat:

[<img class="imgcenter" alt="newlayout" src="http://linuxien.legtux.org/uploads/images/2011/11/mocperso.png">](http://linuxien.legtux.org/uploads/images/2011/11/mocperso.png)

et la ligne correspondante:

	Layout1 = "playlist:0,0,100%,10% directory:0,10%,100%,FILL"

On pourrait aussi utiliser des valeurs absolues, mais cela engendrerait des erreurs dans le cas où la taille du terminal change (j'ai essayé).
Cette ligne n'est pas compliquée, elle déclare à moc d'utiliser 10% d'espace du haut du terminal pour afficher la playlist (et 100% de largeur) et l'espace restant est utilisé pour afficher les pistes dans le dossier. Je trouve ce layout plus adéquat, sachant que j'affiche moc dans un terminal à gauche, occupant 35% de l'écran. Par conséquent, il vaut mieux afficher un layout vertical plutôt qu'un horizontal comme par défaut.

--------------------------------------------------------------------

Comme il m'a plusieurs fois été conseillé, j'ai décidé de tester Ranger. On m'a dit beaucoup de bien de ce gestionnaire de fichiers CLI. Je l'ai donc installé avec:

	pacman -S ranger

Si tout va bien, vous aurez juste besoin de Python 3.2 (je n'utilise pas la version git qui est dispo sur AUR).

J'étais déjà très content de mc, qui me permettait de gérer mes fichiers assez facilement, mais depuis que je me suis essayé à [Ranger](http://ranger.nongnu.org/), je suis conquis. Le mot est d'ailleurs assez faible. Avec [Ranger](http://ranger.nongnu.org/), la navigation dans les dossiers est très rapide car on utilise les flèches pour ce déplacer, contrairement à mc où c'est plus beaucoup plus rébarbatif. Pourquoi?

Tout simplement, parce que Ranger affiche trois colonnes "liées" et qu'il est donc plus facile de naviguer dans l'arborescence, alors que mc affiche deux colonnes indépendantes. Avec Ranger, vous pouvez aussi voir dans la troisième colonne un aperçu du fichier/dossier sélectionné. Si par exemple, c'est un fichier texte, vous avez un aperçu avec nano, ou avec un fichier audio/vidéo, les propriétés du fichier sont affichées (vous aurez besoin de [mediainfo](http://mediainfo.sourceforge.net/en)).

[<img class="imgcenter" alt="ranger" src="http://linuxien.legtux.org/uploads/images/2011/11/rangeraperçu.png">](http://linuxien.legtux.org/uploads/images/2011/11/rangeraperçu.png)

Il dispose d'autres avantages extrêmement utiles:

  * système de bookmarks pour se déplacer encore plus rapidement dans les dossiers favoris.

  * hautement personnalisable (applis par défaut et options) via des fichiers.

  * raccourcis claviers nombreux similaire à vim.

  * onglets

  * recherches

Je ne suis pas encore, un adepte de vim mais j'arrive tout de même à me familiariser avec les raccourcis. Ils sont souvent sous la forme de deux lettres et lorsque vous appuyer sur la première, une liste s'affiche et montre différentes combinaisons réalisables. Cela aide à se souvenir des combinaisons. Il est aussi possible d'utiliser les raccourcis de mc bindés sur les Fx (de F1 à F10).

[<img class="imgcenter" alt="shortcuts" src="http://linuxien.legtux.org/uploads/images/2011/11/raccourcis.png">](http://linuxien.legtux.org/uploads/images/2011/11/raccourcis.png)

Chose importante, il faut aussi se décider à modifier le thème de couleur. Celui de base est acceptable (avec un .Xdefaults peaufiné), mais je cherche à obtenir un thème similaire à mc car je me suis habitué aux couleurs.

<img class="imgcenter" alt="color" src="http://linuxien.legtux.org/uploads/images/2011/11/color.png">

Avant de personnaliser toutes ses configs, exporter les dans le dossier '~/.config' avec:

	ranger --copy-config=all

Pour créer un thème, je pars du thème default (car il comporte le plus d'options) et je l'adapte à mes besoins. Il faut créer un dossier 'colorschemes' dans '~/.config/ranger' et y placer votre thème suivit de .py. Il faudra se frotter un petit peu au Python, même si il n'y a rien de compliqué. Par contre, je n'ai pas réussi à trouver comment modifier une couleur pour une extension personnalisée comme .sql. Si quelqu'un à l'info, je suis preneur.

Astuce: Pour afficher des bordures autour des colonnes:

	# Draw borders around columns?
	draw_borders = True

Je vous invite à consulter mon thème [ici](https://github.com/Ypnose/Madfiles/blob/master/ranger/colorschemes/spacecolor.py).

Le dossier '~.config/ranger' comporte:

  * apps.py pour choisir le logiciel à utiliser en fonction de l'extension.

  * bookmarks qui contient vos dossiers favoris.

  * commands.py pour les commandes.

  * options.py pour configurer les options de ranger.

  * rc.conf pour les raccourcis clavier.

  * scope.sh pour afficher les aperçus.

Tout ces fichiers rendent le soft entièrement configurable et on peut donc changer la moindre option sans difficultés. Je vais certainement affiner mes configs dans les semaines qui viennent, mais je suis déjà très content de ce logiciel.

Cependant, un petit  'man ranger' s'impose ou sinon lancez ranger et appuyer sur '?'.

Merci à tous ceux qui me l'ont conseillé.
