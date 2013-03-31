---
date: 2012-05-01 11:22:00
layout: post
published: false
title: "Accélérer le boot sous Fedora 16"
description: "Des optimisations pour réduire le temps de démarrage de votre PC, tournant sous Fedora."
categories:
- Astuce
- Conseil
tags:
- astuce
- fedora
---

Salut,

Encore un article sur Fedora 16, cela signifie qui n'y aura pas d'Archlinux aujourd'hui (mais ce n'est que partie remise).

Fedora 16 me satisfait vraiment beaucoup, actuellement je n'ai pas trouvé mieux en distrib non-minimaliste, pour mon laptop. Cependant, cette dernière nécessite quelques ajustements pour obtenir un résultat quasi-parfait. J'avais déjà traité dans un précédent article, de tweaks au niveau du combo CPU / GPU / RAM. Maintenant, je vais vous parler du boot.

<!-- more -->

Pour moi, c'est un peu le seul point noir de cette Fedora, car effectivement beaucoup de "services" (ils sont appelés comme ça, au niveau de SystemD) sont lancés par défaut au démarrage, alors qu'ils ne sont même pas utilisés (je pense à sendmail). Il faut donc les désactiver et ainsi on peux gagner quelques secondes. Pour le tutoriel, j'ai réactivé les services fautifs que j'avais précédemment enlevé. J'expliquerai aussi comment enlever Plymouth, pour ceux qui le souhaite.

Cet article devrait aussi fonctionner avec les distributions qui utilisent SystemD.

**- Services -**

Donc on allume notre PC, on espère que le boot sera long et quand vous vous êtes logué en graphique, vous lancez dans votre terminal favori, la commande:

	systemd-analyze blame

Et là, on voit nettement quels sont les services qui prennent le plus de temps à s'initialiser, plus la valeur est haute, plus le service met du temps à être fonctionnel:

	60201ms sendmail.service
	22955ms iscsi.service
	10545ms udev-settle.service
	9069ms fedora-loadmodules.service
	8537ms var-lib-nfs-rpc_pipefs.mount
	8120ms systemd-vconsole-setup.service
	5353ms fedora-readonly.service
	4258ms udev-trigger.service
	3131ms media.mount
	3051ms mdmonitor-takeover.service
	3000ms sys-kernel-debug.mount
	2993ms dev-mqueue.mount
	2992ms sys-kernel-security.mount
	2991ms dev-hugepages.mount
	2981ms udev.service
	2759ms remount-rootfs.service
	2757ms systemd-remount-api-vfs.service
	2345ms systemd-sysctl.service
	786ms fedora-storage-init.service
	410ms NetworkManager.service
...

Dorénavant, il suffit de désactiver ces services (faites attention à ne pas en avoir besoin). Je sais que sendmail est utilisé par Thunderbird, mais je n'en suis pas à 100% sûr. Dans mon cas, j'ai juste touché aux services sendmail et iscsi et ça a suffit pour gagner environ 3 à 4 secondes.

[<img class="imgcenter" alt="systemd1" src="http://linuxien.legtux.org/uploads/images/2012/05/screen.png">](http://linuxien.legtux.org/uploads/images/2012/05/screen.png) Avant le "tweak"

On doit user de la commande systemctl pour faire le ménage dans ces services. J'ai donc procédé comme ceci:

	sudo systemctl disable votre_service.service

Dans mon cas:

	sudo systemctl disable iscsi.service
	sudo systemctl disable sendmail.service

Faites de même avec les services qui vous posent problèmes. Voilà de précieuses secondes gagnés lors du boot. Je dois dire que c'est assez agréable.

[<img class="imgcenter" alt="systemd2" src="http://linuxien.legtux.org/uploads/images/2012/05/screen2.png">](http://linuxien.legtux.org/uploads/images/2012/05/screen2.png) Après le "tweak"

** - Plymouth -**

Plymouth est l'écran qui est affiché lors du chargement de Fedora 16, où on voit le logo Fedora qui se remplit au fur et à mesure que votre système charge, pour enfin afficher le logo final quand tout est terminé.

<img class="imgcenter" alt="plymouth" src="http://linuxien.legtux.org/uploads/images/2012/04/plymouth.png">

Sachant que certains l'aiment et d'autres non, je vais expliquer comment l'enlever. De mon côté, je l'avais désactivé puis je l'ai réactivé peu après, car finalement je trouve ça joli. Donc, éditez votre fichier de configuration GRUB2, avec la commande:

	sudo nano /etc/default/grub

Vous devriez obtenir quelque chose de la forme:

	GRUB_TIMEOUT=5
	GRUB_DISTRIBUTOR="Fedora"
	GRUB_DEFAULT=saved
	GRUB_SAVEDEFAULT=true
	GRUB_CMDLINE_LINUX="rd.md=0 rd.lvm=0 rd.dm=0 quiet SYSFONT=latarcyrheb-sun16 rhgb rd.luks=0  KEYTABLE=fr-pc LANG=fr_FR.UTF-8"

Enlevez le paramètre "rhgb" et Plymouth aura disparu au prochain redémarrage. Vous noterez aussi que j'ai rajouté la ligne "GRUB_SAVEDEFAULT", qui permet d'enregistrer le choix fait dans GRUB2 et de le mettre par défaut.

Ce n'est pas fini, maintenant vous devez update le grub.cfg, avec la commande:

	sudo grub2-mkconfig -o /boot/grub2/grub.cfg

Voilà, vous pouvez "reboot" votre ordinateur, en espérant que vous ayez gagné des secondes, bien évidemment.

Bye.
