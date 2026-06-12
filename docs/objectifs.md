---
layout: default
nav_order: 3
title: Objectifs du projet
---
#  Présentation Générale du Projet

## 1. Introduction
« Puzzle Bot » est un projet pratique et innovant développé au sein du MakerSpace d'UniLaSalle Amiens. L'idée centrale est de concevoir et de réaliser de A à Z une machine automatisée intelligente, en partant d'une feuille blanche et sans plans préexistants. 

Ce projet propose une approche concrète et stimulante de la robotique en combinant quatre disciplines majeures de l'ingénierie : **la mécanique, l'électronique, la programmation et la vision par ordinateur**.

---

## 2. Contexte du Projet
Dans le monde de l'industrie et de la recherche, les ingénieurs doivent souvent créer des solutions sur mesure pour répondre à des besoins spécifiques, sans pouvoir s'appuyer sur des guides existants. 

Inspiré par l'esprit créatif de créateurs de contenu et ingénieurs reconnus comme **Mark Rober** ou **Stuff Made Here**, ainsi que par la philosophie du mouvement *Open Source*, le projet Puzzle Bot place les étudiants dans une situation réelle de conception en autonomie. Face à un problème donné, l'équipe doit imaginer la structure, dessiner les pièces, choisir les composants et programmer l'intelligence du robot en exploitant les ressources et les outils de fabrication numérique disponibles au MakerSpace (imprimantes 3D, découpeuse laser).

---

## 3. Objectifs du Projet

L'objectif principal est de construire un système automatisé capable d'identifier, de saisir et de déplacer des pièces de manière autonome pour accomplir une tâche précise (tri, assemblage ou résolution de puzzle).

Pour l'équipe d'étudiants, les objectifs pédagogiques sont :
* **Concevoir en autonomie :** Passer de l'idée théorique à un prototype physique fonctionnel.
* **Maîtriser la chaîne mécatronique :** Faire interagir du code (Arduino), des cartes électroniques (CNC Shield), des moteurs et des capteurs.
* **Intégrer l'intelligence artificielle / Vision :** Permettre au robot de "voir" son environnement grâce à une caméra pour prendre des décisions en temps réel.
* **Travailler en mode Agile :** Adapter l'architecture de la machine au fil des tests (comme le passage d'un modèle simple à une structure de portique X-Y).

---

## 4. Cahier des Charges (CdC)

Pour encadrer la conception du Puzzle Bot, nous avons défini les critères techniques et fonctionnels suivants :

### 🔹 Fonctions Principales (Ce que le robot doit faire)
* **Vision & Détection :** Le système doit être capable de scanner la zone de travail via une caméra supérieure, de distinguer les formes ou les couleurs des pièces et de calculer leurs coordonnées.
* **Déplacement Précis (Axes X-Y) :** La tête robotisée doit se déplacer de manière fluide et précise au-dessus d'une zone de travail parfaitement quadrillée par des profilés aluminium.
* **Saisie et Manipulation (Axe Z & Pneumatique) :** Le robot doit pouvoir descendre verticalement, attraper une pièce à l'aide d'une ventouse (système d'aspiration par le vide), la soulever et la faire pivoter (via un servomoteur) pour la repositionner correctement.

### 🔸 Contraintes Techniques (Les règles à respecter)
* **Matériaux imposés :** Utilisation d'une carte Arduino Uno couplée à une CNC Shield V3 pour le contrôle des moteurs pas-à-pas (NEMA 17).
* **Structure et Fixations :** Utilisation d'une planche en Plexiglas (PMMA) de 5 mm d'épaisseur comme base solide, et de profilés aluminium de type V-Slot.
* **Fabrication locale :** Toutes les pièces de liaison spécifiques (coudes d'angles, supports moteurs, chariot mobile, support caméra) doivent être modélisées en CAO et imprimées en 3D au MakerSpace.
* **Sécurité et Fiabilité :** Le système doit intégrer une gestion rigoureuse des câbles et tuyaux pour éviter les blocages lors des translations, et le circuit électrique doit être protégé contre les inversions de polarité.
