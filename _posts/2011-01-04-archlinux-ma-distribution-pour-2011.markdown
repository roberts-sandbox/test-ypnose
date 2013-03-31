---
date: 2011-01-04 14:30:35
layout: post
published: false
title: 'Archlinux: ma distribution pour 2011'
categories:
- Avis
tags:
- archlinux
- chakra
- distrib
- openbox
---

J'ai toujours été une personne curieuse, c'est pour ça que j'ai testé pas mal de distributions Linux. Il est toujours bon de voir ce que fait le voisin. Il a quelques années de ça, j'ai commencé sur Ubuntu (comme de nombreux Linuxiens) et je dois dire que je me suis assez vite dirigé vers KDE que je trouvais très esthétique. Un choix c'est donc imposé: Kubuntu.

<!-- more -->

<img class="imgcenter" alt="Chakra logo" src="http://linuxien.legtux.org/uploads/images/2011/01/Chakra-gradient.png">

Mais lors de la sortie de la version 9.10, j'ai rencontré beaucoup de problèmes comme la surconsommation de CPU par le système (20 à 25% à vide). J'ai donc décidé de changer. Après cela, j'ai eu plus que du mal à trouver une distribution qui me convienne. J'ai utilisé pendant un long moment une [Chakra Linux](http://chakra-project.org/), qui avait à l'époque ArchLinux comme base. J'en garde un excellent souvenir avec par exemple une intégration de KDE exceptionnelle, comportant des thèmes uniques à la distrib', le gestionnaire de paquets [pacman](http://wiki.archlinux.fr/arch/pacman) qui est d'une efficacité redoutable (ancien adepte de Synaptic), un démarrage rapide, KDEmod (un KDE modifié par les développeurs avec plus de fonctionnalités). Cependant la version était en Alpha et malgré la stabilité, il y avait certains bugs.

Maniaque que je suis, je cherchais la perfection et je suis tombé sur OpenSUSE. Il semble que beaucoup de développeurs de KDE utilisent cette dernière. J'ai passé le cap et je n'ai pas été déçu: on est en présence d'une distribution de bonne facture, avec des outils très pratique comme [Yast](http://fr.opensuse.org/YaST/A_propos) qui permet de paramétrer finement le système sans avoir à passer par la console (même si ça ne me dérange pas). Autre bon point: KDE démarre au quart de tour, aucun plantages, pas de bugs (sauf une [incompatibilité notoire](http://forums.opensuse.org/english/get-technical-help-here/applications/448653-nvidia-260-19-issues.html) des nouveaux drivers Nvidia 260.19 avec la version 11.3 en 32 bits).

Mais récemment, Novell (la maison mère d'OpenSUSE) a été rachetée par** **Attachmate Corp qui serait de près ou de loin liée à Microsoft et cela a entraîné un malaise chez certains utilisateurs y compris moi. Certes, il ne faut pas crier au loup sans l'avoir aperçu mais cela reste inquiétant.

J'ai cherché une autre distribution et après moult lectures d'articles, j'ai décidé de venir sur [Archlinux](http://archlinux.fr/), une distribution qui semble fabuleuse après avoir lu de nombreux posts sur différents forums.

Ce que j'aime sur Archlinux: L'installation n'est pas si difficile et en s'aidant de la doc sur [Archlinux.fr](http://archlinux.fr/) et [Archlinux.org](http://www.archlinux.org/) qui est bien fournie, on a pas trop de difficultés. Il n'y a pas d'installateur graphique mais cela permet d'obtenir un boot à partir du CD assez rapide, et les options sont bien détaillées.

Autre bonne surprise, l'installation se déroule vite.  En 25 minutes c'est réglé. Certes, c'est plutôt minimal mais fini les gigas inutiles. La grande force d'Archlinux c'est que l'on choisi ce qui va être installé. Pas de fioritures, on a juste l'essentiel. Après la mise en place de xorg et les drivers pour les GPU, on peut choisir son environnement de bureau ou encore son gestionnaire de fenêtres en stand-alone. C'est l'opportunité pour moi de tester [OpenBox](http://fr.wikipedia.org/wiki/Openbox) et [PekWm](http://fr.wikipedia.org/wiki/Pekwm) qui me faisaient de l'œil depuis pas mal de temps.

<img class="imgleft" "Openbox" src="http://linuxien.legtux.org/uploads/images/2011/01/OpenBox_logo_v2_by_skeletux.png"> <img class="imgright" alt="PekWM" src="http://linuxien.legtux.org/uploads/images/2011/01/pekwm_logo.png">

OpenBox n'est pas très difficile à paramétrer. On peut utiliser un éditeur de texte comme vim ou gEdit pour modifier les fichiers mais il existe aussi quelques utilitaires comme Obmenu, Obconf (pour le thème Openbox). Et bien sûr on peut utiliser Lxappearance pour le thème GTK. Le système est très léger et consomme peu de RAM (140 Mo à vide).

Je n'ai pas encore eu le temps de me pencher en détail sur PekWm mais il semble que les thèmes soit encore plus jolis car il est possible d'ajouter des images pour ces derniers.

D'autres points forts pour Arch: la disponibilité dans les dépôts des dernières versions des logiciels, un catalogue d'applications énorme (et il y a [AUR](https://aur.archlinux.org/) en plus), une distrib' qui démarre en 20s, l'utilisateur apprend beaucoup car il doit configurer lui-même ses fichiers et possibilités de customisation quasie infinie.

Ce que j'aime moins: une fois que tout est configuré aux petits oignons et que tout marche comme sur des roulettes et il ne reste plus rien à faire sauf un petit "pacman -Syu" de temps en temps.

Pour conclure, j'adore cette distribution et je ne suis pas près de m'en séparer. L'essayer c'est l'adopter.
