# Waste Management Analytics

Proyek ini berisi analisis data layanan persampahan kabupaten/kota di Indonesia menggunakan data SIPSN KLHK, data fasilitas TPA, dan data geospasial batas wilayah. Analisis berfokus pada statistik deskriptif, eksplorasi distribusi dan pola wilayah, pembangunan Indeks Ketimpangan Layanan Persampahan (IKLP), visualisasi geospasial, clustering, serta rekomendasi prioritas intervensi.

## Struktur Folder

```text
waste-management-analytics/
├── README.md
├── Kelompok_1.ipynb
└── Dataset/
    ├── Data_Capaian_SIPSN_KLHK_2025.xlsx
    ├── Data_Capaian_SIPSN_KLHK_2025-2.xlsx
    ├── data_sipsn.xlsx
    ├── gadm41_IDN_2.json
    ├── merged_waste_management.csv
    ├── cleaned_waste_management.csv
    └── final_waste_management.csv
```

Keterangan file utama:

| File/Folder | Keterangan |
|---|---|
| `Kelompok_1.ipynb` | Notebook utama berisi proses load data, cleaning, feature selection, feature engineering, EDA, IKLP, clustering, visualisasi, insight, dan rekomendasi. |
| `Dataset/` | Folder data mentah, data hasil cleaning, data final, dan file GeoJSON batas kabupaten/kota. |
| `Dataset/final_waste_management.csv` | Dataset final yang digunakan untuk sebagian besar analisis eksploratif, IKLP, dan clustering. |
| `Dataset/gadm41_IDN_2.json` | Data geospasial kabupaten/kota Indonesia untuk visualisasi choropleth. |

## Dependensi

Proyek ini menggunakan Python dan beberapa library analisis data.

| Dependensi | Fungsi |
|---|---|
| `pandas` | Membaca, membersihkan, menggabungkan, dan menganalisis data tabular. |
| `numpy` | Operasi numerik dan transformasi data. |
| `matplotlib` | Visualisasi grafik dasar dan choropleth. |
| `seaborn` | Visualisasi statistik seperti histogram, boxplot, heatmap, dan scatter/regression plot. |
| `scipy` | Analisis statistik tambahan. |
| `scikit-learn` | Standardisasi fitur, K-Means clustering, dan evaluasi Silhouette Score. |
| `geopandas` | Membaca GeoJSON dan membuat visualisasi geospasial. |
| `openpyxl` | Membaca file Excel `.xlsx` melalui pandas. |
| `jupyter` | Menjalankan notebook `.ipynb`. |

## Cara Menjalankan Sistem

### 1. Clone atau buka folder proyek

Pastikan terminal berada di root folder proyek:

```bash
cd waste-management-analytics
```

### 2. Buat virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Untuk Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install dependensi

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn geopandas openpyxl jupyter
```

Jika instalasi `geopandas` bermasalah, gunakan conda sebagai alternatif:

```bash
conda install -c conda-forge geopandas
```

### 4. Jalankan Jupyter Notebook

```bash
jupyter notebook
```

Lalu buka file:

```text
Kelompok_1.ipynb
```

Jalankan notebook dari atas ke bawah agar seluruh variabel, dataset hasil antara, visualisasi, IKLP, dan clustering terbentuk secara berurutan.

### 5. Alur eksekusi notebook

Urutan analisis di notebook:

1. Import library
2. Load dataset
3. Data cleaning
4. Feature selection
5. Feature engineering
6. Penyimpanan dataset final
7. Exploratory Data Analysis
8. Segmentation & Clustering Analysis
9. Deep Dive Diagnosis
10. Visualisasi Geospasial & IKLP
11. Enhanced Cluster & Diagnostic Visualizations
12. Interpretasi, rekomendasi, dan implikasi

## Output Analisis

Output utama proyek:

| Output | Keterangan |
|---|---|
| Statistik deskriptif | Ringkasan performa pengelolaan, pengurangan, penanganan, recycling rate, dan infrastruktur TPA. |
| Visualisasi eksploratif | Histogram, bar chart, scatter plot, heatmap, boxplot, dan radar chart. |
| IKLP | Indeks Ketimpangan Layanan Persampahan skala 0-1; skor tinggi berarti daerah lebih tertinggal. |
| Choropleth | Peta spasial rasio pengelolaan, skor infrastruktur, IKLP, dan cluster wilayah. |
| Clustering | Segmentasi kabupaten/kota berdasarkan rasio pengelolaan dan skor infrastruktur. |
| Ranking prioritas | Daftar kabupaten/kota dengan IKLP tertinggi untuk prioritas peningkatan fasilitas. |
| Rekomendasi | Rekomendasi berbasis data untuk DLH kabupaten/kota, Bappenas, KLHK, dan perencana kota. |

## Catatan Data

- Analisis menggunakan data yang tersedia pada folder `Dataset/`.
- Data final utama berada pada `Dataset/final_waste_management.csv`.
- Beberapa analisis geospasial membutuhkan kecocokan nama wilayah antara dataset SIPSN/TPA dan file GeoJSON.
- Data bersifat snapshot tahun 2025, sehingga tren tahunan tidak dapat disimpulkan secara kausal tanpa data multi-tahun.

## Troubleshooting

| Masalah | Solusi |
|---|---|
| `ModuleNotFoundError` | Pastikan virtual environment aktif dan jalankan ulang instalasi dependensi. |
| Error saat membaca Excel | Pastikan `openpyxl` sudah terinstall. |
| Error pada peta/GeoJSON | Pastikan `geopandas` sudah terinstall dan file `Dataset/gadm41_IDN_2.json` tersedia. |
| Visualisasi tidak muncul | Jalankan notebook melalui Jupyter Notebook/JupyterLab, bukan hanya terminal biasa. |
| Hasil cell bergantung pada variabel sebelumnya | Jalankan notebook dari awal dengan urutan cell yang benar. |
