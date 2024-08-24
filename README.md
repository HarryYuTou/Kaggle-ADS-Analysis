# Kaggle ADS Analysis Project

## Overview
This project aims to analyze the chosen Automated Decision System (ADS) which develops a predictive system to assess loan default probabilities. The ADS leverages various data sources to help financial institutions make informed decisions about loan approvals, particularly focusing on underserved populations who may lack extensive credit histories. We analyzed the ADS for various aspects, including the accuracy, fairness across gender groups, stability, robustness and feature importance.

## Project Structure

### 1. **Background**
The ADS is designed to address the challenge of predicting loan defaults, which is critical in financial services. By analyzing credit applications, the system predicts the likelihood of a client experiencing difficulties in repaying a loan, thereby aiding in more responsible and fair financial decision-making. 

### 2. **Data Description**
The dataset used in this project includes multiple sources of information provided by Home Credit:
- **application_train/application_test**: Static data for all loan applications.
- **bureau**: Information about previous credits from other financial institutions.
- **bureau_balance**: Monthly balances of previous credits.
- **POS_CASH_balance**: Monthly balance snapshots of previous POS and cash loans.
- **credit_card_balance**: Monthly balance snapshots of previous credit cards.
- **previous_application**: Historical data of all previous applications.
- **installments_payments**: Repayment history for previously disbursed credits.

### 3. **Input Features**
The input data includes both categorical (e.g., 'CODE_GENDER', 'FLAG_OWN_CAR') and numerical features (e.g., 'DAYS_CREDIT', 'AMT_CREDIT_SUM'). Missing values are handled using simple imputation techniques, such as filling missing values with zeros or means, depending on the feature’s importance.

### 4. **Output**
The ADS outputs a probability score between 0 and 1, indicating the likelihood of a client defaulting on a loan. A threshold is applied to this score to classify applications as high or low risk.

### 5. **Implementation and Validation**
The implementation process involves:
- **Data Preprocessing**: Cleaning and preparing the data, including handling missing values, merging related datasets, and feature engineering.
- **Modeling**: The primary model used is the XGBoost classifier, which is efficient and scalable, making it suitable for large datasets.
- **Validation**: The model’s performance is validated using the ROC AUC score, with a final score of around 78%, indicating decent predictive power given the dataset’s complexity.

### 6. **Outcome Analysis**
- **Accuracy Metrics**: The overall accuracy of the model is 91.9%. However, recall scores are low across different demographics, indicating the model’s difficulty in correctly identifying clients who may default.
- **Fairness Evaluation**: The model is evaluated for fairness across gender and income levels, using metrics like Demographic Parity, Equal Opportunity, and Predictive Equality.
- **Stability and Robustness**: The model’s stability is assessed using bootstrapping, while robustness is tested through cross-validation and data perturbation.

### 7. **Summary**
The ADS demonstrates high overall accuracy but struggles with recall, particularly in identifying potential defaulters. The model’s performance is stable and robust, making it suitable for deployment in public sectors, though improvements in handling class imbalance and fairness are recommended.
