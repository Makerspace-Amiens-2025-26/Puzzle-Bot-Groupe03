---
layout: default
nav_order: 8
title: Perspectives et travaux futurs
---

##  **Perspectives d'Évolution et Améliorations Futures**

Le Puzzle-Bot actuel constitue une preuve de concept fonctionnelle validant nos choix d'architecture. Cependant, pour passer d'un prototype de laboratoire à une machine plus robuste, performante et industrielle, plusieurs pistes d'amélioration ont été identifiées :

### 1. Vision et Intelligence Artificielle
* *Modèles de détection avancés :* Remplacer les algorithmes de détection de formes simples par des modèles de Deep Learning (ex: YOLOv8) pour identifier les pièces de puzzle même en cas d'occlusion partielle ou de faible luminosité.
* *Calibration de la caméra :* Mise en œuvre d'une matrice de correction  afin d'augmenter la précision des coordonnées $(X, Y)$ envoyées au robot.

### 2. Précision Mécanique

* *Gestion des câbles :* Installation de chaînes porte-câbles  imprimées en 3D pour sécuriser les faisceaux électriques et éviter leur usure ou leur accrochage lors des déplacements rapides.
* *Optimisation des matériaux :* Remplacer les pièces structurelles en impression 3D par de l'aluminium usiné pour accroître la rigidité et réduire les vibrations à haute vitesse.

### 3. Fiabilité Électronique

* *Communication sans fil :* Migration du contrôle filaire (USB) vers une liaison sans fil (Wi-Fi ou Bluetooth via ESP32) pour isoler le robot de l'ordinateur de contrôle.

### 4. Logiciel et Optimisation

* *Optimisation des trajectoires (TSP) :* Intégrer un algorithme de résolution pour calculer le trajet optimal permettant de ramasser toutes les pièces dans l'ordre le plus rapide possible.
* *Interface Homme-Machine (IHM) :* Développer une interface graphique en Python ou sur une page web pour piloter le robot, visualiser le retour caméra et suivre l'état d'assemblage en temps réel sans interagir avec le code source.
