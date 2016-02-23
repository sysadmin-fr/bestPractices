---
categories: [monitoring,performance]
title: Observer les performances sous Linux
--- 

# Observer les performances sous Linux

> <xxx> une saturation est indicateur d'un bon usage des ressources, ce n'est pas un problème en soi.

## packages

* sysstat

## Commandes

### iostat 

> iostat -x 1

le 1 indique un refresh de 1 seconde

* ne pas regarder la load, ni la colonne svc time de iostat
* tant que y a de la ram free, c'est que la machine a trop de ram
* colonne await : un disque pas chargé tourne à quelques dizaines de milli secondes
* %util : c'est le pourcentage du temps pendant lequel le disque a au moins une io pendante; tout les disques moderne sont capable de traiter plusieurs IO en parallèle, tant que c'est pas 100% c'est que le disque n'est pas à fond, c'est comme free en ram

> iostat -x  5, avgqu-sz

le nombre d'IO en attente pour voir si t'as pas une IO coincé

**Disques durs**
* cpu wait c'est poubelle
* wait time, c'est le temps de réponse moyen d'une IO


### vmstat

> vmstat 1

le 1, c'est depuis le début des temps depuis le boot plutôt donc ça inclut les périodes creuses

* le manque de ram se regarde sur si/so1("swap in / swap out") dans vmstat


## outils

FIXME sar/cacti/jrds/collectd

### Tool maps
[![schemas](/bestPractices/images/linux_observability_tools.png "Linux Performance Observability Tools")](/bestPractices/images/linux_observability_tools.png) \\
source: <http://brendangregg.com/linuxperf.html>
