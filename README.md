# Overview : 
________________________
## 🫁 Lung Cancer Prediction using Machine Learning 

Lung cancer is one of the most life-threatening diseases.
Where early detection plays a critical role. 
in improving patient survival rates.  
This project presents a Machine Learning–based medical prediction system.
designed to identify the likelihood of lung cancer.
using patient symptoms and lifestyle factors.

### This Model analyzes Multiple. 
### Health indicators such as: 

- Smoking and alcohol consumption
- Chest pain, wheezing, coughing
- Swallowing difficulty, fatigue, anxiety
- Chronic disease and allergy indicators
- and predicts a **binary outcome**:
 
- `1 → Lung Cancer Detected`
- `0 → No Lung Cancer`

## A. Project Objective : 

The primary goal of this project is to build a.
**reliable and medically safe prediction system**. 
by prioritizing **Recall score**, followed by Precision and overall Accuracy.

>  In medical diagnosis, a **False Negative**
> (cancer present but not detected) can be fatal.  
> Therefore, this project focuses on **maximizing Recall**
> to ensure that cancer cases are not missed.

## B . Approach Summary : 

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
  
# 2. Dataset Overview
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
The dataset includes the following.
medical and lifestyle indicators:

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

To ensure reliable and medically safe predictions.
the raw dataset was carefully preprocessed before.
training any Machine Learning model.

### A 🔹 Data Cleaning

- Duplicate records were identified and removed to avoid biased learning.
- The final dataset was reduced from **309 to 276 samples** after duplicate removal.
- No missing values were present in the dataset.

### B 🔹 Label Encoding

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

### C 🔹 Outlier Analysis

- Age distribution was analyzed using boxplots.
- A small number of high-age outliers were observed.
- Since age is a **medically valid and realistic factor**,
- no outliers were removed.

### D 🔹 Class Imbalance Handling

- The dataset was **highly imbalanced**, with cancer cases dominating.
- To address this, **ADASYN (Adaptive Synthetic Sampling)** was applied.
- This technique generates synthetic samples for the minority class,
- helping models learn balanced decision boundaries.

### E🔹 Feature Scaling

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
 
 ### Features such as:
  
  - **ALLERGY**
  - **ALCOHOL CONSUMING**
  - **SWALLOWING DIFFICULTY**
  - **COUGHING**
  - **WHEEZING**
  showed relatively higher correlation with lung cancer.

- Features like **AGE**, **GENDER**, and **SHORTNESS OF BREATH**
- showed weaker correlation but were retained
- due to their medical significance.

### Heatmap Visualization

- Correlation heatmaps were used to visually inspect
- feature dependencies.Strong inter-feature 
- relationships were identified, particularly between 
- **ANXIETY** and **YELLOW FINGERS**.

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

## 🤖 Models, Algorithms & Performance Metrics

To build a reliable medical prediction system.
this project evaluates **14 Machine Learning and Deep Learning models**.  
Each model was assessed using **medical-critical evaluation metrics**,. 
with **Recall given the highest priority**.

### 🔬 Evaluation Metrics Used

- **Accuracy** – Overall correctness of the model  
- **Precision** – How many predicted cancer cases were actually cancer  
- **Recall** – How many actual cancer cases were correctly
-  detected (**most important**).  
- **F1-Score** – Balance between Precision and Recall. 

### Model-wise Performance Summary

| Model | Accuracy (%) | Precision (%) | Recall (%) |
|-----|-------------|---------------|------------|
| Logistic Regression | ~96.6 | ~95.0 | ~98.0 |
| Decision Tree | ~95.8 | ~94.9 | ~96.5 |
| Random Forest | ~89.0 | ~88.0 | **100.0** |
| XGBoost | ~95.0 | ~93.3 | ~96.5 |
| KNN | ~98.3 | **100.0** | ~96.5 |
| SVM | ~97.5 | ~98.2 | ~96.5 |
| Bernoulli Naive Bayes | ~95.8 | ~94.9 | ~96.5 |
| AdaBoost | ~95.8 | ~94.9 | ~96.5 |
| Gradient Boosting | ~95.8 | ~94.9 | ~96.5 |
| LightGBM | ~95.8 | ~94.9 | ~96.5 |
| Voting Classifier | ~96.6 | ~96.5 | ~96.5 |
| Stacking Classifier | ~97.5 | ~96.6 | ~98.2 |
| Artificial Neural Network | ~95.8 | ~94.9 | ~96.5 |
| **CatBoost (Final Model)** | **~96.7** | **~96.5** | **~96.5** |

---

### 🧠 Medical Interpretation

- **Random Forest** achieved **100% Recall**, ensuring.
-  no cancer case was missed , but suffered from.
-  **lower Precision** leading to more false positives.
- **CatBoost** provided a **balanced trade-off**,.
-  maintaining **high Recall while significantly improving Precision**.
-  This balance is crucial in **real-world medical diagnosis**,.
-  where both missed cases and  unnecessary alarms must be minimized.

## 🏆 Final Model Selection
_______________________________________________________

Multiple high-performing models were obtained
during experimentation.The final model was selected after
carefully analyzing **Recall, Precision, Accuracy, stability,
and real-world medical suitability**.

#### Below is a clear justification for the final decision:

---

### A🔹 Random Forest Classifier

- **Recall:    100%**
- **Precision:  ~88%**

 **Strength:**
 
- Did not miss any lung cancer case (False Negatives = 0)

 **Limitation:**
 
- Lower precision resulted in a higher
- number of **false positives**
- Over-sensitive behavior due to
- **small dataset and ADASYN oversampling**

**Interpretation:**

Random Forest is highly suitable for **initial medical screening**,  
but excessive false alarms make it less ideal for final diagnosis.

---

### 🔹 K-Nearest Neighbors (KNN)

- **Accuracy: ~98%**
- **Precision: 100%**
- **Recall: ~96%**

 **Strength:**
- Very high accuracy and perfect precision on the test split

**Limitation:**

- Distance-based algorithm, sensitive to data distribution
- Scalability and stability issues on unseen or large real-world medical data

**Interpretation:**

KNN performs very well as a **baseline and comparison model**,  
but is not preferred for deployment in critical medical systems.

---

### 🔹 CatBoost Classifier (Final Model)

- **Accuracy: ~96–97%**
- **Precision: ~96–97%**
- **Recall: ~96–97%**
- **F1-Score: ~96–97%**

 **Strength:**
- Balanced trade-off between **Recall and Precision**
- Strong regularization and robustness on tabular medical data
- Reduced false positives while maintaining high cancer detection rate
- More stable and generalizable for real-world healthcare applications

📌 **Interpretation:**

CatBoost provides the **most reliable and medically safe performance**,  
making it the best choice for final lung cancer prediction.

###  Final Decision
___________________________________________

Although Random Forest achieved perfect Recall (100).
and KNN achieved very high Accuracy and Precision, but. 
**CatBoost was selected as the final model** due to. 
its **balanced performance, stability, and.
real-world medical reliability**.

> In medical diagnosis, a slightly lower Recall is
> acceptable if it significantly reduces false alarms,  
> provided that cancer detection remains consistently high.





    



