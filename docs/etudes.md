---
layout: default
nav_order: 4
title: Études et choix techniques
---

## ÉTUDE ET CHOIX TECHNIQUE

## I. Cahier des charges – Projet Puzzle Bot
## 1. Contexte

Ce projet s'inscrit dans une démarche d'apprentissage en ingénierie mêlant mécanique, électronique, informatique et vision par ordinateur.

## 2. Objectif

Développer un système automatisé capable de :

* Détecter les pièces d'un puzzle à l'aide d'une caméra.
* Identifier leur position et leur orientation.
* Déterminer leur emplacement dans l'image finale.
* Manipuler les pièces avec précision.
* Assembler progressivement le puzzle sans intervention humaine.
## 3. Besoins fonctionnels
Fonction principale:
* Résoudre automatiquement un puzzle à partir de pièces disposées sur une zone de travail.

Fonctions secondaires:
* Acquérir des images du plateau.
* Traiter les images pour identifier les pièces.
* Déplacer un outil de préhension sur les axes X et Y.
* Saisir et déposer les pièces avec précision.
* Contrôler les moteurs et les capteurs.
* Permettre le démarrage et l'arrêt du système.
## 4. Contraintes techniques
Mécaniques
* Structure rigide et stable.
* Déplacement précis sur l'ensemble de la zone de travail.
* Système de préhension adapté aux pièces de puzzle.
Électroniques
* Utilisation d'une carte de contrôle (Arduino ou équivalent).
* Alimentation sécurisée.
* Communication entre les différents modules.
Informatiques
* Développement d'un programme de contrôle.
* Utilisation d'algorithmes de vision par ordinateur.
* Interface de configuration et de supervision.
## 5. Performances attendues
* Précision de positionnement 
* Détection fiable des pièces 
* Fonctionnement continu sans intervention humaine.
* Assemblage progressif et reproductible.
## 6. Sécurité
* Protection des parties mobiles.
* Arrêt d'urgence accessible.
* Alimentation électrique sécurisée.
* Respect des règles de sécurité du MakerSpace.
## 7. Livrables
* Modèle CAO complet sur Onshape.
* Schémas électroniques.
* Code source documenté.
* Documentation technique.
* Poster de présentation.
* Vidéo de démonstration.
* Prototype fonctionnel.

# II. Choix techniques de conception

## 1. LA MÉCANIQUE
Les choix techniques concernant la conception de notre machine ont été réalisés de manière progressive après l'identification des différents besoins du projet ainsi que des contraintes liées aux mouvements, à la précision de positionnement et à l'intégration des composants mécaniques et électroniques.

## Structure mécanique

Le châssis principal est constitué de profilés en aluminium, offrant à la fois rigidité. De nouveaux pieds supports ont été conçus afin de surélever le plateau de travail. Cette modification permet le passage des éléments de transmission et facilite le déplacement des différents axes de la machine.

![PLATEAU SUPPORT](https://i.postimg.cc/3RSTy2yG/Whats-App-Image-2026-06-13-at-19-49-20.jpg)

## Système de déplacement

Le déplacement suivant l'axe X est assuré par un moteur pas à pas. Le système est composé de deux rails latéraux reliés entre eux par un profilé aluminium et une barre métallique. Cette barre est directement couplée à l'arbre moteur à l'aide de deux coupleurs d'arbre, garantissant une transmission synchronisée du mouvement sur l'ensemble de l'axe.

![PLATEAU SUPPORT](https://i.postimg.cc/V66NHfnX/Capture-d-ecran-2026-06-13-200141.png)

## Tête de préhension

La tête de préhension a été conçue pour assurer la manipulation et le positionnement des pièces du puzzle. Elle comprend :
- Un système pignon-crémaillère permettant le déplacement vertical de la ventouse.
- Un support orientable pour la ventouse afin d'ajuster l'orientation des pièces.
- Un support pour la pompe à vide et l'électrovanne assurant la préhension des pièces.
- Un moteur pas à pas permettant le déplacement de la tête suivant l'axe Y.

![PLATEAU SUPPORT](https://i.postimg.cc/NMH0wNCz/Capture-d-ecran-2026-06-13-200542.png)

Cette conception permet de saisir, déplacer et positionner les pièces avec précision sur la zone d'assemblage.

## Boîtier électronique

Un boîtier électronique a été conçu pour regrouper et protéger l'ensemble des composants de commande. Il comprend :

- Un support pour le bouton d'arrêt d'urgence.
- Un support pour la carte de contrôle.
- Un support pour les capteurs de fin de course.
  
 ![PLATEAU SUPPORT](https://i.postimg.cc/4dmW4cph/Capture-d-ecran-2026-06-13-200942.png)
 
 
Un support dédié au profilé de maintien de la caméra ainsi qu'à son système de fixation.

 ![PLATEAU SUPPORT](https://i.postimg.cc/Z5bFK3S0/Capture-d-ecran-2026-06-13-201106.png)
 
Cette organisation facilite le câblage de l'ensemble du système.

##  2.l'ÉLECTRONIQUE 

## Électronique : Choix Techniques 

L'électronique du robot Puzzle-Bot a été pensée pour répondre à trois besoins simples : bouger avec précision, gérer l'aspiration des pièces, et garantir la sécurité de tous. 

### 1. Le "Cerveau" du robot (Arduino Uno + CNC Shield)
* *Notre choix :* Un Arduino Uno (carte très classique) sur lequel on a clipsé une carte d'extension appelée "CNC Shield".
* *Pourquoi ce choix ?* L'Arduino est amplement suffisant pour recevoir des ordres simples de l'ordinateur et piloter les moteurs. Le CNC Shield agit comme une grosse "multiprise" bien rangée. Au lieu d'avoir un plat de spaghettis de fils partout, cette carte permet de brancher proprement les moteurs et les capteurs. Si une pièce grille, on peut la remplacer en quelques secondes.

 ![PLATEAU SUPPORT](https://i.postimg.cc/jS7zdr3K/Capture-d-ecran-2026-06-13-212453.png)
### 2. Le contrôle des mouvements (Drivers A4988)
* *Notre choix :* Des petits modules appelés "A4988" pour piloter les moteurs.
* *Pourquoi ce choix ?* Ces modules servent d'intermédiaires entre le cerveau (l'Arduino) et les moteurs. Ils ont deux gros avantages : 
  1. On peut régler précisément l'énergie envoyée aux moteurs pour éviter qu'ils ne surchauffent.
  2. Ils permettent de diviser les mouvements des moteurs en "micro-pas". Cela donne des déplacements très fluides et très précis, ce qui est indispensable pour emboîter des pièces de puzzle.
 ![PLATEAU SUPPORT](https://i.postimg.cc/cCtJMd8P/Capture-d-ecran-2026-06-13-212329.png)
### 3. La gestion de l'aspiration (Carte sur mesure plutôt que des relais)
* *Notre choix :* On a fabriqué notre propre petite carte électronique (avec des composants appelés MOSFETs) au lieu d'acheter des interrupteurs automatiques classiques (relais).
* *Pourquoi ce choix ?*Tout d’abord, nous avons remarqué que notre alimentation de 12.7 V était très importante pour la pompe. Pour éviter de griller la pompe, nous avons du fabriquer une carte électronique afin de commander les mosfets pour le bon fonctionnement de système d’aspiration. Ensuite, nous avons également fait ce choix pour lâcher la pièce de puzzle au bon endroit, la vanne doit s'ouvrir instantanément. Les relais mécaniques sont trop lents et finissent par s'user. Nos composants (MOSFETs) fonctionnent comme des interrupteurs ultra-rapides et silencieux. De plus, on y a soudé des composants de protection (diodes) car les pompes créent des chocs électriques quand on les éteint, ce qui pourrait griller notre circuit.
 ![PLATEAU SUPPORT](https://i.postimg.cc/qMT2jFjY/Whats-App-Image-2026-06-13-at-21-59-52.jpg)
### 4. Deux circuits électriques séparés
* *Notre choix :* On utilise deux alimentations totalement séparées.
* *Pourquoi ce choix ?* C'est une question de stabilité. On a séparé l'énergie en deux circuits :
  * Un petit circuit "calme" (USB) pour le cerveau (l'Arduino).
  * Un gros circuit "musclé" (Batterie 12,7 V) pour les moteurs et la pompe.
  Si tout était sur le même circuit, l'effort soudain d'un moteur ou de la pompe ferait chuter le courant et ferait redémarrer ("planter") l'Arduino. En séparant les deux, le cerveau reste protégé des variations d'énergie.

### 5. Le bouton d'Arrêt d'Urgence
* *Notre choix :* Un bouton "d’arrêt d’urgence" qui coupe physiquement le fil du gros circuit (12,7 V).
* *Pourquoi ce choix ?* On ne fait pas confiance au code pour la sécurité ! Si on avait programmé l'arrêt dans l'Arduino et que celui-ci "plante", le bouton ne servirait à rien. En coupant directement le fil d'alimentation général des moteurs, on est certain qu'appuyer sur le bouton arrêtera tout, quoi qu'il arrive dans l'ordinateur.
 ![PLATEAU SUPPORT](https://i.postimg.cc/Dwx8Tpnv/bouton-AU.jpg)

### 6. Le choix des moteurs (Pas à pas et Servomoteur)
* *Notre choix :* Des moteurs "pas à pas" (NEMA 17) pour déplacer le bras sur la table, et deux petits "servomoteurs" (MG996R) pour tourner la pièce de puzzle et le deuxième qui permet le mouvement de translation de la ventouse pour qu’il puisse aller chercher la pièce.
* *Pourquoi ce choix ?* * *Les moteurs pas à pas :* Ils tournent cran par cran (comme les aiguilles d'une montre). En comptant le nombre de crans envoyés, l'ordinateur sait exactement à quel endroit de la table se trouve le robot, au millimètre près, sans avoir besoin de caméras ou de capteurs complexes pour se repérer.
* *Le servomoteur :* Il est très léger et possède une intelligence intégrée qui lui permet de tourner à un angle très précis. Il est parfait pour pivoter la pièce de puzzle (ex: "tourne de 45 degrés") au bout du bras, sans alourdir la machine.
 ![PLATEAU SUPPORT](https://i.postimg.cc/90PytPTX/Capture-d-ecran-2026-06-13-220557.png)
 ![PLATEAU SUPPORT](https://i.postimg.cc/mgYKzKh0/Chariot.jpg)
### 7. Les capteurs de fin de course
* *Notre choix :* Des petits interrupteurs mécaniques placés aux extrémités des axes de déplacement.
* *Pourquoi ce choix ?* Les moteurs pas à pas sont "aveugles" : quand on allume la machine, le robot ne sait pas où se trouve son bras. Il a donc besoin d'un point de repère. Au démarrage, le robot bouge jusqu'à venir taper doucement contre ces interrupteurs. Dès que le bouton fait "clic", le robot sait qu'il est arrivé à son point de départ (le point Zéro). Cela sert aussi de sécurité pour empêcher le robot de continuer à forcer et de s'écraser contre les bords de sa propre structure.
 ![PLATEAU SUPPORT](https://i.postimg.cc/bJxPzdkS/capteur.jpg)
