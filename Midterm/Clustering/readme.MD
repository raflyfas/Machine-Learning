# UTS Machine Learning - Clustering

## Data Diri

| Kategori | Detail |
| :--- | :--- |
| **Nama** | **Rafly Fasha Purnomo Putra** |
| **Kelas** | **TK-46-GAB** |
| **NIM** | **1103223050** |

## 1. Tujuan Repositori
Repository ini berisi implementasi end-to-end machine learning pipeline untuk melakukan customer segmentation menggunakan metode unsupervised learning, yaitu K-Means Clustering. 

Proyek ini dibuat untuk memenuhi tugas Midterm Clustering yang berfokus pada pengelompokan pelanggan berdasarkan perilaku penggunaan kartu kredit, seperti aktivitas pembelian, pembayaran, cash advance, dan limit kredit.

## 2. Gambaran Singkat Proyek
Pada proyek ini dilakukan proses clustering terhadap data pelanggan kartu kredit untuk mengidentifikasi pola perilaku pelanggan berdasarkan aktivitas transaksi dan pembayaran mereka.

Pada proyek ini dilakukan:
- **Data preprocessing**
- **Penanganan missing values**
- **Penanganan outlier**
- **Feature scaling**
- **Penentuan jumlah cluster optimal**
- **Evaluasi clustering**
- **Interpretasi hasil cluster**

Dataset yang digunakan:
- `clusteringmidterm.csv`

---

## 3. Model
Model utama yang digunakan:
- K-Means Clustering

## 4. Evaluation Metrics
Metode evaluasi yang digunakan:
- Elbow Method
- Silhouette Score

Evaluasi per Cluster :

| Number of Clusters (K) | Silhouette Score |
|---|---|
| 2 | 0.2100 |
| 3 | 0.2510 |
| 4 | 0.1977 |
| 5 | 0.1931 |
| 6 | 0.2029 |
| 7 | 0.2077 |
| 8 | 0.2217 |
| 9 | 0.2260 |
| 10 | 0.2204 |

Hasil evaluasi menunjukkan bahwa jumlah cluster **optimal** adalah:
K = 3

Karena menghasilkan nilai Silhouette Score tertinggi dibandingkan jumlah cluster lainnya.

---


## 5. Repository Structure / Notebook Navigation

```text
├── Midterm_Clustering.ipynb
├── clusteringmidterm.csv
└── README.md
```

---


# 6. Guide to Run Project

Project ini dapat dijalankan menggunakan Google Colab ataupun Jupyter Notebook.

Sebelum menjalankan notebook, install terlebih dahulu library yang dibutuhkan:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```
