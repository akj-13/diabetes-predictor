# "Diabetes Prediction Using Machine Learning"

**NITK 1st Year DSAI Course Project**

A machine-learning-based study of diabetes risk classification using patient health indicators. This project explores data preprocessing, exploratory data analysis, supervised learning, model evaluation, feature importance, dimensionality reduction, and unsupervised clustering to investigate patterns associated with diabetes.

---

## Project Overview

Diabetes is a major health concern, making the identification of relevant risk indicators an important area of data-driven research.

This project develops and evaluates multiple machine learning classification models to predict the presence of diabetes using demographic and medical attributes. Starting with a dataset of **100,000 records**, the workflow involves systematic data inspection and cleaning, preprocessing, model development, hyperparameter optimization, and performance evaluation.

A key focus is comparing different classification algorithms and evaluating their ability to identify positive diabetes cases, with particular attention to recall and the F2-score.

## Dataset

- **Source:** [Diabetes Prediction Dataset – Kaggle](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset)
- **Original size:** 100,000 records
- **Attributes:** 8 input features and 1 target variable
- **Target variable:** `diabetes`

### Features Used

| Feature | Description |
|---|---|
| Gender | Patient gender |
| Age | Age of the patient |
| Hypertension | Presence of hypertension |
| Heart Disease | Presence of heart disease |
| Smoking History | Patient's smoking history |
| BMI | Body Mass Index |
| HbA1c Level | HbA1c measurement |
| Blood Glucose Level | Blood glucose measurement |
| Diabetes | Target classification (0 or 1) |

## Methodology

The project follows a structured machine-learning workflow:

1. **Data Collection and Inspection** – Loading the dataset and examining its dimensions, attributes, data types, descriptive statistics, and target distribution.
2. **Data Cleaning** – Investigating and handling duplicate records, categorical inconsistencies, and missing values.
3. **Exploratory Data Analysis (EDA)** – Using visualizations, descriptive statistics, correlation analysis, and outlier investigation to understand the dataset.
4. **Data Preprocessing** – Applying numerical imputation, categorical imputation, missing-value indicators, feature scaling, and one-hot encoding through Scikit-learn pipelines.
5. **Model Development** – Training and comparing multiple supervised classification algorithms.
6. **Hyperparameter Optimization** – Using stratified cross-validation and randomized search to improve model performance.
7. **Model Evaluation** – Comparing accuracy, precision, recall, F1-score, F2-score, ROC-AUC, PR-AUC, and confusion matrices.
8. **Model Interpretation** – Applying permutation feature importance to investigate the contribution of individual features.
9. **Additional Analysis** – Performing PCA for dimensionality reduction, MiniBatch K-Means clustering, and subgroup performance analysis.

## Machine Learning Models

The following classification algorithms are implemented and compared:

- Logistic Regression
- K-Nearest Neighbours (KNN)
- Decision Tree Classifier
- Random Forest Classifier
- Gradient Boosting Classifier
- Multi-Layer Perceptron (MLP) Neural Network

The final model is selected using validation performance, with emphasis on the F2-score to give greater importance to recall.

## Results

**Selected Model: Random Forest Classifier**

The selected model achieved the following results on the held-out test set:

| Evaluation Metric | Score |
|---|---:|
| Accuracy | 95.08% |
| Precision | 69.02% |
| Recall | 79.40% |
| F1-Score | 73.84% |
| F2-Score | 77.08% |
| ROC-AUC | 97.29% |
| PR-AUC | 87.26% |

### Confusion Matrix

| | Predicted Negative | Predicted Positive |
|---|---:|---:|
| Actual Negative | 12,658 | 448 |
| Actual Positive | 259 | 998 |

The decision threshold was optimized using validation data, resulting in a threshold of approximately **0.51515** for the reported test evaluation.

### Feature Importance

Permutation importance identified the following features as particularly influential:

1. HbA1c Level
2. Blood Glucose Level
3. Age
4. BMI
5. Hypertension

These results highlight the relative predictive contribution of the available features within the selected model.

## Additional Analysis

Beyond classification, the project incorporates several complementary analytical techniques:

- **Exploratory Data Analysis:** Distribution plots, boxplots, scatterplots, and correlation analysis.
- **Outlier Analysis:** Investigation using the Interquartile Range (IQR) method.
- **Dimensionality Reduction:** Principal Component Analysis (PCA), with the first two principal components explaining approximately 38.77% of the variance.
- **Unsupervised Learning:** MiniBatch K-Means clustering to explore patterns within the data.
- **Subgroup Evaluation:** Comparison of model recall across selected gender and age groups.
- **Generalization Analysis:** Comparison of training and test performance to investigate potential overfitting.

## Technology Stack

- **Programming Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Data Visualization:** Matplotlib
- **Machine Learning:** Scikit-learn
- **Model Persistence:** Joblib
- **Dataset Acquisition:** KaggleHub
- **Development Environment:** Google Colab
- **Interactive Demonstration:** IPyWidgets

## How to Run

1. Open the project notebook in Google Colab.
2. Ensure that Google Drive access is available, as the project stores datasets, trained models, and outputs in Drive.
3. Run the notebook cell to install any missing dependencies, load or download the dataset, and execute the workflow.
4. The script automatically checks for an existing saved model and loads it when the dataset and configuration match.
5. Set `FORCE_RETRAIN = True` in the configuration section if you want to train the models again from scratch.

The notebook also provides an interactive demonstration in which example patient attributes can be entered to obtain a model prediction.

## Project Team

**Group 11 | Section S13 | Department of Computer Science and Engineering**

- **Akshaj Nambudiri** – 261CS106
- **Ridham Pincha** – 261CS146
- **Shounak Debnath** – 261CS154

**Institution:** National Institute of Technology Karnataka (NITK), Surathkal  
**Course:** Data Science and Artificial Intelligence  
**Academic Year:** 2026

## Disclaimer

This project is developed strictly for academic and educational purposes. The model demonstrates machine learning techniques for diabetes risk classification and is **not intended to serve as a medical diagnostic tool**. Its predictions should not replace professional medical advice, clinical testing, or diagnosis.

---

*An academic exploration of data science and machine learning applied to healthcare-related classification.*
