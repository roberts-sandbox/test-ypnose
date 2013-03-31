---
date: 2012-04-28 11:17:16
layout: post
published: false
title: "Des nouvelles fraîches"
description: "Après un long moment d'inactivité, me voici de retour!"
categories:
- News
tags:
- bilan
- fedora
---

Bonjour,

Effectivement, cela fait pas mal de temps que je n'ai pas écrit d'articles sur le blog. Cela n'est pas parce que j'ai décidé de le délaisser et de l'abandonner, bien au contraire. Mais plutôt parce que j'ai eu un moment de relâchement, où j'ai drastiquement changé mes habitudes. Le blog est pour moi plus qu'important et je ne souhaite pas jeter l'éponge.

<!-- more -->

J'ai effectué un nombre importants de travaux informatiques, sur différents périphériques, et cela à occupé mon temps libre. Par ailleurs, j'ai brûlé beaucoup d'heures sur le RPG Skyrim et je n'ai pas vu le temps passer.

Pendant une période, je ne savais pas trop de quoi parler et puis tout d'un coup, j'ai eu de nombreuses idées d'articles et de projets. Je vais vous expliquer plus loin ces travaux.

Je mentionne aussi très souvent le fait que j'aimerais avoir plus de lecteurs, qui profitent de mes contenus mais le format de se blog (c'est-à-dire des articles à intervalles non-réguliers) n'est pas quelque chose de communs, comme d'autres blogs où il y a des news plusieurs fois par semaine. Cela je pense, m'empêche de vraiment faire mon trou. Je vous encourage à faire un peu de bouche à oreille autour de vous, peu importe si le public est novice ou confirmé.

<img class="imgcenter" alt="twitter" src="http://linuxien.legtux.org/uploads/images/2012/04/twitter.png">

J'ai donc décide d'écrire un article, qui vous permettra d'y voir un peu plus clair sur les sujets que je souhaite développer, dans les prochains mois. Les points cités sont survolés car j'écrirai des articles complets en les traitant au cas par cas.

**- Laptop -**

Il y a plusieurs mois, je m'étais mis à Fedora 16 avec GNOME 3 (en mode Fallback) mais non content de certaines choses, comme des programmes qui crashent ou sinon des widgets qui refusent de se lancer au démarrage, j'ai changé d'environnement. J'ai switché sur XFCE et je suis plus que satisfait de ce changement. J'ai pu obtenir un système très stable et qui répond parfaitement à mes besoins.

[<img class="imgcenter" alt="desk" src="http://linuxien.legtux.org/uploads/images/2012/04/Capture.png">](http://linuxien.legtux.org/uploads/images/2012/04/Capture.png)

J'ai grandement modifié les services qui se lancent au démarrage, afin de gagner quelques secondes au boot (désactivation de Plymouth). Je me suis donc frotté à SystemD, pour la première fois et j'ai été assez étonné du fonctionnement.

**- Enregistrement -**

Pas mal de lecteurs ont suggéré dans les commentaires du second épisode, de faire un enregistrement non seulement vocal mais aussi vidéo. Avec un outil très pratique qui est [RecordMyDesktop](http://recordmydesktop.sourceforge.net/about.php) (je ne suis pas familier avec ffmpeg), je pense réaliser le troisième épisode sur ma Fedora 16 sous XFCE. Vous pourrez ainsi profiter du changement et de la grande réactivité de cet environnement de bureau. Je table comme d'habitude, sur une durée de 15 minutes.

**- Dockstar(s) -**

Si vous suivez le blog (et le [twitter](https://twitter.com/#!/tetedulinuxien/)), vous savez que j'ai mis la main sur un 2nd Dockstar acheté en occasion mais dans un excellent état. Pour la petite histoire, je m'étais acheté un Pogoplug mais le modèle censé être neuf, semblait être déjà utilisé. Je l'ai donc renvoyé.

J'en ai profité pour comme d'habitude y installer une Debian Squeeze dessus. Pourquoi une Debian? Parce que la grande force de cette distrib, est quelle ne nécessite pas de mise à jour fréquente. Elle peut fonctionner de manière stable, tout en étant totalement autonome.

<img class="imgcenter" alt="dockstar" src="http://linuxien.legtux.org/uploads/images/2012/04/dockstar.png">

Les Dockstars me permettent de réaliser pleins d'applications très utiles comme:

  * un serveur d'impression accessible sur le réseau local

  * un monitorage 24h/24 et 7j/j de mon onduleur EATON avec journal/logs

  * un "NAS" logiciel sur lequel je prévoie de brancher mon prochain disque dur externe USB2, qui sera partagé sur le réseau gigabits via un routeur

  * station autonome de téléchargement de fichiers

Actuellement, seul le serveur d'impression et le monitorage onduleur sont actifs et fonctionnels. Je vais mettre en place le reste au fur et à mesure. Vous retrouverez toutes les procédures sur le blog et les configs sur [Github](https://github.com/Ypnose/Dockstar).

En tout cas, j'aime beaucoup "travailler" et tester des choses sur les Dockstars. Il est très intéressant de voir les possibilités offertes (quasiment infinies) par ce matériel.

**- Divers -**

Afin de fournir une connexion internet à mes Dockstars, sans descendre à l'étage inférieur (où se trouve la Box), j'ai paramétré un partage de connexion à partir du PC de bureau (avec IPtables) qui est relié en Wifi vers les périphériques en aval, branchés en Ethernet sur un routeur. Cela fonctionne parfaitement et me facilite la tâche pour mettre à jour mon matériel.

<img class="imgcenter" alt="routeur" src="http://linuxien.legtux.org/uploads/images/2012/04/dir100.jpg">

En parlant de matériel, vous pouvez consulter la page "[Hardware](http://tetedulinuxien.fr/hardware/)", qui liste tout le matériel que j'utilise. Cela peux aider des personnes, qui ne savent pas si tel ou tel matos, est pris en charge.

Pour finir, je me demande si il serait utile ou pas de créer une page Google+, afin de ramener un peu plus de monde sur le blog. Actuellement, je ne dispose pas encore de compte sur Google+, car je ne suis pas très branché réseau social, sauf Twitter que je trouve pratique. Donc, si vous estimez que cela peux être un plus, n'hésitez pas à en faire part dans les commentaires.

Voilà une synthèse des sujets, dont je vais vous parler, dans les prochains mois. J'espère que cela a éveillé votre curiosité et vous a incité à revenir, pour lire des choses intéressantes.

A bientôt, lecteurs!
