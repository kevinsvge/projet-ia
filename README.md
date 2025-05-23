# 🏡 Estimation de prix immobilier avec Machine Learning

Bienvenue dans ce projet de **prédiction de prix immobilier** utilisant des techniques avancées de Machine Learning, optimisé pour le GPU avec XGBoost, et déployé sous forme d’interface web interactive avec Streamlit.

---

## 🎯 Objectifs

- Prédire le **prix de vente d’un bien immobilier** à partir de ses caractéristiques
- Comparer plusieurs modèles de régression (Linear, Random Forest, XGBoost)
- Optimiser les performances avec `GridSearchCV`
- Offrir une **interface web ergonomique** pour tester le modèle avec vos propres données

---

## 🗂️ Structure du projet

```
projet-ia/
├── data/                         # Données source Kaggle
│   └── train.csv
├── models/                       # Modèles sauvegardés (joblib)
│   ├── best_xgboost_model.joblib
│   ├── best_random_forest_model.joblib
│   └── template_columns.csv
├── src/                          # Code source Python
│   ├── data_preparation.py       # Nettoyage et split train/test
│   ├── model_training.py         # Modèles de base
│   ├── model_optimization.py     # GridSearchCV Random Forest
│   └── model_xgboost.py          # GridSearchCV + XGBoost GPU
├── app/
│   └── interface.py              # Interface Streamlit complète
├── main.py                       # Script principal d'entraînement
└── README.md
```

---

## 🛠️ Installation

```bash
conda create -n projet-ia python=3.10
conda activate projet-ia
pip install -r requirements.txt
```

Fichiers requis :
- Données Kaggle : `train.csv`
- Modèles sauvegardés (`main.py` les génère automatiquement)

---

## 🚀 Lancement de l’interface

```bash
streamlit run app/interface.py
```

Fonctionnalités :
- Saisie simplifiée des caractéristiques du bien
- Sélecteur de modèle : `XGBoost` ou `Random Forest`
- Prédiction du prix en temps réel

---

## 🔬 Modélisation et Pipeline

- Prétraitement avec `ColumnTransformer`
- Encodage des variables catégorielles (`map`, `OneHotEncoder`)
- Standardisation des variables numériques
- Modèles testés : `LinearRegression`, `Ridge`, `DecisionTree`, `RandomForest`, `XGBoost`
- Optimisation avec `GridSearchCV` (CPU + GPU)

---

## 📊 Évaluation

📈 Métriques utilisées :
- **MAE** : Mean Absolute Error
- **RMSE** : Root Mean Squared Error
- **R²** : Coefficient de détermination

📉 Exemple de comparaison :
```
🔍 Random Forest
MAE  : 15 478 €
RMSE : 22 096 €
R²   : 0.88

🔍 XGBoost (GPU)
MAE  : 14 950 €
RMSE : 21 450 €
R²   : 0.89
```

---

## 🧠 Technologies utilisées

- Python 3.10
- Scikit-learn
- XGBoost (GPU)
- Streamlit
- Pandas, Matplotlib, Seaborn
- Joblib

---

## ✨ Auteur

Projet réalisé par **Kevin Sauvage** dans une démarche d’apprentissage et de valorisation des compétences en Data Science et IA appliquée.

---

## 📌 À venir (idées d'amélioration)

- 📂 Ajout d’un historique des prédictions
- 🧾 Export PDF ou CSV des résultats
- ☁️ Déploiement sur Streamlit Cloud ou HuggingFace Space
- 🔍 Analyse de SHAP values pour l’interprétabilité du modèle

---

Merci pour votre lecture et bonne exploration du projet ! 🚀
