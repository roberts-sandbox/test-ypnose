---
layout: post
title: "Pourquoi Archlinux est-elle si efficace?"
description: "Mon avis sur cette distribution et aussi sur d'éventuelles alternatives."
date: 2013-02-27 13:30:16
categories:
- Libre
- Avis
- Reflexion
---

Bonjour,

Cette question, je me la suis posé un bon nombre de fois et pour moi c'est finalement assez clair. La réponse est en même temps simple et compliqué. Pourquoi?  
Simplement parce que   
Finalement, je me suis aperçu que je reste accroché ou "aimanté" à cette distrib'. Il y a quelques semaines, je suis parti à la recherche d'une alternative solide et cela n'a pas été si facile.  
Entre les distributions "Source-based", les minimalistes et les autres, le choix n'est pas simple.

<figure>
<img alt="tux question" src="http://linuxien.legtux.org/uploads/images/2013/tux_ask.png">
<figcaption>Même le Tux est perdu...</figcaption>
</figure>

[Slackware](http://www.slackware.com/) a très vite retenu mon attention. Effectivement, je connaissais uniquement le nom mais je n'avais jamais essayé cette dernière. Elle est mythique et elle
possède aussi des avantages non-négligeables: une stabilité à toutes épreuves, une configuration KISS, un installateur assez complet et des paquets plutôt récents. Le gestionnaire de paquet (ici slackpkg) ne gère pas les
dépendances, mais ce n'est en aucun cas un problème. Cela permet une gestion plus fine des paquets. Cependant, j'aurais aimé une installation différente car si l'on veut un système minimal
comme avec Arch (seul base + base-devel), on doit bidouiller les [tagfiles](http://slackwiki.com/Tagfile_Install) afin de choisir les paquets à installer.  
Mais c'est après que le bât blesse selon moi, car lorsque vous mettez à jour votre système, tout les paquets ajoutés récemment sur le dépôt vous sont proposés pour l'upgrade. Même ceux que vous n'avez pas installé.
Par exemple, si je n'installe que le strict minimum (kernel + coreutils + network) et que j'update ma machine, les paquets KDE, xfce et Gnome vont être ajoutés à cette mise à jour.  
On peut éviter ce phénomène en "blacklistant" les paquets non-installés (par groupes) mais je trouve ça beaucoup trop contraignant, car il est fort probable que des paquets soient omis.
Et c'est bien dommage, car Slackware est très agréable à utiliser, d'autant plus que les Archers ne sont pas dépaysés.

