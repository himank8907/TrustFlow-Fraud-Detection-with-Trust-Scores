# 🛡️ TrustFlow – Fraud Detection with Trust Scores

## 📌 Project Overview

TrustFlow is a Machine Learning-based Payment Risk Assessment and Fraud Detection Engine designed to evaluate the trustworthiness of digital transactions.

The system analyzes multiple trust parameters associated with users, merchants, transaction reliability and behavioural safety to predict potentially fraudulent transactions.

By combining machine learning predictions with a weighted trust scoring mechanism, TrustFlow provides an intelligent decision-support system for assessing payment risks.

## 🎯 Project Objectives

- Detect potentially fraudulent digital transactions.
- Evaluate transaction risk using multiple trust parameters.
- Compare different machine learning classification algorithms.
- Optimize the fraud classification threshold.
- Generate an overall transaction trust score.
- Categorize transactions into APPROVE, REVIEW or BLOCK.
- Export a reusable trained machine learning model.

## 🚀 Key Features

- CSV dataset uploading and validation
- Exploratory Data Analysis (EDA)
- Automated model training and comparison
- Fraud probability prediction
- Weighted trust score calculation
- Classification threshold optimization
- Feature importance analysis
- Performance evaluation and visualization
- Trained model export using Joblib
- Rule-based transaction recommendations

## 🧠 Machine Learning Algorithms

### 1. Logistic Regression

A supervised learning classification algorithm used to estimate the probability of a transaction being fraudulent.

StandardScaler is used for feature scaling, and balanced class weights are applied to address potential class imbalance.

### 2. Random Forest Classifier

An ensemble learning algorithm that combines multiple decision trees to identify potentially fraudulent transaction patterns.

Model configuration:

- Number of estimators: 200
- Maximum depth: 10
- Minimum samples split: 5
- Class weight: Balanced
- Random state: 42

The best-performing model is automatically selected based on its validation average precision (PR-AUC metric).

## 📊 Dataset Description

The project uses a synthetic transaction dataset containing the following attributes:

| Feature | Description |
|---|---|
| user_trust_score | Trustworthiness of the user |
| merchant_trust_score | Trustworthiness of the merchant |
| transaction_reliability_score | Reliability of the transaction |
| behavioural_safety_score | Safety of user behaviour |
| fraud_label | Transaction classification label |

### Target Variable

- **0:** Genuine Transaction
- **1:** Fraudulent Transaction

All four trust parameters range from 35 to 100.

## 🔄 Project Workflow

```text
CSV Dataset Upload
        ↓
Data Validation
        ↓
Exploratory Data Analysis
        ↓
Feature Selection
        ↓
Train / Validation / Test Split
        ↓
Machine Learning Model Training
        ↓
Model Comparison and Selection
        ↓
Threshold Optimization
        ↓
Final Model Evaluation
        ↓
Fraud Probability Prediction
        ↓
Trust Score Calculation
        ↓
Transaction Recommendation
        ↓
Trained Model Export
```

## 📈 Dataset Splitting

| Dataset | Percentage |
|---|---:|
| Training Dataset | 70% |
| Validation Dataset | 15% |
| Testing Dataset | 15% |

Stratified sampling is used to maintain the class distribution across all three datasets.

## 🔐 Trust Score Calculation

TrustFlow calculates an overall trust score using a weighted combination of four parameters.

| Parameter | Weight |
|---|---:|
| User Trust Score | 30% |
| Merchant Trust Score | 30% |
| Transaction Reliability Score | 25% |
| Behavioural Safety Score | 15% |
| Total | 100% |

### Mathematical Formula

```text
Trust Score = (0.30 × User Trust Score)
            + (0.30 × Merchant Trust Score)
            + (0.25 × Transaction Reliability Score)
            + (0.15 × Behavioural Safety Score)
```

## 🚦 Transaction Decision System

| Overall Trust Score | Recommended Action |
|---|---|
| Below 40 | 🔴 BLOCK |
| 40 to below 70 | 🟡 REVIEW |
| 70 and above | 🟢 APPROVE |

The machine learning fraud prediction and the weighted trust score recommendation are calculated separately, providing two complementary indicators of transaction risk.

## 📉 Model Evaluation Metrics

The machine learning models are evaluated using:

- Precision
- Recall
- F1-Score
- PR-AUC (Average Precision)
- ROC-AUC
- Confusion Matrix
- Classification Report

The classification threshold is optimized using the validation dataset to maximize the F1-Score.

## 📊 Data Visualizations

TrustFlow generates the following visualizations:

- Transaction Class Distribution
- Trust Score Distribution
- Confusion Matrix
- Precision-Recall Curve
- ROC Curve
- Feature Importance Graph

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming Language |
| NumPy | Numerical Computation |
| Pandas | Data Processing and Analysis |
| Matplotlib | Data Visualization |
| Scikit-learn | Machine Learning |
| Joblib | Model Serialization |
| Google Colab | Development Environment |
| GitHub | Version Control and Collaboration |

## 💻 How to Run the Project

1. Open the Jupyter Notebook available in this repository.
2. Click the **Open in Colab** button.
3. Select **Runtime → Run all**.
4. Upload the `trustflow_synthetic_dataset.csv` file when prompted.
5. Allow the system to train and evaluate the machine learning models.
6. View the evaluation metrics, graphs and transaction prediction report.
7. Download the generated trained model.

### Required Libraries

```bash
pip install numpy pandas matplotlib scikit-learn joblib ipython
```

The current notebook is designed to run in Google Colab.

## 🧪 Example Transaction

```python
predict_transaction(
    user_score=45,
    merchant_score=60,
    reliability_score=72,
    behaviour_score=40
)
```

The system generates a transaction report containing:

- Selected Machine Learning Model
- ML Fraud Probability
- Fraud or Genuine Prediction
- Overall Trust Score
- Recommended Transaction Action

## 📦 Trained Model

The trained machine learning model is exported as:

```text
trustflow_updated_model.joblib
```

The exported model package contains:

- Best-performing trained model
- Selected input features
- Optimized classification threshold
- Model name
- Trust score weights
- Dataset information
- Evaluation metrics

## 🔮 Future Scope

- Real-time payment fraud detection
- Integration with payment gateways and banking systems
- Interactive fraud monitoring dashboard
- REST API development
- Real-world transaction dataset integration
- Explainable AI using SHAP
- Automated fraud alerts
- Cloud deployment and scalable architecture

## ⚠️ Disclaimer

TrustFlow is an educational machine learning project developed using synthetic demonstration data. It is not a production-ready financial fraud detection system and requires further validation using real-world data before practical deployment.

## 🎓 Academic Project

Developed as a Machine Learning project to explore intelligent fraud detection, digital payment security and trust-based risk assessment.

---

**TrustFlow — Making Digital Transactions Safer Through Machine Learning.**
