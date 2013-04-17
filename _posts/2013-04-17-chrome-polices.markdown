---
layout: post
title: "Chrome et polices: un cauchemar!"
description: 
date: 2013-04-17 16:33:28
categories:
- Avis
- Reflexion
---

Bonjour,

Comme vous l'avez certainement remarqué (pour les lecteurs fidèles), j'ai fait une grosse "mise à jour" de mon design. J'ai décidé de le rendre encore plus simple,
épuré et intuitif. J'ai aussi changé les polices, pour quelque chose de plus harmonieux. On se rapproche donc du design d'une page de livre.  
Les choses se sont corsées quand j'ai du choisir ces polices. Je n'ai pas choisi de polices trop lourdes (n'incluant pas une large gamme de symboles), afin de ne pas
ralentir le chargement des pages.

<figure>
<img alt="police" src="http://linuxien.legtux.org/uploads/images/2013/police.jpg">
<figcaption>Police, qui a dit police?</figcaption>
</figure>

Cependant, il a quelque chose qui m'énerve au plus haut point et j'en avais déjà parlé sur Twitter, il y a quelques mois. Cette chose, c'est le rendu "MADE IN CHROME"
de certaines polices TTF, utiles pour les sites web.  
En effet, certaines polices sont extrêmement mal affichées avec Chrome (j'ai essayé sous Vista et Seven). On se retrouve donc avec des polices aliasées et "craquelées".
J'avais réussi plus ou moins à contourner ce problème, avec la version précédente de mon design, en utilisant une police "grasse". Comble de l'ironie, certaines de
ces polices proviennent de [Google Font](http://www.google.com/fonts).

<figure>
<img alt="chromecrap" src="http://linuxien.legtux.org/uploads/images/2013/goochrome.jpg">
<figcaption>Bravo à Chrome, qui n'affiche pas mon site correctement</figcaption>
</figure>

Bref, je pousse un coup de gueule parce que j'en ai marre. Afin que vous puissiez voir de quoi je parle, voici des images (pas d'aperçus, car les images sont trop nombreuses).
Je vous laisse comparer:

### Windows Vista ###

  * [IE9 + Vista](http://linuxien.legtux.org/uploads/images/2013/IE_Vista_render.png)  
  * [Chrome + Vista](http://linuxien.legtux.org/uploads/images/2013/Chrome_Vista_render.PNG)

### Windows Seven ###

  * [Firefox + 7](http://linuxien.legtux.org/uploads/images/2013/FF_7_render.PNG)   
  * [IE9 + 7](http://linuxien.legtux.org/uploads/images/2013/IE_7_render.PNG)  
  * [Chrome + 7](http://linuxien.legtux.org/uploads/images/2013/Chrome_7_render.PNG)

Mea culpa, car je pensais que ce phénomène était lié à Webkit, mais ce n'est pas le cas. J'ai testé le rendu sur plusieurs navigateurs Webkit et le problème est moins présent.
Par conséquent, si vous utilisez encore Chrome, malgré le fait que ce soit un pur produit Google, avec les abus que cela engendrent et que vous notez un mauvais rendu,
sachez que ce n'est pas par ma faute.  
Je me suis appliqué à écrire un code propre et conforme aux normes, ce n'est pas mon problème si Chrome à décidé, de ne pas faire son travail correctement.

Ce "bug" est plus que récurrent (il existe depuis un moment déjà) et personne ne semble disposé à s'en [occuper](http://code.google.com/p/chromium/issues/detail?id=137692).
Si vous êtes curieux, je vous laisse chercher de votre côté. Mais si vous lancez une recherche sur Google (tiens donc!) avec des termes tels que "chrome font bug" ou "chrome font rendering",
vous vous apercevrez de la situation.  
Aussi dingue que cela puisse paraître, je m'y attendais après les soucis que j'avais rencontré auparavant (même si j'avais un mince espoir).

J'ai une idée pour "contourner" ce problème, mais cela va me prendre du temps supplémentaire, alors que j'aurais pu m'en passer.

Alors, par pitié, les gars de chez Google, pensez aux webmasters / designers et affichez <span style="text-decoration:underline">CORRECTEMENT</span> les polices webs!!
Tout le monde sera heureux et on gagnera du temps.
