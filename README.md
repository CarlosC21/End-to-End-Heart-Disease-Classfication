Predicting Heart Disease Using Machine Learning

This project explores the use of Python-based machine learning techniques to predict the presence of heart disease using clinical patient data. The goal was to build and evaluate classification models capable of identifying whether a patient has heart disease based on medical attributes.

Problem Statement

Given clinical parameters about a patient, can we accurately predict whether they have heart disease?

Target variable:

0 → No heart disease

1 → Heart disease

Dataset

The dataset used is the Cleveland Heart Disease dataset from the UCI Machine Learning Repository.

303 patient records

14 attributes (13 features + 1 target)

No missing values

Features include:

Demographics (age, sex)

Clinical measurements (cholesterol, resting blood pressure, max heart rate)

Diagnostic results (ECG, ST depression, slope)

Exercise-induced angina

Number of major vessels (fluoroscopy)

Thalassemia status

Exploratory Data Analysis (EDA)

Performed comprehensive data exploration including:

Class distribution analysis (balanced dataset)

Crosstab analysis (e.g., sex vs. heart disease, chest pain type vs. disease)

Scatter plots (Age vs. Max Heart Rate)

Correlation matrix and heatmap visualization

Distribution analysis of key features

Key insights:

Chest pain type (cp) and maximum heart rate (thalach) showed strong positive correlation with heart disease.

Exercise-induced angina (exang), ST depression (oldpeak), and number of vessels (ca) were negatively correlated with the target.

No missing values were present in the dataset.

Models Implemented

Three classification models were trained and compared:

Logistic Regression

K-Nearest Neighbors (KNN)

Random Forest Classifier

Baseline Accuracy (Test Set)
Model	Accuracy
Logistic Regression	88.5%
Random Forest	83.6%
KNN	68.8%

Logistic Regression performed best and was selected for further tuning.

Hyperparameter Tuning

Used:

RandomizedSearchCV

GridSearchCV

Best Logistic Regression parameters:

C = 0.2043
solver = "liblinear"


Tuned model accuracy (test set): 88.5%

Model Evaluation

Beyond accuracy, the model was evaluated using:

ROC Curve & AUC

Confusion Matrix

Classification Report

Cross-validated metrics (5-fold)

Cross-Validated Metrics (Mean)

Accuracy: 84.5%

Precision: 82.1%

Recall: 92.1%

F1-score: 86.7%

High recall indicates the model is effective at identifying patients with heart disease (minimizing false negatives).

Feature Importance (Logistic Regression Coefficients)

Most influential features:

Chest pain type (cp)

Maximum heart rate (thalach)

Slope of ST segment (slope)

Number of vessels (ca)

Thalassemia (thal)

Exercise-induced angina (exang)

ST depression (oldpeak)

These align well with medical intuition and clinical relevance.

🛠 Tools & Libraries

NumPy

Pandas

Matplotlib

Seaborn

Scikit-learn

Conclusion

Logistic Regression achieved strong and stable performance.

The model generalizes well under cross-validation.

Recall score suggests strong detection capability for heart disease cases.

Feature importance analysis provides interpretability and medical insight.

While the initial goal was 95% accuracy for proof of concept, the achieved performance (~88%) demonstrates solid predictive capability and establishes a strong baseline for further experimentation.
