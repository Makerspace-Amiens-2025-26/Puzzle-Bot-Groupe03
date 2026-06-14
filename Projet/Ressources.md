
## Ressources du Projet


Cette section regroupe l'ensemble des fichiers techniques, des nomenclatures et des codes sources nécessaires pour comprendre, évaluer en détail ou reproduire intégralement le robot Puzzle-Bot.


### 1. Conception Mécanique

Cette partie contient les modélisations 3D de la structure, des pieds sur mesure et de la tête de préhension.
* **Fichiers CAO natifs :** [Lien vers les fichiers sources du logiciel de modélisation 3D]

* **Fichiers pour impression 3D :** [Lien vers les fichiers .STL des pièces fabriquées]


### 2. Électronique

Cette partie regroupe les éléments de la chaîne d'énergie, de commande, et de la carte sur mesure.
* **Nomenclature (BOM) :** [Lien vers le tableur listant les composants : CNC Shield, NEMA 17, MG996R, relais/MOSFETs, etc.]
* **Fichiers de conception (KiCad) :** [Lien vers le schéma électrique et le fichier de routage du PCB](https://www.kicad.org/)
* **Fichiers de fabrication :** [Lien vers les fichiers Gerber de la carte de puissance]()

### 3. Programmation

Cette partie détaille l'environnement logiciel nécessaire pour compiler et exécuter le projet.
* **Environnements de développement :** [Arduino IDE, environnement ](https://www.arduino.cc/en/software)
* **Bibliothèques (Libraries) requises :** [Lister les dépendances, ex: Servo.h pour les servomoteurs, librairies de traitement d'image]
* **Logique et algorithmes :** [Lien vers les diagrammes d'états ou algorithmes de détection]

### 4. Code Source

Cette partie contient l'accès direct aux scripts qui pilotent la machine.
* **Code Bas Niveau (Contrôle) :** [Lien vers le dossier des fichiers Arduino `.ino` gérant la cinématique et la pneumatique]
* **Code Haut Niveau (Vision) :** [Lien vers le dossier des scripts gérant l'analyse d'image, le calcul d'angle et la génération de coordonnées]
