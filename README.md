# Fraud Detection – ML Evaluation & Threshold Calibration

This project simulates a fraud detection scenario using a synthetically generated dataset with realistic business logic and class imbalance (~3% fraud rate).

The main goal is not only to train a model, but to analyze how decision thresholds impact fraud detection performance and operational load.

---

##  Problem Context

Fraud detection datasets are typically highly imbalanced.  
Accuracy alone is not a reliable metric in this setting.

In this project, we focus on:

- Precision
- Recall
- F1 Score
- Operational impact (alert volume and alerts per captured fraud)

---

##  Dataset

- 20,000 synthetic transactions
- Fraud rate: ~3%
- Features simulate real-world fraud signals:
  - Transaction amount
  - Account age
  - Foreign transaction indicator
  - High-risk country
  - Late-night activity
  - Behavioral spikes (amount ratio)
  - Transaction frequency (last 24h)

The target variable (`fraud`) is generated using a probabilistic risk model (logistic function).

---

##  Model

Baseline model:
- Logistic Regression
- `class_weight="balanced"` to handle imbalance

Train/Test split:
- 70/30
- Stratified sampling to preserve fraud proportion

---

##  Threshold Analysis

Instead of relying on the default threshold (0.5), multiple thresholds were evaluated.

Metrics analyzed per threshold:

- Precision
- Recall
- F1 Score
- Alert Rate
- Alerts per True Positive (alerts_per_tp)

This allows translating model performance into operational impact.

---

##  Example Decision (Business-Oriented)

Threshold = **0.60**

- Precision ≈ 0.10
- Recall ≈ 0.43
- Alerts per captured fraud ≈ 9.9

This threshold represents a compromise between:
- Capturing a meaningful portion of fraud cases
- Controlling false positives and investigation workload

Different thresholds can be selected depending on business priorities:

- Lower threshold → Higher recall, more alerts
- Higher threshold → Higher precision, fewer alerts

---

##  Key Insight

Model evaluation in fraud detection must go beyond accuracy.

The real decision depends on:

- Cost of False Negatives (missed fraud)
- Cost of False Positives (customer friction / operational cost)
- Investigation capacity

Threshold calibration is therefore a strategic business decision, not only a statistical one.

---

##  Next Improvements

- Add cost-sensitive evaluation
- Compare with tree-based models (Random Forest / XGBoost)
- Introduce customer segmentation for differentiated thresholds
- Evaluate Precision-Recall AUC

---

##  Technologies

- Python
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
