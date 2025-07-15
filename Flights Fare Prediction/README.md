# Flight Price Prediction & Deployment

A full ML pipeline to predict flight fares using feature engineering, Random Forest regression, and model serialization for deployment.

---

## 📋 Overview

This project builds a regression model that predicts airline ticket prices based on journey details, temporal data, and route information. After preprocessing and feature engineering, the model is tuned with randomized search and saved for downstream deployment.

---

## ⚙️ Key Steps

1. **Data Ingestion & Cleaning**

   * Load `Data_Train.xlsx` (≈100 000 records).
   * Drop <1% missing values.

2. **Feature Engineering**

   * Extract journey date features: `Journey_day`, `Journey_month`, `Dep_hour`, `Dep_min`, `Arr_hour`, `Arr_min`.
   * Parse `Duration` into `Duration_hours`, `Duration_mins`.
   * Encode categorical features: one-hot for `Airline`, `Source`, `Destination`; label encoding for `Route` splits and `Total_Stops`.

3. **Model Training & Tuning**

   * Split data (80% train, 20% test).
   * Random Forest Regressor with `RandomizedSearchCV` over 100 parameter combinations and 3-fold CV.
   * Evaluate using R², MAE, MSE, RMSE.

4. **Model Serialization**

   * Serialize best estimator as `model.pkl` via `pickle.dump`

---

## 🛠️ Tech Stack

* **Language:** Python 3
* **Notebook:** Jupyter
* **Libraries:** pandas, NumPy, matplotlib, seaborn, scikit-learn

---

## 🚀 Usage

1. Place `Data_Train.xlsx` in the project directory.
2. Install requirements:

   ```bash
   pip install -r requirements.txt
   ```
3. Run preprocessing & training:

   ```bash
   jupyter notebook flight_price_deploy.ipynb
   ```
4. Load serialized model for predictions in your deployment (Flask/Streamlit).

---

## 📈 Results

* **Best R² Score:** \~0.80
* **MAE:** \~Rs. 2 500
* **MSE / RMSE:** reported in notebook

---

## 🔄 TODO

* Build a REST API (Flask or FastAPI)
* Create a Streamlit UI for end users
* Integrate real-time price feeds and retraining pipeline
