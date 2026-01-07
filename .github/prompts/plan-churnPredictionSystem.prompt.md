# Plan: Telco Customer Churn Prediction ML System

Build an end-to-end churn prediction system using the 7,043-customer telco dataset. Train classification models (Logistic Regression, Random Forest, XGBoost) with engineered features, evaluate with business-focused metrics, and deliver insights via visualizations highlighting key churn drivers and actionable retention strategies.

## Approach

**Single comprehensive notebook** in notebooks/ containing all stages:

1. **Data Loading & Exploration** – Load data/WA_Fn-UseC_-Telco-Customer-Churn.csv, analyze dataset structure, check churn distribution, fix `TotalCharges` empty strings, explore feature-churn relationships with visualizations

2. **Data Preprocessing** – Encode categorical features (binary for gender/services, one-hot for `PaymentMethod`/`InternetService`), engineer features (tenure bins, service count, automatic payment flag, monthly-to-total ratio), handle "No internet/phone service" values, scale numerical features

3. **Model Training & Comparison** – Split data 80/20 stratified, train three models (Logistic Regression baseline, Random Forest, XGBoost), handle class imbalance with SMOTE/class weights, tune hyperparameters with cross-validation

4. **Model Evaluation** – Generate confusion matrices for all models, calculate precision/recall/F1/ROC-AUC, compare model performance, extract feature importance from best model

5. **Business Insights & Visualization** – Segment customers by churn probability (low/medium/high risk), visualize churn drivers (contract type, tenure, payment method), create feature importance charts, plot ROC curves, generate actionable retention recommendations

6. **Model Persistence** – Save best performing model as pickle file for deployment, document model performance metrics and business recommendations

## Further Considerations

1. **Target metric priority** – Should we optimize for recall (catch all churners, more false positives) or precision (only confident predictions)? Depends on retention campaign cost vs customer lifetime value.

2. **Deployment format** – Dashboard only, or also include Streamlit web app for real-time predictions? Web app adds interactivity but requires more development time.

3. **Feature engineering depth** – Start with 4-5 core engineered features (tenure bins, service count, automatic payment, charges ratio) and expand if models underperform, or engineer all 12 suggested features upfront?
