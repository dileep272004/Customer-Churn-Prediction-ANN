# Customer Churn Prediction Using Artificial Neural Networks

## Project Overview

This project focuses on predicting customer churn in the telecom industry using Artificial Neural Networks (ANN) and traditional Machine Learning models.

The objective is to identify customers who are likely to leave the telecom service so that the company can take proactive customer retention actions.

## Business Problem

Customer churn is a major challenge for telecom companies because losing customers can affect revenue and long-term business growth.

This project uses customer demographic, service, and account-related information to predict whether a customer is likely to churn.

## Dataset

- Dataset: Telco Customer Churn
- Rows: 7,043
- Columns: 21
- Target Variable: Churn
- Problem Type: Binary Classification
- Learning Type: Supervised Learning

Target classes:

- Yes → Customer churns
- No → Customer stays

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- TensorFlow
- Keras
- Keras Tuner
- Imbalanced-learn
- Jupyter Notebook

## Project Workflow

1. Data Loading
2. Exploratory Data Analysis
3. Data Cleaning
4. Missing Value Handling
5. Categorical Encoding
6. Feature Scaling
7. Train-Test Split
8. Class Imbalance Handling using SMOTE
9. Vanilla ANN Model
10. ANN Hyperparameter Tuning using Keras Tuner
11. Traditional Machine Learning Models
12. Hyperparameter Tuning using GridSearchCV
13. Model Performance Comparison
14. Final Model Selection
15. Business Recommendations

## Exploratory Data Analysis

EDA was performed to understand customer characteristics and identify patterns related to churn.

Important observations included:

- Month-to-month contract customers showed higher churn.
- Fiber optic customers showed higher churn compared with DSL and customers without internet service.
- Electronic check users showed higher churn.
- The dataset contains class imbalance, with more non-churn customers than churn customers.

## Data Preprocessing

The following preprocessing steps were performed:

- Checked missing values and duplicates.
- Converted `TotalCharges` into numeric format.
- Removed the customer identifier from model features.
- Applied One-Hot Encoding to categorical variables.
- Applied StandardScaler to numerical features.
- Split the data into training and testing sets.
- Applied SMOTE only to the training data.

After preprocessing, the dataset contained 45 input features.

## Vanilla ANN

A baseline Artificial Neural Network was developed with the following architecture:

45 → 32 → 16 → 1

- Hidden layer activation: ReLU
- Output activation: Sigmoid
- Optimizer: Adam
- Loss function: Binary Cross-Entropy
- Epochs: 50
- Batch Size: 32

### Vanilla ANN Result

- Accuracy: 77.40%
- ROC-AUC: 81.16%

## Tuned ANN

Keras Tuner with Random Search was used to search for a better ANN architecture.

The best architecture was:

45 → 32 → 64 → 48 → 1

- Learning Rate: 0.0005
- Number of Trials: 10
- Validation Accuracy: 84.81%

The tuned ANN achieved 76.33% accuracy on the unseen test data.

## Machine Learning Models

Traditional Machine Learning models were also developed for comparison:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting

Random Forest and Gradient Boosting were further tuned using GridSearchCV.

## Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

## Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Vanilla ANN | 77.40% | 55.02% | 67.38% | 60.58% | 81.16% |
| Tuned ANN | 76.33% | 55.04% | 59.89% | 57.36% | 80.20% |
| Logistic Regression | 73.21% | 49.74% | 77.81% | 60.69% | 83.34% |
| Decision Tree | 73.99% | 50.93% | 58.29% | 54.36% | 68.98% |
| Random Forest | 77.19% | 57.10% | 56.95% | 57.03% | 81.11% |
| Gradient Boosting | 76.69% | 55.02% | 67.38% | 60.58% | 83.36% |
| Tuned Random Forest | 77.33% | 57.07% | 59.36% | 58.19% | 81.35% |

## Key Findings

- Highest Accuracy: Vanilla ANN – 77.40%
- Highest Recall: Logistic Regression – 77.81%
- Highest F1-Score: Logistic Regression – 60.69%
- Highest ROC-AUC: Gradient Boosting – 83.36%
- Highest Precision: Random Forest – 57.10%

## Final Model Selection

Logistic Regression was selected as the preferred model for the customer churn prediction objective.

The main reason was its highest recall of 77.81%.

Since the business goal is to identify customers who may churn, higher recall helps identify more potential churn customers and provides more opportunities for proactive retention.

## Business Recommendations

- Identify high-risk customers using churn predictions.
- Provide personalized offers and retention plans.
- Focus retention efforts on customers with high churn probability.
- Use model predictions to support proactive customer retention strategies.

## Conclusion

This project demonstrates how Artificial Neural Networks and traditional Machine Learning models can be used for customer churn prediction.

The results show that ANN performed competitively with traditional Machine Learning models. However, different models performed best on different evaluation metrics.

Therefore, model selection should be based on the business objective rather than accuracy alone.
