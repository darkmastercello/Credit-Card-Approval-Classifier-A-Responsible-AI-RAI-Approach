# Credit-Card-Approval-Classifier-A-Responsible-AI-RAI-Approach
**Overview** <br>
This repository contains a machine learning pipeline designed to automate credit card application approvals for a financial institution. Moving beyond raw predictive power, this project heavily emphasizes Responsible AI (RAI) principles. It demonstrates how to build a model that not only performs well on highly imbalanced data but also maintains strict fairness, global transparency, and local explainability to ensure regulatory compliance and customer trust.

**Key Features & Methodologies** <br>
Handling Imbalanced Data (The Accuracy Paradox): Demonstrated why raw accuracy is a deceptive metric in financial datasets. A baseline Random Forest achieved ~87% accuracy simply by denying almost all applicants (0.00 F1-Score for approvals).

Model Evaluation & Selection: Evaluated Random Forest, CatBoost, and XGBoost using ROC-AUC and class-weighting techniques (scale_pos_weight and auto_class_weights). XGBoost was selected as the optimal model for successfully identifying the minority class while maximizing the ROC-AUC score.

Fairness Assessment (Demographic Parity): Audited all models for demographic bias, specifically looking at approval rates across genders. While CatBoost introduced a ~6.5% gender bias, XGBoost maintained a highly acceptable Demographic Parity difference of just 2.4%.

Global Explainability (SHAP): Utilized SHAP (SHapley Additive exPlanations) to map the macro-level decision-making logic of the model, confirming that features like Account_length and Total_income drove decisions, while sensitive demographic data (Gender) was actively ignored.

Local Explainability (LIME): Implemented LIME (Local Interpretable Model-agnostic Explanations) to generate personalized, transparent explanations for individual applicant denials, eliminating the "black box" effect for customer service operations.

**Technologies Used** <br>
Languages: Python<br>

Machine Learning: scikit-learn, XGBoost, CatBoost<br>

Responsible AI / Interpretability: SHAP, LIME<br>

Data Processing: pandas, numpy, category_encoders (BinaryEncoder)<br>

**Results** <br>
The final XGBoost classifier achieved the most viable balance between predictive performance (highest ROC-AUC) and ethical compliance (low Demographic Parity difference). By integrating SHAP and LIME, the pipeline ensures that every automated decision can be mathematically explained both to regulators and to the individual customer.
<br>**LIME output**
<img width="1510" height="479" alt="Screenshot (602)" src="https://github.com/user-attachments/assets/c652bc1d-c33d-4a24-b80e-670425306c5f" />

