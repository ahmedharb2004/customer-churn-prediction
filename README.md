# 🏦 Bank Customer Churn Prediction

A machine-learning project that predicts whether a bank customer will leave (churn) based on demographic and financial data, comparing three classification models on a held-out test set.

---

## 📌 Problem Statement

Customer churn is a major challenge in the banking industry. This project builds and compares multiple classification models to identify customers at risk of leaving, enabling proactive retention strategies.

---

## 📊 Dataset

- **Source:** [Churn Modelling Dataset on Kaggle](https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling) (a widely used fictional bank dataset for ML teaching)
- **Records:** 10,000 customers
- **Features:** 13 input features including CreditScore, Geography, Gender, Age, Tenure, Balance, NumOfProducts, HasCrCard, IsActiveMember, EstimatedSalary
- **Target:** `Exited` (1 = churned, 0 = retained); about 20.4% of customers churned

> The CSV is **not** stored in this repository: the dataset's redistribution license is not stated on its source page, so it is linked instead of republished. Download `Churn_Modelling.csv` from the Kaggle link above and place it next to the notebook to reproduce every number below.

---

## 📈 Results (actual run)

Reproduced by running the notebook's exact code on the public dataset: 80/20 train/test split (`random_state=42`, 2,000 test rows). `StandardScaler` is fit on the training data only, so no test-set statistics leak into training. One-hot encoding uses fixed category values (Geography, Gender) and carries no target information.

| Model | Accuracy | Precision (churn) | Recall (churn) | F1 (churn) |
|---|---|---|---|---|
| Logistic Regression | 81.1% | 55.2% | 20.1% | 29.5% |
| Random Forest | 86.7% | 75.8% | 47.1% | 58.1% |
| **XGBoost** | **87.0%** | 71.7% | **55.5%** | **62.6%** |

For context, always predicting "no churn" scores 79.6% accuracy but catches zero churners. XGBoost is the best overall model here and catches 218 of 393 actual churners in the test set.

![Model comparison and XGBoost confusion matrix](results_model_comparison.png)

**Honest limitation:** all three models still miss many churners (best recall 55.5%). The dataset is imbalanced (80/20) and the notebook trains with default class weights. Handling the imbalance (class weights, SMOTE, threshold tuning) is the natural next step, and it is exactly what my [Health Check ML](https://github.com/ahmedharb2004/Health-Check-ML) project explores.

---

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn, XGBoost, Matplotlib, Seaborn

---

## 🔄 Project Pipeline

1. **Data Loading & Exploration** — info, describe, visualizations
2. **Data Visualization** — countplot, histograms, correlation heatmap
3. **Data Cleaning** — drop duplicates, check nulls
4. **Preprocessing** — drop irrelevant columns, One-Hot Encoding (Geography, Gender), StandardScaler fit on the training split only
5. **Train/Test Split** — 80/20 split (`random_state=42`)
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

## 🚀 How to Run

```bash
# 1. Clone the repo
git clone https://github.com/ahmedharb2004/customer-churn-prediction.git
cd customer-churn-prediction

# 2. Download the dataset (see the Dataset section) and place
#    Churn_Modelling.csv in this folder

# 3. Install dependencies
pip install pandas scikit-learn xgboost matplotlib seaborn jupyter

# 4. Run the notebook
jupyter notebook "Machine Learning Projec The last update.ipynb"
```

---

## 📁 Repository Structure

```
├── Machine Learning Projec The last update.ipynb   # full analysis notebook
├── results_model_comparison.png                    # real test-set results figure
└── README.md
```

(`Churn_Modelling.csv` is downloaded separately, see the Dataset section.)

---

## 👤 Author

**Ahmed Harb**
- GitHub: [@ahmedharb2004](https://github.com/ahmedharb2004)
- LinkedIn: [Ahmed Harb](https://www.linkedin.com/in/ahmed-harb-735786322/)
