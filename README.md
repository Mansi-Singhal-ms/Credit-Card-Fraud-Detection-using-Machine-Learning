# Credit-Card-Fraud-Detection-using-Machine-Learning

## 📌 Project Overview

This project focuses on detecting fraudulent transactions using machine learning techniques on an imbalanced dataset. The primary goal is to build a model that generalizes well to unseen data while prioritizing the detection of fraud cases.

## Problem Statement

Fraudulent transactions are rare and hard to detect, posing a significant challenge to financial institutions. The goal is to identify these fraudulent transactions without disrupting legitimate activities.

Binary classification problem: Fraud (1) vs Non-Fraud (0)

Highly imbalanced target variable

## Feature Explanation:

distance_from_home - the distance from home where the transaction happened.

distance_from_last_transaction - the distance from last transaction happened.

ratio_to_median_purchase_price - Ratio of purchased price transaction to median purchase price.

repeat_retailer - Is the transaction happened from same retailer.

used_chip - Is the transaction through chip (credit card).

used_pin_number - Is the transaction happened by using PIN number.

online_order - Is the transaction an online order.

fraud - Is the transaction fraudulent.

## 🔍 Exploratory Data Analysis (EDA)

Analyzed feature distributions

Performed data leakage checks using correlation analysis

Verified data quality (missing values, outliers)

Correlation Heatmap: Plotted to examine relationships between features.

Class Distribution: Checked the balance of fraudulent vs. legitimate transactions in the fraud column.

## Data Preprocessing

### Missing Data
We checked for missing values using df.isnull().sum(). Missing data was imputed or removed based on its significance.

### Outlier Detection and Handling
Outliers were detected using box plots for key columns:

distance_from_home
distance_from_last_transaction
ratio_to_median_purchase_price

Outliers were handled using a combination of log transformation and IQR-based capping, with all preprocessing parameters learned exclusively from training data to ensure robust and leakage-free model evaluation.

Train-test split performed before modeling

## 🤖 Model Development

Multiple models were initially evaluated:

Decision Tree

Random Forest

Logistic Regression

Tree-based models showed near-perfect validation scores, which raised concerns about overfitting or memorization. After verification, a simpler, reliable and more interpretable model was selected.

## ✅ Final Model Selected

Logistic Regression (with regularization and class balancing)

Reasons for selection:

Demonstrates better generalization on unseen data

Stable validation metrics

High interpretability

Effective handling of class imbalance

## 📈 Model Evaluation (Test Set)

Metric	                    Value
Accuracy	                  95%
Recall (Fraud)	            97%
Precision (Fraud)	          64%
ROC-AUC	                    0.99
PR-AUC	                    0.88

### Metric Interpretation

ROC-AUC measures overall class separability
PR-AUC is more informative for imbalanced datasets and reflects fraud detection quality

## 🧠 Key Learnings

Proper model evaluation on imbalanced data is more important than achieving high accuracy.

PR-AUC is a critical metric for fraud detection problems

High recall is essential to minimize missed fraud cases

## 📁 Repository Structure
├── eda & preprocessing.ipynb
├── model training.ipynb
├── README.md
├── requirements.txt
└── final_model.pkl

## 🏁 Conclusion

A well-regularized Logistic Regression model was successfully built and evaluated for fraud detection. The model demonstrates strong performance on unseen data and is suitable for real-world imbalanced classification problems.

## Recommendations:
Real-Time Monitoring: Implementing this model in a real-time transaction monitoring system can help flag high-risk transactions promptly, reducing fraud-related losses.

Continuous Model Updating: Regular updates with new transaction data will ensure the model adapts to emerging fraud patterns.

By integrating this machine learning-based solution into financial systems, organizations can strengthen their defenses against fraud, ensuring both security and a seamless customer experience.
