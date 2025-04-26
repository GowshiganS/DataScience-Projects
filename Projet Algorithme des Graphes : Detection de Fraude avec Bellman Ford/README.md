# Détection de Fraude sur Transactions – Analyse par Graphe

![Python](https://img.shields.io/badge/python-3.10-blue?logo=python)
![License](https://img.shields.io/badge/license-MIT-green)

> **Projet académique (M1 Data Science)** — démonstration de détection de transactions frauduleuses via **analyse de graphe** et heuristiques de scoring. Notebook principal : `Projet_Detection_Fraude_Notebook.ipynb`.

---

## Sommaire

1. [Contexte](#contexte)
2. [Approche](#approche)
3. [Structure du dépôt](#structure-du-dépôt)
4. [Installation](#installation)
5. [Lancement rapide](#lancement-rapide)
6. [Résultats](#résultats)
7. [Roadmap & TODO](#roadmap--todo)
8. [Crédits](#crédits)

---

## Contexte

Les systèmes de paiement décentralisés génèrent des graphes de transactions où chaque nœud représente un compte et chaque arête représente une transaction monétaire. L’objectif est de **repérer les schémas anormaux** (cycles rapides, montants fractionnés, hubs suspects) indicateurs d’activités frauduleuses.

Dans ce prototype :

- **Jeu de données synthétique** créé pour illustrer différentes typologies de fraude (boucle de blanchiment, layering, etc.).
- Utilisation de `networkx` pour construire un graphe orienté et appliquer des heuristiques :
  - Score de risque par arête : combinaison du montant, de la récurrence et de la centralité des nœuds.
  - Détection de cycles courts de moyenne négative.
- Visualisation interactive via `matplotlib`.

## Approche

<p align="center">
  <img src="docs/graph_pipeline.png" width="70%" alt="Pipeline"/>
</p>

1. **Préparation des données**
   - Génération ou ingestion d’un CSV `transactions.csv` (`nameOrig`, `nameDest`, `amount`, `isFraud`).
   - Nettoyage minimal (noms normalisés, montants > 0).
2. **Construction du graphe**
   - `G = nx.DiGraph()` avec attributs `weight`, `fraud`, `risk_score`.
3. **Scoring & règles**
   - Fonction `compute_risk_score()` agrège : z‑score montant, degré sortant, densité de boucle.
4. **Détection d’anomalies**
   - Étiquetage en « frauduleux » si `risk_score > τ`.
5. **Visualisation et rapport**
   - Arêtes rouges = suspectes, étiquette du score sur le graphe.

## Structure du dépôt

```text
.
├── data/                # (optionnel) jeux de données externes
├── notebooks/
│   └── Projet_Detection_Fraude_Notebook.ipynb
├── src/                 # modules réutilisables
│   ├── graph_utils.py
│   └── scoring.py
├── docs/                # figures pour le README / présentations
├── requirements.txt
└── README.md            # vous êtes ici ✨
```

## Installation

> Pré‑requis : **Python ≥ 3.9**, `git`, `virtualenv` ou `conda`.

```bash
# 1. Cloner le dépôt
$ git clone https://github.com/<votre-username>/projet-detection-fraude.git
$ cd projet-detection-fraude

# 2. Créer un environnement
$ python -m venv .venv
$ source .venv/bin/activate  # Windows: .venv\Scripts\activate

# 3. Installer les dépendances
$ pip install -r requirements.txt
```

`requirements.txt`
```text
pandas
networkx
matplotlib
numpy
jupyter
```

## Lancement rapide

```bash
# 1. Démarrer le notebook
$ jupyter notebook notebooks/Projet_Detection_Fraude_Notebook.ipynb

# 2. Exécuter toutes les cellules (Kernel ▶ Run All)
```

Le graphe s’affiche avec les arêtes suspectes en **rouge** et le score de risque en label.

<p align="center">
  <img src="docs/demo_graph.png" width="60%" alt="Demo"/>
</p>

## Résultats

| Métrique | Valeur (jeu synthétique) |
|----------|--------------------------|
| Précision | 0.92 |
| Rappel    | 0.88 |
| F1‑score  | 0.90 |

*(Ces chiffres dépendent du seuil τ choisi – voir cellule « Hyperparamètres ».)*

## Roadmap & TODO

- [ ] Intégrations d'autres modèles pertients 
- [ ] Benchmarker sur un vrai dataset public (PaySim dataset Kaggle).
- [ ] Déployer une démo .

## Crédits

Ce notebook a été réalisé dans le cadre du Master OIVM — parcours **Data Science & Systèmes Distribués** (UPEC).

- **Auteur** : Gowshigan Selladurai — [@GowshiganS](https://github.com/GowshiganS)
- **Contact** : gowshigan.selladurai@gmail.com

License MIT — voir `LICENSE` pour le détail.

