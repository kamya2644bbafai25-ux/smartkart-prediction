# Qure.ai TB Screening ML Pipeline

## Project Overview

This project presents an educational Machine Learning prototype inspired by the healthcare screening problem addressed by Qure.ai.

The primary business problem is to support faster screening and prioritization of chest X-ray cases that may require further tuberculosis (TB) evaluation. The proposed workflow demonstrates how an AI-assisted screening system can help organize cases for clinical review while keeping healthcare professionals responsible for diagnosis and treatment decisions.

This repository contains a Jupyter Notebook demonstrating a complete supervised Machine Learning pipeline using a synthetic dataset.

## Business Problem

Tuberculosis screening can involve large volumes of medical cases, creating workload and delays, particularly in settings where specialist resources are limited.

AI and Machine Learning can support healthcare workflows by identifying patterns in screening data and generating outputs that help prioritize cases for further clinical assessment.

The objective of this prototype is to demonstrate how a classification model can be developed to generate a screening-support prediction.

## Organization Studied

**Organization:** Qure.ai

Qure.ai is a healthcare AI company associated with AI-assisted medical imaging and screening solutions. In this case study, its TB screening use case is used as the business context for understanding the potential application of AI and ML in healthcare.

## Project Objectives

* Understand a healthcare-related AI/ML business problem.
* Demonstrate a complete supervised Machine Learning workflow.
* Perform data cleaning and preprocessing.
* Select relevant features and define a target variable.
* Train a Logistic Regression classification model.
* Generate predictions and positive-class probabilities.
* Evaluate the model using classification metrics.
* Interpret model coefficients.
* Connect the technical workflow to business value and human oversight.

## Dataset Description

This notebook uses a **synthetic tabular dataset** containing 300 screening cases.

The dataset includes the following variables:

| Feature                  | Description                                 |
| ------------------------ | ------------------------------------------- |
| `Case_ID`                | Synthetic case identifier                   |
| `Age`                    | Age of the screening case                   |
| `Cough_Days`             | Number of days with cough                   |
| `Weight_Loss`            | Synthetic indicator for weight loss         |
| `Fever`                  | Synthetic indicator for fever               |
| `Prior_TB`               | Synthetic indicator for previous TB         |
| `Xray_Abnormality_Score` | Synthetic abnormality score between 0 and 1 |
| `Referral_Priority`      | Synthetic referral-priority indicator       |
| `TB_Screen_Positive`     | Synthetic binary target variable            |

### Target Variable

`TB_Screen_Positive`

* `0` = Synthetic screening-negative case
* `1` = Synthetic screening-positive case

The target is created for educational demonstration and must not be interpreted as a medical diagnosis.

## Machine Learning Pipeline

The notebook follows these 15 steps:

1. Data Collection
2. Data Understanding and Inspection
3. Data Cleaning
4. Outlier Detection and Treatment
5. Feature Selection
6. Target Variable Definition
7. Target Encoding
8. Train-Test Split
9. Feature Standardisation
10. Model Building
11. Model Training
12. Prediction
13. Model Evaluation
14. Model Interpretation
15. Final Output

## Technologies and Libraries Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

## Model Used

### Logistic Regression

Logistic Regression is used as a simple and interpretable binary classification algorithm.

The model learns relationships between the selected synthetic features and the target variable. It produces:

* A predicted class: `0` or `1`
* A predicted probability for the positive class

Logistic Regression is suitable for demonstrating the fundamentals of classification. A production chest X-ray screening system would generally require image-based deep-learning methods, representative clinical data, and extensive validation.

## Data Preprocessing

The notebook performs the following preprocessing tasks:

* Removes duplicate rows.
* Identifies and handles missing values.
* Replaces invalid negative cough-duration values.
* Handles abnormality scores outside the defined 0–1 range.
* Fills missing numeric values using the median.
* Detects and caps outliers using the IQR method.
* Removes `Case_ID` from the selected model features.
* Splits the data into training and testing sets using an 80:20 ratio.
* Applies `StandardScaler` to standardise features.

The scaler is fitted only on the training data to reduce the risk of data leakage.

## Model Evaluation

The model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC
* Confusion Matrix
* Classification Report

Recall is particularly relevant to examine in a screening-oriented context, but no single metric is sufficient to establish clinical effectiveness.

The actual evaluation values are generated when the notebook is executed.

## Model Interpretation

The notebook displays Logistic Regression coefficients to demonstrate the direction and relative contribution of features within the synthetic model.

These coefficients are specific to the educational dataset. They are not clinical evidence, medical risk estimates, or recommendations for patient care.

## Business Interpretation

### Potential Business Value

An AI-assisted screening workflow could potentially support:

* Faster screening of large case volumes.
* Better organization and prioritization of cases.
* Improved use of specialist time.
* Support for TB case-finding activities.
* Earlier identification of cases requiring further clinical assessment.

These are potential workflow benefits of the broader use case, not results established by this prototype.

### Human Oversight

The intended workflow is:

```text
Chest X-ray
    ↓
AI Image Analysis
    ↓
Screening or Priority Output
    ↓
Clinician Review
    ↓
Confirmatory Testing and Clinical Action
```

The AI output is intended to support clinical workflow and should not replace professional diagnosis or treatment decisions.

## Project Limitations

This project has several important limitations:

1. It does not use real chest X-ray images.
2. It uses a synthetic dataset and synthetic target labels.
3. It does not reproduce Qure.ai's proprietary qXR model.
4. Model performance values cannot be used to claim clinical effectiveness.
5. The abnormality score is a synthetic proxy and is not a real Qure.ai/qXR score.
6. Real-world deployment would require representative clinical data, privacy and security controls, external validation, monitoring, and clinical or regulatory governance.

## Repository Structure

```text
QureAI_TB_Screening_ML_Pipeline/
│
├── QureAI_TB_Screening_ML_Pipeline.ipynb
└── README.md
```

> Update the notebook filename in this structure if your uploaded file is saved with a different name.

## How to Run the Project

### Option 1: Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload the `.ipynb` notebook.
3. Select **Runtime**.
4. Click **Run all**.
5. Review the data-processing steps, model predictions, evaluation metrics, and visualisations.

### Option 2: Run Locally Using Jupyter Notebook

1. Install Python.
2. Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

3. Start Jupyter Notebook:

```bash
jupyter notebook
```

4. Open the project notebook.
5. Run the cells sequentially.

## Expected Outputs

After executing the notebook, the following outputs are generated:

* Dataset preview
* Dataset shape and data-type information
* Missing-value and duplicate inspection
* Data-cleaning results
* Outlier-treatment summary
* Selected features
* Target distribution
* Training and testing dataset sizes
* Standardised feature data
* Trained Logistic Regression model
* Prediction results
* Classification metrics
* Confusion matrix
* Logistic Regression coefficient table
* Feature coefficient visualisation
* Final screening-priority output

## Educational Purpose

This project is created for academic learning and demonstrates how a Machine Learning workflow can be connected to a real-world healthcare business problem.

It is not intended for clinical use, medical diagnosis, patient management, or treatment decisions.

## Conclusion

The project demonstrates how supervised Machine Learning can be applied to a healthcare screening-support scenario. By following the complete ML pipeline, it shows the relationship between data preparation, model development, prediction, evaluation, and business interpretation.

The prototype also highlights the importance of responsible AI, clinical validation, privacy, and human oversight when applying AI in healthcare.

## Author

**Name:** Aarushi Verma

**Course:** Introduction to AI & ML | BBA AI/ML

**Institution:** Chitkara Business School

## Disclaimer

This repository is an educational demonstration only. It does not represent Qure.ai's proprietary technology, does not reproduce the qXR model, and must not be used to diagnose tuberculosis or make medical decisions.
