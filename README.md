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

### A.  Project Objective

The primary goal of this project is to build a.
**reliable and medically safe prediction system**. 
by prioritizing **Recall score**, followed by Precision and overall Accuracy.

>  In medical diagnosis, a **False Negative**
> (cancer present but not detected) can be fatal.  
> Therefore, this project focuses on **maximizing Recall**
> to ensure that cancer cases are not missed.

### B.  Approach Summary

- End-to-end ML pipeline from data preprocessing to model evaluation
- Comparison of **14 Machine Learning & Deep Learning algorithms**
- Special focus on **Boosting and Ensemble techniques**
- Final model selection based on **balanced medical performance**, not just accuracy

      This project demonstrates a **real-world healthcare 
      application of Machine Learning**, combining technical
      rigor with domain-specific decision making.
  
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

Each feature represents a **binary or numerical medical condition** contributing to lung cancer risk assessment.

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


