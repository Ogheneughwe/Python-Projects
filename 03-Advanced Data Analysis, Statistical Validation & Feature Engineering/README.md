
# Heart Disease Prediction Project

## Introduction
This project focuses on the exploratory data analysis, statistical validation, and feature engineering for a heart disease dataset. The ultimate goal is to develop a robust predictive model to identify individuals at risk of heart disease, enabling early intervention and improved patient outcomes.

## Installation
To run this notebook, you will need the following Python libraries. You can install them using `pip`:

```bash
pip install pandas numpy scipy matplotlib seaborn scikit-learn
```

## Execution Steps
1.  **Load the Dataset**: Ensure the `clean_encoded_heart_disease_data.csv` file is accessible (e.g., in the `/content/sample_data/` directory as used in the notebook).
2.  **Run Cells Sequentially**: Execute all code cells in the notebook from top to bottom. The notebook is structured to flow logically through data inspection, exploratory data analysis, statistical testing, and feature engineering.
3.  **Review Outputs**: Pay attention to the printed outputs, visualizations, and markdown interpretations provided in each section to understand the analysis.

## Workflow/Architecture Diagram
 <img width="1536" height="1024" alt="Workflow Diagram" src="https://github.com/user-attachments/assets/23c51c42-3ad9-40db-85c7-e78c9074dfd1" />

## Sample Output Screenshots
<img width="508" height="346" alt="Age Distri by HDS" src="https://github.com/user-attachments/assets/fbbbcb3b-ca30-4b9c-a6f1-b4a650890ed9" />
<img width="523" height="350" alt="MaxHR by HDS" src="https://github.com/user-attachments/assets/39537efe-c867-4aca-86ef-61f9766fecb2" />
<img width="511" height="354" alt="Oldpeak Distri by HDS" src="https://github.com/user-attachments/assets/9755589f-1005-4e4b-8ffc-182f634ca0c8" />
<img width="521" height="372" alt="RestingBP Distri by HDS" src="https://github.com/user-attachments/assets/87dfe273-3ed1-4a05-b69e-7148997b75ee" />
<img width="507" height="354" alt="Cholesterol Distri by HDS" src="https://github.com/user-attachments/assets/a7995e25-7d32-4b10-aa10-c4d0b41a5a96" />
<img width="556" height="362" alt="Heart Rate to Age Ratio by Heart Disease Status" src="https://github.com/user-attachments/assets/c97968ab-0b20-454d-8917-fb63aa765161" />
<img width="305" height="210" alt="ST Exercise Risk by Heart Disease Status" src="https://github.com/user-attachments/assets/ca994a6c-dd67-4b9c-b2de-fc3a74bc1b8d" />
<img width="932" height="296" alt="Final Modelling Dataset 1" src="https://github.com/user-attachments/assets/15946ee6-11ee-465c-948a-2c7777cadc17" />
<img width="930" height="301" alt="Final modelling Dataset 2" src="https://github.com/user-attachments/assets/6439461f-53f1-4aa4-bff9-cead69535408" />
<img width="954" height="464" alt="Feature Evaluation Table" src="https://github.com/user-attachments/assets/4f84f638-f7e7-4e33-9418-a82d918d55fb" />


## Dataset Limitations and Assumptions
This analysis is based on a specific heart disease dataset with the following limitations and implicit assumptions:

*   **Sample Size:** The dataset contains 918 entries. While sufficient for initial analysis, a larger and more diverse dataset would enhance the generalizability and robustness of the findings.
*   **Data Source and Representativeness:** The specific origin and representativeness of the dataset are not fully detailed, which might limit the generalizability of findings to broader, diverse populations.
*   **Potential Bias:** Data collection might contain inherent biases (e.g., primarily individuals who have sought medical attention, potentially underrepresenting undiagnosed cases).
*   **Missing Information:** Although the cleaned dataset has no missing values, the original raw data may have undergone imputation or row removal, which could influence data distribution.
*   **Limited Feature Set:** Important external factors (e.g., family history, genetics, detailed lifestyle information, other comorbidities) are not included, potentially limiting a holistic understanding.
*   **Cross-Sectional Nature:** The dataset represents a snapshot in time, lacking longitudinal information crucial for understanding disease progression.
*   **Categorization Thresholds:** Engineered features like `Age_Group` and `BP_Category` rely on standard medical thresholds, which might yield slightly different insights if alternative thresholds were used.
*   **Dependence on Clinical Measurements:** The data relies on clinical measurements and patient-reported symptoms, where subjectivity or measurement variability could introduce noise.

## Roadmap for Future Predictive Modeling

The `Final_Modelling_Dataset` is now prepared for the next phase: predictive modeling.

1.  **Data Splitting**: Divide the dataset into training, validation, and test sets for robust model development and evaluation.
2.  **Model Selection**: Choose appropriate machine learning models (e.g., Logistic Regression, Decision Trees, Random Forests, Gradient Boosting Machines) suitable for a binary classification task with mixed feature types.
3.  **Model Training**: Train selected models on the training data.
4.  **Hyperparameter Tuning**: Optimize model hyperparameters using the validation set to maximize performance and prevent overfitting.
5.  **Model Evaluation**: Rigorously assess model performance on the unseen test set using metrics like accuracy, precision, recall, F1-score, and ROC-AUC.
6.  **Feature Importance Analysis**: Conduct post-modeling analysis to confirm the most significant predictors, further validating EDA insights.
7.  **Interpretability and Explainability**: Focus on interpreting model predictions, especially for complex models, to provide actionable clinical insights.
