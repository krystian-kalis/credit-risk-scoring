# Credit Risk Assessment & Explainable AI (XAI)

## Overview
This repository contains a machine learning project focused on **Credit Risk Assessment**. The primary objective is to build highly accurate "black-box" predictive models using econometric data and, more importantly, to demystify their decision-making processes using state-of-the-art **Explainable AI** techniques. This ensures the models are transparent, trustworthy, and compliant with financial risk management standards.

## Key Results & XAI Insights
* **Model Performance & Calibration:** The final XGBoost model achieved a stable **AUC-ROC of 0.74** on the unseen test set. Crucially, by heavily penalizing False Negatives (setting FN cost 15x higher than FP), the decision threshold was optimized to achieve a **Recall of 79.5%**, successfully identifying the vast majority of high-risk applicants. 
* **Probability Calibration:** Both models were rigorously calibrated (Platt Scaling for Logistic Regression, Isotonic Regression for XGBoost) to match the real-world central tendency of **4% default rate**, significantly reducing the Expected Calibration Error (ECE to 0.018) and Brier Score.
* **Global Insights (SHAP/PDP):** Global explainability revealed that the **efficiency of working capital management** (Sales to Working Capital ratio) is the absolute key predictor of risk, outperforming traditional debt metrics. The model explicitly penalizes companies with "frozen" operational capital.
* **Local Explanations (LIME):** We successfully demonstrated how XAI techniques can justify individual credit scoring decisions. For instance, LIME effectively uncovers how high long-term liabilities combined with low asset turnover accurately flag specific clients as High Risk, aligning with banking right-to-explanation standards.

## Repository Structure
* **`project.ipynb`**: The main Jupyter Notebook containing data preprocessing, the training of black-box classifiers, and the comprehensive implementation of SHAP, LIME, PDP, and ICE visualizations.
* **`data.csv`**: The underlying econometric dataset used for modeling credit risk.
* **`description.pdf`**: The data dictionary, providing crucial definitions and business context for the econometric variables used in the dataset.
* **`report.pdf`**: A detailed technical report documenting model performance metrics, the XAI methodology, and in-depth interpretations of the generated explanations.
* **`presentation.pdf`**: An executive slide deck designed to translate complex machine learning and XAI outputs into actionable business insights for non-technical stakeholders.

## Authors
Barbara Jankowska, Krystian Kaliś