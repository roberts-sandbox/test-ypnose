---
layout: post
title: "2013: l'année du changement"
published: false
description: "La nouvelle année apporte de nombreux changements."
date: 2013-01-11 13:33
categories:
- News
- Avis
- Libre
tags:
- archlinux
- bilan
---

Salut les lecteurs,

Pour commencer, je vous souhaite une bonne et heureuse année 2013.

Ce titre illustre parfaitement ce qu'il va se passer pendant cette année, je vais donc essayer de faire une sorte de récapitulatif et aussi un petit bilan de l'année 2012.  
Comme vous l'avez remarqué, j'ai complètement changé mon site. J'ai quitté Wordpress pour [Octopress](http://octopress.org/), sans le moindre remords, à cause de tout un tas de raisons. Wordpress est beaucoup trop lourd pour mon utilisation et chaque mise à jour, renforce
l'idée que c'est une usine à gaz. Je cherchais aussi quelque chose de minimaliste (dans le bon sens du terme) et je suis tombé sur Octopress. <!-- more -->
Octopress est un framework pour le mythique [Jekyll](http://jekyllrb.com/), qui facilite donc la mise en œuvre d'un blog. Jekyll (et par conséquent Octopress) génère de simples pages web statiques, grâce à des fichiers utilisant la syntaxe markdown.
Tout est géré via [Git](http://git-scm.com/). On reste donc dans l'aspect [KISS](http://fr.wikipedia.org/wiki/Principe_KISS), qui est si cher à mes yeux. Autre point qui m'a conquis, c'est que je n'ai plus besoin de PHP et MySQL, l'hébergement ne nécessite donc rien de bien puissant. Cela me permet aussi de réfléchir
à une éventuelle évolution (auto-hébergement avec Dockstar / Raspberry ?).

<img class="imgcenter" alt="octopress" src="http://linuxien.legtux.org/uploads/images/2013/articles/octopress.png">

Question légèreté, j'avais déjà été tenté par [PluXml](http://www.pluxml.org/) (CMS sans BDD), il y a quelque mois. Cependant, j'avais fait machine arrière, car il était question que je perde mes "précieux" commentaires. Effectivement, j'accorde beaucoup d'importance aux liens auteur / lecteurs.
Toutefois,  j'ai décidé de sauter le pas, sans exporter les commentaires. Pourquoi? Simplement, parce que cela est trop contraignant. L'export des articles et des pages a été relativement facile, même si j'ai dû modifier la mise en page effectuée
par Wordpress et les liens vers les images (merci [sed](http://www.grymoire.com/Unix/Sed.html)); cela m'a finalement pris du temps de rattraper les erreurs de Wordpress. Je n'ai pas exporté les commentaires, car Octopress et Jekyll ont besoin d'applications externes comme [Disqus](http://disqus.com/) pour les
afficher. Ceci est contraire à ma philosophie et puis ce n'est pas comme ci j'avais 25 commentaires par jour, je peux m'en passer.

<img class="imgcenter" alt="KISS" src="http://linuxien.legtux.org/uploads/images/2013/articles/kiss.gif">

Le thème affiché est une modification de celui de base. Je me suis dirigé vers un design ultra-minimaliste. Au final, je suis vraiment satisfait du résultat actuel. C'est clair, simple et parfaitement lisible. Nous n'avons pas besoin de plus.
Plutôt que d'afficher une "sidebar", j'ai décidé de placer les liens importants dans des pages ou les afficher dans le bas de la page principale. N'hésitez pas à jeter un œil à ces pages / liens.

### Retrospective 2012 ###

Cette année 2012 aura été une année relativement riche, puisque j'ai réalisé 3 enregistrements (deux vocaux et un avec une vidéo). C'était une chose que je souhaitais développer et je pense m'en être plutôt bien sorti. J'ai aussi écrit 10 articles.
Ce nombre n'est pas particulièrement important, mais je préfère privilégier la qualité à la quantité. Je rédige mes articles, en essayant de penser à l'intérêt que cela peut susciter, et surtout je le fais sans me forcer.
Je pense "signer" encore pour un an au minimum, après je ferai mon choix en décidant ou pas, d'arrêter ce site et jeter l'éponge. Dans le pire des cas, je me limiterai aux 140 caractères pour exprimer et partager mes idées (cf [Twitter](https://twitter.com/tetedulinuxien)).

### 2013 commence... ###

*Fedora 18*

Depuis début Décembre, j'attends avec impatience la nouvelle mouture de Fedora 18. La sortie a été repoussée de deux mois au total, mais elle arrivera le 15 Janvier 2013. Sachant, que je n'ai pas été capable d'attendre la release pour l'essayer, j'ai
installé la version Beta mi-Décembre. Le résultat est quasiment parfais. Je suis passé par [BFO](http://boot.fedoraproject.org/) pour l'installer, c'est une sorte de netinstall, avec laquelle on peut choisir les versions de Fedora (même les plus anciennes).  
La nouvelle version de l'installateur [Anaconda](http://fedoraproject.org/wiki/Anaconda) est déroutante, surtout quand on est habitué aux anciens installateurs. Dorénavant, il n'y pas d'ordre pour les différentes étapes (partitionnement, fuseau horaire),
vous êtes juste obligé de paramétrer toutes les options, avant de pouvoir commencer l'installation. D'ailleurs, j'ai remplacé le miroir par défaut pour un autre situé en Allemagne, car l'installation avait un bug avec ceux inclus automatiquement.

[<img class="imgcenter" alt="anaconda" src="http://linuxien.legtux.org/uploads/images/2013/articles/fedora-18.png">](http://linuxien.legtux.org/uploads/images/2013/articles/fedora-18.png)

J'ai d'abord choisi [MATE](http://mate-desktop.org/) que j'attendais beaucoup, mais je n'ai pas été convaincu par ce dernier, donc je suis retourné sous Xfce 4.10. Les changements sont les bienvenus, comme par exemple le remplacement de GDM par [lightDM](https://launchpad.net/lightdm)
(ce qui évite donc des dépendances GNOME presque inutiles) ou encore le dossier /tmp monté automatiquement en tmpfs. Même en passant par BFO, j'ai désinstallé quelques logiciels inclus de base comme Pragha, car je sais pertinemment que je n'allais pas les utiliser.

J'ai été bluffé par la stabilité de l'ensemble, alors que nous sommes pas encore en stable. À part un ou deux bugs (dépendances manquantes avec xfce4-power-manager, par exemple), tout est parfait.
Autre point positif, yum semble moins poussif que dans Fedora 17, mais selon moi, on reste encore loin de la rapidité d'un pacman. Soulignons que yum possède une fonctionnalité intéressante, qui permet de télécharger les paquets parallèlement. Plus besoin
d'attendre qu'un paquet soit téléchargé, pour commencer le suivant.
Au quotidien, cette Fedora est très agréable, ça répond au quart de tour et je suis comme un poisson dans l'eau. Comme d'habitude, j'ai fait des réglages de systemd (désactiver des services au démarrage, ajout de services / tmpfiles personnels). J'ai aussi
créé une sauvegarde de la racine avec dd (j'adore ce soft). Je vous conseille grandement cette distribution, que j'apprécie énormément depuis la version 16.

*Migration FreeBSD, début...*

Je pense profiter de cette nouvelle année pour sérieusement me lancer dans l'univers BSD et plus particulièrement FreeBSD. Je suis motivé par plusieurs choses comme la curiosité et l'envie de tester un OS différent, mais pas uniquement. D'autres points
commencent à peser lourd sur la balance. Durant cette année, ça va pas mal bouger dans l'écosystème Linux. Peut-être que vous l'ignorez mais le successeur de X (presque 30 ans d'âge) arrive à grands pas et il s'appelle [Wayland](http://wayland.freedesktop.org/).
On pourrait se réjouir, mais malheureusement tout n'est pas rose.

<img class="imgcenter" alt="wayland" src="http://linuxien.legtux.org/uploads/images/2013/articles/wayland.png">

*Premier point*, actuellement Wayland utilise [KMS](http://fr.wikipedia.org/wiki/Kernel-based_mode-setting) ce qui implique donc, que seuls les drivers libres sont capables de supporter Wayland. Ne nous mentons pas, même si les drivers libres sont de bonne qualité (j'utilise moi-même le radeon libre avec mon laptop), au niveau de
l'accélération 3D, on est loin du niveau des drivers privateurs. Dans mon cas, je dispose d'un GPU NVidia GTX 460, je suis donc obligé d'utiliser ce driver "officiel". Pourquoi? Je joue à une poignée de jeux sous GNU/Linux, qui ont besoin de la 3D. Il est donc impossible
pour moi de passer sous Nouveau. Ou alors, ma GTX 460 ne me sers plus à rien. Et apparemment, NVidia ne semble pas bien pressé de sortir un driver qui supporte Wayland. Qui se retrouve coincé? LE POWER USER!  
Si les fabricants de GPU (actuellement seul NVidia est concerné) décident dans quelques années, de sortir leurs drivers sous Wayland, que se passera-t-il de BSD avec leur X? Plus aucuns drivers?

*Second point*, cela va rendre obsolète un nombre incroyable de programmes. Je pense surtout aux WM minimalistes comme Xmonad, Awesome, Dwm ou Openbox. Ils auront besoin d'être écrit de nouveau. Vous pourriez aussi me dire, que Wayland permet de lancer un serveur X, afin de faire
tourner des applis, pour ainsi assurer une certaine compatibilité. Oui, c'est vrai, mais cela à ses limites et c'est plus une solution de contournement qu'un véritable tournant. Ainsi, pour certains programmes (comme ceux cités avant), je pense qu'il est préférable de les porter
sur Wayland. Cependant, les devs ne semblent pas particulièrement chaud, et ça pourrait se comprendre.

*Troisième point*, comme je l'ai expliqué plus haut, Wayland à besoin de KMS et sous \*BSD, on n'a pas encore de KMS. Les devs sont en train de s'en occuper, mais le projet n'est pas encore fini. Quel plaisir de pouvoir trouver son logiciel favori
sous BSD, simplement parce les standards [POSIX](http://fr.wikipedia.org/wiki/POSIX), ont été respectés. Et alors, on en fait quoi de POSIX? Actuellement, on dirait que c'est la mode de bouder POSIX et par conséquent cela entraîne une limitation.
Je pense en particulier à systemd, qui n'est pas portable sur BSD car il utilise des fonctions internes au kernel Linux. Et c'est même le développeur principal de systemd, aka [Lennart Poettering](http://linuxfr.org/users/patrick_g/journaux/linux-ou-posix) qui s'en vante.
C'est du beau! Cette philosophie ne me plaît pas du tout et me révolte.

<img class="imgcenter" alt="xorg" src="http://linuxien.legtux.org/uploads/images/2013/articles/xorg.png">

Notez que je ne suis pas le genre de personne à troller, sinon je me serais bien amusé avec l'adoption de systemd, sur "presque" toutes les distribs grands publics (cf débat systemd / Arch). D'ailleurs, notre ami Lennart Poettering ne comprends pas pourquoi, Ubuntu exploite [Upstart](https://plus.google.com/115547683951727699051/posts/X3fUhyJREKq)
au lieu de systemd. Et encore, je ne parle pas des propos calomnieux, suite au fork de udev, par les devs de Gentoo.  
Je déplore grandement cette manie qu'ont les devs Red Hat, à imposer leurs logiciels et leurs conventions à tout l'écosystème Linux. systemd, Wayland et ensuite quoi? Je ne nie pas que X à besoin d'être remplacé, mais je n'aime pas la manière.

Quelques [articles](http://linuxfr.org/news/x-org-est-mort-vive-wayland) assez [instructifs](http://linuxfr.org/users/sinma/journaux/linux-only-et-bsd).

*Et fin.*

Il y a d'autres news qui ne me rassurent pas et qui m'inquiètent même. Vous ne le savez peut-être pas, mais Valve va sortir une console appelé Steambox, basée sur un noyau Linux (je savais que le client natif n'était pas un cadeau fait aux Linuxiens, mais plutôt un projet caché de Valve).
Inévitablement, cela aura pour objectif de "populariser" GNU/Linux. Tous les Windows "haters" et les missionnaires linuxiens vont être aux anges. Plusieurs choses: je suis totalement contre cette politique, qui consiste à "convertir" le plus d'users possible. Convertir n'est pas tout, il
faut comprendre les fondements et la philosophie générale. J'ai d'ailleurs été très heureux quand j'ai appris dernièrement que des personnes dans mon entourage, utilisent Ubuntu en connaissant les grandes lignes. Comme quoi, comprendre ce dont on profite, ce n'est pas si compliqué...   
Par ailleurs, je me pose des questions à propos du modèle économique qui sera adopté, car j'ai des difficultés à imaginer comment on va concilier GNU/Linux et machine à fric. Que va dire RMS à ce sujet (même si j'ai ma petite idée)? Mon sentiment sur ce sujet est assez explicite, mais
j'ai la nette impression que ce noyau (qui est à disposition de tous) est parfois exploité de façon abusive.

Ainsi, vous vous doutez que notre OS favori va devenir "en vogue" (avec une bonne partie d'users, qui ne s'occupe pas des principes). N'est-ce-pas le déclin, qui est en marche? Beaucoup essaient d'enlever ou oublient volontairement GNU de Linux, et il semblerait que cela fonctionne dans l'esprit général.  
Je ne supporterai pas de voir GNU/Linux, comme un produit grand public et formaté. J'ai une peur maladive en pensant à ce que pourrait devenir cet OS, si nous ne défendons pas l'éthique et si nous laissons faire n'importe quoi, n'importe comment...

<img class="imgcenter" alt="BSD" src="http://linuxien.legtux.org/uploads/images/2013/articles/bsd.jpg">

C'est pourquoi la famille des BSD me tente de plus en plus. Je vois BSD comme un concept qui s'assume, c'est-à-dire qu'il n'y a pas cette volonté de ramener le plus de gens possibles, ou de devenir l'alternative à DOS. L'OS est là, avec ses qualités et ses difficultés, seuls la passion et la soif
de découverte motivent le changement. C'est un peu ce que je reproche à GNU/Linux, qui cherche désespérement à s'affirmer et à avoir sa place (alors que c'est déjà le cas). Nous pourrions être 1000 dans le monde, ça ne changerai rien aux qualités...  

Certes, l'apprentissage ne sera pas facile (même si la doc est très riche), mais je pense en être capable. Certains pourront me dire, que BSD n'est pas forcement un exemple, où la license générale est plus permissive que la GPL, celà ne m'empèchera pas de toujours soutenir mes idées. J'ai hâte
de découvrir ce monde, qui me paraît immensément riche et intéressant. Voilà mon but et mon envie.

J'ai exposé mes opinions, en argumentant avec des exemples concrets. Libre à vous, d'avoir un avis différent sur la question, par contre je vous demande de respecter le mien. Si vous êtes en désaccord, je vous encourage à me le faire savoir via le formulaire ou via Twitter. Si au contraire, vous
partagez ce point de vue, je vous invite à propager cet article.  
Pour finir, j'ai me suis vraiment appliqué à l'écrire et j'espère que vous vous en rendrez compte.

À bientôt

Ypnose
