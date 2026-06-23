# Machine Learning FinalTermProjects

## Data Diri

| Kategori | Detail |
| :--- | :--- |
| **Nama** | **Rafly Fasha Purnomo Putra** |
| **Kelas** | **TK-46-GAB** |
| **NIM** | **1103223050** |

---

## Deskripsi Proyek

Notebook ini berfokus pada implementasi **Fraud Detection** menggunakan pendekatan Machine Learning. Tujuan utama dari proyek ini adalah membangun model yang mampu mengidentifikasi transaksi yang berpotensi sebagai fraud berdasarkan pola data historis.

---

## Alur Pengerjaan (Pipeline)

### Fraud Detection Assignment
Implementasi end-to-end deteksi fraud menggunakan MLFlow dan Optuna.
- (Code) # Re-installing libraries quietly for the T4 runtime session...
- (Code) import pandas as pd...
- (Code) drive.mount('/content/drive', force_remount=True)...

### Exploratory Data Analysis (EDA)
Mari kita lihat distribusi target `isFraud` dan korelasi antar fitur.
- (Code) plt.figure(figsize=(6,4))...

### Analisis Distribusi Target
Grafik di atas menunjukkan bahwa dataset sangat tidak seimbang (*imbalanced*). Mayoritas transaksi (~96.5%) adalah normal (0), sedangkan transaksi fraud (1) hanya sekitar 3.5%. Hal ini sangat penting karena model ML cenderung mengabaikan kelas minoritas jika tidak ditangani dengan benar.
- (Code) plt.figure(figsize=(15, 5))...

### Data Preprocessing
Langkah ini mencakup penanganan missing values dan encoding variabel kategorikal.
- (Code) # Identifikasi kolom dengan banyak missing values...

### Data Splitting
Sebelum melakukan training, kita memisahkan data menjadi **Training Set** (untuk melatih model) dan **Test Set** (untuk menguji performa model pada data yang belum pernah dilihat).
- (Code) from sklearn.model_selection import train_test_split...
- (Code) # Preprocessing: Drop columns with > 50% missing values...

### Apa itu Hyperparameter Tuning?
Setiap algoritma (seperti CatBoost) memiliki 'pengaturan' internal yang disebut **Hyperparameters** (misalnya `learning_rate` atau `depth`). Tuning adalah proses mencari kombinasi pengaturan terbaik agar model memiliki akurasi atau AUC tertinggi.

Fungsinya:
- Menghindari model yang terlalu sederhana (*underfitting*) atau terlalu kompleks (*overfitting*).
- Memaksimalkan kemampuan prediksi model pada dataset spesifik ini.
- Kita menggunakan **Optuna**, framework otomatis yang mencoba berbagai kombinasi secara cerdas untuk menemukan hasil terbaik.
- (Code) import mlflow...
- (Code) # Menjalankan ulang tuning dengan trials lebih banyak...

### Final Evaluation & MLflow Tracking
Melatih model final dengan parameter terbaik dan mencatatnya ke MLflow.
- (Code) from sklearn.metrics import classification_report, confusion_matrix...


---

## Insight Penting

- Data transaksi memiliki ketidakseimbangan kelas (fraud vs non-fraud), sehingga perlu perhatian khusus saat training model.
- Preprocessing sangat krusial untuk memastikan model tidak bias.
- Evaluasi model tidak cukup hanya menggunakan accuracy, tetapi juga perlu melihat precision, recall, dan confusion matrix.
- False Negative menjadi perhatian utama karena transaksi fraud yang lolos bisa merugikan.

---

## Kesimpulan

Model Machine Learning dapat digunakan untuk membantu mendeteksi fraud secara otomatis, namun performa sangat bergantung pada kualitas data, preprocessing, dan pemilihan model. Evaluasi yang tepat diperlukan agar model benar-benar usable di dunia nyata.

---

## Cara Menjalankan

1. Buka file `FraudDetection.ipynb`
2. Jalankan cell secara berurutan
3. Pastikan semua dependency sudah terinstall (pandas, sklearn, dll)

