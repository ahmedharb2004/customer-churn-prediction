# 🏦 Bank Customer Churn Prediction

A machine learning project that predicts whether a bank customer will leave (churn) based on demographic and financial data.

---

## 📌 Problem Statement

Customer churn is a major challenge in the banking industry. This project builds and compares multiple classification models to identify customers at risk of leaving, enabling proactive retention strategies.

---

## 📊 Dataset

- **Source:** [Churn Modelling Dataset](https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling)
- **Records:** 10,000 customers
- **Features:** 13 input features including CreditScore, Geography, Gender, Age, Tenure, Balance, NumOfProducts, HasCrCard, IsActiveMember, EstimatedSalary
- **Target:** `Exited` (1 = churned, 0 = retained)

---

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn, XGBoost, Matplotlib, Seaborn

---

## 🔄 Project Pipeline

1. **Data Loading & Exploration** — info, describe, visualizations
2. **Data Visualization** — countplot, histograms, correlation heatmap
3. **Data Cleaning** — drop duplicates, check nulls
4. **Preprocessing** — drop irrelevant columns, One-Hot Encoding (Geography, Gender), StandardScaler
5. **Train/Test Split** — 80/20 split
6. **Model Training & Evaluation** — 3 models compared
7. **Model Comparison** — accuracy table

---

## 🤖 Models Used

| Model | Description |
|---|---|
| Logistic Regression | Baseline linear classifier |
| Random Forest | Ensemble of decision trees |
| XGBoost | Gradient boosting classifier |

---

## 📈 Evaluation Metrics

- Accuracy Score
- Confusion Matrix
- Classification Report (Precision, Recall, F1-score)

---

## 🚀 How to Run

```bash
# 1. Clone the repo
git clone https://github.com/ahmedharb2004/customer-churn-prediction.git
cd customer-churn-prediction

# 2. Install dependencies
pip install pandas scikit-learn xgboost matplotlib seaborn

# 3. Run the notebook
jupyter notebook Machine_Learning_Projec_The_last_update.ipynb
```

---

## 📁 Repository Structure

```
├── Churn_Modelling.csv
├── Machine_Learning_Projec_The_last_update.ipynb
└── README.md
```

---

## 👤 Author

**Ahmed Harb**
- GitHub: [@ahmedharb2004](https://github.com/ahmedharb2004)
- LinkedIn: [Ahmed Harb](https://www.linkedin.com/in/ahmed-mohamed-el-sayed-harb-735786322)
