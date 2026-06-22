# Machine Learning Midterm Projects

Repository ini berisi kumpulan project Midterm Machine Learning yang mencakup tiga pendekatan utama dalam machine learning, yaitu:

- Regression
- Classification (Fraud Detection)
- Clustering

Semua project dibuat menggunakan Python dan dikerjakan menggunakan Jupyter Notebook / Google Colab.

---

# Data Diri

| Kategori | Detail |
| :--- | :--- |
| **Nama** | **Rafly Fasha Purnomo Putra** |
| **Kelas** | **TK-46-GAB** |
| **NIM** | **1103223050** |

---

# Repository Structure

```text
Midterm/
│
├── Clustering/
│   ├── Midterm_Clustering.ipynb
│   ├── clusteringmidterm.csv
│   └── README.md
│
├── Fraud Detection/
│   ├── Fraud_Detection.ipynb
│   └── README.md
│
├── Regresi/
│   ├── savemodel-tuned/
│   ├── savemodel/
│   ├── UTS_ML_Regresi.ipynb
│   ├── requirements.txt
│   └── README.md
│
└── README.md
```

---

# Project Overview

## 1. Regression Project

Project regresi bertujuan untuk memprediksi nilai numerik menggunakan beberapa algoritma machine learning regression.

### Model yang Digunakan
- Random Forest Regressor
- XGBoost Regressor
- XGBoost + Optuna Tuning

### Evaluation Metrics
- MAE
- MSE
- RMSE
- R² Score

### File Utama
```text
Regresi/UTS_ML_Regresi.ipynb
```

---

## 2. Fraud Detection Project

Project fraud detection bertujuan untuk mendeteksi transaksi fraud menggunakan metode classification machine learning.

### Model yang Digunakan
- CatBoost Classifier

### Evaluation Metrics
- ROC-AUC Score
- Precision
- Recall
- F1-Score
- Confusion Matrix

### File Utama
```text
Fraud Detection/Fraud_Detection.ipynb
```

---

## 3. Clustering Project

Project clustering bertujuan untuk melakukan customer segmentation menggunakan metode unsupervised learning.

### Model yang Digunakan
- K-Means Clustering

### Evaluation Metrics
- Elbow Method
- Silhouette Score

### File Utama
```text
Clustering/Midterm_Clustering.ipynb
```

---

# Technologies & Libraries

Library yang digunakan pada project ini antara lain:

- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- XGBoost
- CatBoost
- Optuna
- MLflow

---
