### 📄 `README.md`

```markdown
# 🏠 House Price Prediction — End-to-End Machine Learning Project
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## 🚀 Project Summary

**Goal:** Predict house prices from structured real-estate features.  
**Approach:** Preprocessing + Regression (core) + Classification (interpretability) + Unsupervised (segmentation).  
**Deliverables:** Clean pipeline notebooks, evaluation, and a production-oriented monitoring plan.

## 📌 Project Overview
This project implements an end-to-end machine learning pipeline to analyze and predict house prices using structured real-estate data. The objective is not only to achieve accurate price predictions, but also to explore alternative problem framings (classification) and uncover hidden market structures (unsupervised learning).

The project is designed to reflect **real-world machine learning workflows**, from data preprocessing to model evaluation and interpretation.

---

## 📊 The Dataset

This pipeline processes a massive housing dataset containing 80+ variables regarding property zoning, material quality, basement specifications, and geospatial coordinates. 

* 🎯 **Target Variable:** `price` (Continuous)
* 📖 **Full Feature Definitions:** Please refer to the [DATA_DICTIONARY.md](./DATA_DICTIONARY.md) file for a complete breakdown of all categorical and numerical features used in this pipeline.

---

## 🎯 Objectives
- Predict house prices using supervised regression models.
- Explore price categorization through classification to aid business decision-making.
- Identify latent patterns in the housing market using advanced unsupervised learning.
- Demonstrate clean ML architecture and professional documentation.

---

## 🧱 Project Architecture

```text
Raw Dataset
    ↓
Data Cleaning & Feature Engineering
    ↓
Train / Validation Split
    ↓
Regression Models (Price Prediction)
    ↓
Classification Models (Price Categories)
    ↓
Unsupervised Learning (Market Segmentation)
    ↓
Evaluation & Insights

```

This modular structure allows each stage of the pipeline to be analyzed, improved, or extended independently.

---

## 📂 Repository Structure

```text
├── 01_PREPROCESSING.ipynb
├── 02_REGRESSION.ipynb
├── 03_CLASSIFICATION.ipynb
├── 04_UNSUPERVISED.ipynb
├── README.md
├── requirements.txt

```

### Notebook Descriptions

* **01_PREPROCESSING.ipynb**
Data cleaning, handling high-nullity columns, low variance filtering, handling extreme outliers (using Z-scores), categorical encoding, feature scaling, and feature engineering.
* **02_REGRESSION.ipynb**
Supervised regression models (Linear, Ridge, RandomForest, XGBoost, LightGBM, CatBoost) to predict continuous house prices. Includes robust evaluation (RMSLE, RMSE, R²) and Hyperparameter Tuning using GridSearchCV.
* **03_CLASSIFICATION.ipynb**
Reformulation of the problem into price categories (Low / Medium / High) using discretized target variables. Evaluates Tree-based models (Random Forest, XGBoost) utilizing F1-Weighted scores and Confusion Matrices.
* **04_UNSUPERVISED.ipynb**
Clustering techniques to identify natural groupings. Explores K-Means (with the Elbow Method) and advanced non-linear dimensionality reduction combined with density-based clustering (UMAP + HDBSCAN).

---

## 🧪 Data Preprocessing

Real-estate data typically contains heterogeneous features, missing values, and categorical attributes. This project applies systematic preprocessing:

* **Missing Value Handling:** Dropped high-nullity columns.
* **Low Variance Removal:** Filtered features with near-zero variance.
* **Outlier Removal:** Removed extreme outliers based on robust Z-score thresholds to ensure stable model training.
* **Feature Engineering:** Derived impactful domain-specific features (e.g., HouseAge, TotalBath).

---

## 📈 Regression Modeling

Regression is the primary modeling approach, focusing on precisely estimating the continuous `SalePrice`.

* **Metrics:** RMSLE (primary), RMSE, and R².
* **Best Models:** After exhaustive GridSearchCV hyperparameter tuning, **CatBoost** and **XGBoost** emerged as the top performers.
* *CatBoost (Tuned):* Test RMSLE: **0.1283**, Test R²: **0.9219**
* *XGBoost (Tuned):* Test RMSLE: **0.1279**, Test R²: **0.9197**


* **Insight:** Tree-based ensemble models significantly outperformed baseline linear models in capturing non-linear relationships and interactions.

---

## 🧮 Classification Modeling

House prices were discretized into Low, Medium, and High categories to explore a business-driven classification perspective.

* **Why classification?** It improves interpretability for non-technical stakeholders (e.g., categorizing homes into distinct market segments).
* **Models:** Evaluated Random Forest Classifier vs. XGBoost Classifier.
* **Insight:** **XGBoost** provided superior robust generalization and outperformed the Random Forest. If hardware capacity and training time are not constraints, XGBoost stands out as the optimal choice.

---

## 🔍 Unsupervised Learning

Unsupervised techniques were used to identify hidden structures in the data without relying on price labels.

* **Techniques:** K-Means vs. UMAP + HDBSCAN.
* **Insight:** While K-Means offered a fast baseline, **UMAP combined with HDBSCAN** successfully isolated dense, organically shaped market segments while accurately flagging highly irregular properties as noise. This proved to be the superior choice for strategic, real-world market segmentation.

---

## 📊 Key Results & Insights

* **Predictive Power:** Tuned ensemble models (XGBoost/CatBoost) yield highly accurate and consistent numerical price estimates ($R^2 > 0.91$).
* **Market Positioning:** Classification models effectively map properties to budget tiers, complementing precise valuations.
* **Latent Segments:** Density-based clustering (HDBSCAN) reveals realistic, non-linear property segments and uniquely identifies market anomalies.

---

## ⚠️ Limitations

* Dataset size and quality may limit generalization to other geographic markets.
* Feature availability restricts external factors (e.g., macroeconomic indicators, mortgage rates).

---

## 🚀 Future Improvements

* Feature importance and explainability (e.g., SHAP values).
* Model deployment (API) with monitoring/retraining strategies.

---

## 🧠 Skills & Tools

* **Techniques:** Preprocessing, Feature Engineering, Supervised Learning (Regression/Classification), Unsupervised Learning (Clustering, Dimensionality Reduction).
* **Stack:** Python, pandas, NumPy, scikit-learn, XGBoost, LightGBM, CatBoost, UMAP, HDBSCAN, Matplotlib, Plotly, Seaborn.

---

## ⚡ Quickstart

1. Clone repo
2. Install dependencies: `pip install -r requirements.txt`
3. Data Setup:
- Download the full dataset from [Link to Kaggle](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data).
- Extract the file and place housing_data.csv into the /data/raw/ directory.
4. Run notebooks in order:
* `01_PREPROCESSING.ipynb`
* `02_REGRESSION.ipynb`
* `03_CLASSIFICATION.ipynb`
* `04_UNSUPERVISED.ipynb`



---

📬 *Feel free to explore the notebooks or reach out for questions or collaboration.*

```
