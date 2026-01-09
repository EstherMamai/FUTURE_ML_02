# Models Directory

This folder contains the trained machine learning models and preprocessing artifacts for the customer churn prediction system.

## Files

- **logistic_regression_churn_model.pkl** - Trained Logistic Regression model (best performing model)
- **scaler.pkl** - StandardScaler fitted on training data for feature scaling
- **feature_names.pkl** - List of feature names in the correct order for model input

## Usage

To load the model for predictions:

```python
import pickle
import pandas as pd

# Load model
with open('../models/logistic_regression_churn_model.pkl', 'rb') as f:
    model = pickle.load(f)

# Load scaler
with open('../models/scaler.pkl', 'rb') as f:
    scaler = pickle.load(f)

# Load feature names
with open('../models/feature_names.pkl', 'rb') as f:
    feature_names = pickle.load(f)

# Use for predictions
# scaled_features = scaler.transform(your_data)
# predictions = model.predict(scaled_features)
# probabilities = model.predict_proba(scaled_features)
```

## Model Information

- **Model Type**: Logistic Regression
- **Training Date**: January 9, 2026
- **Performance Metrics**:
  - Accuracy: ~78.8%
  - Precision: ~59.2%
  - Recall: ~64.4%
  - F1-Score: ~61.7%
  - ROC-AUC: ~0.834

## Notes

- Models should be retrained quarterly with new data
- Feature preprocessing must match the training pipeline
- All categorical variables must be one-hot encoded
- Numerical features must be scaled using the saved scaler
