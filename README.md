# 1. Project Overview
___________________________

## 🫁 Lung Cancer Prediction using Machine Learning 

Lung cancer is one of the most life-threatening diseases.
Where early detection plays a critical role. 
in improving patient survival rates.  
This project presents a Machine Learning–based medical prediction system.
designed to identify the likelihood of lung cancer.
using patient symptoms and lifestyle factors.

### The model analyzes multiple health indicators such as

- Smoking and alcohol consumption
- Chest pain, wheezing, coughing
- Swallowing difficulty, fatigue, anxiety
- Chronic disease and allergy indicators
- and predicts a **binary outcome**:
 
- `1 → Lung Cancer Detected`
- `0 → No Lung Cancer`

### A .  Project Objective

The primary goal of this project is to build a.
**reliable and medically safe prediction system**. 
by prioritizing **Recall score**, followed by Precision and overall Accuracy.

>  In medical diagnosis, a **False Negative**
> (cancer present but not detected) can be fatal.  
> Therefore, this project focuses on **maximizing Recall**
> to ensure that cancer cases are not missed.

### B .  Approach Summary

- End-to-end ML pipeline from data preprocessing to model evaluation
- Comparison of **14 Machine Learning & Deep Learning algorithms**
- Special focus on **Boosting and Ensemble techniques**
- Final model selection based on **balanced medical performance**, not just accuracy

      This project demonstrates
      a real-world healthcare 
      application of Machine 
      Learning,combining technical
      rigor with domain-specific
      decision making.
  
# 2.  Dataset Overview
_____________________________

This project uses a **medical survey–based lung cancer dataset** 
containing patient health indicators, lifestyle habits,
and clinical symptoms that are commonly
associated with lung cancer risk.

### 🔹 Dataset Size

- Total samples (after cleaning):  **276**
- Total features:                  **16**
- Target variable:          **LUNG_CANCER**

### 🔹 Input Features

The dataset includes the following medical and lifestyle indicators:

- 1. AGE  
- 2. GENDER  
- 3. SMOKING  
- 3. ALCOHOL CONSUMING  
- 4. CHEST PAIN  
- 5. COUGHING  
- 6. WHEEZING  
- 7. SHORTNESS OF BREATH  
- 8. SWALLOWING DIFFICULTY  
- 9. FATIGUE  
- 9. ANXIETY  
- 10. ALLERGY  
- 11. YELLOW FINGERS  
- 12. PEER PRESSURE  
- 13. CHRONIC DISEASE  

          Each feature represents a
          binary or numerical medical
          condition contributing to
          lung cancer risk assessment.

### 🔹 Target Variable

- `LUNG_CANCER = 1` → Lung cancer detected  
- `LUNG_CANCER = 0` → No lung cancer  

##  DataSet Challenge
______________________________

The dataset is **highly imbalanced**, with lung cancer. 
cases dominating the samples.  
To address this issue and prevent biased learning,
**ADASYN oversampling** was applied to balance.
the dataset before model training.

Balancing the dataset ensures that the models learn meaningful.
medical patterns instead of favoring the majority class.

#  Data Preprocessing
___________________________

To ensure reliable and medically safe predictions, the raw dataset was carefully preprocessed before training any Machine Learning model.

### 🔹 Data Cleaning

- Duplicate records were identified and removed to avoid biased learning.
- The final dataset was reduced from **309 to 276 samples** after duplicate removal.
- No missing values were present in the dataset.

### 🔹 Label Encoding

- Binary features were encoded as:
  
  - `1 → Yes`
  - `0 → No`
    
- Target variable `LUNG_CANCER` was converted to:
 
  - `1` for cancer detected
  - `0` for no cancer
  - 
- Gender was encoded as:
 
  - `0 → Male`
  - `1 → Female`

### 🔹 Outlier Analysis

- Age distribution was analyzed using boxplots.
- A small number of high-age outliers were observed.
- Since age is a **medically valid and realistic factor**,
-  no outliers were removed.

### 🔹 Class Imbalance Handling

- The dataset was **highly imbalanced**, with cancer cases dominating.
- To address this, **ADASYN (Adaptive Synthetic Sampling)** was applied.
- This technique generates synthetic samples for the minority class,
- helping models learn balanced decision boundaries.

### 🔹 Feature Scaling

- **StandardScaler** was applied to normalize feature values.
- Scaling was essential for distance-based and gradient-based algorithms such as:
  - Logistic Regression
  - SVM
  - KNN
  - Neural Networks

         These preprocessing steps
         ensured that the dataset
         was clean, balanced, and
         numerically stable, 
         allowing fair and consistent
         evaluation across all models.
    
 ##  Exploratory Data Analysis & Feature Engineering
 ______________________________________________________________

- Before training the models, detailed **EDA** was performed 
- to understand feature relationships and medical relevance.

### 🔹 Target Distribution Analysis

- The target variable `LUNG_CANCER` showed a **strong class imbalance**,
- with cancer-positive cases dominating.
- This confirmed the need for imbalance
-  handling techniques during preprocessing.

 ### 🔹 Correlation Analysis

- A correlation matrix was generated to analyze the
- relationship between input features and lung cancer.
 
 #### Features such as:
  
  - **ALLERGY**
  - **ALCOHOL CONSUMING**
  - **SWALLOWING DIFFICULTY**
  - **COUGHING**
  - **WHEEZING**
  showed relatively higher correlation with lung cancer.

- Features like **AGE**, **GENDER**, and **SHORTNESS OF BREATH**
- showed weaker correlation but were retained
- due to their medical significance.

####  Heatmap Visualization

- Correlation heatmaps were used to visually inspect feature dependencies.
- Strong inter-feature relationships were identified,
-  particularly between **ANXIETY** and **YELLOW FINGERS**.

###  Feature Engineering

- Based on correlation insights, a new interaction feature was created:
  
- `ANXI_YELLOW_FING = ANXIETY × YELLOW_FINGERS`
    
- This feature captures the combined effect of anxiety-related
-  behavior and physical symptoms, enhancing model learning capability.

#### 🔹 Medical Insight

EDA confirmed that lung cancer risk is influenced by a. 
**combination of symptoms rather than a single factor**.  
Feature engineering helped the models learn **non-linear.
and interaction-based medical patterns**.
improving predictive performance.

    This step ensured that the 
    models  were trained on informative, 
    medically meaningful, and 
    optimized features.

 ## Models & Algorithms Used
 _________________________________

To ensure robust and unbiased medical predictions, this project evaluates a **wide range of Machine Learning and Deep Learning algorithms**.  
In total, **14 different models** were trained, tested, and compared using consistent evaluation metrics.

### 🔹 Traditional Machine Learning Models
- **Logistic Regression** – Baseline linear classifier for medical risk prediction  
- **Decision Tree Classifier** – Interpretable tree-based model  
- **K-Nearest Neighbors (KNN)** – Distance-based classifier  
- **Support Vector Machine (SVM)** – Margin-based classifier  
- **Bernoulli Naive Bayes** – Probabilistic model for binary features  

### 🔹 Ensemble & Boosting Models
- **Random Forest Classifier** – Bagging-based ensemble of decision trees  
- **AdaBoost Classifier** – Boosting technique focusing on hard-to-classify samples  
- **Gradient Boosting Classifier** – Sequential boosting of weak learners  
- **XGBoost Classifier** – Optimized gradient boosting framework  
- **LightGBM Classifier** – High-performance gradient boosting model  
- **CatBoost Classifier** – Advanced boosting model with strong regularization  

### 🔹 Ensemble Combination Techniques
- **Voting Classifier (Soft Voting)** – Combines predictions from multiple models  
- **Stacking Classifier** – Meta-learning approach using base learners and a final estimator  

### 🔹 Deep Learning Model
- **Artificial Neural Network (ANN)** – Multi-layer perceptron trained on scaled features  

### 🔬 Model Selection Strategy
- All models were evaluated using:
  - **Recall**
  - **Precision**
  - **Accuracy**
  - **F1-Score**
  - **Confusion Matrix**
- Since this is a **medical diagnosis problem**, **Recall was prioritized** to minimize false negatives.

After extensive comparison, **Boosting-based models demonstrated superior performance**, with **CatBoost** selected as the final model due to its **balanced Recall and Precision**, making it suitable for real-world medical applications.


    



