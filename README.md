# Projet CNC – Fabrication Mécanique & Productique
### 1. Description du projet

Ce dépôt GitHub présente un projet académique de fabrication mécanique réalisé dans le cadre du module Productique et Fabrication Mécanique.
L’objectif principal est la conception, la programmation et l’usinage CNC d’une pièce mécanique, en reliant les notions théoriques (CAO/FAO, G-code) à une application pratique sur machine-outil à commande numérique.

Le projet couvre l’ensemble du processus industriel :

- Conception de la pièce sous SolidWorks
- Génération et compréhension du programme CNC (G-code)
- Simulation de l’usinage
- Usinage réel sur machine CNC
- Analyse et validation du résultat final
### 2. Objectifs du projet

Les objectifs principaux de ce projet sont :

- Comprendre le fonctionnement des machines CNC et leur rôle dans l’industrie moderne
- Appliquer les principes de la CAO / FAO
- Maîtriser les bases de la programmation CNC (G-code)
- Réaliser la simulation et l’usinage réel d’une pièce mécanique
- Relier les notions théoriques de fabrication mécanique à une application pratique
### 3. Structure du dépôt
 
 /code
 
    ├─ Code_simuler.txt
    
    ├─ Code_usiner.txt 
    
 /image

    ├─ Capture.PNG        → drawing avec annotations 
 
    ├─ part1.PNG          → La pièce conçue sur SOLIDWORKS
 
    ├─ schema.PNG         → photos des dimensions de la pièce  
 
    └─ usinage.PNG        → usinage réel sur machine CNC
 
 
/model

    ├─ Part1.SLDPRT       → fichier SolidWorks (Part)
 
    └─ Part1.SLDDRW       → fichier SolidWorks (Drawing)
 

README.md

### 4. Description de la pièce mécanique
La pièce conçue présente une géométrie combinant :

- Des segments rectilignes
- Des arcs de cercle de différents rayons
- Des zones nécessitant une précision géométrique et dimensionnelle

La définition géométrique repose sur :

- Un repère XY clairement défini
- Des points caractéristiques (P1 à P12)
- Des profondeurs d’usinage distinctes pour la simulation et l’usinage réel
- Les détails complets sont disponibles dans les drawings annotés présents dans le dossier /image.

![La pièce à concevoir et usiner :](image/schema.PNG)
### 5. Les points choisis:
Le rectangle:

- P1 (X+50 ; Y-150) {Point de départ}
- P2 (X-50 ; Y-150)
- P3 (X-50 ; Y-230)
- P4 (X+50 ; Y-230)
  
Les courbes de rayon R80:

- P5 (X0 ; Y-150) {Point entre P1 et P2, centre de la courbe 1}
- P6 (X0 ; Y-230) {Point entre P3 et P4, centre de la courbe 2}
  
Les arcs de rayon R60:

- P7 (X+25 ; Y-190) {Point de rencontre des deux arcs entre P1 et P5}
- P8 (X-25 ; Y-180) {Point de rencontre des deux arcs entre P3 et P6}
  
Les 3/4 cercles de rayon R10:

{les points de départ et d’arrivée du cercle centrée en P2}
- P9 (X-40 ; Y-150)
- P10 (X-50 ; Y-160)
  
{les points de départ et d’arrivée du cercle centrée en P4}
- P11 (X+40 ; Y-230)
- P12 (X+50 ; Y-220)
  
Les Z :

{Pour La simulation}
- Z1=-79 {Z pour approcher}
- Z2=-89 {Z pour simuler l’usinage}
  
{Pour l’usinage}
- Z3=-89 {pour approcher}
- Z4=-100 {pour usiner}

### 6. Processus d'usinage CNC
#### 6.1. Conception de la pièce sur SOLIDWORKS
La pièce a été modélisée en trois dimensions à l’aide du logiciel SolidWorks, en respectant les contraintes géométriques et fonctionnelles définies dans le cahier des charges. À partir de ce modèle 3D, un drawing technique a été élaboré, intégrant l’ensemble des cotes, tolérances et annotations nécessaires à la fabrication. Une vérification des dimensions et de la faisabilité de l’usinage a ensuite été réalisée afin de garantir la compatibilité de la pièce avec les capacités de la machine CNC et d’assurer la conformité du résultat final.

![La pièce conçue :](image/part1.PNG)

[fichier SolidWorks Part](model/Part1.SLDPRT)

![Drawing avec annotations :](image/Capture.PNG)

[fichier SolidWorks Drawing](model/Part1.SLDDRW)

#### 6.2. Programmation CNC 

Les machines CNC utilisent le G-code pour commander les mouvements et les opérations d’usinage, tandis que les M-codes assurent la gestion des fonctions auxiliaires de la machine. Le G-code permet de contrôler avec précision la position, la vitesse et la direction de coupe sur différentes machines automatisées. Le code S définit la vitesse de rotation de la broche et influence directement la qualité d’usinage et la durée de vie des outils.

##### G-codes (Fonctions de mouvement):
- G00 : Déplacement rapide
- G01 : Interpolation linéaire (déplacement en ligne droite)
- G02 : Interpolation circulaire horaire (CW)
- G03 : Interpolation circulaire antihoraire (CCW)
##### M-codes (Fonctions auxiliaires):
- M02 : Fin de programme
- M03 : Démarrage de la broche en rotation horaire
##### S-codes (Fonctions de vitesse de broche)
- S (Vitesse de rotation de la broche) : S1200 définit une vitesse de 1200 RPM.
- F (Vitesse de déplacement d'outil) : F150 définit une vitesse d'avance de 150 mm/min.

#### 6.3. Code à simuler 
[Le code à simuler](code/Code_simuler.txt)
#### 6.4. Code à usiner 
[Le code à usiner](code/Code_usiner.txt)
