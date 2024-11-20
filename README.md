# Credit Risk Classification - Module 20 Challenge

## Reopository Overview

This repository contains the code for the Module 20 challenge, which uses supervised machine learning to train a model based on loan risk.

The original data can be found in the `Resources` folder, and is in a file titled `lending_data.csv`. The main codebook is in the file titled `credit_risk_classification.ipynb`, which is found in the main repository. To write this code, I referred to the starter code (located in the main repository and titled `credit_risk_classification_starter.ipynb`) as well as the in-class activities from Module 20.

# Credit Risk Analysis Report
## Overview of the Analysis

This analysis aimed to predict the status of loans as either healthy (`0`) or high-risk of default (`1`) using machine learning. The main goal was to develop a model that can accurately classify loans to help financial institutions effectively assess risk. The dataset contained financial information about loans, including the size of the loan, the interest rate, and income and debt information of the borrower. 96.8% of the loans in the dataset were classified as healthy (`0`), and 3.2% were classified as high-risk (`1`).

The stages of the machine learning process included:
1. **Data Preprocessing**: Separating the features (`X`) and labels set (`y`) and splitting the data into training and testing sets using `train_test_split`.
2. **Model Selection**: The `LogisticRegression` algorithm was used for its simplicity and interpretability.
3. **Model Training**: The model was trained on the training data, and then used this training to make its predictions.
4. **Model Evaluation**: A confusion matrix and classification report were generated to assess the model's performance using metrics such as accuracy, precision, recall, and F1-score.

## Results

### Machine Learning Model: Logistic Regression
- **Accuracy**: 99%  
  - **Explanation**: Accuracy measures the percentage of all predictions (both `0` and `1`) that are correct. This indicates that 99% of the loans were correctly classified as either healthy or high-risk.

- **Precision**:  
  - Class `0` (Healthy Loan): 100%  
    - **Explanation**: Precision for class `0` indicates that every loan predicted as healthy (`0`) was actually healthy. There were no false positives for this class.  
  - Class `1` (High-Risk Loan): 84%  
    - **Explanation**: Precision for class `1` shows that 84% of loans predicted as high-risk were truly high-risk. However, 16% of loans classified as high-risk were actually healthy loans (false positives).

- **Recall**:  
  - Class `0` (Healthy Loan): 99%  
    - **Explanation**: Recall for class `0` reflects the model's ability to correctly identify healthy loans. It correctly labeled 99% of all actual healthy loans, with 1% misclassified as high-risk loans (false negatives).  
  - Class `1` (High-Risk Loan): 94%  
    - **Explanation**: Recall for class `1` indicates that 94% of all actual high-risk loans were correctly identified. Only 6% of high-risk loans were misclassified as healthy loans (false negatives).

- **F1-Score**:  
  - Class `0` (Healthy Loan): 100%  
    - **Explanation**: The F1-score for class `0` combines precision and recall into a single metric. A perfect score indicates the model excels in predicting healthy loans with balance.  
  - Class `1` (High-Risk Loan): 89%  
    - **Explanation**: The F1-score of 89% for class `1` indicates the model is good at identifying high-risk loans, though there is some trade-off between precision and recall.


## Summary

The Logistic Regression model performs exceptionally well, achieving high accuracy (99%) and strong precision and recall scores for both classes. 

### Recommendation
- The model performs best at predicting healthy loans (`0`), with near-perfect precision and recall.
- It also predicts high-risk loans (`1`) effectively, with 94% recall and 84% precision, though there is a trade-off in precision where some healthy loans are misclassified as high risk.

### Problem-Specific Consideration
- If minimizing false negatives (i.e., missing high-risk loans) is critical, this model is highly suitable because of its high recall for class `1`.
- If minimizing false positives (i.e., misclassifying healthy loans as high risk) is more critical, the model could benefit from further tuning to improve precision for class `1`.

In this context, it is likely that the more important thing would be to avoid false negatives, for which this model is well-suited. If this model were to be used, since high-risk loans are less frequent anyway, a loan flagged as high-risk could be inspected by hand to make sure it is indeed high-risk and not misclassified. If the financial institution using this model is equipped to do so, this would be the recommened approach with using this model.

Overall, the Logistic Regression model is recommended for its balanced performance, particularly in identifying high-risk loans while maintaining high accuracy for healthy loans.