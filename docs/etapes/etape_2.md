---
layout: default
title: Assemblage
parent: Etapes de fabrication
nav_order: 2
---

# Assemblage

Après la préparation des matériaux, l'étape suivante est l'assemblage.

## Étapes d'Assemblage

1. **Organisation** : Organisez tous les composants préparés.
2. **Assemblage Initial** : Commencez par assembler les pièces principales.
3. **Fixation** : Fixez solidement les pièces ensemble en utilisant les outils appropriés.



# Assemblage du Puzzle Bot

Après la préparation des matériaux, l'étape suivante est l'assemblage complet de la machine. Cette phase permet de donner vie au robot en combinant la structure mécanique, les pièces imprimées en 3D et le système d'aspiration.

---

##  1. Organisation du Poste de Travail

Avant de commencer le montage, préparez un espace propre et bien rangé au MakerSpace. Cela évite de perdre des pièces ou de faire des erreurs.

* **Trier les pièces :** Mettez d'un côté la quincaillerie (vis et écrous classés par taille) et de l'autre les morceaux du châssis en aluminium ainsi que toutes les pièces imprimées en 3D.
* **Protéger les éléments fragiles :** Gardez les cartes électroniques à l'écart pendant que vous montez la structure lourde. Cela évite de faire tomber des petits morceaux de métal ou des outils dessus.

---

##  2. Assemblage Initial (Le Châssis et les Axes X-Y)

Pour obtenir une machine stable, nous avons repensé la base afin de créer un système de portique qui quadrille parfaitement notre zone de travail.

### Le Cadre et le Quadrillage de la Zone (Axe X)
* **Les nouveaux coudes d'angle (Corners) :** Commencez par installer les nouveaux coudes en plastique conçus en 3D aux quatre coins de la planche en Plexiglas. Ils servent à maintenir fermement les deux grands profilés en aluminium parallèles. Cela crée un cadre rigide et un repère fixe pour délimiter la zone de travail.

  <img src="https://github.com/Makerspace-Amiens-2025-26/Puzzle-Bot-Groupe03/blob/main/docs/images/Chariot.jpeg" width="200">
    
* **Le profilé mobile et ses supports à roues :** Prenez le profilé en aluminium qui traverse la machine pour l'axe X. Fixez à ses deux extrémités les deux pièces 3D spécifiques sur lesquelles sont vissées des roues de guidage. Emboîtez ces roues dans les rails du cadre. Pour motoriser ce déplacement, l'une de ces deux pièces d'extrémité est dotée d'un moteur pas-à-pas. Ainsi, ce côté est entraîné directement par le moteur, ce qui permet de déplacer l'ensemble du profilé mobile de manière fluide sur l'axe X, tout en le maintenant bien droit et sans qu'il ne se mette de travers.

  <img src="https://github.com/Makerspace-Amiens-2025-26/Puzzle-Bot-Groupe03/blob/main/docs/images/Chariot.jpeg" width="200">

###  Le Chariot Mobile (Axe Y)
* **Le bloc central coulissant :** Assemblez le groupe de pièces 3D autour du profilé mobile. Une fois vissées ensemble, ces pièces forment un unique bloc compact qui glisse de gauche à droite sur l'axe Y. C'est ce bloc qui porte tout le système de l'axe Z (la pompe, l'électrovanne et la ventouse) pour déplacer les pièces de puzzle.
  
  <img src="https://github.com/Makerspace-Amiens-2025-26/Puzzle-Bot-Groupe03/blob/main/docs/images/Chariot.jpeg" width="200">



##  3. Fixation et Montage de l'Axe Vertical (Z) et de ses Outils

L'axe Z est installé directement sur le chariot de l'axe Y. Il gère la descente de tout le système pour aspirer et déplacer les pièces.

* **Le montage de l'axe Z :** Installez les glissières verticales sur le chariot de l'axe Y, puis fixez le moteur pas-à-pas qui fait monter et descendre le système d'aspiration.
* **L'installation de la pompe et de la vanne :** Fixez la mini-pompe à air et l'électrovanne directement sur le chariot mobile. En les plaçant ici, tout le système pneumatique se déplace en même temps que le robot.
* **Le support de la caméra (Suivi du mouvement) :** Fixez la pièce 3D de la caméra sur la partie mobile de l'axe Z. De cette façon, la caméra descend en même temps que la pompe pour suivre précisément la saisie de la pièce de puzzle.

  <img src="" width="200">
  
* **Le support coudé du servomoteur et de la ventouse :** Tout en bas de l'axe Z, installez le support en coude (à 90°) imprimé en 3D. Fixez-y le servomoteur et la ventouse reliée aux tuyaux en silicone. Ce coude permet à la ventouse de tourner la pièce sur elle-même sans la décaler du centre.
---


##  Vérifications Finales

Avant de passer à la suite, effectuez ces derniers contrôles :

* **Vérifier le glissement :** Poussez chaque axe à la main, moteurs éteints. Le mouvement doit être souple et sans effort sur toute la zone de travail. Si ça coince, desserrez un peu les vis, réalignez les profilés et revissez.
* **Vérifier le serrage :** Assurez-vous qu'aucune vis n'a été oubliée et que toutes les pièces 3D sont solidement fixées.
