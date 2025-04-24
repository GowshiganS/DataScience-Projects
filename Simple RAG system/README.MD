# Système RAG basique pour support technique

Un chatbot de support technique basé sur **Retrieval-Augmented Generation** (RAG) permettant de répondre à des questions courantes d’IT (réinitialisation de mot de passe, problèmes réseau, installation de logiciels).  
Le système combine :  
1. **Récupération de documents** via FAISS + embeddings (sentence-transformers)  
2. **Génération de réponses** avec un modèle open-source (distilgpt2)  
3. **Interface utilisateur** simple avec Streamlit  

---

## Table des matières

1. [Fonctionnalités](#fonctionnalités)  
3. [Structure du projet](#structure-du-projet)  
4. [Installation et exécution](#installation-et-exécution)  
   - [Prérequis](#prérequis)  
   - [Installation locale](#installation-locale)  
   - [Exécution avec Streamlit](#exécution-avec-streamlit)  
   - [Exécution avec Docker](#exécution-avec-docker)  
5. [Déploiement sur Azure](#déploiement-sur-azure)  
6. [Améliorations et perspectives](#améliorations-et-perspectives)  
7. [Auteur](#auteur)  

---

## Fonctionnalités

- **Récupération contextuelle** : FAISS + all-MiniLM-L6-v2 pour extraire les FAQ/documents les plus pertinents.  
- **Génération open-source** : pipeline Transformers (distilgpt2) pour produire des réponses adaptées au contexte.  
- **Interface web** : Streamlit pour une démonstration rapide et intuitive.  
- **Conteneurisation** : Dockerfile inclus pour un déploiement reproductible.  
- **Déploiement cloud** : instructions pour Azure Container Instances (ACI) et Azure Container Registry (ACR).

---


---

## Structure du projet

```
Simple RAG system/
├── embeddings_setup.py      # Chargement du modèle, docs, embeddings & index FAISS
├── retrieval.py             # Fonction retrieve_documents(query)
├── generate_response.py     # Fonction generate_response(query, docs)
├── streamlit_app.py         # Front-end Streamlit (app unique)
├── Dockerfile               # Définition du conteneur Docker
├── requirements.txt         # Dépendances Python avec versions
└── README.md                # Ce fichier
```

---

## Installation et exécution

### Prérequis

- Python 3.10+
    
- Git (pour cloner le repo)
    
- (Optionnel) Docker
    

### Installation locale

1. **Cloner le dépôt**
    
    ```bash
    git clone https://github.com/GowshiganS/DataScience-Projects.git
    cd DataScience-Projects/Simple\ RAG\ system
    ```
    
2. **Créer un environnement virtuel**
    
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```
    
3. **Installer les dépendances**
    
    ```bash
    pip install --upgrade pip
    pip install -r requirements.txt
    ```
    

### Exécution avec Streamlit

```bash
streamlit run streamlit_app.py
```

- Ouvrez votre navigateur sur `http://localhost:8501`
    
- Posez vos questions, le chatbot utilisera directement les modules Python (pas d’appel HTTP externe).
    

### Exécution avec Docker

1. **Construire l’image**
    
    ```bash
    docker build -t simple-rag-chatbot .
    ```
    
2. **Lancer le conteneur**
    
    ```bash
    docker run -p 8501:8501 simple-rag-chatbot
    ```
    
3. **Accéder à l’interface**  
    Ouvrez `http://localhost:8501`.
    

---

## Déploiement sur Azure

Ce guide utilise **Azure Container Registry (ACR)** + **Azure Container Instances (ACI)** :

1. **Connexion Azure CLI**
    
    ```bash
    az login
    ```
    
2. **Créer un groupe de ressources**
    
    ```bash
    az group create --name rg-simple-rag --location eastus
    ```
    
3. **Créer un registre de conteneurs**
    
    ```bash
    az acr create --resource-group rg-simple-rag --name acrsimpleRAG --sku Basic
    az acr login --name acrsimpleRAG
    ```
    
4. **Tag & push de l’image**
    
    ```bash
    docker tag simple-rag-chatbot acrsimpleRAG.azurecr.io/simple-rag-chatbot:latest
    docker push acrsimpleRAG.azurecr.io/simple-rag-chatbot:latest
    ```
    
5. **Déployer sur ACI**
    
    ```bash
    az container create \
      --resource-group rg-simple-rag \
      --name rag-instance \
      --image acrsimpleRAG.azurecr.io/simple-rag-chatbot:latest \
      --cpu 1 --memory 1 \
      --ports 8501 \
      --dns-name-label monchatbotrag
    ```
    
6. **Récupérer l’URL publique**
    
    ```bash
    az container show \
      --resource-group rg-simple-rag \
      --name rag-instance \
      --query ipAddress.fqdn \
      --output tsv
    ```
    
    Ouvrez `http://monchatbotrag.eastus.azurecontainer.io:8501`.
    

---

## Auteur

**Gowshigan SELLADURAI**
