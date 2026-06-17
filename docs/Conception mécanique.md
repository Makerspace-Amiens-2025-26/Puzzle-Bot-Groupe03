---
layout: default
nav_order: 1
parent: Conception et prototypage
title: Conception mecanique
---


# I.Conception mecanique 
## Conception Mécanique

### 1. Structure Principale et Châssis
* *Bâti en profilés d'aluminium :* Le châssis principal est construit à partir de profilés standards. Ce choix garantit une excellente rigidité structurelle tout en conservant une grande modularité pour l'assemblage et l'ajustement des équerrages.
* *Pieds de surélévation sur mesure :* De nouveaux pieds supports ont été spécifiquement conçus et intégrés pour surélever le plateau de travail. Ce dégagement vertical est indispensable : il permet le passage fluide des éléments de transmission sous la zone d'assemblage et facilite le débattement des différents axes de la machine sans risque de collision.

* ![Vue du châssis et des pieds](https://i.postimg.cc/FHMvLwyT/Capture-d-ecran-2026-06-13-232324.png)

### 2. Cinématique de Déplacement (Axes X et Y)
* *Transmission de l'axe X :* Le déplacement longitudinal du portique est piloté par un moteur pas à pas. Pour garantir un mouvement parfaitement translationnel et éviter l'arc-boutement, le système de guidage s'appuie sur deux rails latéraux. La synchronisation de l'entraînement entre les deux côtés est assurée par une barre de transmission métallique, accouplée directement à l'arbre du moteur via deux coupleurs flexibles.
* *Guidage de l'axe Y :* Le moteur pas à pas gérant l'axe transversal (Y) est directement embarqué sur la structure mobile, assurant le déplacement de la tête de préhension sur toute la largeur du portique.

* ![Détail de la transmission Axe X](https://i.postimg.cc/pV66rzJx/Capture-d-ecran-2026-06-13-232701.png)

### 3. Tête de Préhension (Outil et Axe Z)
La tête de l'effecteur est l'élément central pour la manipulation des pièces. Elle a été compactée au maximum pour intégrer de multiples fonctions mécaniques :
* *Déplacement vertical (Axe Z) :* Un système de pignon-crémaillère a été intégré pour convertir le mouvement de rotation du moteur en un déplacement vertical linéaire de la ventouse.
* ![Conception de la tête de préhension](https://i.postimg.cc/dVV21pxH/Capture-d-ecran-2026-06-15-175727.png)
* *Rotation de la pièce :* Un support orientable est fixé au bout de la crémaillère pour faire pivoter la ventouse, permettant d'ajuster l'angle de la pièce de puzzle avec précision avant sa pose.
* *Intégration pneumatique :* La tête dispose de supports de fixation dédiés pour embarquer directement la pompe à vide et l'électrovanne. Cette proximité avec la ventouse réduit la longueur du circuit d'air et garantit un temps de réponse immédiat lors de la préhension et du relâchement.

* ![Conception de la tête de préhension](https://i.postimg.cc/13QhRDy9/Capture-d-ecran-2026-06-13-233024.png)

### 4. Boîtier d'Intégration et Support Caméra
Pour finaliser la machine, la rendre autonome et sécuriser les utilisateurs, un boîtier global a été modélisé :
* *Organisation de l'électronique :* Il comprend les supports de fixation sur mesure pour la carte de contrôle principale, facilitant le routage propre des câbles.
* *Sécurité et Capteurs :* Des emplacements spécifiques et rigides sont prévus pour le maintien des capteurs de fin de course, ainsi qu'une façade accessible pour le bouton d'arrêt d'urgence.
* *Module Vision :* Le boîtier intègre également la base de maintien du profilé vertical dédié à la caméra. Ce système de fixation garantit que l'objectif reste parfaitement stable et centré au-dessus de la zone de travail, ce qui est crucial pour la précision de l'algorithme de détection.

* ![Modélisation du boîtier électronique](https://i.postimg.cc/ZYGXj6BL/Capture-d-ecran-2026-06-13-233236.png)
  
