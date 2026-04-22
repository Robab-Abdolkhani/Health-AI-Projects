# ICU Mortality Prediction with Explainable AI 
## Overview
This project develops and interprets a machine learning model for predicting in-hospital mortality in intensive care unit (ICU) patients using a PhysioNet-derived critical care dataset. The project was designed not only to build a predictive model, but also to demonstrate how explainability and clinically meaningful evaluation can support safer and more trustworthy use of AI in healthcare.

Rather than focusing only on model accuracy, this project examines how ICU mortality prediction should be evaluated in a high-stakes clinical context, where missed high-risk patients may have serious consequences.

## Clinical Problem Statement
Early identification of ICU patients at increased risk of in-hospital mortality can support timely escalation of care, closer monitoring, and more informed clinical prioritisation. In real-world settings, such models could function as clinical decision-support tools for risk stratification rather than autonomous decision-makers.

This project therefore asks:

Can a machine learning model identify patients at higher mortality risk using structured ICU variables, and can its predictions be explained in a way that supports clinical trust?

This project aimed to:
1. Build a baseline ICU mortality prediction model
2. Evaluate the model using clinically relevant metrics beyond accuracy
3. Apply explainable AI methods to identify which features drive predictions
4. Frame results in terms of clinical utility, limitations, and governance considerations

## Dataset
This project uses a PhysioNet-derived ICU dataset containing outcome labels and clinically relevant severity indicators. The selected dataset structure reflects real-world critical care modelling tasks and is aligned with the broader MIMIC/PhysioNet ecosystem commonly used in Health AI research.
Using a PhysioNet-derived ICU dataset signals greater domain relevance than generic benchmark datasets because:
- It represents a real critical care setting
- It includes clinically meaningful variables and outcome labels
- It reflects the kinds of data challenges seen in healthcare AI, including missingness, heterogeneity, and the need for careful interpretation

## Important limitations
- This is a secondary, processed dataset rather than a full raw MIMIC workflow
- It may not fully represent current ICU populations or local care pathways
- Model performance may not generalise to other hospitals or health systems without external validation
Project Objectives

## Methods
### Data preparation
- Loaded structured ICU outcome data from a PhysioNet-derived source
- Defined In-hospital_death as the target variable
- Separated predictors and outcome
- Split the data into training and test sets
- Applied imputation to handle missing values
### Modelling
The project used:
- Logistic Regression as an interpretable baseline
- Random Forest as a more flexible non-linear model
### Evaluation
In healthcare, accuracy alone can be misleading, especially when class imbalance is present. For this reason, the project focused on:
Recall / Sensitivity
Precision
Confusion Matrix
ROC-AUC
This is important because in a mortality prediction setting, false negatives may represent patients whose risk is underestimated.
Explainability
To improve interpretability, SHAP was used to identify which features most strongly influenced mortality predictions. This supports transparency and helps connect model outputs to clinically meaningful signals.
Key Findings
This project showed that:
ICU mortality can be predicted with structured clinical variables
Evaluation must go beyond accuracy to reflect clinical risk
Explainability is essential in high-stakes settings such as critical care
Severity-related variables were among the strongest contributors to model output, which is consistent with established ICU risk assessment logic
Explainability insight
SHAP analysis was used to examine feature influence at the model level. This helps answer an important question in healthcare AI:
Why is the model flagging this patient as high risk?
That question is central to trust, clinical adoption, and governance.
Clinical Utility
This project is not intended to propose autonomous clinical decision-making. Instead, the model should be understood as a decision-support tool that could potentially help clinicians:
identify higher-risk ICU patients earlier
support prioritisation and escalation decisions
complement existing severity scoring approaches
improve visibility of risk patterns in complex patient data
Any real-world deployment would require local validation, workflow integration, human oversight, and continuous monitoring.
Why this project is relevant to Health AI
This project demonstrates several capabilities that are especially important in Health AI and Digital Health:
working with a clinically relevant critical care dataset rather than a generic public dataset
evaluating models using healthcare-appropriate metrics
applying explainable AI in a low-trust, high-risk domain
recognising that model performance alone is insufficient without clinical context, interpretability, and governance thinking
Ethical and Governance Considerations
Healthcare AI systems should not be judged only by technical performance. This project highlights several broader considerations:
1. Accountability
If a model contributes to risk assessment, responsibility for decisions still remains with the clinical team and the deploying organisation.
2. Explainability
Black-box outputs are harder to justify in critical care. Explainability methods such as SHAP help improve transparency but do not replace clinical judgment.
3. Bias and generalisability
A model trained on one dataset may not perform equally well across settings, populations, or workflow environments.
4. Missing data
Clinical data is often incomplete for non-random reasons. Even simple imputation strategies should be acknowledged as methodological limitations.
Limitations
Simplified modelling workflow relative to full MIMIC pipelines
No external validation
Baseline imputation strategy
Limited bias analysis across demographic subgroups
Retrospective data only
Future Improvements
Potential next steps include:
cross-validation instead of single train/test split
subgroup bias analysis
calibration assessment
comparison with clinical severity scores
Streamlit dashboard for interactive exploration
external validation on another ICU dataset
patient-level SHAP explanations for individual case review
Reproducibility
Environment
This project was developed in Google Colab using Python.
Main libraries
pandas
numpy
scikit-learn
matplotlib
shap
Setup
Install dependencies with:
pip install -r requirements.txt
Files
mimic_xai_icu_mortality.ipynb — notebook containing preprocessing, modelling, evaluation, and explainability workflow
README.md — project documentation
requirements.txt — package list for reproducibility
Final Reflection
The value of healthcare AI does not lie only in building predictive models. It lies in building models that can be interpreted, questioned, and used responsibly within clinical systems.
This project was therefore designed not just as a machine learning exercise, but as a step toward more trustworthy and clinically meaningful AI in healthcare.
