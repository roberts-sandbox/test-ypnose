---
date: 2011-10-10 17:43:29
layout: post
title: Le retour d'Ypnose
description: "Je suis toujours vivant et motivé par ce blog!"
categories:
- Astuce
- News
- Personnalisation
tags:
- archlinux
- bashrc
- terminal
---

Bonjour,

Cela fait un bon mois que je n'écris plus d'articles. Cette période m'a paru être une éternité car d'habitude, j'écris plus souvent des news. Contrairement, à ce que l'on pourrait croire, le blog n'est pas mort. NON. La passion GNU/Linux m’anime toujours autant.

J'ai toujours autant soif de découverte et ce monde est extrêmement intéressant, car il y a toujours quelqu'un pour nous apprendre une chose. D'ailleurs, ce mois a été plutôt chargé, j'ai effectué beaucoup de "tweaks" sur mon ordinateur de bureau et testé pas mal de nouveaux logiciels. Cette fois-ci, je ne vous écrierai pas un simple article détaillant un point mais je vous ferais profiter d'une sorte de bilan.

<!-- more -->

J'avais déjà publié un article à propos du .bashrc, mais n'utilisant plus aucun GUI (sauf Geany), j'ai passé pas mal de temps à "améliorer" ce petit fichier. Je suis parvenu à un système très pratique et intuitif. Je rappelle que j'utilise dwm 5.9 dans lequel je n'ai que des terminaux clients, me permettant de rentrer des commandes. Je passe donc par des "alias" pour me faciliter la vie et éviter d'écrire des commandes trop compliquées et longues.

<img class="imgcenter" alt="aliases" src="http://linuxien.legtux.org/uploads/images/2011/10/alias.png">

J'ai aussi totalement modifié mon prompt, pour quelque chose de moins "tape à l'oeil" mais toujours utile. Il est indiqué l'user, le chemin absolu et l'heure à laquelle la commande a été validé.

<img class="imgcenter" alt="prompt" src="http://linuxien.legtux.org/uploads/images/2011/10/prompt.png">

Xarchiver me paraissant trop contraignant, j'ai décidé de complètement l'effacer et j'ai trouvé une fonction extract à rajouter dans le .bashrc. Cela permet d'extraire un grand nombre d'archives sans se compliquer la vie (avec un alias). Et petit plus, si l'archive comporte un dossier, vous êtes automatiquement placé dans ce dernier grâce à un 'cd'.

Vous pouvez retrouvez mon .bashrc sur [Github](https://github.com/Ypnose/Madfiles/blob/master/.bashrc). Il est souvent amélioré.

Autre point, je me suis acharné à créer un .Xdefaults comportant une gamme de couleurs convenables et qui soit agréable à regarder. Je pense être non-loin du modèle de couleurs parfait. Comme vous vous en doutez, je suis un utilisateur convaincu de rxvt-unicode (même si à mes débuts sous Arch, j'utilisais XTerm). Voici un screenshot:

<img class="imgcenter" alt="colorscheme" src="http://linuxien.legtux.org/uploads/images/2011/10/colors.png">

Cela représente les couleurs dans le terminal et sans me vanter, je dois dire que je suis content du travail rempli. Evidemment, vous pouvez retrouvez ma config [ici](https://github.com/Ypnose/Madfiles/blob/master/.Xresources).

_________________________


En tant que grand nostalgique, j'ai décidé de ressortir mon légendaire Doom I et II. Je rappelle que nous disposons en natif d'une bonne dizaine de[ ports](http://en.wikipedia.org/wiki/Doom_source_port), permettant de rejouer à ces jeux fabuleux. Il existe Doomsday Engine, ZDoom, GZDoom, PrBoom, PrBoom-Plus, Chocolate Doom et bien d'autres. Je ne fais pas partie de ceux, qui cherchent à tout prix à obtenir un jeu avec des textures HD, je préfère me rapprocher le plus possible de l'original.
J'ai donc choisi PrBoom-Plus. A moi donc, les longues heures dans des couloirs sombres remplis de démons.

<img class="imgcenter" alt="doom" src="http://linuxien.legtux.org/uploads/images/2011/10/doom.png">

Vous vous demandez certainement quel est le rapport avec mon blog? Voulant être de plus en plus impliqué et apporter mon aide en complément des forums, j'ai décidé de me mettre à écrire/modifier des pages du wiki [Archlinux.fr](http://wiki.archlinux.fr/Accueil). Je suis conscient que la communauté à vraiment besoin de contributeurs, voilà pourquoi j'essaie d'apporter mon aide. Attention, je ne me glorifie pas, comparé à d'autres, mon travail est mince.

Par conséquent, j'ai écris une page sur [PrBoom](http://wiki.archlinux.fr/Prboom) pour que les personnes tenté par ce port ne soient pas perdues.

_________________________


Actuellement, j'utilise Midnight Commander, que je trouve très adapté à une utilisation CLI. Je suis un ancien utilisateur de Thunar (quand j'avais Openbox), et je m'en suis séparé non sans mal, mais maintenant je suis habitué à MC.
Tout comme Moc, le thème par défaut est assez disgracieux (un bleu clair), et j'ai donc cherché à modifier les thèmes. Sur le toile, il y a quelques tutos pour créer son thème mais je n'ai pas été convaincu. J'ai trouvé dans /usr/share/mc/skins, des thèmes disponibles. Je m'en suis donc servi de base, pour l'adapter à mes besoins.

<img class="imgcenter" alt="mc" src="http://linuxien.legtux.org/uploads/images/2011/10/mc.png">

Utiliser un thème personnalisé n'est pas vraiment compliqué. Il faut ajuster les couleurs, créer le dossier skins dans $HOME/.mc dans lequel on place le thème et modifier la ligne "skin=" dans le fichier ini. Voici un exemple avec l'image précédente.

Encore une fois, retrouvez la config [ici](https://github.com/Ypnose/Madfiles/tree/master/mc).

J'ai réalisé d'autres travaux mais je ne veux pas tout vous détailler, pour ne pas vous paraître répétitif. Mais je peux vous dire que ce n'est pas le boulot qui manque (changement de l'arbre de Portage sous Funtoo qui coince, UUID dans le fstab, ou le /tmp sur la RAM).

Autre chose, j'ai vu que mon article "[Balayons les préjugés](http://tetedulinuxien.fr/2011/08/01/balayons-les-prejuges/)", a été plutôt bien accueilli et même retweeté. Je suis heureux de voir de l'enthousiasme pour ce sujet qui nous concerne tous.

Et n'hésitez pas à parler du blog autour de vous! Vive GNU/Linux.
