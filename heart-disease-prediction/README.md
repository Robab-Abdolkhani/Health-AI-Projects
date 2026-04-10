# Heart Disease Risk Prediction in Healthcare
## Overview
This project developed a machine learning model for predicting the presence of heart disease using a structured clinical dataset.
Rather than focusing solely on predictive performance, this project examines the clinical relevance, limitations, and governance considerations associated with deploying such models in healthcare settings.
## Clinical Problem Statement
Cardiovascular disease remains one of the leading causes of mortality globally. Early identification of individuals at high risk is critical for:
Preventive interventions
Prioritisation of clinical resources
Reducing hospital admissions and long-term complications
This project simulates a decision-support scenario in which a predictive model could assist clinicians in identifying patients who may require further diagnostic evaluation.
Dataset
The dataset used in this project is a publicly available heart disease dataset sourced from Kaggle.
It includes clinical variables such as:
Age
Cholesterol levels
Resting blood pressure
Maximum heart rate
Chest pain type
Limitations of the Dataset
The dataset is relatively small and may not represent real-world population diversity
Data collection context (e.g., single-centre vs multi-centre) is unclear
Potential selection bias may limit generalisability
Methodology
The following steps were performed:
Data loading and exploratory analysis
Basic data quality checks (e.g., missing values)
Train-test split for model evaluation
Model development using Logistic Regression
Performance evaluation using classification metrics
Model Evaluation
While the initial evaluation focused on accuracy, healthcare applications require more nuanced metrics.
Key considerations include:
Sensitivity (Recall): Ability to correctly identify patients with disease
Specificity: Ability to correctly identify patients without disease
False Negatives: Particularly critical, as missed diagnoses can have severe consequences
Results
Logistic Regression achieved moderate predictive performance
The model captures general trends but may not fully represent complex clinical relationships
Key Insights
Linear models such as Logistic Regression, provide interpretability, which is valuable in clinical settings
However, they may underperform compared to more complex models when relationships are non-linear
Model performance alone is insufficient to determine clinical usefulness
Governance & Ethical Considerations
From a Health AI perspective, several considerations emerge:
Interpretability vs Performance Trade-off:
Simpler models may be preferred in clinical environments due to transparency
Bias and Generalizability:
Models trained on limited datasets may not perform well across diverse populations
Clinical Integration:
Predictions must align with clinical workflows and support—not replace—clinical judgment
Risk of Misclassification:
False negatives (missed disease cases) pose significant safety risks
Limitations
Use of a simplified dataset that may not reflect real-world clinical complexity
Lack of external validation on independent datasets
Limited feature engineering and domain-specific preprocessing
Reproducibility
This project was developed using:
Python
Pandas
Scikit-learn
Matplotlib
Google Colab
To reproduce:
Upload the dataset (heart.csv)
Run the notebook step-by-step in Colab
Future Improvements
Apply cross-validation for more robust performance estimation
Introduce explainability methods (e.g., feature importance, SHAP)
Validate the model on external datasets
Explore integration into clinical decision-support systems
Final Reflection
This project highlights that building machine learning models in healthcare is not solely a technical task.
It requires careful consideration of clinical relevance, data limitations, interpretability, and ethical implications to ensure safe and effective deployment.
