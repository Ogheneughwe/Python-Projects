
# Updated Data Dictionary

This updated data dictionary describes all features present in the `Final_Modelling_Dataset`.

### Original Features:

*   **Age**: The patient's age in years. (Numerical)
*   **RestingBP**: Resting blood pressure (mm Hg). (Numerical)
*   **Cholesterol**: Serum cholesterol (mg/dl). (Numerical)
*   **FastingBS**: Fasting blood sugar (categorized as '≤ 120 mg/dl' or '> 120 mg/dl'). (Categorical)
*   **MaxHR**: Maximum heart rate achieved (Standardized Numerical).
*   **Oldpeak**: Oldpeak = ST depression induced by exercise relative to rest (Standardized Numerical).
*   **HeartDisease**: The target variable (0 = Normal; 1 = Heart Disease). (Binary/Categorical)
*   **Sex_M**: Gender of the patient ('Male' or 'Female'). (Categorical)
*   **ChestPainType_ATA**: Atypical Angina (True/False, original one-hot encoding).
*   **ChestPainType_NAP**: Non-Anginal Pain (True/False, original one-hot encoding).
*   **ChestPainType_TA**: Typical Angina (True/False, original one-hot encoding).
*   **RestingECG_Normal**: Normal resting electrocardiographic results (True/False, original one-hot encoding).
*   **RestingECG_ST**: ST-T wave abnormality (True/False, original one-hot encoding).
*   **ExerciseAngina_Y**: Exercise-induced angina ('Yes' or 'No'). (Categorical)
*   **ST_Slope_Flat**: The slope of the peak exercise ST segment (True/False, original one-hot encoding).
*   **ST_Slope_Up**: The slope of the peak exercise ST segment (True/False, original one-hot encoding).

### Engineered Features:

*   **ST_Slope**: Reconstructed categorical feature from `ST_Slope_Flat` and `ST_Slope_Up` ('Flat', 'Up', 'Down'). (Categorical)
*   **Age_Group**: Categorical age groups ('Young', 'Middle-Aged', 'Elderly'). (Categorical)
*   **BP_Category**: Categorical blood pressure status ('Normal', 'Elevated', 'Hypertension'). (Categorical)
*   **ChestPainType**: Reconstructed categorical feature from `ChestPainType_ATA`, `ChestPainType_NAP`, `ChestPainType_TA` ('Atypical Angina', 'Non-Anginal Pain', 'Typical Angina', 'Asymptomatic'). (Categorical)
*   **Heart_Rate_Age_Ratio**: Ratio of `MaxHR` to `Age` (`MaxHR / Age`). (Numerical)
*   **ST_Exercise_Risk**: Combined categorical feature from `ST_Slope` and `ExerciseAngina_Y` (e.g., 'Flat_Yes', 'Up_No'). (Categorical)
