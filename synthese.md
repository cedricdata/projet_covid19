# Projet: Classification de radiographies pulmonaires

# PARTIE 1: Définition de l'objectif du projet

Mettre en place un modèle prédictif de deep learning, chargé de classer les radiographies pulmonaires, dans 3 catégories différentes appelées 'classe'.

**Classe covid19**: Pour les patients atteints de la covid19

**Classe normale**: Pour les patients sains

**Classe pneumonie**: Pour les patients atteints de pneumonie virale

# PARTIE 2: Analyse exploratoire de données (EDA)

**Analyse du jeu de données**

Le jeu de données brutes, téléchargé sur le site Kaggle, est composé de clichés radiographiques pulmonaires, répartis dans 3 dossiers.

**Dossier COVID-19**: Ce dossier contient les radiographies pulmonaires de patients atteints par la covid 19. 

**Dossier NORMAL**: Ce dossier contient les radiographies pulmonaires de patients sains.

**Dossier Viral Pneumonia**: Ce dossier contient les radiographies pulmonaires de patients atteints de pneumonie virale.

Dans le jeu de données brutes, les radiographies présentent les résolutions suivantes:
* 256x256
* 331x331
* 160x187x3
* 197x253x3
* 1024x1024
* 1024x1024x3

L'objectif de cette partie est de regrouper toutes les images dans un dataframe afin de faciliter leur traitement.  
Cette opération nécéssite d'avoir des radiographies de même résolution, celle choisie pour l'ensemble des images est de 256x256.

# PARTIE 3: DATA-PREPROCESSING

**Augmentation d'image**\
La technique d'augmentation d'image permet d'enrichir le jeu de données et de réduire le phénomène d'overfitting.

# PARTIE 4: MODELISATION

**Transfer learning**\
Cette modélisation est basé sur le principe du transfer learning qui consiste à utiliser un modèle pré-entrainé sur des centaines de milliers d'images.\
VGG16, un modèle pré-entrainé, est utlisé pour extraire les caractéristiques des radiographies. Une couche dense de réseaux de neurones, entièrement connectés, est mise en place pour réaliser la classification des radiographies.

# PARTIE 5: EVALUATION
**Matrice de confusion**\
Accuracy: 96%

**Rapport de classication**
- Classe Covid
  - Précision: 99%
  - Recall: 99%
  - F1 Score: 99% 
  
- Classe Normal
  - Précision: 90%
  - Recall: 99%
  - F1 Score: 94%
  
- Classe Pneumonie
  - Précision: 98%
  - Recall: 89%
  - F1 Score: 93%  
    
**Précision et perte**\
Les courbes de precision et de perte convergent à la fois sur les données d'entrainement et sur les données de test.

# CONCLUSION
La recall et la précision sont élevés pour toutes les classes, en particuliers pour la classe COVID.

La sensibilité est de 99% sur la classe COVID, par conséquent, le taux de faux négatif est extrêmement faible.\
L'analyse de cliché radiographique à partir d'un modèle basé sur des réseaux de neurones semble fiable pour détecter la présence de la maladie chez un patient.
