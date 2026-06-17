---
layout: default
nav_order: 5
title: Essais réalisés et résultats obtenus
---

## **Essais réalisés et résultats obtenus**

Afin de valider les différentes pièces de la machine, plusieurs prototypes ont été réalisés par impression 3D. Les premières versions des supports ont permis de vérifier les dimensions, les interfaces de fixation ainsi que l'intégration des composants mécaniques et électroniques.

#  Mécanique
Les essais ont consisté à comparer différentes versions des pièces afin d'évaluer leur rigidité, leur facilité d'assemblage et leur compatibilité avec les profilés aluminium, les moteurs et les autres éléments de la structure. Les pièces présentées ci-dessous illustrent les différentes itérations réalisées au cours du projet.
<p align="center">
<img src="https://i.postimg.cc/LssR713Q/Whats-App-Image-2026-06-13-at-13-23-43.jpg)" width="300">
</p>

Différentes versions de supports imprimés en bois pour le dispositif de prehesion 
la piece en bois n'ai pas pu stabilise a structure et cella s'est donc soldé par un echec
<p align="center">
<img src="https://i.postimg.cc/L60VLd0H/Whats-App-Image-2026-06-13-at-13-234.jpg" width="300">
</p>
les pieces on eté revue et ameeliorer en impression impression 3d et cella nous a aussi permis d'integere directement le capteur fin de courses 
<p align="center">
<img src="https://i.postimg.cc/qRkKWQZ1/Whats-App-Image-2026-06-13-at-13-233.jpg" width="300">
</p>
la tete de prehension a ete pensé en suport fixe avec un gros chassis cella ne nous a pas permis d'inrtegrer le deplagement et la rotation des pieces saisis cet option a donc ete un echec 
<p align="center">
<img src="https://i.postimg.cc/90yrM7SX/Whats-App-Image-2026-06-1.jpg" width="300">
</p>
Les résultats obtenus ont permis d'identifier plusieurs améliorations à apporter, notamment le renforcement de certaines zones mécaniques, l'ajout de points de fixation supplémentaires et l'optimisation de la géométrie de certaines pièces pour faciliter leur montage.


Après plusieurs phases de test et de modification, les pièces finales ont répondu aux exigences de résistance, de précision et d'intégration nécessaires au bon fonctionnement de la machine. Ces essais ont également permis de réduire les risques d'erreur lors de l'assemblage final et d'améliorer la fiabilité globale du système.

#  Electronique

Pour commander la pompe et l'électrovanne, nous avons utiliser un module L91105 mais malheureusement qui n'a pas permis le bon fonctionnement de ceux-ci.

![Whats-App-Image-2026-06-17-at-18-14-44.jpg](https://i.postimg.cc/fWFgx0PD/Whats-App-Image-2026-06-17-at-18-14-44.jpg)
1. Pourquoi utiliser le L9110S au début ?
   
Le L9110S est un Double Pont en H. On l'a choisi initialement pour plusieurs raisons :
 * Disponibilité : C'est un composant très commun dans les kits Arduino.
 * Polyvalence : Il possède deux canaux indépendants, ce qui permet de contrôler deux charges (pompe + vanne) avec une seule carte.
 * Interface simple : Il communique très facilement en niveaux logiques avec l'Arduino.
 
2. Pourquoi cela ne fonctionne pas pour le projet ?
   
Le L9110S a atteint ses limites physiques pour plusieurs raisons critiques :
 Le courant d'appel: Au démarrage, une pompe à vide et une électrovanne consomment beaucoup plus de courant que lorsqu'elles sont en régime établi. Le L9110S a une capacité de courant limitée (généralement < 800mA). Le pic de démarrage fait surchauffer, voire griller instantanément la puce.
 Les charges inductives (Force contre-électromotrice) : Contrairement à une LED, une pompe ou une vanne contient une bobine. Quand tu coupes l'alimentation, la bobine décharge une pointe de tension extrêmement élevée (plusieurs centaines de volts). Le L9110S n'a pas de protection interne suffisante contre ces retours de courant, ce qui finit par détruire les transistors du module.
 
3. La solution pour résoudre ce problème

Pour resoudre ce problème, nous avons utiliser des MOSFETs de puissance (type N-Channel) plus Précisement le ZVN4306A avec une diode de roue libre.
Pourquoi c'est mieux :
 * Résistance ultra-faible : Le MOSFET laisse passer quasiment tout le courant. La pompe reçoit les 12.7V réels.
 *  Robustesse : Un MOSFET de puissance peut gérer des courants bien plus élevés et ne craint pas la chauffe comme le petit module L9110S.
 * La Diode de Roue Libre (Crucial) : On ajoute une diode  aux bornes de la pompe/vanne. Elle sert de "soupape de sécurité" qui boucle le courant de retour de la bobine lors de l'extinction, protégeant ainsi tout ton système.

  [![Whats-App-Image-3.jpg](https://i.postimg.cc/hG2qgttZ/Whats-App-Image-3.jpg)](https://postimg.cc/qt6Fx0n2)

# Programmation

* *Génération des pas :* La génération des signaux Step et Dir a été gérée de façon optimisée pour garantir la fluidité sans alourdir le processeur de l'Arduino.
* *Gestion des Servomoteurs :* L'utilisation de la bibliothèque Servo.h a facilité la conversion des angles issus de la vision en signaux PWM.
* *Synchronisation Pneumatique :* L'arrêt de la pompe ne suffisant pas à relâcher la pièce à cause de l'air résiduel, le programme ouvre l'électrovanne juste après l'arrêt de la pompe afin de "casser le vide" instantanément.
  
pour y remedier nous avons mis sur pied une interface grafique afin de controler distintement chaque dospositif pour pouvoir mieux uunifrmioser le deplacement de la machines 

[![interface-graphique.png](https://i.postimg.cc/Cxd2Dshn/interface-graphique.png)](https://postimg.cc/XrSx6Fyn)

## Résultats obtenus

- Validation des dimensions des pièces imprimées.
- Vérification de la compatibilité avec les profilés aluminium.
- Amélioration de la rigidité des supports.
- Optimisation de l'assemblage des composants mécaniques.
- Réduction des risques d'interférence entre les différentes pièces.
- Validation des solutions retenues pour la version finale de la machine.
