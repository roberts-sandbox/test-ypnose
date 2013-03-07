---
date: 2012-10-05 14:04:00
layout: post
description: "La procédure pour bien effectuer la mise de jour de filesystem, avec la distribution Archlinux."
title: "Guide de l'upgrade de filesystem sous Archlinux"
categories:
- Astuce
tags:
- archlinux
- astuce
- terminal
---

Salut les cocos,

Malgré le fait que je sois plutôt occupé en ce moment, j'arrive à trouver le temps et surtout l'inspiration pour mes articles. Je ne suis pas mécontent de la fréquence actuelle, à savoir un article par mois (à peu de choses près). Vous savez aussi que je ne veux pas me lancer dans une optique, d'un article par semaine. Je préfère vous pondre quelque chose de complet et d'intéressant. C'est un peu la recette de ce site (je n'aime pas le mot blog finalement, cela me fait penser à du Skyblog...).

<!-- more -->

Aujourd'hui, j'ai décidé d'écrire un article fonctionnel. Je sais qu'une bonne partie de mes lecteurs provient du forum [Archlinux.fr](http://forums.archlinux.fr/) et aussi de son [Planet](http://planet.archlinux.fr/). Cela implique que pas mal de personnes ici, utilisent Archlinux. D'ailleurs, je dois beaucoup à cette communauté et à cette distrib, je ne l'oublie pas.

<img class="imgcenter" alt="arch" src="http://linuxien.legtux.org/uploads/images/2012/10/archlinux.png">

Lors de la mise-à-jour quasi-journalière, il a été proposé [filesystem](http://www.archlinux.org/packages/core/any/filesystem/) en plus de [systemd](http://www.archlinux.org/packages/core/x86_64/systemd/) (que je trouve super) et [util-linux](http://www.archlinux.org/packages/core/x86_64/util-linux/). Je me suis renseigné sur le [git](https://projects.archlinux.org/svntogit/packages.git/log/trunk?h=packages/filesystem), comme j'ai l'habitude de faire pour les paquets "essentiels", afin de voir les changements. À l'issue de cette maintenance, pacman m'installe les fichiers passwd, group et gshadow (contenus dans l'archive), en *.pacnew. L'intervention administrateur impose le merge des nouveautés dans les fichiers existants.

Il est important de prendre connaissance des modifications. Si vous ne le faites pas, vous vous exposez à des éventuels bugs / limitations, qui ne devraient pas être présents.

Voici quelques infos:

- passwd contient des informations sur les utilisateurs enregistrés.

- group liste les groupes avec les utilisateurs associés.

- gshadow est uniquement consultable par root. Il contient des informations sur les groupes et les administrateurs.

AVANT TOUT, SACHEZ QUE JE NE SUIS PAS RESPONSABLE SI CES MANIPULATIONS ENTRAINENT DES PROBLÈMES. Chez moi, ça fonctionne.

Pour passwd et group, rien de bien compliqué. Plusieurs possibilités:

- Il y a les outils fournit par le paquet [pacman-contrib](http://www.archlinux.org/packages/community/any/pacman-contrib/) (avec vimdiff par exemple).

- Des [scripts](http://xyne.archlinux.ca/projects/pacnew_scripts/) en perl qui permettent le merge des fichiers.

- Vous pouvez passer par les commandes vipw et vigr pour les éditer, ajouter les lignes nécessaires et aussi vérifier la syntaxe (évite les erreurs). L’éditeur par défaut est vi, mais il est possible de passer par $EDITOR pour en spécifier un autre (qui a dit nano?). vipw edite le fichier /etc/passwd et vigr edite le fichier /etc/group.

Par exemple:

	EDITOR=nano vigr

Je vous conseille une petite lecture de man:

	man vipw

ou

	man vigr

- La méthode (color)diff pour voir les différences et les ajouter dans ces fichiers via nano. C'est cette méthode que j'utilise. Avec la coloration syntaxique et les comparaisons diff, je suis sûr de ne rien oublier. Et je prends connaissance des modifications, sans effectuer un simple merge bête et méchant.

Avant de s'occuper du gshadow, je vous conseille d'utiliser grpck. Mais que fait-il? grpck vérifie l'intégrité des fichiers de groupes (format + données valides ou non). À utiliser avec sudo (ou su -c).

	grpck

Chez moi aucun soucis apparemment car la commande ne me retourne rien. J'utilise aussi la commande avec l'argument "-s", qui permet de trier les lignes par GID dans les fichiers group et gshadow (de 0 vers 1000 par exemple). Cela est très utile, car le fichier est parfaitement lisible.

	grpck -s

Pour plus d'infos:

	man grpck

Déjà vous savez que les changements sont bons. Nous devons maintenant nous occuper du gshadow. Ce fichier n'est pas visible en simple utilisateur. Comme je suis plutôt minutieux et que je fais attention, je me suis renseigné sur la méthode la plus adapté / efficace.
Je ne l'éditerai pas, mais je passerai plutôt par la commande grpconv. Cette commande permets de créer un fichier gshadow à partir de group et d'un éventuel gshadow déjà existant.

	grpconv

Pour plus d'infos:

	man grpconv

Voilà c'est OK. Tout de même, sachez qu'il n'est pas forcément nécessaire de la faire, mais je préfère le faire. Je garde un système propre.


_edit: Mise à jour des explications pour les fichiers concernés._
