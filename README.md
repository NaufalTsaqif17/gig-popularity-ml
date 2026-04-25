# Analisis Data Fiverr Gigs

Proyek ini bertujuan melakukan analisis data terhadap gig Fiverr untuk memahami faktor-faktor yang berkontribusi pada jumlah reviewer. Tujuan utama analisis ini adalah:

- Mengidentifikasi pola dan hubungan antara fitur gig dan jumlah reviewer yang diterima.
- Menentukan fitur paling penting yang mempengaruhi performa gig di Fiverr.
- Mengembangkan model prediktif yang dapat memperkirakan jumlah reviewer berdasarkan atribut gig.
- Menyediakan wawasan yang dapat membantu seller Fiverr meningkatkan daya saing gig mereka.

## Daftar Isi
- [Tentang Proyek](#tentang-proyek)
- [Tujuan Analisis](#tujuan-analisis)
- [Dataset](#dataset)
- [Struktur File](#struktur-file)
- [Instalasi](#instalasi)
- [Penggunaan](#penggunaan)
- [Fitur Utama](#fitur-utama)
- [Model](#model)
- [Hasil](#hasil)
- [Dependencies](#dependencies)

## Tentang Proyek

Analisis ini menggunakan data gig Fiverr yang telah dibersihkan untuk mengevaluasi tren dan performa pasar. Studi ini fokus pada aspek-aspek seperti rating, harga, judul gig, dan level seller, kemudian membandingkan kontribusi masing-masing faktor terhadap jumlah reviewer.

## Tujuan Analisis

1. Menjelaskan tujuan bisnis dari analisis data ini:
   - Menilai apakah kualitas dan karakteristik gig dapat mempengaruhi jumlah reviewer.
   - Menentukan segmen layanan Fiverr yang menunjukkan kesenjangan antara pasokan dan permintaan.
   - Memberikan rekomendasi berbasis data bagi seller untuk memperbaiki judul, harga, dan fitur gig.

2. Menjelaskan tujuan teknis dari analisis data ini:
   - Melakukan pembersihan data dan transformasi fitur yang relevan.
   - Mengeksplorasi distribusi dan korelasi antar fitur.
   - Melatih model machine learning untuk memprediksi jumlah reviewer.
   - Menginterpretasi hasil model dan mengukur keakuratan prediksi.

## Dataset

**File**: `fiverr-data-gigs-cleaned.csv`

Dataset ini berisi data gig Fiverr yang sudah dibersihkan dengan kolom utama sebagai berikut:
- `Title` - Judul gig
- `Number of Reviewers` - Jumlah reviewer/pembeli
- `Average Rating` - Rating rata-rata
- `Price (USD)` - Harga dalam USD
- `Seller Level` - Tingkat seller (Basic, Intermediate, Pro, Top Rated)

## Struktur File

```
Dataset2/
├── README.md
├── market_gap_analysis.ipynb
└── fiverr-data-gigs-cleaned.csv
```

## Instalasi

### Prasyarat
- Python 3.8 atau lebih tinggi
- pip atau conda

### Langkah Persiapan

1. Buat virtual environment:
   ```bash
   python -m venv venv
   ```

2. Aktifkan virtual environment:
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

3. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
   ```

   Jika tersedia, gunakan:
   ```bash
   pip install -r requirements.txt
   ```

## Penggunaan

1. Buka Jupyter Notebook:
   ```bash
   jupyter notebook market_gap_analysis.ipynb
   ```

2. Jalankan semua cell secara berurutan.

3. Analisis menghasilkan:
   - Visualisasi distribusi jumlah reviewer per kategori.
   - Ringkasan market gap berdasarkan kategori gig.
   - Wawasan tentang permintaan dan kompetisi di Fiverr.

## Fitur Utama

### Data Cleaning
- Memproses nilai `Number of Reviewers` dengan format seperti `1k` atau `1k+`.
- Mengonversi kolom numerik ke tipe yang sesuai.
- Menyiapkan fitur tambahan untuk analisis kategori.

### Kategorisasi Gig
- Mengelompokkan gig ke dalam kategori layanan seperti:
  - Web Scraping & Data Mining
  - Excel & Google Sheets
  - Machine Learning & AI
  - Data Engineering & Big Data
  - Other Data Services

### Eksplorasi Data
- Menentukan distribusi jumlah gig per kategori.
- Mengukur rata-rata reviewer dan persentase gig tanpa reviewer.
- Menampilkan korelasi antara harga dan jumlah reviewer.

### Rekomendasi Bisnis
- Mengidentifikasi kategori yang paling diminati pembeli.
- Mengamati potensi oversupply pada layanan tertentu.
- Memberikan rekomendasi bagi seller baru dan yang ingin meningkatkan performa gig.

## Model

Analisis ini terutama berbasis eksplorasi data dan kategori pasar. Model machine learning dapat ditambahkan sebagai langkah lanjutan untuk memprediksi jumlah reviewer berdasarkan fitur yang diekstrak.

## Hasil

Dari analisis saat ini, yang ditonjolkan adalah:
- Kategori dengan permintaan tinggi dan rata-rata reviewer tinggi.
- Kategori yang menunjukkan banyak gig tetapi sedikit reviewer.
- Kategori dengan potensi kesenjangan pasar untuk seller baru.

Hasil analisis diarahkan untuk membantu memahami struktur pasar Fiverr dan mengidentifikasi peluang layanan yang lebih menguntungkan.

## Dependencies

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- jupyter

## Catatan

Pastikan `fiverr-data-gigs-cleaned.csv` berada di direktori yang sama dengan notebook. Jika file berada di lokasi lain, sesuaikan path di cell data loading.
