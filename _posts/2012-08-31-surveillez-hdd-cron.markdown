---
date: 2012-08-31 17:46:47
layout: post
title: "Surveiller son HDD avec cron"
description: "Quelques idées pour être sûr que son disque dur ne s'abime pas prématurément."
categories:
- Astuce
- Personnalisation
tags:
- archlinux
- astuce
- fedora
---

Avec le problème des parcages des têtes de disques durs (en grande majorité dans les laptops, mais aussi dans les HDD dit "ECO" ou "GREEN"), il peut être assez intéressant de surveiller que son disque ne s'abime pas prématurément. Effectivement, si ce problème n'est pas repéré assez tôt et corrigé, il est possible que votre matériel rende l'âme en quelques mois, en entrainant la perte pure et simple de vos données.

<!-- more -->

Sachant que mon laptop tournant sous Fedora 17 et comportant un modèle de HDD Hitachi, est concerné par ce phénomène, j'ai essayé d'appliquer un correctif suivi d'un monitorage assez drastique.

<img class="imgcenter" alt="hdd" src="http://linuxien.legtux.org/uploads/images/2012/08/hitachi.jpg">

Avant tout, sachez que je me suis aperçu de ces parcages que très récemment. Depuis un moment, j'appliquais la commande `hdparm -B 254 /dev/sda` par mesure de sécurité, mais un soir j'ai entendu un bruit bizarre sous mon laptop et en consultant de temps en temps la valeur `193 Load_Cycle_Count` avec smartmontools, j'ai directement compris.

Les outils utilisés restent assez basiques mais permettent une surveillance efficace et il est aussi possible d'exploiter ces paramètres (courbe dans tableur).

Cette méthode est fonctionnelle sur Fedora 17 et très certainement sur Arch. Je vais d'ailleurs la mettre en place, dans quelques jours. Cependant, je surveillerai uniquement mon HDD mais je n'appliquerai aucun changements, car je ne peux pas le faire avec le modèle, sur mon Desktop.

<img class="imgcenter" alt="dellaptop" src="http://linuxien.legtux.org/uploads/images/2012/08/laptop.jpg">

Pour commencer, il serait judicieux de baisser la valeur ou même désactiver ce paramètre appelé APM (qui est le responsable). Un bon moyen de rendre la modification permanente et effective après reboot, est de modifier le fichier rc.local et ajouter la commande `hdparm -B 254 /dev/sdx`. Assurez-vous de choisir le bon disque avec `fdisk -l`. La valeur 254 permet de fixer l'APM à la plus basse valeur, mais vous pouvez aussi désactiver ce dernier avec 255.

Comme je l'ai déjà dit, sous Fedora 17, rc.local n'existe pas. Il faut le créer dans le dossier `/etc/rc.d/` et le rendre exécutable.

	#!/bin/sh
	hdparm -B 254 /dev/sdx

À chaque redémarrage, cette valeur sera fixée automatiquement. Faites attention car à chaque mise en veille la valeur de l'APM est de nouveau fixée à 128. Pour moi, c'est d'ailleurs la chose la plus grave. Avec ce qui a été fait, on pourrait croire que c'est réglé, mais ce n'est pas le cas. Sous Fedora 17 (XFCE), pm-utils est l'outil qui permet de mettre le PC en veille (via pm-suspend) mais il est possible que ce soit "systemctl suspend".

Par conséquent, il faut être sûr du logiciel qui est mis en place, sur votre distribution (dans notre exemple, ce sera pm-utils). Si ce n'est pas pm-utils, je vous donnerai un lien pour faire la bidouille avec systemctl.

Afin de fixer cette valeur à chaque sortie de mise en veille, il faut créer une règle pm-utils et la placer dans `/etc/pm/sleep.d`. Pour plus de clarté, je vous conseille d'inclure hdparm dans le nom du fichier. J'ai appelé la règle 50-hdparm_pm avec les lignes suivantes:

	#!/bin/sh
	if [ -n "$1" ] && ([ "$1" = "resume" ] || [ "$1" = "thaw" ]); then
 	hdparm -B 254 /dev/sda > /dev/null
	fi

Ainsi à chaque sortie de mise en veille, la commande est lancé et l'APM est réglé automatiquement.

Pour s'assurer que le disque ne se détériore plus, il y a plusieurs astuces. La première c'est de lancer la mise en veille du système et contrôler le log pm-suspend.log qui se trouve dans `/var/log`. Vous pourrez savoir si votre règle est prise en compte. Cherchez 50-hdparm_pm (ou le nom que vous lui avez donné) dans le log.

Veuillez lancer aussi:

	hdparm -I /dev/sda | grep "Advanced power"

Si l'output correspond à la valeur désirée, c'est que la règle fonctionne. Sur mon Desktop (qui ne supporte pas le changement de l'APM), cela ne me retourne rien.

La seconde méthode consiste à vérifier la ligne `193 Load_Cycle_Count` et tout particulièrement la `RAW_VALUE`. Si vous voyez qu'elle commence à se stabiliser, c'est bon signe. Pour ne plus avoir de doutes possibles, j'ai décidé de lancer à intervalle régulier (via cron) un script qui affichera ces mesures dans un fichier. Je pourrais ainsi examiner l'évolution de mon disque.

J'ai écrit un petit bout de code que j'ai placé dans /etc/cron.d:

	#!/bin/sh
	DATE=$(date '+%A %d %B')
	TIME=$(date '+%R')
	APM=$(/usr/sbin/hdparm -I /dev/sda | grep 'Advanced power')
	PCC=$(/usr/sbin/smartctl -A /dev/sda | grep -i 'Load_Cycle_Count')
	
	echo -e "--> $DATE | $TIME <--"
	echo -e $APM
	echo -e "$PCC\n"
	exit

Je l'ai appelé discp pour "disc power". La variable $PATH est obligatoire, si vous n'ajoutez pas cette ligne, les commandes ne seront pas exécutées. Rendez le script exécutable. Voici le script pour mon Desktop: [ici](https://github.com/Ypnose/Madfiles/blob/master/bin/discd).

Cette étape est je pense la plus intéressante. Vous devez déclarer à quel intervalle ce script sera lancé, via cron. Dans mon cas, j'ai décidé de l’exécuter toutes les 2 heures. Éditez le fichier crontab avec:

	sudo EDITOR=nano crontab -u root -e

J'ai spécifié EDITOR=nano car de base crontab utilise $EDITOR. Sous mon user, j'ai déclaré nano mais pour le root, cela reste vi. J'ai ajouté la ligne suivante:

	0 */2 * * * /etc/cron.d/discp >> /home/my_username/hdd.out

Voici quelques explications: discp est lancé toutes les deux heures (à 10:00 - 12:00 - 14:00), tout les jours de l'année et il redirige le résultat vers un fichier, situé dans mon $HOME. Changez la période en fonction de  vos besoins.

<img class="imgcenter" alt="cron" src="http://linuxien.legtux.org/uploads/images/2012/08/crontab-syntax.gif">

Sur mon Desktop, il sera amorcé un fois par jour à 18h00.

	0 18 * * * /etc/cron.d/discp >> /home/my_username/hdd.out

Sans passer par crontab, vous pouvez placer le script dans le dossier cron.daily, cron.hourly ou cron.monthy. Mais il faudra éditer discp pour rediriger la sortie et vous ne pourrez pas choisir, l'heure de déclenchement. Soyez sûr que le daemon cron est bien lancé au démarrage (ce qui devrait être le cas sur la plupart des distribs).

Encore une fois, le wiki francophone et anglophone d'Arch m'a bien aidé. J'apprends beaucoup grâce aux travail des contributeurs. Un grand merci!

Pour faire la manip avec systemctl (non testé): [https://wiki.archlinux.org/index.php/Systemd#Sleep_hooks](https://wiki.archlinux.org/index.php/Systemd#Sleep_hooks)

Tchao!!

EDIT: Ajouté le script pour mon Desktop (sans la prise en charge APM).
