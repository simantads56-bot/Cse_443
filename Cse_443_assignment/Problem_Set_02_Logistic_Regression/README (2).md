
# Bank Marketing Prediction Using Logistic Regression

## Problem Statement

The objective of this project is to develop a Logistic Regression model
to predict whether a bank customer will subscribe to a term deposit.

The target variable is:

- NO: Customer did not subscribe to a term deposit
- YES: Customer subscribed to a term deposit

## Dataset

The Bank Marketing dataset contains 45,211 customer records and 17 attributes.

The dataset contains:

- 45,211 total records
- 16 input features
- 1 target variable (`y`)

The target distribution is:

- NO: 39,922 (88.30%)
- YES: 5,289 (11.70%)

The target variable is imbalanced, with significantly more NO samples
than YES samples.

## Methodology

The following steps were performed:

1. Loaded the Bank Marketing dataset.
2. Inspected the dataset structure and data types.
3. Checked for missing values.
4. Encoded the target variable:
   - NO = 0
   - YES = 1
5. Separated input features and target variable.
6. Split the dataset into 80% training and 20% testing data.
7. Used stratified splitting to preserve the target class distribution.
8. Applied StandardScaler to numerical features.
9. Applied One-Hot Encoding to categorical features.
10. Trained a Logistic Regression model.
11. Generated predictions on the test dataset.
12. Evaluated the model using Accuracy, Precision, Recall, F1-Score,
    Classification Report, and Confusion Matrix.

## Feature Preprocessing

### Numerical Features

The following numerical features were standardized using StandardScaler:

- age
- balance
- day
- duration
- campaign
- pdays
- previous

### Categorical Features

The following categorical features were encoded using One-Hot Encoding:

- job
- marital
- education
- default
- housing
- loan
- contact
- month
- poutcome

After preprocessing, the 16 original features were transformed into
51 numerical features.

## Train-Test Split

The dataset was divided using an 80:20 train-test split.

- Training samples: 36,168
- Testing samples: 9,043

Stratified splitting was used to maintain approximately the same class
distribution in both sets.

## Model

The classification model used in this project is Logistic Regression.

Model configuration:

- Algorithm: Logistic Regression
- Maximum iterations: 1000
- Random state: 42

## Evaluation Metrics

The model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

## Results

The model achieved the following results on the test dataset:

| Metric | Score |
|---|---:|
| Accuracy | 90.12% |
| Precision | 64.45% |
| Recall | 34.78% |
| F1-Score | 45.18% |

## Classification Report

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| NO | 91.86% | 97.46% | 94.57% |
| YES | 64.45% | 34.78% | 45.18% |

## Confusion Matrix

| Actual / Predicted | NO | YES |
|---|---:|---:|
| NO | 7782 | 203 |
| YES | 690 | 366 |

Therefore:

- True Negative (TN): 7,782
- False Positive (FP): 203
- False Negative (FN): 690
- True Positive (TP): 366

## Findings

The Logistic Regression model achieved a high overall accuracy of 90.12%.
However, accuracy alone does not fully represent the model performance
because the dataset is highly imbalanced.

The model achieved a recall of only 34.78% for the YES class. This means
that many customers who actually subscribed to a term deposit were
classified as NO.

The model performed much better on the NO class, achieving a recall of
97.46% and an F1-score of 94.57%.

The difference between the performance of the NO and YES classes indicates
that class imbalance is an important limitation of this model.

## Model Saving

The trained model and preprocessing pipeline were saved together using
Joblib:

`bank_logistic_regression.pkl`

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Joblib
- Matplotlib
- Seaborn
- Google Colab

## Conclusion

A Logistic Regression model was successfully developed to predict term
deposit subscription using the Bank Marketing dataset.

The model achieved 90.12% accuracy on the test dataset. However, the
relatively low recall of 34.78% for the YES class shows that the model
has difficulty identifying customers who subscribe to a term deposit.

The class imbalance in the dataset is an important factor affecting the
model's performance. Future work could investigate techniques such as
class weighting, resampling, or alternative classification algorithms
to improve minority-class detection.
