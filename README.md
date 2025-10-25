# 📊 Bitcoin Market Analysis

> Analyse complète des corrélations entre Bitcoin et les marchés financiers traditionnels avec visualisations interactives animées

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## 📋 Table des matières

- [Aperçu](#aperçu)
- [Fonctionnalités](#fonctionnalités)
- [Structure du projet](#structure-du-projet)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Visualisations](#visualisations)
- [Données](#données)
- [Technologies](#technologies)

## 🎯 Aperçu

Ce projet analyse les relations entre Bitcoin et différents actifs financiers (S&P 500, NASDAQ, Or, Pétrole) sur la période 2022-2025. Il génère des visualisations interactives animées permettant d'explorer l'évolution des corrélations dans le temps et l'impact des événements macroéconomiques.

### Points clés analysés

- **Corrélations dynamiques** entre BTC et les marchés traditionnels
- **Bitcoin Dominance** (part de BTC dans le marché crypto total)
- **Régressions linéaires** animées pour visualiser l'évolution des relations
- **Impact des événements** : guerre Ukraine, hausse des taux Fed, ETF Bitcoin, halving, élections US

## ✨ Fonctionnalités

- 🔄 Pipeline ETL automatisé (extraction Yahoo Finance + CSV, transformation, chargement)
- 📊 5 visualisations interactives avec animations temporelles
- 🎨 Heatmaps de corrélation avec sélecteur de périodes
- 📈 Rolling correlation sur fenêtre glissante de 30 jours
- 🎯 Analyses de régression dynamiques avec calcul du β (bêta)
- 🗓️ Annotations d'événements économiques et crypto
- 💾 Export CSV et HTML pour réutilisation et partage

- 

## 📁 Structure du projet
crypto_analysis/
  ├── POLISHED_FINAL.ipynb # Notebook principal
  ├── DATASETS/ # Données d'entrée
  │ ├── btc_cap_price.csv # Prix et market cap BTC
  │ └── global_crypto_cap.csv # Market cap crypto total
  ├── OUTPUTS/ # Fichiers générés
  │ ├── CSV/
  │ │ └── Merged_df.csv # Dataset fusionné
  │ └── HTML/ # Visualisations interactives
  │ ├── 1_correlation_matrix.html
  │ ├── 2_btc_spx_rolling_corr_dynamic.html
  │ ├── 3_btc_dominance_price_animated.html
  │ ├── 4_regression_btc_sp500_animated.html
  │ └── 5_regression_btc_gold_animated.html
  └── requirements.txt # Dépendances Python


## 🚀 Installation

### Prérequis

- Python 3.8 ou supérieur
- Jupyter Notebook / JupyterLab
- Connexion internet (pour télécharger les données Yahoo Finance)

### Étapes d'installation
- Cloner le repository
  
git clone https://github.com/votre-username/crypto-analysis.git
cd crypto-analysis

- Installer les dépendances
pip install -r requirements.txt


Le fichier **requirements.txt** contient : pandas, numpy, yfinance, plotly, scipy, jupyter

## 💻 Utilisation

### Démarrage rapide

1. Placer les fichiers CSV dans le dossier `DATASETS/`
2. Lancer Jupyter : `jupyter notebook POLISHED_FINAL.ipynb`
3. Exécuter toutes les cellules : `Cell → Run All`
4. Ouvrir les visualisations générées dans `OUTPUTS/HTML/`

### Paramètres configurables

Le notebook permet de modifier facilement la période d'analyse, les actifs étudiés, et la fenêtre de corrélation roulante dans la section Configuration.

## 📊 Visualisations

### 1. Matrice de corrélation interactive
Heatmap avec échelle de couleurs personnalisée, sélecteur de périodes (période complète, dernière année, 2024, 90j, 30j, événements spécifiques), et annotations dynamiques avec valeurs de corrélation.

### 2. Corrélation roulante BTC vs S&P 500
Animation temporelle avec slider et contrôles play/pause, marqueurs d'événements avec zones colorées par période, variations dynamiques affichées pour chaque période, et prix en temps réel.

### 3. Bitcoin Dominance & Prix
Dual-axis chart avec dominance (%) et prix (USD), moyenne mobile 30 jours pour filtrer le bruit, et animation progressive avec étiquettes dynamiques.

### 4-5. Régressions animées (BTC vs S&P 500 / Or)
Scatter plots avec points colorés par période d'événement, ligne de régression évolutive recalculée à chaque frame, et statistiques en temps réel (β, R², p-value, équation).

## 📁 Données

### Sources
- **Yahoo Finance (API yfinance)** : prix de clôture quotidiens des actifs, téléchargement automatique
- **CSV fournis** : btc_cap_price.csv (historique prix et market cap Bitcoin) et global_crypto_cap.csv (market cap total crypto)

### Format des fichiers CSV

Le fichier `btc_cap_price.csv` doit contenir les colonnes : date, price, market_cap. Le fichier `global_crypto_cap.csv` doit contenir : date (timestamp en millisecondes), total_market_cap.

## 🛠️ Technologies

- **pandas** : manipulation et analyse de données
- **numpy** : calculs numériques (log returns, matrices)
- **yfinance** : téléchargement données financières
- **plotly** : visualisations interactives (graphiques animés)
- **scipy** : analyses statistiques (régressions, corrélations)
- **pathlib** : gestion des chemins cross-platform

## 📈 Structure du Notebook

| Section | Description | Sorties |
|---------|-------------|---------|
| **1️⃣ Configuration** | Imports, chemins, paramètres, événements | Variables globales |
| **2️⃣ Functions** | Fonctions réutilisables (nettoyage, corrélations, régressions) | 9 fonctions |
| **3️⃣ ETL Pipeline** | Extract → Transform → Load → Export | Merged_df.csv |
| **4️⃣ Calculations** | Corrélations, rolling metrics, préparation régression | Matrices, séries |
| **5️⃣ Visualizations** | Création des 5 graphiques interactifs | 5 fichiers HTML |



---



