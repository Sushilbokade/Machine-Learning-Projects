# Password Strength Classifier

A machine learning–powered tool for evaluating password strength as **Weak**, **Medium**, or **Strong** using engineered features and XGBoost.

---

## 📋 Overview

This project ingests raw passwords, applies custom preprocessing and feature extraction, and trains an XGBoost model to classify password strength with high accuracy and interpretability.

---

## ⚙️ Key Steps

1. **Data Processing**

   * Cleaned 1 000 000 raw passwords into 133 928 labeled samples (Weak 13.5%, Medium 74.1%, Strong 12.4%) using regex filters.

2. **Feature Engineering**

   * Computed 5 heuristic metrics: password length, digit ratio, special‑character ratio, repetition score, and Shannon entropy.
   * Generated character‑level TF‑IDF n‑grams (1–3‑grams) yielding \~10 000‑dim sparse vectors.

3. **Model Training & Evaluation**

   * Trained an **XGBoost** classifier achieving **98.6% test accuracy** and a **0.99 weighted F1‑score**.

---

## 🛠️ Tech Stack

* **Language:** Python 3
* **Environment:** Jupyter Notebook
* **Libraries:** XGBoost, scikit-learn, pandas, NumPy, matplotlib

---

## 🚀 Usage

1. Clone the repo:

   ```bash
   git clone <repo-url>
   cd Password_Strength_Classifier
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Launch the notebook or script:

   ```bash
   jupyter notebook Password_Strength_classifier.ipynb
   ```

---

## 📈 Results

* **Accuracy:** 98.6%
* **Weighted F1‑score:** 0.99

---

## 🔄 TODO

* Deploy as a REST API (Flask or FastAPI)
* Build a front‑end interface (Streamlit)
* Explore deep learning approaches for further gains
