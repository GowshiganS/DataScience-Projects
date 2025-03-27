# Analyse de Données et Méthodes d’Ensemble – Élevage de Poulets

Projet réalisé dans le cadre du cours **Analyse Totale de Données et Modélisation (ATDN)**.

## Objectifs du projet

Ce projet a pour but d'appliquer différentes techniques de Data Science sur des données réelles issues d’un élevage de poulets. Les objectifs principaux sont :

- Réaliser une analyse exploratoire des données (statistiques, visualisation, outliers)
- Tester des hypothèses statistiques (normalité, moyennes)
- Réduire la dimensionnalité des données (ACP, Kernel PCA)
- Appliquer des méthodes d'ensemble pour la prédiction (Bagging, Boosting)
- Comparer les performances des algorithmes et interpréter les résultats

## Données

Le fichier `donnees_elevage_poulet.csv` contient les mesures suivantes :

- `poids` : poids du poulet
- `nourriture` : quantité de nourriture ingérée
- `température` : température ambiante
- `survie` : indicateur de survie (0/1)
- `gain_poids` : variation du poids sur une période donnée

## Contenu du projet

Le projet est organisé en plusieurs parties dans le notebook `TP2.ipynb` :

### Partie 1 : Analyse exploratoire

- Statistiques descriptives (moyenne, médiane, écart-type, etc.)
- Histogrammes, boxplots
- Détection des outliers (IQR, Z-Score)
- Tests de normalité (Shapiro-Wilk)
- Comparaison de moyennes (t-test, ANOVA)

### Partie 2 : Réduction de dimensionnalité

- ACP manuelle avec NumPy
- Visualisation des composantes principales
- Kernel PCA (linéaire, RBF, polynôme)

### Partie 3 : Méthodes d'ensemble

- Random Forest pour prédire la survie des poulets
- AdaBoost vs Gradient Boosting sur le gain de poids
- Analyse des performances (accuracy, F1-score)
- Étude de la sensibilité aux outliers

## Technologies utilisées

- Python (NumPy, pandas, matplotlib, seaborn, scikit-learn)
- Jupyter Notebook

## Lancer le projet

1. Cloner le dépôt :
   ```bash
   git clone https://github.com/ton-utilisateur/nom-du-repo.git
   cd nom-du-repo
   ```
2. Installer les dépendances :
   ```bash
   pip install -r requirements.txt
   ```
3. Ouvrir le notebook :
   ```bash
   jupyter notebook TP2.ipynb
   ```

## Résultats attendus

- Visualisation claire des distributions et des outliers
- Interprétation des tests statistiques
- Identification des meilleures composantes principales
- Évaluation des modèles d’ensemble pour des tâches de classification et de régression

## Auteur

Projet réalisé par Gowshigan Selladurai 
