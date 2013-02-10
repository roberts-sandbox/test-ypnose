---
date: 2011-11-09 13:09:51
layout: post
title: Logitech Compact K300
description: "Le test de mon nouveau clavier Logitech K300"
categories:
- Avis
tags:
- archlinux
- clavier
- logitech
- terminal
- urxvt
- xorg
---

Une fois n'est pas coutume, je vais vous parler aujourd'hui de hardware et non de software, comme j'ai l'habitude de faire.
Il y a une semaine, j'a décidé de m'acheter un nouveau clavier. Le cahier des charges était: un clavier abordable, compact, bien pris en charge sous GNU/Linux, connecté en filaire (USB). J'ai donc opté pour le Logitech Compact K300.

<!-- more -->

<img class="imgcenter" src="http://linuxien.legtux.org/uploads/images/2011/11/K300.jpg">

En général, les produits Logitech tournent bien et sont reconnus nativement par le système (comme ma G5), et je n'ai pas trouvé de retour catastrophique sur le K300. Petit plus, le clavier dispose de touches "multimédias" bindées sur les Fx (de F1 à F12). Pour les utiliser, on doit passer par la touche "Fn". Voilà qui sera plus qu'utile pour binder mon DWM.

Le clavier fonctionne "Out of the Box" mais j'ai quand même ajouté une règle Xorg. Je vais vous expliquer pourquoi, un peu plus loin.

Pour connaître l'adressage des touches, on passe par "xev" qui signale par exemple : '180 XF86HomePage'. Suffit ensuite, d'aller chercher le fichier appelé 'XF86keysym.h' dans /usr/include/X11/ et on obtient le code à rajouter dans son config.h.

	cat /etc/include/X11/XK86keysym.h | grep XF86XK_HomePage
	#define XF86XK_HomePage 0x1008FF18   /* Display user's home page   */[/sourcecode]


On peut sinon ajouter la ligne '#define XF86XK_HomePage 0x1008FF18' dans son config.h, au lieu de passer directement par le code 0xxxxxxxxx. Mon [config.h](https://github.com/Ypnose/Madfiles/blob/master/dwm/config.h).

Le clavier a une frappe agréable trés proche des laptops (comme mon Dell), les touches ne s’enfoncent pas trop et ne font pas de bruits. Cela rend la frappe plaisante, même si j'ai eu besoin de quelques jours pour m'habituer, car la sensation, est un peu déroutante.

Les touches ne sont pas rétro-éclairées (sauf celles touchant au multimédia) et lorsque vous appuyer sur "Fn", le niveau de l'éclairage augmente sensiblement. Le design du clavier est plutôt joli, avec sur les bords une finition glossy (qui laisse les traces de doigts) assez salissante, malheureusement. Il faudra souvent passer un coup de chiffon.
Ce que j'aime beaucoup, c'est que ce clavier est très compact. Il prend donc moins de place sur le bureau et je n'ai plus besoin de me contorsionner pour écrire.

Maniaque que je suis, j'ai jeté un oeil sur le Xorg.0.log et j'ai trouvé quelque chose d'assez surprenant. Voyez plutôt:

	[  2668.271] (--) Logitech Logitech USB Keyboard: Found 1 mouse buttons
	[  2668.271] (--) Logitech Logitech USB Keyboard: Found scroll wheel(s)

Xorg trouve un bouton de souris sur mon clavier. Effectivement, xinput me retourne aussi un résultat dans "Virtual Core Pointer":

	⎡ Virtual core pointer                 id=2   [master pointer  (3)]
	⎜   ↳ Virtual core XTEST pointer            id=4   [slave  pointer  (2)]
	⎜   ↳ Logitech Logitech USB Keyboard        id=9   [slave  keyboard (3)]
	⎜   ↳ Logitech USB Gaming Mouse             id=10  [slave  pointer  (2)]
	⎣ Virtual core keyboard                      id=3   [master keyboard (2)]
		↳ Virtual core XTEST keyboard           id=5   [slave  keyboard (3)]
		↳ Power Button                          id=6   [slave  keyboard (3)]
		↳ Power Button                          id=7   [slave  keyboard (3)]
		↳ Logitech Logitech USB Keyboard        id=8   [slave  keyboard (3)]


Je ne sais d'où cela vient, sachant que le clavier ne dispose pas d'un touchpad, comme d'autres modèles Logitech. J'ai donc ajouté des options dans mon '10-evdev.conf' pour essayer d'améliorer ce phénomène.
Après moults options et essais, j'ai préféré créer un règle spécifique pour Xorg, plutôt que de modifier le '10-evdev.conf'. J'ai écris un fichier '30-keyboard.conf' et je l'ai placé dans "/etc/X11/xorg.conf.d". Vous pouvez le voir [ici](https://github.com/Ypnose/Madfiles/blob/master/Xorg/30-keyboard.conf).

Dorénavant, xinput affiche les deux périphériques 'Logitech Logitech USB Keyboard' dans 'Virtual Core keboard'. Je trouve ça plus propre qu'avant, même si j'obtiens toujours dans les logs:

	(--) Logitech Logitech USB Keyboard: Found 1 mouse buttons
	(--) Logitech Logitech USB Keyboard: Found scroll wheel(s)
	(II) Logitech Logitech USB Keyboard: Relative axes present but ignored.
	(II) Logitech Logitech USB Keyboard: Absolute axes present but ignored.
	(--) Logitech Logitech USB Keyboard: Found keys
	(II) Logitech Logitech USB Keyboard: Configuring as mouse
	(II) Logitech Logitech USB Keyboard: Configuring as keyboard
	(II) Logitech Logitech USB Keyboard: Adding scrollwheel support
	(**) Logitech Logitech USB Keyboard: YAxisMapping: buttons 4 and 5
J'ai aussi cette petite erreur que je ne sais pas résoudre:

	Logitech Logitech USB Keyboard: failed to initialize for relative axes.

Attention, ma règle n'est pas forcément nécessaire. Le clavier répond bien de base et fait son boulot correctement, j'ai juste appliqué mon '30-keyboard.conf' pour fignoler le tout.

Au final, je donne un joli 4,5 / 5 à ce produit!
