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

## 🛠️ 1. Organisation du Poste de Travail

Avant de commencer le montage, préparez un espace propre et bien rangé au MakerSpace. Cela évite de perdre des pièces ou de faire des erreurs.

* **Trier les pièces :** Mettez d'un côté la quincaillerie (vis et écrous classés par taille) et de l'autre les morceaux du châssis en aluminium ainsi que toutes les pièces imprimées en 3D.
* **Protéger les éléments fragiles :** Gardez les cartes électroniques à l'écart pendant que vous montez la structure lourde. Cela évite de faire tomber des petits morceaux de métal ou des outils dessus.

---

## 🏗️ 2. Assemblage Initial (Le Châssis et les Axes X-Y)

Pour obtenir une machine stable, nous avons repensé la base afin de créer un système de portique qui quadrille parfaitement notre zone de travail.

### Le Cadre et le Quadrillage de la Zone (Axe X)
* **Les nouveaux coudes d'angle (Corners) :** Commencez par installer les nouveaux coudes en plastique conçus en 3D aux quatre coins de la planche en Plexiglas. Ils servent à maintenir fermement les deux grands profilés en aluminium parallèles. Cela crée un cadre rigide et un repère fixe pour délimiter la zone de travail.
* **Le profilé mobile et ses supports à roues :** Prenez le profilé en aluminium qui traverse la machine pour l'axe X. Fixez à ses deux extrémités les deux pièces 3D spécifiques sur lesquelles sont vissées des roues de guidage. Emboîtez ces roues dans les rails du cadre. Ce système maintient le profilé bien droit et lui permet de glisser de manière fluide sans se mettre de travers.

### Le Chariot Mobile (Axe Y)
* **Le bloc central coulissant :** Assemblez le groupe de pièces 3D qui entoure le profilé mobile. Une fois vissées ensemble, ces pièces forment un unique bloc compact et ultra-rigide qui translate d'un côté à l'autre de l'axe Y, et qui supportera tout l'axe vertical (Z).
* **Le support de la caméra :** Fixez la pièce 3D spécialement conçue pour accueillir la caméra de vision. Ce support la maintient parfaitement stable et orientée vers le bas pour scanner la zone, identifier les formes des pièces et donner les coordonnées au robot.

---

## 📐 3. Fixation et Montage de l'Axe Vertical (Z)

L'axe Z est la partie qui descend pour attraper les pièces de puzzle et utilise un servomoteur pour les faire pivoter.

* **Montage de la colonne verticale :** Installez le système de guidage vertical sur le chariot de l'axe Y, puis fixez le moteur pas-à-pas qui gère la montée et la descente.
* **Le support coudé du servomoteur :** À la base de cet axe Z, installez le support en coude (à 90°) imprimé en 3D. Ce coude permet d'aligner parfaitement l'axe du servomoteur avec le centre de la ventouse pour que celle-ci tourne sur elle-même sans décentrer la pièce.
* **Le système pneumatique :** Vissez la mini-pompe à air et l'électrovanne sur un coin stable de la planche en Plexiglas. Branchez les tuyaux en silicone transparent de la ventouse vers la vanne, puis vers la pompe. Attachez proprement les tuyaux le long des profilés avec des liens en plastique en laissant assez de mou pour les mouvements du robot.

---

## 🔒 Vérifications Finales

Avant de passer à la suite, effectuez ces derniers contrôles :

* **Vérifier le glissement :** Poussez chaque axe à la main, moteurs éteints. Le mouvement doit être souple et sans effort sur toute la zone de travail. Si ça coince, desserrez un peu les vis, réalignez les profilés et revissez.
* **Vérifier le serrage :** Assurez-vous qu'aucune vis n'a été oubliée et que toutes les pièces 3D sont solidement fixées.
