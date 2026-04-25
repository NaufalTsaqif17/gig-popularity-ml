# Analisis Data Fiverr Gigs 📊

Proyek analisis data untuk memprediksi jumlah reviewer pada gig Fiverr menggunakan machine learning.

## 📋 Daftar Isi
- [Tentang Proyek](#tentang-proyek)
- [Dataset](#dataset)
- [Struktur File](#struktur-file)
- [Instalasi](#instalasi)
- [Penggunaan](#penggunaan)
- [Fitur-Fitur](#fitur-fitur)
- [Model](#model)
- [Hasil](#hasil)

## 🎯 Tentang Proyek

Proyek ini menganalisis data gig dari platform Fiverr untuk memahami faktor-faktor apa yang mempengaruhi jumlah reviewer (pembeli) pada setiap gig. Menggunakan machine learning (XGBoost), proyek ini membangun model prediktif untuk memprediksi jumlah reviewer berdasarkan berbagai fitur seperti:

- Rating rata-rata
- Harga gig
- Panjang judul
- Konten judul (scraping, Excel, Python, ETL)
- Tingkat seller

## 📊 Dataset

**File**: `fiverr-data-gigs-cleaned.csv`

Dataset ini berisi informasi tentang gig Fiverr yang sudah dibersihkan, dengan kolom-kolom:
- `Title` - Judul gig
- `Number of Reviewers` - Jumlah reviewer/pembeli
- `Average Rating` - Rating rata-rata
- `Price (USD)` - Harga dalam USD
- `Seller Level` - Tingkat seller (Basic, Intermediate, Pro, Top Rated)

## 📁 Struktur File

```
dataset/
├── README.md                           # File dokumentasi ini
├── market_gap_analysis.ipynb              # Notebook Jupyter dengan analisis lengkap
└── fiverr-data-gigs-cleaned.csv       # Dataset yang sudah dibersihkan
```

## 🔧 Instalasi

### Prerequisites
- Python 3.8+
- pip atau conda

### Setup Environment

1. **Buat virtual environment:**
   ```bash
   python -m venv venv
   ```

2. **Aktivasi virtual environment:**
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

3. **Install dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap jupyter
   ```

   Atau gunakan requirements.txt (jika ada):
   ```bash
   pip install -r requirements.txt
   ```

## 📖 Penggunaan

1. **Buka Jupyter Notebook:**
   ```bash
   jupyter notebook analisis_fiverr.ipynb
   ```

2. **Jalankan semua cell** secara berurutan (Shift + Enter)

3. **Hasilnya:**
   - Visualisasi distribusi jumlah reviewer
   - Analisis per tingkat seller
   - Metrik model (MAE, R²)
   - Feature importance

## ✨ Fitur-Fitur Utama

### 1. **Data Cleaning**
- Cleaning kolom "Number of Reviewers" (handling format 1k+, k+)
- Konversi tipe data ke numeric
- Menghilangkan missing values

### 2. **Exploratory Data Analysis (EDA)**
- Histogram distribusi jumlah reviewer
- Box plot: jumlah reviewer per seller level

### 3. **Feature Engineering**
- `title_length` - Panjang judul dalam karakter
- `has_scraping` - Apakah judul mengandung kata "scraping"
- `has_excel` - Apakah judul mengandung kata "excel", "vba", "macro", "google sheet"
- `has_python` - Apakah judul mengandung kata "python"
- `has_etl` - Apakah judul mengandung kata "etl", "pipeline", "spark", "airflow"
- One-hot encoding untuk Seller Level

### 4. **Model Prediction**
- Algorithm: XGBoost Regressor
- Train-test split: 80-20
- Prediksi: jumlah reviewer

## 🤖 Model

### Algoritma: XGBoost Regressor

**Parameter:**
- `n_estimators`: 200
- `learning_rate`: 0.1
- `random_state`: 42

**Train-Test Split**: 80% training, 20% testing

## 📈 Hasil

Setelah training, model menghasilkan:

- **MAE (Mean Absolute Error)**: Rata-rata kesalahan absolut prediksi
- **R² Score**: Seberapa baik model menjelaskan varians data
- **Feature Importance**: Grafik 10 faktor terpenting yang mempengaruhi jumlah reviewer

### Top Features (Umumnya):
1. Average Rating - Rating gig sangat mempengaruhi jumlah pembeli
2. Price (USD) - Harga gig mempengaruhi aksesibilitas
3. Seller Level - Tingkat seller berpengaruh pada kepercayaan pembeli
4. Title Length - Panjang judul mempengaruhi SEO dan clarity
5. Domain-specific features (scraping, Excel, Python, ETL)

## 💡 Insights Utama

- Gig dengan rating tinggi cenderung memiliki lebih banyak reviewer
- Seller Level berpengaruh signifikan terhadap jumlah pembeli
- Keyword tertentu (scraping, Excel, Python) dalam judul dapat mempengaruhi visibility
- Harga gig memiliki hubungan dengan jumlah reviewer

## 📝 Notes

- Pastikan `fiverr-data-gigs-cleaned.csv` ada di directory yang sama dengan notebook
- Jika path berbeda, ubah di cell data loading
- Visualisasi menggunakan matplotlib dan seaborn dengan style 'seaborn-v0_8'

## 🔗 Dependencies

- **pandas** - Data manipulation
- **numpy** - Numerical computation
- **matplotlib** - Visualization
- **seaborn** - Statistical visualization
- **scikit-learn** - Machine learning (train-test split, metrics)
- **xgboost** - XGBoost regressor
- **shap** - Model interpretability (opsional)
- **jupyter** - Interactive notebook

## 📧 Author

Dataset Analysis Project - April 2026

---

**Happy analyzing!** 🚀
