# ICU Mortality Prediction with Explainable AI 
## Overview
This project develops and interprets a machine learning model for predicting in-hospital mortality in intensive care unit (ICU) patients using a PhysioNet-derived critical care dataset. The project was designed not only to build a predictive model, but also to demonstrate how explainability and clinically meaningful evaluation can support safer and more trustworthy use of AI in healthcare.

Rather than focusing only on model accuracy, this project examines how ICU mortality prediction should be evaluated in a high-stakes clinical context, where missed high-risk patients may have serious consequences.

## Clinical Problem Statement
Early identification of high-risk patients in Intensive Care Units (ICUs) is critical for timely intervention, resource allocation, and improving patient outcomes. This project explores whether machine learning models can support ICU mortality risk stratification using clinically established severity indicators. Rather than focusing purely on predictive performance, the project emphasises:
- Clinical plausibility
- Explainability
- Responsible use of health data


## Dataset
This project uses a publicly available ICU outcomes dataset derived from PhysioNet.
The dataset contains 4,000 ICU patient records with:
- SAPS-I (Simplified Acute Physiology Score)
- SOFA (Sequential Organ Failure Assessment)
- Outcome variable: In-hospital mortality

Key characteristics:
- Mortality rate: ~13.8%
- Structured clinical severity data
- No missing values in selected predictors

## Methods
1. Feature Selection 
Only clinically appropriate variables were used:
- SAPS-I
- SOFA
Variables such as Length of stay, Survival time, and Record identifiers were explicitly excluded to avoid data leakage and ensure that the model uses only information available at the time of clinical decision-making.
2. Model Development
Two models were implemented:
- Logistic Regression (baseline, interpretable model)
- Random Forest (non-linear ensemble model)

Data was split into training and test sets using stratification to preserve class balance.

3. Evaluation Strategy
Model performance was evaluated using:
- Precision, Recall, F1-score
- ROC-AUC
- Confusion Matrix
  
This reflects a healthcare-aware evaluation approach, where recall (sensitivity) is particularly important to avoid missing high-risk patients.

## Explainability
To move beyond black-box modelling, SHAP (SHapley Additive exPlanations) was used to interpret model predictions.
Key Findings:
- SAPS-I and SOFA contributed almost equally to model predictions
- No single dominant feature
- No spurious or non-clinical variables influencing predictions

The model’s behavior aligns with clinical reasoning:
- SAPS-I reflects overall physiological severity
- SOFA reflects organ dysfunction
The balanced importance suggests that mortality risk in ICU settings is driven by a combination of severity and organ failure, rather than a single dominant factor.
This increases confidence in the model’s validity and interpretability.

## Final Consideration
This project demonstrates that in healthcare AI, model validity is not just about performance —
it is about clinical plausibility, explainability, and responsible design.

