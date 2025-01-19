# Projet 2 : Machine Learning appliqué aux données textuelles

## Description du Projet

Ce projet explore l’utilisation de techniques de Machine Learning pour l’analyse et la classification de données textuelles. Il vise à fournir une compréhension pratique des différents étapes de préparation et d’analyse des données textuelles, ainsi que de leur classification à l'aide d'algorithmes d'apprentissage supervisé.

## Objectifs

- Prétraiter les données textuelles en utilisant des techniques modernes.
- Implémenter des modèles de classification supervisée pour détecter des spams dans un jeu de données.
- Évaluer les performances des modèles avec des métriques standards telles que la précision, le rappel et le score F1.

## Contenu

1. **Préparation des données** :

    - Chargement et exploration des données textuelles (fichier `spam.csv`).
    - Nettoyage et normalisation des textes.

2. **Extraction de caractéristiques** :

    - Représentation des textes à l’aide de méthodes comme le Bag-of-Words (BoW) et TF-IDF.

3. **Modélisation** :

    - Implémentation de modèles tels que Naive Bayes, Random Forest ou SVM pour la classification des spams.

4. **Evaluation des modèles** :

    - Calcul des métriques de performance.
    - Comparaison des performances des différents modèles.

## Fichiers

- **`Projet_2.ipynb`** : Notebook principal contenant le code et les analyses.
- **`spam.csv`** : Jeu de données contenant des SMS marqués comme spam ou non.

## Dépendances

Assurez-vous d’avoir les librairies suivantes installées avant d’exécuter le notebook :

```bash
pip install numpy pandas matplotlib scikit-learn
```

## Instructions pour l’exécution

1. Clonez ce dépôt :

    ```bash
    git clone <>
    ```

2. Naviguez dans le répertoire :

    ```bash
    cd Projet 2: Machine Learning appliqué aux données textuelles
    ```

3. Installez les dépendances :

    ```bash
    pip install -r requirements.txt
    ```

4. Lancez le notebook avec Jupyter :

    ```bash
    jupyter notebook Projet_2.ipynb
    ```

## Aperçu des Visualisations

Le notebook fournit des visualisations des données textuelles ainsi que des matrices de confusion pour illustrer les performances des modèles.

## Structure du Code

1. **Prétraitement des données** :

    - Nettoyage et normalisation des textes.
    - Division des données en ensembles d’entraînement et de test.

2. **Extraction de caractéristiques** :

    - Transformation des données textuelles en vecteurs numériques avec TF-IDF.

3. **Entraînement des modèles** :

    - Implémentation de plusieurs modèles supervisés.

4. **Evaluation des modèles** :

    - Analyse des performances avec des métriques comme la précision, le rappel et le score F1.

## Licence

Ce projet est sous licence MIT. Vous êtes libre de l’utiliser, de le modifier et de le distribuer tout en respectant les termes de la licence.

## Contributions

Les contributions sont les bienvenues ! Si vous souhaitez améliorer ce projet, n’hésitez pas à ouvrir une pull request ou à soumettre une issue.

## Auteur

Ce projet a été réalisé par SELLADURAI Gowshigan. N’hésitez pas à me contacter pour toute question ou suggestion.


