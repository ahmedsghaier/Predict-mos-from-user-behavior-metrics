# Predict-mos-from-user-behavior-metrics
## 🧠 Description du Projet

Ce projet vise à prédire automatiquement le Mean Opinion Score (MOS) - une mesure subjective de la qualité perçue d'une page web - en utilisant des techniques de Machine Learning et Deep Learning. Le MOS est traditionnellement évalué via des enquêtes utilisateurs coûteuses et chronophages. Notre approche propose une alternative automatisée basée sur l'analyse des données comportementales des utilisateurs.

## 🚀 Objectifs du Projet

- Développer un modèle capable de prédire le MOS à partir de métriques comportementales
- Comparer différentes architectures de ML et DL pour identifier la plus performante
- Fournir un outil d'évaluation automatique de l'expérience utilisateur (UX) pour les sites web

## 📊 Dataset

Le jeu de données comprend 10,376 observations de sites web avec les caractéristiques suivantes :

- Durée moyenne des visites (Avg. Visit Duration)
- Pages par visite (Pages/Visit)
- Taux de rebond (Bounce Rate)
- Changement de classement (Rank Change)
- 194 catégories uniques réparties en 23 catégories principales

## 🔧 Prétraitement des Données

  - **Nettoyage** : Gestion des valeurs manquantes et conversion des formats
  - **Feature Engineering** :  Création d'un score MOS synthétique basé sur :
     - Durée de visite (40%)
     - Pages vues (30%)
     - Taux de rebond inversé (30%)
  - **Normalisation** : Application de Min-Max scaling [0,1]
  - **Split** : 80% entraînement / 20% test avec validation croisée K-Fold

  ## 🤖 Modèles Implémentés

  ### Machine Learning

  - **Random Forest** : Méthode ensembliste d'arbres de décision
  
  ### Deep Learning

  - **Autoencoder** : Réduction de dimensionnalité et extraction de features
  - **MLP (Multilayer Perceptron)** : Réseau neuronal feedforward
  - **MLP + Autoencoder** : Combinaison hybride (meilleure performance)
  - **Wide and Deep** : Architecture combinant mémorisation et généralisation
  - **TabNet** : Architecture avec mécanisme d'attention pour données tabulaires

 ## 📈 Résultats 


| Model | MAE  | MSE  | R²  |
|-------|-------|-------|------|
| Autoencoder | 0.0100 | 0.0004 | 0.5100 |
| MLP | 0.0100 | 0.1000 | 0.8800 |
| RF + Autoencoder | 0.1730 | 0.0670 | 0.9200 |
| **MLP + Autoencoder** | **0.1059** | **0.0310** | **0.9600** |
| TabNet | 0.0316 | 0.1777 | 0.9600 |
| Wide & Deep | 0.0150 | 0.0066 | 0.9150 |

🏆 **Meilleur modèle : MLP + Autoencoder** avec un R² de 0.96, offrant le meilleur compromis entre précision et complexité.

## 📊 Métriques d'Évaluation

- **MAE (Mean Absolute Error)** : Erreur absolue moyenne
- **MSE (Mean Squared Error** : Erreur quadratique moyenne
- **RMSE (Root Mean Squared Error)** : Racine de l'erreur quadratique
- **R² (Coefficient de Détermination)** : Proportion de variance expliquée

## 🧩 Technologies utilisées

- **Langage** : Python 🐍
- **Bibliothèques** : NumPy, Pandas, Matplotlib, Seaborn,Scikit-learn,TensorFlow / Keras
- **Outils d’évaluation et visualisation** : Jupyter Notebook, Google Colab
