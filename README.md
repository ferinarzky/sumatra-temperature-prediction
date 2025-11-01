# Random Forest Regression for Sumatra Temperature Forecasting (99.61% R² Score)

[![Status: Selesai](https://img.shields.io/badge/Status-Completed-green.svg)]()
[![Algoritma: Random Forest Regressor](https://img.shields.io/badge/Algorithm-Random%20Forest%20Regressor-orange.svg)]()
[![Akurasi (R²): 99.61%](https://img.shields.io/badge/R%C2%B2%20Score-99.61%25-brightgreen.svg)]()
[![Bahasa: Python 3.9](https://img.shields.io/badge/Language-Python%203.9-blue.svg)](https://www.python.org/)
[![Lisensi: MIT](https://img.shields.io/badge/License-MIT-lightgrey.svg)]()

Temperature forecasting over Sumatra using ERA5 reanalysis data and Random Forest regression. Includes data preprocessing, model training, evaluation, and spatial visualization.

## 📂 Dataset

This project uses **ERA5 reanalysis climate data** for temperature prediction over Sumatra in 2024.

Currently included:
- `data/era5_sumatra_202401.csv` — sample data (January 2024)

Full merged dataset (~53MB) is **not uploaded** due to GitHub file size limitations.
It will be shared via cloud storage or Git LFS in the future.

**Source:** ERA5 — Copernicus Climate Data Store  
https://cds.climate.copernicus.eu

## Data Description
- Temperature data (2m air temperature)
- Sumatra region
- Monthly aggregated dataset
- Reanalysis model (not observational station data)

## Data Structure (Full Features)

Proyek ini menggunakan 7 parameter meteorologi sebagai fitur input untuk memprediksi suhu permukaan (t2m) sebagai target/label.

| Fitur Input (X) | Keterangan |
| :--- | :--- |
| `latitude`, `longitude` | Koordinat lokasi. |
| **`u_10`, `v_10`** | Komponen Angin Zonal (u) dan Meridional (v) pada ketinggian 10 meter. |
| **`d2m`** | Dewpoint Temperature (Indikator Kelembaban). |
| **`SST`** | Sea Surface Temperature (Suhu Permukaan Laut). |
| **`MSL`** | Mean Sea Level Pressure (Tekanan Permukaan Laut). |
| **`SP`** | Surface Pressure (Tekanan Permukaan). |
| **Target (Y)** | Keterangan |
| **`t2m`** (temperature) | Suhu udara pada ketinggian 2 meter (Target Prediksi). |

> This repository includes a **sample dataset**.  
> Full dataset available upon request.

## ⚙️ Metodologi dan Konfigurasi Model

1. **Periode Data:** Januari, Februari, Maret, April, dan Mei 2024 (Pukul 10.00-12.00 WIB).
2. **Total Data Poin:** 795.717 data.
3. **Pembagian Data:**
    * **Data Training:** Data bulan **Januari - April 2024** digunakan untuk melatih model.
    * **Data Testing/Validation:** Data bulan **Mei 2024** digunakan untuk pengujian dan validasi program.
    * **Rasio Train/Test Split:** 75% Training / 25% Testing.
4.  **Konfigurasi Random Forest:**
    * **Algoritma:** Random Forest Regressor (Scikit-learn).
    * **Hyperparameter:** `n_estimator` = 200.
      
## 🚀 Cara Menjalankan Model

```bash
# Install dependencies
pip install -r requirements.txt

# Jalankan training
python src/train_model.py

# Generate map visualization
python src/plot_maps.py

```

## 📈 Hasil Kunci dan Validasi Prediksi

Model diuji pada data bulan Mei 2024 dan menunjukkan hasil sebagai berikut:

| Metrik Evaluasi | Nilai | Interpretasi |
| :--- | :--- | :--- |
| **Akurasi (R-squared)** | **99.61%** | Model sangat cocok dengan data, menjelaskan 99.61% variabilitas suhu Mei. |
| **Mean Absolute Error (MAE)** | **$0.39^{\circ}C$** | Tingkat kesalahan yang sangat rendah, membuktikan model mampu memprediksi suhu aktual di Mei 2024 dengan akurasi tinggi. |

## Bukti Visual: Peta Prediksi Suhu Mei 2024

Hasil terpenting dari proyek ini adalah **Peta Prediksi Suhu** di bulan Mei 2024, yang divalidasi oleh model Random Forest.

![Peta Hasil Prediksi Suhu Sumatera Mei 2024](results/maps/peta_hasil_mei_2024.png)

**Kesimpulan Validasi:**
Prediksi model menunjukkan suhu rata-rata stabil pada $\mathbf{27^{\circ}C}$ hingga $\mathbf{28^{\circ}C}$ di wilayah Sumatera. Peta ini berfungsi sebagai **bukti keberhasilan** model Machine Learning dalam memetakan dan memprediksi pola suhu bulanan berdasarkan data ERA5.

---

## 👩‍💻 Author

**Ferina Rizky Kurniawati**  
Data Science & Climate Modeling Enthusiast  
📍 Indonesia  
📫 Email: *Ferinarzky@gmail.com*  
LinkedIn: *www.linkedin.com/in/ferinarizkykurniawati*
