# Rossmann Store Sales — EDA + Feature Engineering (WIP)

## 📌 Overview
This project explores and models the **Rossmann Store Sales** dataset from Kaggle.  
The goal is to predict daily sales for Rossmann stores using historical sales, promotions, holidays, and store metadata.  

## 📊 Current Progress (v0.1)
- ✅ **Step 1: Import & Load**
  - Loaded `train.csv`, `test.csv`, `store.csv`
- ✅ **Step 2: Quick Peek**
  - Checked shapes, dtypes, missing values
- ✅ **Step 3: Exploratory Data Analysis**
  - Sales are right-skewed → plan to model on `log1p(Sales)`
  - Mondays show highest sales; Sundays near zero (mostly closed)
  - Promotions lift sales significantly
  - School holidays cause a small dip
- ✅ **Step 4: Data Preparation & Feature Engineering**
  - Merged `store.csv` metadata into train/test
  - Handled missing values  
    - `CompetitionDistance` → filled with large value (1,000,000) for “no competitor”  
    - Competition open dates → filled with 0  
    - Promo2 fields → filled with 0 or `"None"`  
  - Created time-based features: `Year`, `Month`, `Day`, `WeekOfYear`  
  - Created log-transformed target: `Sales_log = log1p(Sales)` (train only)  

## 📥 Data
This project uses the [Rossmann Store Sales dataset](https://www.kaggle.com/competitions/rossmann-store-sales) from Kaggle.  

➡️ Download these files and place them in a local `data/` folder (kept out of GitHub for size reasons):  
- `train.csv`  
- `test.csv`  
- `store.csv`  
- `sample_submission.csv`  

## 🚀 Next Steps
- Step 5: Train a baseline LightGBM model with time-aware validation  
- Evaluate baseline RMSPE and generate `submission.csv` for Kaggle  
- Add richer features: Promo2 active flag, months since competition, lagged and rolling sales features  
- Refine cross-validation with time-series folds  

## 📌 Note
This repository is a **work in progress**. Current milestone covers data exploration and feature preparation (Steps 1–4). Upcoming commits will expand to modeling and Kaggle submissions.

