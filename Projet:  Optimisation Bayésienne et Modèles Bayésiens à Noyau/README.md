
# TP2 : Optimisation Bayésienne et Modèles Bayésiens à Noyau

Ce projet est un travail pratique réalisé dans le cadre d’un cours de Data Science. Il a pour objectif d’implémenter et d’expérimenter des méthodes d’optimisation bayésienne ainsi que des modèles bayésiens à noyau appliqués à des données agricoles.

Le projet couvre notamment :

- **Optimisation bayésienne** pour maximiser le rendement agricole en fonction des variables climatiques (humidité et température).
- **Optimisation des hyperparamètres** d’un modèle de régression (Random Forest) via Grid Search, Random Search et BayesSearchCV.
- **Régression bayésienne à noyau** (Gaussian Process Regression) avec visualisation des prédictions et des intervalles de confiance.
- **Classification bayésienne à noyau** (Gaussian Process Classification) pour prédire le type de sol (argileux, sableux, limoneux) et comparaison avec un SVM classique.

## Table des matières

- [Installation](#installation)
- [Utilisation](#utilisation)
- [Description des Composants](#description-des-composants)
  - [Optimisation Bayésienne](#optimisation-bayésienne)
  - [Optimisation des Hyperparamètres](#optimisation-des-hyperparamètres)
  - [Régression Bayésienne à Noyau](#régression-bayésienne-à-noyau)
  - [Classification Bayésienne à Noyau](#classification-bayésienne-à-noyau)
- [Données](#données)
- [Auteur](#auteur)
- [Licence](#licence)

## Installation

Ce projet nécessite Python 3.6 ou une version ultérieure. Pour installer les dépendances, exécutez :

```bash
pip install -r requirements.txt
```

Le fichier `requirements.txt` inclut par exemple :
- numpy
- pandas
- matplotlib
- scikit-learn
- scikit-optimize

## Utilisation

1. Clonez ce dépôt sur votre machine :

   ```bash
   git clone https://github.com/votre_utilisateur/nom_du_depot.git
   ```

2. Placez le fichier de données CSV (`tp2_atdn_donnees.csv`) dans le répertoire racine du projet.

3. Lancez le notebook pour visualiser et exécuter le code :

   ```bash
   jupyter notebook TP3.ipynb
   ```

   ou exécutez le script principal :

   ```bash
   python script_principal.py
   ```

Les différents graphiques générés illustrent les prédictions du modèle, les intervalles de confiance et la comparaison entre la classification bayésienne à noyau et un SVM classique.

## Description des Composants

### Optimisation Bayésienne

Cette partie utilise un Gaussian Process pour modéliser une fonction objective (ici, le rendement agricole) et applique une optimisation bayésienne afin d’identifier les conditions optimales (par exemple, l’humidité et la température optimales).

### Optimisation des Hyperparamètres

Différentes méthodes sont comparées pour l’optimisation des hyperparamètres d’un modèle de régression (Random Forest) :
- **Grid Search**
- **Random Search**
- **BayesSearchCV**

Ces approches permettent d’ajuster les paramètres du modèle pour améliorer ses performances prédictives.

### Régression Bayésienne à Noyau

Un modèle de régression utilisant un Gaussian Process est implémenté pour prédire le rendement agricole. Le modèle fournit à la fois des prédictions et des intervalles de confiance, permettant d’identifier les zones où le modèle est moins confiant (souvent en dehors des plages de données d’entraînement).

### Classification Bayésienne à Noyau

Un Gaussian Process Classifier est utilisé pour prédire le type de sol en fonction des variables climatiques. Les résultats obtenus sont comparés à ceux d’un SVM classique pour évaluer la performance des approches bayésiennes.

## Données

Le fichier CSV (`tp2_atdn_donnees.csv`) doit contenir les colonnes suivantes :

- **Humidité (%)** : Taux d'humidité
- **Température (°C)** : Température en degrés Celsius
- **Rendement agricole (t/ha)** : Rendement agricole en tonnes par hectare
- **Type de sol** : Type de sol (argileux, sableux, limoneux) pour la classification

Assurez-vous que les noms des colonnes correspondent exactement à ceux attendus par le code.

## Auteur

- **SELLADURAI Gowshigan**
- [Votre Profil GitHub](https://github.com/GowshiganS)

## Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
