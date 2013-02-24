---
date: 2011-04-01 11:11:39
layout: post
title: Faille de sécurité Linux
description: "Encore une nouvelle faille, on commence à en avoir marre."
categories:
- News
---

Il y a quelques jours, une faille GNU/Linux a été découverte. Il était possible de rendre le système instable en insérant une lib trafiquée par un utilisateur malicieux. On peux s'en rendre compte en testant le MD5 de cette lib. Par exemple:

	echo libjpeg.so.8.0.2 | openssl md5  --> 0e3d683efa9f5500c55bd413eb13ba64

La vrai somme: 7174bdd52a1dab26e2d5c55051221154

<img class="imgcenter" alt="gnutux" src="http://linuxien.legtux.org/uploads/images/2011/04/gnulinux.jpg">

Si cet utilisateur réussi donc à mettre la lib dans /usr/lib, il pourra effectuer des opérations non permises comme la modification du nom d'hôtes, de l'utilisateur root et de bien d'autres choses touchant à l'administration. Je vous conseille donc de tester les libs qui semble suspectes. Les développeurs ont confirmés un correctif dans les heures qui viennent.
