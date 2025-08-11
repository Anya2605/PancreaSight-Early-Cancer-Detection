# 🧬 PancreaSight – Early Detection of Pancreatic Cancer using Machine Learning

Pancreatic cancer is one of the most lethal cancers due to late diagnosis and lack of early symptoms. This project, named **PancreaSight**, aims to detect pancreatic cancer at an early stage using machine learning models trained on real-world biomarker data. The objective is to build a predictive model that differentiates between healthy individuals, patients with non-cancerous pancreatic conditions, and those with pancreatic ductal adenocarcinoma (PDAC).

---

## 📊 Dataset Overview

This dataset is derived from the open-access research paper by Silvana Debernardi et al., published in PLOS Medicine (2020). The dataset contains **590 patient samples** covering multiple diagnostic groups.

### 🔬 Study Background

- Pancreatic cancer has a <10% five-year survival rate, primarily due to late detection.
- The dataset contains urine biomarker data from three groups:
  - Healthy individuals
  - Patients with non-cancerous pancreatic conditions (e.g., chronic pancreatitis)
  - Patients with pancreatic ductal adenocarcinoma (PDAC)

### 🧪 Key Features

- **Urinary Biomarkers:**
  - `creatinine`: indicator of kidney function
  - `LYVE1`: involved in tumor metastasis
  - `REG1B`: associated with pancreas regeneration
  - `TFF1`: supports urinary tract repair
- **Additional Features:**
  - `age`, `sex`, `sample_origin`, `patient_cohort`
  - `plasma_CA19_9`: blood biomarker (partial data)
  - `diagnosis`: 1 = Healthy, 2 = Benign, 3 = Cancer

---

## 🧼 Data Preprocessing

- Removed columns: `sample_id`, `benign_sample_diagnosis`
- Handled missing values with mean imputation
- Label encoding for categorical variables
- Feature scaling using MinMaxScaler and StandardScaler

---

## 🧠 Models Trained

| Model              | Accuracy (Validation) | Accuracy (Test) |
|--------------------|------------------------|------------------|
| LightGBM           | 89.83%                 | —                |
| Random Forest      | 91.53%                 | 82.22%           |
| Extra Trees        | **92.37%**             | **88.98%**       |
| XGBoost            | 88.98%                 | —                |
| Voting Classifier  | 90.68%                 | —                |

✅ **Best Test Accuracy:** 88.98% (Extra Trees Classifier)

---

## 📈 Evaluation Metrics

- Accuracy, Precision, Recall, F1-Score
- Root Mean Squared Error (RMSE)
- Relative Absolute Error (RAE)
- Root Relative Squared Error (RRSE)
- Confusion Matrix for classification analysis

---

## 🔍 Feature Importance

Feature importance was computed using the Extra Trees Classifier.  
Top contributing features included:

- `LYVE1`
- `REG1B`
- `TFF1`
- `plasma_CA19_9`

---

## 📂 Libraries Used

- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `sklearn` (RandomForest, ExtraTrees, train_test_split, metrics)
- `xgboost`, `lightgbm`

---

## 📁 File Info

Dataset: `Debernardi et al 2020 data.csv`  
License: CC-BY (open access)

