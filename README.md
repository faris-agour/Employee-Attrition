
# Employee Attrition Prediction

![Azure](https://img.shields.io/badge/Deployed%20on-Azure-blue)
[Live App 🌐](https://attrition-predictor-app-cse26-ekavdgb6hyeeh8ah.westeurope-01.azurewebsites.net/)

This project aims to predict employee attrition using machine learning techniques. It covers the complete ML workflow — from data preprocessing and exploration, to modeling, hyperparameter tuning, and finally deploying the trained model as a web application on Azure.

---

## 🔍 About the Data

The dataset comes from IBM HR Analytics and contains detailed employee records. It includes 35+ features, both categorical and numerical, related to employee demographics, job role, environment satisfaction, etc.

- **Target Variable**: `Attrition`  
  - Type: Categorical (Yes/No)
  - Goal: Predict if an employee is likely to leave (Yes) or stay (No)

---

## 🧼 Data Exploration and Preprocessing

### 1. **Initial EDA**

Key statistics and visualizations were explored:
- Distribution of target class (`Attrition`)
- Correlation matrix
- Distribution plots for age, salary, distance from home
- Boxplots for job satisfaction vs attrition
- Countplots for categorical variables like JobRole, Department, MaritalStatus

### 2. **Data Cleaning & Processing**
- Removed redundant features (e.g., `EmployeeNumber`, `Over18`)
- Categorical encoding (Label Encoding, OneHotEncoding)
- Feature scaling (StandardScaler)
- Handled class imbalance using oversampling
- Split data into `train`, `validation`, and `test` sets

### 3. **Preprocessing Pipeline**
A full preprocessing pipeline using `scikit-learn` was built, which includes:
- Column transformers for numerical and categorical features
- Imputation
- Encoders
- Scaler
- Integration into ML pipeline

---

## 🤖 Model Building

### Baseline Models:
- **Logistic Regression**
- **Random Forest**
- **AdaBoost**
- **XGBoost**
- **DNN**

Each model was evaluated using:
- Accuracy
- Precision, Recall, F1-Score
- ROC-AUC Curve

### 🔧 Fine-Tuning:
RandomizedSearchCV was used to fine-tune hyperparameters of ensemble models. Best performance was achieved using tuned XGBoost and Random Forest.

---

## 🧠 Deep Neural Network (DNN)

A custom DNN was built using `Pytorch`:
- Input layer matching feature count
- Hidden layers with ReLU activation
- Dropout regularization
- Output layer with sigmoid activation
- Binary Crossentropy loss
- Adam optimizer
- 500 epochs

The DNN model outperformed traditional models in terms of generalization.

---

## 🚀 Deployment

The final trained model (best-performing) was exported using `joblib` and deployed on Azure App Services.

### 🔗 [Live App on Azure](https://attrition-predictor-app-cse26-ekavdgb6hyeeh8ah.westeurope-01.azurewebsites.net/)

The web app allows users to:
- Enter employee attributes
- Predict the probability of attrition
- See the classification outcome in real-time

---

## 🛠️ Tech Stack

- Python, Pandas, NumPy, Seaborn, Matplotlib
- Scikit-learn, Pytorch, XGBoost
- Streamlit (for webapp)
- Azure App Service (deployment)

---
