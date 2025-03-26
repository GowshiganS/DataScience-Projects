# Prédiction du Rendement du Maïs

Projet réalisé dans le cadre du TD ATDN (Analyse Totale de Données et Modélisation) du Master Informatique.

## Objectif

Ce projet applique le cycle complet d’un projet de Data Science pour aider une ferme à prédire le rendement du maïs (en tonnes par hectare) en fonction de :

- la surface cultivée
- le type de sol
- la quantité d'engrais
- les précipitations
- la température moyenne

Le but final est d’optimiser les ressources agricoles et d’améliorer la prise de décision.

## Fichiers

- `Analyse_probleme_culture.ipynb` : Notebook principal contenant toutes les étapes du projet.
- `rendement_mais.csv` : Jeu de données utilisé pour l'analyse (à ajouter dans le dépôt si possible).

## Méthodologie

### Étape 1 : Compréhension du problème
- Identification des variables explicatives et de la variable cible.
- Formulation de la problématique métier.

### Étape 2 : Analyse statistique descriptive
- Calculs de statistiques (moyenne, médiane, variance, etc.)
- Visualisations : histogrammes, boxplots, heatmap de corrélation.

### Étape 3 : Analyse de la variance (ANOVA)
- Vérification de l’impact du type de sol sur le rendement via un test statistique.

### Étape 4 : Modélisation
- Encodage des variables catégorielles (One-Hot).
- Entraînement de plusieurs modèles :
  - Régression Linéaire
  - Ridge Regression
  - Random Forest
- Évaluation des performances (MAE, RMSE, R²).

### Étape 5 : Interprétation et recommandations
- Analyse de l’importance des variables.
- Recommandations concrètes pour la ferme.
- Limites du modèle et pistes d’amélioration.

## Technologies utilisées

- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- scipy

## Résultats

Les modèles n'ont pas atteint de bonnes performances (R² négatif), probablement en raison de la taille limitée du jeu de données et de la complexité du problème.

Meilleur MAE : ~2.06 avec le modèle Random Forest  
R² ≤ 0 pour tous les modèles testés

## Recommandations

- Ajuster la quantité d’engrais selon le type de sol
- Privilégier les parcelles limoneuses ou argileuses
- Semer durant les périodes où la température est optimale (20-25°C)
- Ajouter plus de variables (ensoleillement, pH, type de graine...)
- Collecter plus de données pour améliorer les modèles

## Auteur

- Gowshigan Selladurai — Étudiant en Master Informatique, parcours Data

## Licence

Ce projet est partagé à des fins pédagogiques. Toute réutilisation doit être citée correctement.
