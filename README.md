# 🚄 SNCF Train Delay Prediction & Analysis

## 📌 Overview
This project focuses on **analyzing and predicting train delays** for **SNCF TGVs** using machine learning techniques. It aims to help both **passengers** and **railway operators** anticipate and understand delays better.

We explore **three key aspects** of train delays:
1. **Predicting delays one month in advance** 📅
2. **Predicting delays after departure** 🚉
3. **Classifying causes of delays after they occur** 🔍



## 🔬 Methodology & Techniques
### **1️⃣ Predicting Delays One Month in Advance**
- **Hypothesis:** Future delays are linked to historical patterns.
- **Feature Engineering:**
  - Train station departure & arrival times
  - Monthly seasonality effects
  - COVID-19 impact on train schedules
  - Delays from previous months
- **Preprocessing Techniques:**
  - Handling missing values
  - Tukey’s method for outlier detection
  - MinMax Scaling for numerical features
  - One-Hot Encoding for categorical variables
- **Machine Learning Models:**
  - **Random Forest** 
  - **XGBoost** 
  - **K-Nearest Neighbors (KNN)** 
- **Results:**  
  - **Mean Absolute Error (MAE):** ~2 minutes on test set.
  - **XGBoost slightly outperformed Random Forest.**

### **2️⃣ Predicting Delays After Departure**
- **Use case:** A train is already late—how late will it be at arrival?
- **Methodology:**
  - Model estimates delay evolution based on train priority and historical trends.
  - Trains are categorized as **"prioritized"** (can make up lost time) or **"non-prioritized"** (will accumulate more delay).
- **Best Model:** **Random Forest**, fine-tuned using Grid Search.
- **Findings:**
  - More accurate predictions for **prioritized trains**.
  - Larger variance in delays for non-prioritized trains.

### **3️⃣ Classifying Delay Causes**
- **Objective:** Identify **why** a train was delayed (external causes, infrastructure issues, passenger-related delays, etc.).
- **Features Used:**
  - Number of delayed trains
  - Historical delay trends
  - External factors (weather, strikes, technical issues)
- **Model Performance:**
  - **Best Model:** XGBoost (outperformed baseline models by **12%**).
  - RMSE affected by **external factors (e.g., weather, strikes)** that are harder to predict.

