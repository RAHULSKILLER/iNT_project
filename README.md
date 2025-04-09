# 🔧 Hybrid Engine Monitoring System

A predictive maintenance system that combines anomaly detection, classification, and RUL (Remaining Useful Life) estimation for aircraft engines using the NASA C-MAPSS dataset. The system is designed to detect faults early, categorize engine health, and forecast failures — all scalable to real-time deployment.

---

## 🚀 Project Overview

This project follows a **4-phase pipeline**:

### 📍 PHASE 1: Anomaly Detection
**Goal:** Identify deviations from normal engine behavior using LSTM Autoencoders.
- Data normalization and sliding-window sequence creation
- Trained Autoencoder on healthy early engine cycles
- Reconstruction error calculated on all cycles
- Threshold-based anomaly detection (95th percentile)
- Visualized anomaly trends per engine

### 📍 PHASE 2: Engine Condition Classification
**Goal:** Categorize engine state as **Healthy**, **Degraded**, or **Failing**.
- Labels created using anomaly trends and RUL thresholds
- Features combined: sensor data + anomaly flags
- Classification using 1D CNN or XGBoost
- Evaluated with Accuracy, Precision, Recall, and F1-score
- Plots for per-engine classification trends

### 📍 PHASE 3: Remaining Useful Life (RUL) Prediction
**Goal:** Predict how many cycles remain before engine failure.
- RUL calculated using run-to-failure cycle counts
- Trained LSTM or XGBoost regression model
- Combined with classification output for robust predictions
- Visualized true vs predicted RUL over time

### 📍 PHASE 4: Real-Time Integration & Deployment
**Goal:** Deploy the full pipeline for live diagnostics.
- FastAPI backend for real-time predictions
- Simulated sensor input cycle-by-cycle
- Streamlit dashboard to visualize engine health and RUL
- Portable packaging for on-device deployment (optional)

---

## 🧠 Technologies Used

- **Languages & Libraries:** Python, Pandas, NumPy, Scikit-learn, TensorFlow, XGBoost, Matplotlib, Seaborn
- **Modeling:** LSTM Autoencoder, 1D CNN, XGBoost
- **Deployment Tools:** FastAPI, Streamlit

---

## 📁 Dataset

- **Source:** [NASA C-MAPSS](https://www.nasa.gov/content/prognostics-center-of-excellence-data-set-repository)
- **File Used:** `train_FD001.txt`
- **Contains:** Engine unit number, time in cycles, operational settings, 21 sensor readings

---

## 📊 Output Visuals

- Engine anomaly timelines (reconstruction error plots)
- Classification heatmaps and confusion matrix
- RUL prediction vs actual comparison curves
- Real-time dashboard (simulated inputs)

---

## ⚙️ Future Enhancements

- Multi-engine generalization using FD002–FD004 datasets
- Attention-based temporal modeling (e.g., Transformer for RUL)
- Cloud deployment with sensor streaming
- Integration with edge devices for embedded inference

---

## ⭐ If you find this project insightful, leave a ⭐ or contribute!

