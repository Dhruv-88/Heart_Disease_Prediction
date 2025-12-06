# Heart Disease Prediction

## 1. Introduction
In this project, we employed supervised and unsupervised machine learning methodologies on a heart disease dataset sourced from Kaggle. The report delves into comprehensive analysis and insightful visualizations with the goal of developing precise predictive models. These models aim to help medical practitioners identify patients more susceptible to heart disease, facilitating prompt interventions and better patient outcomes.

## 2. Dataset Overview
*  **Source:** The dataset originated from the UCI health data repository and was sourced via Kaggle.
*  **Dimensions:** The dataset contains 11 columns and 2,943 rows.
*  **Dependent Variable:** Heart Disease (Binary: 0 or 1).
*  **Independent Variables:** Crucial attributes include Age, Sex, Chest Pain Type, Resting Blood Pressure, Cholesterol, Resting ECG, Maximum Heart Rate, Exercise Angina, and Oldpeak, among others.

## 3. Methodology & Applied Techniques

### A. Exploratory Data Analysis (EDA) & Data Cleaning
 We meticulously examined the dataset to ensure data cleanliness and reliability.
* **Cleaning:** The dataset was checked for null values and duplicates;  0 null values and no duplicates were found.
* **Distributions:**
    *  **Target Variable:** The data is fairly distributed, with 55% of patients having heart disease and 45% without.
    *  **Gender:** There is a skew in gender distribution, with 75% males and 25% females.
    *  **Age:** Age follows a normal distribution for both genders.  Heart disease occurrence is consistently distributed across all age groups (approx. 55% per group).
* **Correlations:**
    *  Density plots revealed two peaks in cholesterol levels, suggesting people with higher cholesterol are slightly more likely to have heart disease.
    *  Correlation plots showed strong positive relationships between Fasting Blood Sugar, Chest Pain, Maximum Heart Rate, and Resting Blood Pressure.



### B. Supervised Learning
 We implemented supervised learning techniques to predict the likelihood of heart disease. Models were initially tested on raw data, then re-run after data cleaning and feature selection.

* **Algorithms Evaluated:**
    * K-Nearest Neighbors (KNN)
    * Support Vector Machine (SVM)
    * Naive Bayes
    * Logistic Regression
    * Decision Trees
    *  Random Forest 
*  **Optimization:** For KNN, we found that $k=3$ was well-suited for this dataset, maintaining consistent accuracy.


### C. Unsupervised Learning
 We employed k-means clustering to identify clusters of patients with similar symptoms and patterns.
*  **Process:** We executed the algorithm with varying numbers of centers ($k=1$ to $20$) and recorded the Within-Cluster Sum of Squares (WSS).
*  **Selection:** The improvement in WSS slowed significantly after 4 centers; consequently, we proceeded with 3 clusters for detailed analysis.


## 4. Key Findings & Results

### Model Performance
*  **Random Forest:** This was the best performing model, achieving **91% accuracy**.
* **Feature Importance:** The Random Forest visualization indicated the most significant factors in predicting heart disease are (in order):
    1.  Chest Pain Type
    2.  Cholesterol
    3.  Resting Blood Pressure
    4.   Maximum Heart Rate.
* **Other Models (After Feature Selection):**
    *  KNN: ~76.57%
    *  Logistic Regression: ~75.55% 
    *  SVM: ~73.17%

### Clustering Insights
*  **High Risk Cluster:** "Cluster 1" revealed a striking pattern where nearly **89%** of patients in this group were at high risk of heart disease.
* **Symptom Profile (Cluster 1):**
    *  **Cholesterol:** Average levels shot up to **462** for individuals with heart disease in this cluster (compared to ~208 in other groups).
    *  **Fasting Blood Sugar:** Levels reaching **42** were a significant concern.
    *  **Other Indicators:** Resting ECG and Oldpeak were identified as crucial indicators.

## 5. Conclusions & Recommendations
 The analysis underscores the potential of machine learning in enhancing heart disease prediction. Based on the study, the following monitoring recommendations are suggested:

*  **Cholesterol:** Monitor closely if levels exceed **$208~mg/dL$**.
*  **Blood Sugar:** Fasting levels reaching **$42~mg/dL$** could indicate potential heart issues.
*  **ECG:** Resting ECG readings above **85 bpm** may signal an emergency.
*  **Vitals:** Particular concern is warranted if blood pressure is around **160 mmHg** and maximum heart rate reaches **150 bpm**.
