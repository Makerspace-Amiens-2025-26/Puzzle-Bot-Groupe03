---
layout: default
nav_order: 4
title: Études et choix techniques
---

# ÉTUDE ET CHOIX TECHNIQUE

# I. Cahier des charges – Projet Puzzle Bot
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
* Précision de positionnement inférieure à 2 mm.
* Détection fiable des pièces supérieure à 90 %.
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

## la mecanique
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
- Un support dédié au profilé de maintien de la caméra ainsi qu'à son système de fixation.
  
 ![PLATEAU SUPPORT](https://i.postimg.cc/4dmW4cph/Capture-d-ecran-2026-06-13-200942.png)
 
 ![PLATEAU SUPPORT](https://i.postimg.cc/Z5bFK3S0/Capture-d-ecran-2026-06-13-201106.png)
 
Cette organisation facilite le câblage, la maintenance et la sécurité de l'ensemble du système.
