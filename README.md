# 🚀 Machine Learning Portfolio

Welcome to my machine learning repository! This portfolio showcases a combination of foundational algorithm implementations and an end-to-end industrial machine learning application.

---

## 🔧 Predictive Maintenance — Machine Failure Classification

### 📌 Problem Statement
Industrial machines fail unexpectedly, causing costly downtime and safety hazards. This project builds a predictive maintenance model that uses real-time sensor readings to detect machine failure before it occurs — a core challenge in industrial automation and physical AI.

### 📊 Dataset & Class Balance
* **Size:** 944 operational records tracking environment, air quality, and mechanical metrics.
* **Class Distribution:** 551 Non-Failures (`fail=0`) vs. **393 Failures (`fail=1`)**.
* **Real-World Balance:** The dataset features a realistic, high-wear industrial split (~42% failure rate), which trains the model to recognize true anomalies without triggering excessive false alarms.

### 🔍 Exploratory Data Analysis & Sensor Insights
* **Primary Indicators:** The correlation analysis revealed that **VOC (Volatile Organic Compounds)** and **AQ (Air Quality)** show the strongest direct positive association with machine failure, serving as leading indicators of environmental degradation or leaks.
* **Secondary Drivers:** **Current Sensor (CS)** and **RPM (RP)** values capture distinct electrical and mechanical load variations right before a breakdown occurs.

### 🏗️ Modeling Approach
* **Algorithm:** Random Forest Classifier (100 estimators).
* **Rationale:** Random Forest handles mixed-scale sensor features without extensive normalization, is robust to noisy readings, and critically provides feature importance rankings that are interpretable for engineering teams.
* **Train/Test Split:** 80/20 train-test split.

### 📈 Final Evaluation Results

| Metric | Score |
| :--- | :--- |
| **Accuracy** | **87.8%** |
| **Precision (Failure Class)** | **86.0%** |
| **Recall (Failure Class)** | **87.3%** |
| **F1 Score (Failure Class)** | **86.6%** |

> 💡 **Note on metric priority:** In predictive maintenance, **Recall on the failure class is the most critical metric**. A missed failure (False Negative) is far more costly than a false alarm (False Positive) because an undetected breakdown halts production. This model successfully catches **87.3% of true impending machine failures**.

### 🛠️ Feature Importance Insight
The feature importance plot revealed that **VOC** and **Air Quality (AQ)** were the primary drivers of the model's predictions. This has direct engineering value — in a real factory deployment, these specific sensors would be prioritized for higher-frequency telemetry monitoring to maximize early warning lead time.

### 🚀 What I'd Build Next
1. Compare against XGBoost and LightGBM for performance benchmarking.
2. Wrap the trained model in a FastAPI endpoint so it can be queried in real time from a machine monitoring dashboard.
3. Explore time-series approaches (LSTM) since sensor data has temporal structure that static models ignore.

---

## 📊 Core ML Algorithms Portfolio

* **Type:** Supervised & Unsupervised Learning Implementations
* **Tools:** Python, Scikit-learn, Pandas, Matplotlib, Numpy

A structured set of implementations covering the foundational algorithms of machine learning — built during an end-to-end Data Science, ML, DL, and NLP bootcamp. Each notebook includes problem framing, exploratory data analysis, model training, and performance evaluation.

### 🧮 Algorithms Implemented

| Category | Algorithm |
| :--- | :--- |
| **Regression** | Simple Linear Regression, Multiple Linear Regression |
| **Classification** | Logistic Regression, Decision Trees, Random Forest, Support Vector Machines, K-Nearest Neighbors, Naive Bayes |
| **Unsupervised** | K-Means Clustering, Hierarchical Clustering, PCA |
| **Ensemble** | Bagging, Boosting, Gradient Boosted Trees |

### 🧠 Key Concepts Practiced
* **EDA workflows:** Distribution analysis, outlier detection, correlation matrices, feature engineering.
* **Model selection:** Cross-validation, bias-variance tradeoff, hyperparameter tuning with GridSearchCV.
* **Evaluation:** Confusion matrices, ROC-AUC curves, precision-recall tradeoffs, regression metrics (RMSE, $R^2$).
* **Pipelines:** End-to-end sklearn Pipelines for preprocessing + modeling to avoid data leakage.

---
*This portfolio is actively maintained and updated as I build more projects across GenAI, Computer Vision, and Agentic AI.*
