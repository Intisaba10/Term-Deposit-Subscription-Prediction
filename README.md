#  Term Deposit Subscription Prediction

##  Internship Task – Machine Learning Project

###  Problem Statement

Banks run marketing campaigns to encourage customers to subscribe to **term deposits**. The goal of this project is to **predict whether a customer will subscribe (Yes/No)** based on demographic, financial, and campaign-related information.

This is a **binary classification problem** with a **highly imbalanced dataset**.

---

##  Dataset

* **Name:** Bank Marketing Dataset
* **Source:** UCI Machine Learning Repository
* **Records:** 45,211 customers
* **Target Variable:** `y`

  * `yes` → Customer subscribed (1)
  * `no` → Customer did not subscribe (0)

 Only ~11% of customers subscribed → **class imbalance problem**

---

##  Project Workflow

###  Data Loading & Exploration

* Loaded dataset using Pandas
* Checked data types, missing values, and summary statistics
* Identified class imbalance in the target variable

###  Data Preprocessing

* Separated features (`X`) and target (`y`)
* Encoded categorical variables using **OneHotEncoder**
* Scaled numerical features using **StandardScaler**
* Used **ColumnTransformer + Pipeline** for clean preprocessing

###  Train–Test Split

* 80% training, 20% testing
* Used **stratified sampling** to preserve class distribution

###  Model Training

* Trained a **Random Forest Classifier** with:

  * `class_weight="balanced"`
  * `n_estimators = 80`
  * `max_depth = 12`

This helped handle the imbalanced dataset effectively.

---

##  Model Evaluation

###  Confusion Matrix

* Visualized using a heatmap
* Showed strong detection of minority class (subscribers)

###  Classification Report

* **Accuracy:** 86%
* **Recall (Yes class):** 80%
* **F1-score (Yes class):** 57%

 High recall is crucial for marketing use cases to avoid missing potential subscribers.

###  ROC–AUC Curve

* Demonstrated good class separation
* Suitable metric for imbalanced datasets

---

##  Model Explainability (LIME)

* Used **LIME (Local Interpretable Model-Agnostic Explanations)**
* Explained individual predictions from the Random Forest model
* Key influential features:

  * Call duration
  * Previous campaign outcome
  * Contact method
  * Month of contact
  * Loan and housing status

This improves **model transparency and trust**.

---

##  Conclusion

* The **balanced Random Forest model** performed well on an imbalanced dataset
* Successfully identified customers likely to subscribe
* High recall makes it suitable for real-world bank marketing campaigns
* LIME explanations confirmed logical, business-aligned decisions

---

##  Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* Matplotlib, Seaborn
* LIME


