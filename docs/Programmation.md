---
layout: default
nav_order: 3
parent: Conception et prototypage
title: programmation
---

# III. programmation  

##  Architecture et Logique

La partie logicielle du Puzzle-Bot est divisée en deux niveaux distincts qui communiquent ensemble : un niveau "Haut" (le cerveau analytique sur ordinateur) et un niveau "Bas" (l'exécutant mécanique sur l'Arduino).

### Architecture Logicielle Globale

* *Le Traitement d'Image (Haut Niveau) :* Un programme tournant sur l'ordinateur utilise la caméra pour détecter la position des pièces, calcule leur orientation, et détermine les coordonnées et l'angle de rotation nécessaires.
* *La Communication Série :* L'ordinateur traduit ces coordonnées en instructions textuelles et les envoie à la carte Arduino via un câble USB.
* *Le Contrôle Mécanique (Bas Niveau) :* Le code de l'Arduino traduit les instructions en signaux électriques (PWM, impulsions de pas, commandes statiques).

![Capture-d-ecran-2026-06-14-16](https://i.postimg.cc/xThRkzpS/Capture-d-ecran-2026-06-14-160353.png)
![Modélisation du boîtier électronique](https://i.postimg.cc/Cx9QVtpT/Capture-d-ecran-2026-06-14-182643.png) 
### Séquençage et Machine d'États (Le Cycle de Travail)

Le code de l'Arduino est structuré comme une "machine d'états". Le robot exécute une séquence d'actions stricte pour chaque pièce de puzzle, avec des temporisations ajustées pour la gestion du vide pneumatique.


![Modélisation du boîtier électronique](https://i.postimg.cc/sXsKjCnk/Capture-d-ecran-2026-06-14-182659.png) 

### Gestion des Sécurités Logicielles (Homing)

Avant de pouvoir placer une pièce, une routine d'initialisation (Homing) s'exécute :
1.  *Recherche du Zéro :* L'Arduino fait reculer les moteurs très lentement.
2.  *Détection :* L'écrasement des capteurs de fin de course stoppe les moteurs.
3.  *Calibrage :* Cette position physique devient le point de coordonnées (0,0) de référence pour tous les futurs déplacements.

