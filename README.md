# Telco Customer Churn Prediction

A comprehensive machine learning project for predicting customer churn in the telecommunications industry using advanced analytics and multiple classification models.

## 📋 Project Overview

This project analyzes customer data from a telecommunications company to predict which customers are likely to churn (leave the service). The solution includes data exploration, feature engineering, multiple ML models, and actionable business insights.

### Key Features
- **End-to-end ML pipeline** from data loading to model deployment
- **Multiple model comparison**: Logistic Regression, Random Forest, and XGBoost
- **Advanced feature engineering** with 5 custom predictive features
- **Class imbalance handling** using SMOTE technique
- **Business insights** and customer risk segmentation
- **Production-ready model** with saved artifacts

## 🎯 Business Problem

Customer churn is a critical issue for telecom companies. This project aims to:
1. Identify customers at high risk of churning
2. Understand key factors driving churn
3. Enable targeted retention strategies
4. Reduce customer acquisition costs

## 📊 Dataset

**Source**: Telco Customer Churn Dataset  
**Location**: `data/WA_Fn-UseC_-Telco-Customer-Churn.csv`

**Dataset Characteristics**:
- **Records**: 7,043 customers
- **Features**: 21 original features
- **Target**: Churn (Yes/No)
- **Features Include**: 
  - Demographics (gender, senior citizen, partner, dependents)
  - Services (phone, internet, security, backup, etc.)
  - Account info (tenure, contract, payment method, charges)

## 🛠️ Technologies Used

- **Python 3.8+**
- **pandas & numpy** - Data manipulation
- **matplotlib & seaborn** - Visualization
- **scikit-learn** - ML models and preprocessing
- **XGBoost** - Gradient boosting classifier
- **imbalanced-learn** - SMOTE for class balancing
- **Jupyter Notebook** - Interactive development

## 📁 Project Structure

```
FUTURE_ML_02/
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── notebooks/
│   ├── churn_prediction_complete.ipynb
│   ├── random_forest_churn_model.pkl (generated)
│   ├── scaler.pkl (generated)
│   ├── feature_names.pkl (generated)
│   └── model_metrics.csv (generated)
├── requirements.md
└── README.md
```

## 🚀 Getting Started

### Prerequisites

Ensure you have Python 3.8 or higher installed.

### Installation

1. **Clone the repository** (or download the project folder)

2. **Install dependencies**:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn jupyter notebook
```

3. **Launch Jupyter Notebook**:
```bash
cd FUTURE_ML_02
jupyter notebook
```

4. **Open the notebook**:
   - Navigate to `notebooks/churn_prediction_complete.ipynb`
   - Run all cells sequentially

## 📈 Project Workflow

### 1. Data Loading & Exploration
- Load and inspect the dataset
- Check for missing values and data types
- Analyze churn distribution (~26.5% churn rate)
- Visualize key features vs churn

### 2. Data Preprocessing & Feature Engineering
- Clean TotalCharges column (convert to numeric)
- Handle missing values
- Create 5 engineered features:
  - `tenure_group`: Customer loyalty segments
  - `service_count`: Total subscribed services
  - `automatic_payment`: Binary flag for auto-pay
  - `monthly_to_total_ratio`: Recent plan change indicator
  - `avg_monthly_spend`: Average spending pattern
- Encode categorical variables
- Standardize service values

### 3. Model Training & Comparison
- Split data (80/20 train/test, stratified)
- Apply SMOTE to balance training data
- Scale features using StandardScaler
- Train three models:
  - Logistic Regression
  - Random Forest
  - XGBoost
- Evaluate using multiple metrics

### 4. Model Evaluation
- Compare models on: Accuracy, Precision, Recall, F1-Score, ROC-AUC
- Generate confusion matrices
- Plot ROC curves
- Select best model based on F1-Score

### 5. Business Insights & Visualization
- Feature importance analysis
- Customer risk segmentation (Low/Medium/High risk)
- Churn probability distributions
- Actionable business recommendations

### 6. Model Persistence
- Save best model (pickle format)
- Save preprocessing objects (scaler, feature names)
- Export performance metrics

## 📊 Results

### Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | ~77% | ~64% | ~80% | ~71% | ~85% |
| Random Forest | ~79% | ~67% | ~81% | ~73% | ~87% |
| XGBoost | ~79% | ~68% | ~79% | ~73% | ~87% |

*Best Model*: **Random Forest** (highest F1-Score)

### Key Churn Drivers

1. **Contract Type**: Month-to-month contracts → highest churn
2. **Tenure**: First-year customers most vulnerable
3. **Payment Method**: Electronic check users churn more
4. **Internet Service**: Fiber optic without add-ons → higher risk
5. **Service Count**: Fewer services → higher churn

## 💡 Business Recommendations

### High-Risk Customers (>70% churn probability)
- Offer incentives to switch to annual/2-year contracts
- Promote automatic payment methods with discounts
- Immediate proactive outreach

### Medium-Risk Customers (30-70% churn probability)
- Bundle additional services with attractive pricing
- Early engagement programs for new customers
- Regular satisfaction check-ins

### Low-Risk Customers (<30% churn probability)
- Maintain loyalty programs
- Continue satisfaction monitoring
- Upsell premium services

## 🔮 Future Enhancements

- [ ] Hyperparameter tuning with GridSearchCV
- [ ] Deploy model as REST API
- [ ] Create interactive dashboard (Streamlit/Dash)
- [ ] Implement A/B testing framework
- [ ] Add time-series analysis for temporal patterns
- [ ] Integrate with CRM systems
- [ ] Automated monthly retraining pipeline

## 📝 Model Usage

To use the trained model for predictions:

```python
import pickle
import pandas as pd

# Load model and preprocessing objects
with open('notebooks/random_forest_churn_model.pkl', 'rb') as f:
    model = pickle.load(f)

with open('notebooks/scaler.pkl', 'rb') as f:
    scaler = pickle.load(f)

with open('notebooks/feature_names.pkl', 'rb') as f:
    feature_names = pickle.load(f)

# Prepare new customer data (must match training features)
# new_customer_data = ... (preprocess similar to training)

# Make prediction
prediction = model.predict(new_customer_data)
churn_probability = model.predict_proba(new_customer_data)[:, 1]

print(f"Churn Prediction: {'Yes' if prediction[0] == 1 else 'No'}")
print(f"Churn Probability: {churn_probability[0]:.2%}")
```

## 📄 License

This project is for educational and analytical purposes.

## 👥 Contributors

- Data Science Team
- Business Analytics Team

## 📞 Contact

For questions or collaboration opportunities, please reach out to the project maintainer.

---

**Last Updated**: January 2026  
**Status**: ✅ Production Ready
