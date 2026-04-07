# Explainable_AI

## Overview
Project for course Explainable AI (SOW-BKI266).

In this project we will explore the research question : How can SHAP and Counterfactual Explanations be used to distinguish between actual fraud and false positive anomalies in credit card transaction systems.

We will be applying two explanation methods:

SHAP

Counterfactual (DiCE)

## Repository structure:
```
├── xai_shap_counterfactuals.ipynb   # Main notebook with full analysis
├── card_transdata.csv               # Credit card transaction dataset
├── requirements.txt                 # Python dependencies
├── README.md
└── .gitignore
```

## Requirements and Installation

### Requirements
- Python 3.8+
- See "requirements.txt" for all dependencies
### 1. Clone the repository
```
git clone https://github.com/jiaxingb/Explainable_AI.git
cd Explainable_AI
<<<<<<< HEAD
```

### 2. Create and activate a virtual environment
```
python -m venv venv
```
source venv/bin/activate        # macOS/Linux
venv\Scripts\activate           # Windows

### 3. install dependencies
```
pip install -r requirements.txt

```

### 4. Open the notebook

```
jupyter notebook xai_shap_counterfactuals.ipynb
```


## Dataset
This project uses a sample of 1000 rows of the dataset: card_transdata.csv
https://www.kaggle.com/datasets/dhanushnarayananr/credit-card-fraud


## How does the code work

### 1. Preprocessing the data
- load the data
- use a sample of 1000 transactions for faster computation
- split train and test sets, stratified to preserve fraud ratio
- Standardizes features using `StandardScaler` (fit on train, transform on test to avoid data leakage)

### 2. SHAP Analysis
- Trains a TreeExplainer optimized or random Random Forest
- Computes SHAP values for all test sample
- **Summary plot**: shows global feature importance across all predictions
- **Force plot (true positive)**: shows how each feature pushes a single fraud prediction away from the base value
- **Force plot (false positive)**: same visualization for a misclassified transaction, diagnosing why the model was wrong

### 3. Counterfactual Analysis (DiCE)
- Sets up DiCE using the unscaled training data for human-readable results
- **True positive**: generates counterfactuals showing what would need to change for real fraud to no longer be flagged. Expectation: large changes across multiple features
- **False positive**: generates counterfactuals showing what would need to change for a wrongly flagged transaction to flip back to legit. Expectation: small changes to 1-2 features

### 4. Noise Injection
- Since the model produces no false positives on clean data, noise is added to the test features to simulate false positives. These can be uses to compare true positives and false positives

## Output
- SHAP summary plot showing global feature importance
- SHAP force plots for individual true positive and false positive transactions
- Counterfactual tables showing minimal feature changes needed to flip predictions


## Author
Jia Xing Yang s1152568 
2nd year Bsc AI student at the Radboud University
=======
>>>>>>> f0b4f0adf9757223e357f2c67b0c8b1095b7c9e7
