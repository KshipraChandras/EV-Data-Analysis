# Electric Vehicle Population Data Analysis (Washington State DOL)

An end-to-end exploratory data analysis (EDA), visualization, and predictive modeling project analyzing Battery Electric Vehicles (BEVs) and Plug-in Hybrid Electric Vehicles (PHEVs) registered through the Washington State Department of Licensing (DOL).

## 📌 Project Overview
This project transforms raw government registration records into actionable insights on EV market dominance, geographic adoption patterns, incentive eligibility, and electric range progression using Python.

### Key Objectives & Workflow
1. **Data Cleaning & Preparation:**
   * Audited missing values and replaced unreported zero-values in `Electric Range` using group-median imputation by `Make` and `Model`.
   * Removed duplicate registrations via unique `DOL Vehicle ID`.
   * Anonymized partial `VIN (1-10)` identifiers using deterministic **SHA-256 cryptographic hashing**.
   * Parsed WKT `Vehicle Location` strings (`POINT (lon lat)`) into numeric `Longitude` and `Latitude` coordinates.
2. **Exploratory Data Analysis (EDA):**
   * Analyzed top EV manufacturers and models, county-level registration distributions, yearly adoption growth, CAFV incentive eligibility, and urban vs. rural adoption trends.
3. **Data Visualization:**
   * Built multi-panel bar charts, county-by-drivetrain heatmaps, model-year adoption trend lines, range progression scatter plots, CAFV eligibility pie charts, and interactive geospatial maps.
4. **Predictive Modeling (Linear Regression):**
   * Built a `scikit-learn` preprocessing and Linear Regression pipeline using `OneHotEncoder` on categorical features (`Make`, `Model`, `Electric Vehicle Type`, `CAFV Eligibility`) alongside `Model Year` to predict `Electric Range` (**R² > 0.95**).

## 🛠️ Tech Stack
* **Language:** Python 3
* **Data Manipulation:** `pandas`, `numpy`, `hashlib`
* **Visualization:** `matplotlib`, `seaborn`, `plotly`
* **Machine Learning:** `scikit-learn` (`ColumnTransformer`, `OneHotEncoder`, `Pipeline`, `LinearRegression`)

## 📊 Key Findings
* **Market Leader:** Tesla dominates Washington State registrations (led by the Model Y and Model 3), well ahead of Chevrolet, Nissan, Ford, and Kia.
* **Regional Concentration:** Urban Western Washington—led by **King County**—accounts for the majority of registrations, with **BEVs outnumbering PHEVs by roughly 3-to-1**.
* **Adoption & Range Growth:** EV registrations grew exponentially after 2018 alongside steady increases in maximum battery range across newer model years.

## 📂 Repository Contents
* `EV_Data_Analysis.ipynb` – Complete Jupyter Notebook containing code, visualizations, interpretations, and regression Q&A.
* `README.md` – Project summary and methodology.

## 🔗 Data Source
* [Electric Vehicle Population Data – Data.gov (Washington State DOL)](https://data.gov)
