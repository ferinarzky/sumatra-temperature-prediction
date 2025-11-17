# Random Forest Regression for Sumatra Temperature Forecasting (99.61% R² Score)

[![Status: Completed](https://img.shields.io/badge/Status-Completed-green.svg)]()
[![Algorithm: Random Forest Regressor](https://img.shields.io/badge/Algorithm-Random%20Forest%20Regressor-orange.svg)]()
[![Accuracy (R²): 99.61%](https://img.shields.io/badge/R%C2%B2%20Score-99.61%25-brightgreen.svg)]()
[![Language: Python 3.9](https://img.shields.io/badge/Language-Python%203.9-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-lightgrey.svg)]()

Temperature forecasting over Sumatra using ERA5 reanalysis data and Random Forest regression. Includes data preprocessing, model training, evaluation, and spatial visualization.

## 📂 Dataset

This project uses **ERA5 reanalysis climate data (Hourly data on single levels from 1940 to present)** for temperature prediction over Sumatra in 2024.

Currently included:
- `data/era5_sumatra_202401.csv` — sample data (January 2024)

Full merged dataset (53MB) is **not uploaded** due to GitHub file size limitations.
It will be shared via cloud storage or Git LFS in the future.

**Source:** ERA5 — Copernicus Climate Data Store  
https://cds.climate.copernicus.eu

## Data Description
- Temperature data (2m air temperature).
- Sumatra region.
- Monthly aggregated dataset.
- Reanalysis model (not observational station data).

## Data Structure (Full Features)

This project uses 7 meteorological parameters as input features to predict surface temperature (t2m) as the target/label.

| Input Features (X) | Descriptions |
| :--- | :--- |
| `latitude`, `longitude` | Location coordinates. |
| **`u_10`, `v_10`** | Zonal (u) and meridional (v) wind components at 10 meters height. |
| **`d2m`** | Dewpoint Temperature (Humidity indicator). |
| **`SST`** | Sea Surface Temperature. |
| **`MSL`** | Mean Sea Level Pressure. |
| **`SP`** | Surface Pressure. |
| **Target (Y)** | Description. |
| **`t2m`** (temperature) | Air temperature at 2 meters height (Prediction target). |

> This repository includes a **sample dataset**.  
> Full dataset available upon request.

## ⚙️ Methodology and Model Configuration

1. **Data Period:** January, February, March, April, and May 2024, specifically between 10:00 AM and 12:00 PM Jakarta Time (WIB).
2. **Total Data Points:** 795.717 records.
3. **Split Data:**
    * **Data Training:** **Januari - April 2024** used for training the model.
    * **Data Testing/Validation:** **May 2024** used for testing and validating the program.
    * **Train/Test Split Ratio:** 75% Training / 25% Testing.
4.  **Random Forest Configuration:**
    * **Algorithm:** Random Forest Regressor (Scikit-learn).
    * **Hyperparameter:** `n_estimator` = 200.
      
## 🚀 How to Run the Model

```bash
# Install dependencies
pip install -r requirements.txt

# Run training
python src/train_model.py

# Generate map visualization
python src/plot_maps.py

```

## 📈 Key Results and Prediction Validation

The model was tested on May 2024 data and showed the following results:

| Metrik Evaluasi | Nilai | Interpretasi |
| :--- | :--- | :--- |
| **Accuracy (R-squared)** | **99.61%** | The model fits the data very well, explaining 99.61% of the temperature variability in May. |
| **Mean Absolute Error (MAE)** | **$0.39^{\circ}C$** | Very low error level, demonstrating the model's ability to accurately predict actual temperatures in May 2024. |

## Visual Proof: Temperature Prediction Map for May 2024

The most important outcome of this project is the Temperature Prediction Map for May 2024, validated by the Random Forest model.

![Temperature Map Prediction in May 2024](results/maps/temperaturemappredictioninmay_2024.png)

**Validation Conclusion:**
The model's predictions show average temperatures stable around $\mathbf{27^{\circ}C}$ to $\mathbf{28^{\circ}C}$ across Sumatra. This map serves as evidence of the successful application of a Machine Learning model in mapping and forecasting monthly temperature patterns based on ERA5 data.

---

## 👩‍💻 Author

**Ferina Rizky Kurniawati**  
Data Science & Climate Modeling Enthusiast  
📍 Indonesia  
📫 Email: *Ferinarzky@gmail.com*  
LinkedIn: *www.linkedin.com/in/ferinarizkykurniawati*
