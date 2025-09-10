💳 Microcredit Payback Prediction

📌 Project Overview

This project builds a probability-based classifier to predict whether a microcredit customer will repay their loan within 5 days of issuance.

It sits at the intersection of telecom and inclusive finance, enabling low-income subscribers to access instant small loans while allowing the Microfinance Institution (MFI) to manage risk, minimize defaults, and expand financial inclusion.

🎯 Problem Statement

A telecom operator + MFI partnership provides short-term mobile balance loans.

Each loan transaction is labeled:

1 → Paid back (non-defaulter)

0 → Not paid (defaulter)

Objective: Predict repayment probability for each loan.

✅ Success Criteria:

Low Log Loss (good probability calibration)

High Recall (catch likely defaulters)

Good Precision (avoid unnecessary rejections)

📂 Dataset

File: Micro-credit-Data-file.csv

Features: Subscriber & transaction details (numeric + categorical)

Target: Repayment within 5 days (0/1)

⚙️ Data Preprocessing

Missing values → Mean (numeric), Most frequent (categorical)

Categorical encoding → Label Encoding (binary), One-Hot Encoding (multi-class)

Splitting → Stratified train/validation/test

Scaling → StandardScaler for numeric features

🔎 Exploratory Data Analysis (EDA)

Checked class imbalance & missingness

Univariate & bivariate plots for feature impact

Correlation heatmaps for numeric blocks

Repayment rates across subscriber segments

🛠️ Feature Engineering

Created behavior-driven features such as:

Recent behavior aggregates (loan counts, repayment streaks)

Usage intensity ratios (top-ups/day, ARPU proxies)

Recency features (days since last top-up/loan)

Loan amount transformations (bins, nonlinear scaling)

🤖 Models Used

Trained and compared 45+ models, including:

Linear/Margin: Logistic Regression, SGDClassifier, RidgeClassifier

Tree/Bagging: Decision Tree, RandomForest, ExtraTrees

Boosting: GradientBoosting, HistGradientBoosting, AdaBoost, XGBoost, LightGBM, CatBoost

Others: SVM (with probability), KNN, Naive Bayes, LDA/QDA

📌 Hyperparameter tuning: GridSearchCV & RandomizedSearchCV with scoring = neg_log_loss

📊 Evaluation Metrics

Log Loss → Probability calibration

Precision → Avoid approving risky customers

Recall → Catch as many defaulters as possible

Classification Report for finalists

🌟 Key Insights

Tree-based models (RandomForest, XGBoost, LightGBM) perform best.

Important drivers:

Recency of usage

Loan amount-related features

Aggregate behavior features (frequency, intensity)

💼 Business Implications

Smarter Eligibility → Approve only customers with high repayment probability

Dynamic Credit Limits → Adjust loan size based on repayment likelihood

Collections Prioritization → Focus reminders on medium-risk borrowers

Risk-Based Pricing → Set interest/fees based on repayment probability

Controlled Growth → Expand credit access without increasing default risk

🚀 Future Work

Apply calibration (Platt/Isotonic) for better probability thresholds

Incorporate temporal cross-validation

Deploy as an API service with drift monitoring

Expand stacking/ensembling for improved performance

Optimize with business cost-sensitive metrics
