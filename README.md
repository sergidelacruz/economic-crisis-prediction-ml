# 🌍 World Crisis Predictor

In an era marked by multiple crises and uncertainty, historical country data can provide valuable insights for anticipating potential future crises.

In this **Machine Learning** project, we developed a model capable of **predicting the probability that a country will experience a crisis in a given year**, using economic, financial, trade, and labor indicators.

The data used in this project come primarily from **macroeconomic indicators provided by the World Bank**, combined with historical information on financial crises from **Laeven & Valencia (IMF)**, a database that identifies episodes of **systemic financial crises** across different countries and years.

The ultimate goal of the model is to **identify potential crises early**, improving the capacity for analysis and anticipation of adverse economic events.

## 🚀 Project Highlights

• Built a supervised machine learning model to predict financial crises  
• Combined World Bank macroeconomic indicators with IMF crisis data  
• Addressed class imbalance typical of rare crisis events  
• Optimized models to maximize recall for crisis detection  
• Identified key macroeconomic predictors of crisis risk

<hr style="height:6px;border:none;color:#333;background-color:#333;">

## 📑 Table of Contents
---
- [Description](#description)
- [Research Questions](#-research-questions)
- [Methodology](#%EF%B8%8F-methodology)
- [Results](#-results)
- [Key Insights](#-key-insights)
- [Challenges](#%EF%B8%8F-challenges)
- [Repository Structure](#-repository-structure)
- [Tech Stack](#-tech-stack)
- [My Contributions](#-results)
- [Authors](#authors)

## Description

The objective of the project is to predict the probability that a country will enter an economic crisis in a given year based on historical macroeconomic indicators. To achieve this, a supervised classification model was built and trained using economic and financial data from multiple countries.

Since crises are rare events but have a major impact, the model was optimized to prioritize the detection of real crises, minimizing false negatives.

## ❓ Research Questions

• Which macroeconomic indicators are most associated with economic crises?  
• Can machine learning detect early warning signals of financial crises?  
• What trade-off exists between detecting crises and generating false alarms?  

## ⚙️ Methodology

### 1. **Dataset Construction**
 
A dataset was created using World Bank macroeconomic indicators, selected for their relevance in analyzing economic crises.

The variables include indicators related to:

- Financial System and Liquidity
- External Sector
- Debt and External Sustainability
- Economical Activity
- Investment and Capital Formation
- Inflation and Prizes
- Target Feature

The **target variable** was obtained from the financial crisis database compiled by **Laeven & Valencia (IMF)**.

### 2. **Data Preparation**
 
The dataset went through several preprocessing and feature engineering stages:
  - Variable selection and prioritization through correlation analysis and visualization
  - Conceptual grouping of economic indicators
  - Handling missing values
  - Statistical transformation using Yeo-Johnson
  - Removal of low-information variables
  - Exclusion of countries with insufficient data availability

### 3. **Modeling**

Several baseline classification models were trained to predict the occurrence of economic crises and compared:

- Logistic Regression
- Random Forest
- XGB Classifier
- LGBM Classifier
- Cat Boost Classifier

These models were evaluated using cross-validation to ensure robustness. Since crisis are rare but high-impact events, the model was optimized to prioritize **recall of the crisis class** in order to detect as many real crises as possible. 

### 4. **Model Optimization**

Hyperparameter tuning was performed to improve model performance.

Evaluation metrics included:

- Precision
- Recall
- F1-score

Special attention was given to recall for the crisis class.

## 📊 Results

The model was evaluated using precision, recall, and F1-score for both classes:
- Class 0: No crisis
- Class 1: Economic crisis

Since the main goal of the project is to **detect as many real crises as possible**, the model prioritizes **maximizing recall for the positive class (crisis)**, even if this results in a higher number of false positives.

This behavior is expected and desirable in risk prediction problems, where **failing to detect a crisis (false negative) is much more costly than generating a false alarm**.

The Extreme Gradient Boosting model achieved the best performance (recall = 0.84, ROC-AUC = 0.797), balancing sensitivity to crisis events with acceptable false positive rates.

<img width="691" height="547" alt="curva_ROC_XGBoost" src="https://github.com/user-attachments/assets/10660120-e083-430c-9104-e0d670451b94" />

The final model therefore prioritizes:

✔ High sensitivity to economic crises  
✔ Early warning capability  
⚠ At the cost of generating more crisis predictions that may not actually occur  

This approach is common in **financial or economic early warning models**, where the primary objective is **not to overlook critical events**.

---

## 🔑 Key Insights

Some macroeconomic indicators appear to be strongly associated with crisis events, including:

- external debt growth  
- inflation instability  
- financial sector stress indicators  

Countries experiencing rapid credit expansion were significantly more likely to enter crisis periods in subsequent years. These results are consistent with economic literature on crisis early warning systems. 

---

## ⛰️ Challenges 

Predicting economic crises presents several difficulties:

• Crises are rare events (class imbalance)  
• Macroeconomic indicators are often delayed  
• Countries have structural economic differences  

These factors limit the predictive power of purely data-driven models.

## 📂 Repository Structure
```
src/  
│
├── data_sample/  
│   Muestra del dataset utilizado (máx. 5MB)  
├── img/  
│   Gráficos e imágenes generadas durante el proyecto  
│
├── models/  
│   Modelos entrenados guardados en formato joblib o pickle  
│
├── notebooks/  
│   Notebooks utilizados para exploración, desarrollo y experimentación  
│
└── utils/  
    Código auxiliar reutilizable (funciones, clases y scripts)

README.md
main.ipynb
presentacion.pdf
```

---

## 🛠 Tech Stack

**Languages:**: `python`

**Main libraries**: `numpy, pandas, scikit-learn, matplotlib, seaborn, (incluir modelos)`

---

## My Contributions
 
• Exploratory data analysis  
• Training and evaluation of classification models  

## Authors

Francisco de las Cuevas  
Sandra García Moreno   
Sergi de la Cruz Núñez 
