---
layout: default
nav_order: 5
title: Conception et prototypage
---

# Conception et prototypage

# I.Conception électronique 

## Câblage et Connexions Électriques

Cette section détaille le branchement de chaque composant, fil par fil, pour permettre de reproduire l'électronique du robot à l'identique.



### 1. Alimentation et Arrêt d'Urgence
Toute la puissance mécanique du robot dépend de la batterie 12,7 V. L'objectif est de pouvoir tout couper d'un seul coup.

* **L'Arrêt d'urgence :** Il est placé en "série" sur le fil positif. 
  * Le fil Rouge (+) provenant de la batterie se branche sur l'entrée du bouton coup de poing.
  * En sortie du bouton, le fil Rouge (+) se divise en deux : un câble part vers le bornier d'alimentation du CNC Shield, et l'autre part vers le bornier d'alimentation de notre carte sur mesure (PCB).
* **La Masse :** Le fil Noir (-) de la batterie est directement relié aux borniers "GND" du CNC Shield et de la carte sur mesure.
* **L'Arduino :** Il est alimenté séparément avec son câble USB classique branché à l'ordinateur (qui fournit le 5 V de sécurité).
  
```mermaid
graph TD
    subgraph Énergie Puissance
        B[Batterie 12.7V]
    end
    
    subgraph Sécurité
        AU((Bouton Arrêt <br> d'Urgence))
    end
    
    subgraph Cartes Électroniques
        CNC[Bornier CNC Shield]
        PCB[Bornier PCB Pompe]
    end

    B -- "Fil Rouge (+)" --> AU
    AU -- "Fil Rouge (+)" --> CNC
    AU -- "Fil Rouge (+)" --> PCB
    B -- "Fil Noir (-)" --> CNC
    B -- "Fil Noir (-)" --> PCB
```

### 2. Le Cerveau : Arduino et CNC Shield
Le branchement principal est le plus simple : la carte d'extension **CNC Shield v3** vient simplement s'emboîter directement sur le dessus de la carte **Arduino Uno**. Il faut juste vérifier que toutes les petites broches en métal rentrent bien dans les trous noirs de l'Arduino sans se tordre.

### 3. Les Moteurs de déplacement (Axes X et Y)
Ce sont les gros moteurs (NEMA 17) qui font bouger le robot sur la table.

* **Les Drivers (A4988) :** On enfonce ces petits modules sur les emplacements marqués `X` et `Y` au centre du CNC Shield. *(Attention à mettre la petite vis de réglage du bon côté selon la documentation du module !)*
* **Les Moteurs :** Chaque moteur possède un câble avec un connecteur à 4 fils (les deux bobines internes). Ils viennent se brancher directement sur les 4 petites broches alignées juste à côté de leur driver A4988 respectif. Notez à inverser les deux fils du milieu.

```mermaid
graph TD
    A[Arduino Uno] -->|S'emboîte sur| S[CNC Shield V3]
    S -->|Emplacement X| DX[Driver A4988 - Axe X]
    S -->|Emplacement Y| DY[Driver A4988 - Axe Y]
    DX -->|Câble 4 fils| MX[Moteur NEMA 17 - X]
    DY -->|Câble 4 fils| MY[Moteur NEMA 17 - Y]
```
### 4. La Tête de Préhension (Les 2 Servomoteurs)
Les deux servomoteurs (MG996R) qui gèrent la descente et la rotation de la ventouse possèdent 3 fils chacun :

* **Fil Rouge (Énergie) :** À brancher sur une broche **5V** libre du CNC Shield.
* **Fil Marron ou Noir (Masse) :** À brancher sur une broche **GND** du CNC Shield.
* **Fil Jaune ou Orange (Signal) :** C'est le fil qui transporte les ordres. Puisque les broches classiques sont déjà utilisées, on les branche sur des broches libres capables de faire varier la tension (PWM). Par exemple, le premier sur la broche **5** et le deuxième sur la broche **6**.

```mermaid
graph LR
    subgraph CNC Shield V3
        VCC[Broches 5V]
        G[Broches GND]
        P5[Broche Digitale 5 - PWM]
        P6[Broche Digitale 6 - PWM]
    end

    subgraph Servomoteurs
        S1[Servomoteur 1 - Descente]
        S2[Servomoteur 2 - Rotation]
    end

    VCC -- "Fil Rouge (+)" --> S1
    VCC -- "Fil Rouge (+)" --> S2
    G -- "Fil Noir/Marron (-)" --> S1
    G -- "Fil Noir/Marron (-)" --> S2
    P5 -- "Fil Jaune/Orange (Signal)" --> S1
    P6 -- "Fil Jaune/Orange (Signal)" --> S2
```
### 5. L'Aspiration (La carte sur mesure / PCB)
C'est la carte qui fait l'intermédiaire avec le 12,7 V pour gérer la pneumatique.

* **Les Actionneurs :** * Les 2 fils de la **Pompe à vide** se vissent dans le bornier de sortie (souvent appelé "M1" sur la carte).
  * Les 2 fils de l'**Électrovanne** se vissent dans l'autre bornier de sortie ("M2").
* **La Commande depuis l'Arduino :** On utilise 3 petits fils pour relier cette carte à l'Arduino :
  * Le fil de référence (GND) du PCB se branche sur une broche **GND** libre du Shield.
  * Le fil qui commande l'allumage de la **pompe** est branché sur la broche **A3** (broche analogique de l'Arduino).
  * Le fil qui commande l'ouverture de la **vanne** est branché sur la broche **A4** (broche analogique de l'Arduino).

```mermaid
graph LR
    subgraph Arduino Uno / Shield
        A3[Broche A3]
        D13[Broche 13]
        GND[GND]
    end

    subgraph PCB Sur Mesure
        MOS1[MOSFET 1]
        MOS2[MOSFET 2]
    end

    subgraph Actionneurs Pneumatiques
        P[Pompe à Vide 12V]
        V[Électrovanne 12V]
    end

    A3 -- "Commande (5V)" --> MOS1
    D13 -- "Commande (5V)" --> MOS2
    GND -- "Référence Masse Commune" --> PCB
    
    MOS1 -- "Puissance (12.7V)" --> P
    MOS2 -- "Puissance (12.7V)" --> V
```
### 6. Les Sécurités (Capteurs de fin de course)
Ce sont les interrupteurs qui disent au robot quand il touche les bords de la table. Ils n'ont que 2 fils (connectés sur les pattes "Normalement Ouvert" et "Commun" de l'interrupteur).

* **Capteur de l'axe X :** Les deux fils se branchent sur la zone "End Stops" du CNC Shield. Un fil sur la broche **X+** et l'autre sur la broche **GND** située juste en dessous. *(En code, cela correspond à la broche 9)*.
* **Capteur de l'axe Y :** Un fil sur la broche **Y+** et l'autre sur le **GND** correspondant. *(En code, cela correspond à la broche 10)*.

```mermaid
graph LR
    subgraph CNC Shield - Zone End Stops
        X[Broche X+]
        Y[Broche Y+]
        GX[Broche GND sous X+]
        GY[Broche GND sous Y+]
    end

    subgraph Capteurs Mécaniques
        CX[Capteur Fin de Course X]
        CY[Capteur Fin de Course Y]
    end

    X -- "Fil Signal" --> CX
    GX -- "Fil Masse" --> CX
    
    Y -- "Fil Signal" --> CY
    GY -- "Fil Masse" --> CY
```

# II.Conception mecanique 
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
* *Rotation de la pièce :* Un support orientable est fixé au bout de la crémaillère pour faire pivoter la ventouse, permettant d'ajuster l'angle de la pièce de puzzle avec précision avant sa pose.
* *Intégration pneumatique :* La tête dispose de supports de fixation dédiés pour embarquer directement la pompe à vide et l'électrovanne. Cette proximité avec la ventouse réduit la longueur du circuit d'air et garantit un temps de réponse immédiat lors de la préhension et du relâchement.

* ![Conception de la tête de préhension](https://i.postimg.cc/13QhRDy9/Capture-d-ecran-2026-06-13-233024.png)

### 4. Boîtier d'Intégration et Support Caméra
Pour finaliser la machine, la rendre autonome et sécuriser les utilisateurs, un boîtier global a été modélisé :
* *Organisation de l'électronique :* Il comprend les supports de fixation sur mesure pour la carte de contrôle principale, facilitant le routage propre des câbles.
* *Sécurité et Capteurs :* Des emplacements spécifiques et rigides sont prévus pour le maintien des capteurs de fin de course, ainsi qu'une façade accessible pour le bouton d'arrêt d'urgence.
* *Module Vision :* Le boîtier intègre également la base de maintien du profilé vertical dédié à la caméra. Ce système de fixation garantit que l'objectif reste parfaitement stable et centré au-dessus de la zone de travail, ce qui est crucial pour la précision de l'algorithme de détection.

* ![Modélisation du boîtier électronique](https://i.postimg.cc/ZYGXj6BL/Capture-d-ecran-2026-06-13-233236.png)
# III. programmation  
