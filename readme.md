
# 🔐 Intrusion Detection System using Machine Learning

> Final project for the **Network Security** course — Computer Engineering Degree, Polytechnic School of Basic Sciences, Academic Year 2023/2024  
> **Student:** Francesco Pio Manna — `M63001485`

## 📘 Project Overview

This project focuses on the development of an **Intrusion Detection System (IDS)** using **Machine Learning** techniques applied to network traffic data. It uses the **NSL-KDD dataset**, which is a refined version of the KDD Cup 1999 dataset, as a benchmark to detect various types of cyberattacks.

---

## 🔍 Project Goals

- Understand types of intrusions and how IDS work.
- Explore the NSL-KDD dataset and its attack categories.
- Preprocess and analyze the data for modeling.
- Build and evaluate machine learning models (XGBoost and MLP).
- Identify weaknesses in detection, especially on rare or unseen attacks.

---

## 📦 Dataset

- **Name:** NSL-KDD
- **Source:** Simulated DARPA environment
- **Classes:**
  - DoS (Denial of Service)
  - Probe
  - R2L (Remote to Local)
  - U2R (User to Root)
- **Features:** 43 total (41 input + attack label + difficulty score)
- **Subsets:**
  - KDDTrain+, KDDTest+, KDDTest-21, KDDTrain+_20Percent

---

## 🧪 Data Exploration & Preprocessing

### Exploratory Analysis

- Protocol, Service, Flag distributions
- KDE plots and correlation matrices
- Attack types by protocol and flags

### Preprocessing Steps

- Encoding of categorical features
- Train/validation split (80/20)
- Feature selection via mutual information
- Z-score normalization for MLP

---

## 🤖 Machine Learning Models

### XGBoost

- Used Grid Search with 400+ hyperparameter combinations
- Achieved high accuracy with minimal false negatives
- Key features: `src_bytes`, `dst_bytes`, `same_srv_rate`, `flag`

### Multilayer Perceptron (MLP)

- Architecture: 2 hidden layers (10 neurons each)
- Activation: ReLU, Optimizer: Adam
- Performed better than XGBoost on some test cases
- Still had difficulty with R2L/U2R attacks

---

## 📊 Evaluation & Results

- **False Positives vs. False Negatives** tradeoff
- IDS prefers **false positives** over undetected intrusions
- Analysis of missed attacks (e.g., `guess_passwd`, `sqlattack`)
- Dataset imbalance affected detection of R2L/U2R

---

## ⚠️ Challenges & Limitations

- Unbalanced dataset leads to poor detection on rare attack types
- Certain test attacks were not present in training data (zero-day simulation)
- Classifiers struggle with underrepresented attack classes

---

## 🧩 Future Work

- Apply data augmentation techniques
- Try more advanced models (e.g., Transformers)
- Explore anomaly detection with unsupervised learning
- Address dataset imbalance with resampling or synthetic data

---

## 📄 License

This project is distributed under the MIT License.
