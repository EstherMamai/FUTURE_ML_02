# Project Requirements

## Python Version
- Python 3.8 or higher

## Required Libraries

### Data Processing & Analysis
```
pandas>=1.3.0
numpy>=1.21.0
```

### Visualization
```
matplotlib>=3.4.0
seaborn>=0.11.0
```

### Machine Learning
```
scikit-learn>=1.0.0
xgboost>=1.5.0
imbalanced-learn>=0.9.0
```

### Development & Utilities
```
jupyter>=1.0.0
notebook>=6.4.0
```

## Installation

### Using pip

Install all requirements at once:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn jupyter notebook
```

Or install from a requirements.txt file:
```bash
pip install -r requirements.txt
```

### Using conda

```bash
conda install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn jupyter notebook
```

## requirements.txt Format

For easy installation, create a `requirements.txt` file with:
```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
xgboost>=1.5.0
imbalanced-learn>=0.9.0
jupyter>=1.0.0
notebook>=6.4.0
```

## Verification

To verify all packages are installed correctly, run:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from xgboost import XGBClassifier
from imblearn.over_sampling import SMOTE

print("All packages imported successfully!")
```
