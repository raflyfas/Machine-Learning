# UTS Machine Learning - Fraud Detection

## Data Diri

| Kategori | Detail |
| :--- | :--- |
| **Nama** | **Rafly Fasha Purnomo Putra** |
| **Kelas** | **TK-46-GAB** |
| **NIM** | **1103223050** |

---

# 1. Tujuan Repositori

Repository ini berisi implementasi end-to-end machine learning pipeline untuk mendeteksi kemungkinan transaksi online yang bersifat fraudulent (fraud detection). Proyek ini dibuat untuk memenuhi tugas UTS Machine Learning dengan memanfaatkan model CatBoost Classifier, hyperparameter tuning menggunakan Optuna, serta experiment tracking menggunakan MLflow.

---

# 2. Gambaran Singkat Proyek

Pada proyek ini dilakukan proses pembangunan pipeline machine learning secara lengkap mulai dari data preprocessing, handling missing values, handling class imbalance, training model, hyperparameter tuning, hingga evaluasi model. Dataset yang digunakan adalah `train_transaction.csv` yang berisi data transaksi online beserta label fraud (`isFraud`). Karena external test dataset dan identity table tidak tersedia, proses evaluasi dilakukan menggunakan train-validation-test split dari dataset yang tersedia.

---

# 3. Dataset

Dataset utama yang digunakan pada proyek ini adalah `train_transaction.csv`. Dataset ini berisi informasi transaksi online seperti nominal transaksi, product code, informasi kartu, alamat, email domain, serta berbagai fitur numerik lainnya yang digunakan untuk memprediksi apakah suatu transaksi termasuk fraud atau bukan.


Link dataset : https://drive.google.com/file/d/1SA1qjgssdA-4Nh_a8C3NEAwIndEMzrYB/view?usp=sharing
---

# 4. Data Preprocessing

Tahapan preprocessing yang dilakukan:

- Menghapus kolom dengan missing value terlalu tinggi
- Mengisi missing values numerik menggunakan median
- Encoding categorical features menjadi numerical values
- Menghapus kolom identifier seperti `TransactionID`
- Membagi dataset menggunakan stratified split

Pembagian dataset:
- 70% Training Set
- 15% Validation Set
- 15% Test Set
---

# 5. Handling Class Imbalance

Karena dataset fraud detection memiliki distribusi class yang tidak seimbang, digunakan:

```python
auto_class_weights='Balanced'
```

untuk membantu model menangani ketidakseimbangan data antara fraud dan non-fraud transaction.

---

# 6. Model dan Hyperparameter Tuning

Model utama yang digunakan:
- CatBoost Classifier

CatBoost Classifier memiliki performa yang baik untuk data tabular serta mampu menangani missing values dengan baik. Untuk meningkatkan performa model, dilakukan hyperparameter tuning menggunakan Optuna dengan beberapa parameter seperti learning rate, depth, dan regularization. Proses tuning dijalankan menggunakan GPU T4 di Google Colab agar proses training lebih cepat.

---

# 7. Evaluation Metrics

Evaluasi model dilakukan menggunakan ROC-AUC Score sebagai metric utama karena cocok digunakan pada kasus fraud detection dengan class imbalance. Selain itu digunakan juga precision, recall, f1-score, accuracy, dan confusion matrix untuk melihat performa model secara lebih detail dalam mendeteksi transaksi fraud.

## ROC-AUC Score

| Metric | Score |
| :--- | :--- |
| Validation ROC-AUC | 0.9592 |
| Test ROC-AUC | 0.9629 |

Hasil ROC-AUC menunjukkan bahwa model memiliki kemampuan yang sangat baik dalam membedakan transaksi fraud dan non-fraud.

---

## Classification Report

| Class | Precision | Recall | F1-Score | Support |
| :--- | :--- | :--- | :--- | :--- |
| Non-Fraud (0) | 0.99 | 0.97 | 0.98 | 85482 |
| Fraud (1) | 0.48 | 0.82 | 0.61 | 3099 |

---

## Overall Metrics

| Metric | Score |
| :--- | :--- |
| Accuracy | 0.96 |
| Macro Average F1-Score | 0.79 |
| Weighted Average F1-Score | 0.97 |

Model memiliki performa yang sangat baik pada class non-fraud dan mampu mendeteksi sebagian besar transaksi fraud dengan recall yang cukup tinggi. Namun precision pada class fraud masih relatif rendah karena masih terdapat false positive pada prediksi fraud transaction.
---

# 8. Visualisasi

Visualisasi yang digunakan pada proyek ini:

- Distribusi Fraud vs Non-Fraud
- Missing Values Visualization
- Transaction Amount Distribution
- ROC Curve
- Feature Importance
---

# 9. MLflow Tracking

MLflow digunakan untuk melakukan experiment tracking selama proses training model. Parameter terbaik dari hasil Optuna, nilai evaluation metric, serta model hasil training dicatat menggunakan MLflow agar proses eksperimen menjadi lebih terstruktur dan reproducible.

---

# 10. Repository Structure / Notebook Navigation

```text
├── Fraud_Detection.ipynb
├── fraud_detection_model.cbm
└── README.md
```

---

# 11. Cara Menjalankan Project

Project ini dapat dijalankan menggunakan Google Colab ataupun Jupyter Notebook. Sebelum menjalankan notebook, install terlebih dahulu library yang dibutuhkan seperti CatBoost, Optuna, MLflow, Scikit-learn, Pandas, NumPy, Matplotlib, dan Seaborn.

```bash
pip install catboost optuna mlflow scikit-learn matplotlib seaborn pandas numpy
```

Jika menggunakan Google Colab, aktifkan GPU T4 melalui menu:

```text
Runtime → Change runtime type → T4 GPU
```

Setelah itu jalankan seluruh cell pada notebook secara berurutan.

---

# 12. Kesimpulan

Model CatBoost berhasil digunakan untuk membangun pipeline fraud detection end-to-end dengan performa evaluasi yang baik menggunakan ROC-AUC sebagai metric utama. Pipeline yang dibuat telah mencakup preprocessing data, handling class imbalance, hyperparameter tuning menggunakan Optuna, evaluasi model, serta experiment tracking menggunakan MLflow sehingga proses machine learning menjadi lebih terstruktur dan mudah direproduksi.
