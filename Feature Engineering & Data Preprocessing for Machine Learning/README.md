# Heart Disease Prediction – AnalystLab Africa Week 2

## Project Overview

This project is part of the **AnalystLab Africa Data Science Internship Programme – Week 2: Feature Engineering & Data Preprocessing for Machine Learning**.

The project prepares a Heart Disease Prediction dataset for future machine-learning modelling. The notebook follows a structured workflow covering data inspection, data cleaning, feature engineering, outlier treatment, categorical encoding, feature scaling, feature selection, and preparation of a final machine-learning-ready dataset.

## Business Problem

The project focuses on preparing patient-level heart disease data so that it can support future predictive modelling. The dataset contains demographic, symptom and clinical variables, while **`HeartDisease`** is the target variable.

## Project Objective

The objective is to transform the raw dataset into a clean, structured and machine-learning-ready dataset by:

1. Inspecting the dataset structure and data types.
2. Checking missing, invalid and duplicate values.
3. Cleaning invalid clinical measurements.
4. Creating useful engineered features.
5. Detecting and treating potential outliers.
6. Encoding categorical variables.
7. Scaling numerical variables where appropriate.
8. Investigating correlations and feature relevance.
9. Producing a final dataset suitable for future modelling.

## Dataset

The working dataset is `heart.csv`.

The target variable is:

```text
HeartDisease
```

The predictor variables include demographic, symptom and clinical measurements such as Age, Sex, ChestPainType, RestingBP, Cholesterol, FastingBS, RestingECG, MaxHR, ExerciseAngina, Oldpeak and ST_Slope.

## Data Cleaning

### Cholesterol

The notebook identified **172 records where `Cholesterol = 0`**. These zeros were treated as invalid values, converted to missing values, and replaced using the median calculated from valid, non-zero observations.

Median used:

```text
237.0
```

### RestingBP

The notebook identified **1 record where `RestingBP = 0`**. This value was treated as invalid, converted to a missing value, and replaced using the median of the valid observations.

Median used:

```text
130.0
```

### Duplicate Records

Duplicate records were checked and **0 duplicates** were identified.

## Feature Engineering

Two additional categorical features were created:

### Age_Group

Age was grouped into:

- Young: 0–44
- Middle-Aged: 45–59
- Elderly: 60+

### BP_Category

RestingBP was grouped into project-defined categories:

- Normal: 0–119
- Elevated: 120–138
- Hypertension: 139+

These ranges are used as project-defined analytical bins and are not presented as a clinical diagnostic classification.

## Outlier Detection and Treatment

Potential outliers were investigated using boxplots and the **Interquartile Range (IQR)** method.

The main continuous variables investigated for IQR-based treatment were:

- `MaxHR`
- `Oldpeak`

The IQR boundaries were calculated using:

```text
Lower Bound = Q1 − 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Values outside the calculated boundaries were capped rather than deleted. Outlier treatment is performed before standardisation so that the IQR calculations remain interpretable in the variables' original measurement units.

`FastingBS` was not treated using continuous-variable IQR rules because it is a binary feature containing values of 0 and 1.

## Categorical Encoding

Nominal categorical variables were transformed using **One-Hot Encoding**. This creates binary columns for categories without imposing an artificial numerical order.

The encoded features include variables derived from:

- `Sex`
- `ChestPainType`
- `RestingECG`
- `ExerciseAngina`
- `ST_Slope`
- `Age_Group`
- `BP_Category`

## Feature Scaling

The continuous variables requiring standardisation, including `MaxHR` and `Oldpeak`, are scaled using **StandardScaler** after outlier treatment.

Standardisation places features on a comparable scale and is useful for algorithms that are sensitive to differences in feature magnitude.

## Feature Selection and Exploratory Analysis

The notebook investigates relationships between variables using correlation analysis and visualisations. Correlation is interpreted as an **association**, not proof of causation.

Feature-selection analysis is used to identify potentially useful predictors and investigate redundant or weakly associated variables before future model development.

## Final Machine-Learning Dataset

The processed dataset is prepared as `clean_encoded` and contains the cleaned, engineered, encoded and scaled features together with the target variable.

This dataset is intended for the next project stage:

```text
Machine Learning Model Training
        ↓
Model Evaluation
        ↓
Model Optimisation
```

## Project Workflow

```text
Load Dataset
      ↓
Inspect Data Structure
      ↓
Check Data Quality
      ↓
Clean Invalid Values
      ↓
Feature Engineering
      ↓
Outlier Detection & Treatment
      ↓
One-Hot Encoding
      ↓
Feature Scaling
      ↓
Feature Selection
      ↓
Final ML Dataset
```

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Suggested Repository Structure

```text
Heart-Disease-Prediction/
│
├── README.md
├── heart.csv
├── Heart_Disease_Prediction_Updated.ipynb
│
├── reports/
│   ├── Business_Understanding_Report.docx
│   └── Data_Preprocessing_Report.docx
│
└── output/
    └── heart_disease_clean_encoded.csv
```

## Expected Outcome

The expected Week 2 outcome is a clean and machine-learning-ready dataset that can be used in the next phase of the project for predictive modelling.

The preprocessing stage addresses invalid values, categorical variables, potential outliers and feature-scale differences before model training.

## Important Note

This project is a **data-science and machine-learning training project**. The analysis and any future model are not a clinically validated diagnostic system. Any real-world healthcare application would require appropriate validation, clinical assessment, governance and professional oversight.

## References

AnalystLab Africa. (2026). *Data Science Internship Programme: Week 2 – Feature Engineering & Data Preprocessing for Machine Learning*. Assignment brief.

scikit-learn developers. (2026). *Imputation of missing values*. scikit-learn documentation. https://scikit-learn.org/stable/modules/impute.html

scikit-learn developers. (2026). *OneHotEncoder*. scikit-learn documentation. https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html

scikit-learn developers. (2026). *StandardScaler*. scikit-learn documentation. https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html

World Health Organization. (2025). *Cardiovascular diseases (CVDs).* https://www.who.int/news-room/fact-sheets/detail/cardiovascular-diseases-(cvds)
