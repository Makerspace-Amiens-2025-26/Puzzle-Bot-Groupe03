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

## 🎯 Résumé du Cahier des Charges

Le projet consiste à créer un robot autonome en 90 heures au MakerSpace, sans plans existants, capable de résoudre un puzzle.

### 🔹 1. Ce que le robot doit faire (Les Missions)
* **Vision :** Filmer la zone avec une caméra pour repérer les pièces de puzzle et calculer leur position.
* **Déplacement (X / Y) :** Bouger précisément d'avant en arrière et de gauche à droite pour se placer au-dessus de la bonne pièce.
* **Saisie (Z) :** Descendre l'axe vertical, aspirer la pièce avec une ventouse via une mini-pompe, la soulever et la faire tourner dans le bon sens grâce à un servomoteur.

### 🔸 2. Ce que nous devons respecter (Les Règles)
* **Conception 3D :** Tout dessiner sur OnShape et imprimer nos propres pièces en 3D (coins pour le cadre, roues pour les axes, chariot mobile et support caméra).
* **Matériel imposé :** Utiliser une base en Plexiglas, des barres en aluminium, une carte Arduino Uno et une CNC Shield pour contrôler les moteurs.
* **Sécurité :** Attacher proprement les câbles et les tuyaux pour éviter les blocages, et vérifier les branchements pour ne pas griller les composants.
* **Partage :** Rédiger une documentation claire sur GitHub pour que d'autres étudiants puissent refaire la machine facilement.
