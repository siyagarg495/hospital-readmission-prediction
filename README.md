# Hospital 30-Day Readmission Prediction

## Overview

This project predicts whether a patient will be readmitted to the hospital within 30 days using patient encounter data.

A Logistic Regression model is trained with and without L2 regularization and evaluated using classification metrics and ROC-AUC.

## Problem Statement

Hospital readmissions can increase healthcare costs and resource utilization. 
The objective of this project is to identify patients at higher risk of 30-day readmission.

## Dataset

The project uses the Diabetes 130-US Hospitals dataset.

The dataset contains hospital encounter records along with demographic,
hospitalization, prior-visit and medication-related information.

## Machine Learning Approach

### Data Preprocessing
- Missing value handling
- Removal of high-missing columns
- Removal of identifier columns
- Binary target creation
- Numerical feature scaling
- Categorical feature encoding

### Features

Numerical:
- Time in hospital
- Number of lab procedures
- Number of procedures
- Number of medications
- Outpatient visits
- Emergency visits
- Inpatient visits
- Number of diagnoses

Categorical:
- Race
- Gender
- Age
- Admission type
- Medication change
- Diabetes medication indicator

### Model

- Logistic Regression
- Logistic Regression with L2 regularization

## Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix
- ROC Curve

### L2 Logistic Regression Results

| Metric | Score |
|---|---:|
| Accuracy | 88.85% |
| Precision | 51.61% |
| Recall | 1.41% |
| F1 Score | 2.74% |
| ROC-AUC | 0.641 |

The results show that accuracy alone is not sufficient for evaluating this
imbalanced classification problem. ROC-AUC and recall provide additional
information about model performance.

## Clinical Cost Consideration

False negatives can be important because an actual 30-day readmission may not
be identified for potential follow-up.

False positives may result in additional follow-up or resource utilization.

Therefore, the classification threshold should be selected according to the
relative costs of these errors rather than relying only on the default 0.5 threshold.

## Project Structure

hospital-readmission-prediction/
│
├── README.md
├── notebooks/
│   └── Hospital_30_Day_Readmission_Prediction.ipynb
├── images/
├── data/
├── requirements.txt
└── .gitignore
