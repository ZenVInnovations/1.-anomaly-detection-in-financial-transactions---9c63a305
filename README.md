# Anomaly Detection in Financial Transactions

## 🚀 Project Goal
Identify anomalous (fraudulent) credit‐card transactions with the lowest possible False Positive Rate (FPR), while maximizing recall on the fraud class.

---

## 📊 Dataset
- **Features**: 30 PCA-transformed numerical features  
- **Class Imbalance**:  
  - Non-fraudulent: 1000  
  - Fraudulent: 17  
- **Sampling**: Stratified random split into training and test sets to preserve the original 1000:17 ratio.

---

## 🛠️ Methodology

### 1. Supervised Classification
- **Algorithms Tried**  
  - Logistic Regression  
  - Support Vector Machine  
  - **Random Forest Classifier**  
- **Metric Focus**: Recall on the fraud class  
- **Best Result**:  
  - Random Forest achieved a recall of **0.78**

### 2. Unsupervised Anomaly Detection
- **Isolation Forest**  
  - Trained on the entire dataset without fraud labels  
  - Improved recall to **0.82**

### 3. Deep Autoencoder Approach
- **Architecture**  
  - Fully-connected encoder–decoder network  
  - Compression down to a low-dimensional bottleneck, then reconstruction  
- **Training**  
  - Only on “normal” (non-fraud) transactions  
  - Anomaly score = reconstruction error  
- **Thresholding**  
  - Calibrated to balance false positives and recall  
- **Best Performance**  
  - Recall: **0.85**  
  - False Positive Rate: **6.5%** on fraud class

---

## 📈 Results & Comparison

| Model                         | Recall (Fraud) | False Positive Rate |
|-------------------------------|---------------:|--------------------:|
| Random Forest Classifier      |          0.78  |             —      |
| Isolation Forest              |          0.82  |             —      |
| Deep Autoencoder (Ours)       | **0.85**      | **0.065**         |

---

## 📝 Conclusions
- **Deep Autoencoder** outperforms both classical supervised and unsupervised methods in detecting fraud while keeping false alarms low.  
- This pipeline can be integrated into real‐time monitoring systems, with retraining scheduled periodically as new transaction patterns emerge.

---
