# Lung-Cancer-Risk-Prediction-

![image](https://github.com/user-attachments/assets/593e8307-7bdb-4662-b40b-ed6725ca7309)



## Overview

This project focuses on developing a predictive model to assess the risk of lung cancer in individuals based on various health and lifestyle factors. Utilizing machine learning techniques, the model aims to provide early detection insights, thereby facilitating timely medical interventions.

## Dataset
[Lung Cancer Risk Prediction](https://www.kaggle.com/datasets/thedevastator/cancer-patients-and-air-pollution-a-new-link)

This dataset contains information on patients with lung cancer, including their age, gender, air pollution exposure, alcohol use, dust allergy, occupational hazards, genetic risk, chronic lung disease, balanced diet, obesity, smoking status, passive smoker status, chest pain, coughing of blood, fatigue levels , weight loss , shortness of breath , wheezing , swallowing difficulty , clubbing of finger nails , frequent colds , dry coughs , and snoring. By analyzing this data we can gain insight into what causes lung cancer and how best to treat it

- Age: The age of the patient. (Numeric)

- Gender: The gender of the patient. (Categorical)
- Air Pollution: The level of air pollution exposure of the patient. (Categorical)
- Alcohol use: The level of alcohol use of the patient. (Categorical)
- Dust Allergy: The level of dust allergy of the patient. (Categorical)
- OccuPational Hazards: The level of occupational hazards of the patient. (Categorical)
- Genetic Risk: The level of genetic risk of the patient. (Categorical)
- Chronic Lung Disease: The level of chronic lung disease of the patient. (Categorical)
- Balanced Diet: The level of balanced diet of the patient. (Categorical)
- Obesity: The level of obesity of the patient. (Categorical)
- Smoking: The level of smoking of the patient. (Categorical)
- Passive Smoker: The level of passive smoker of the patient. (Categorical)
- Chest Pain: The level of chest pain of the patient. (Categorical)
- Coughing of Blood: The level of coughing of blood of the patient. (Categorical)
- Fatigue: The level of fatigue of the patient. (Categorical)
- Weight Loss: The level of weight loss of the patient. (Categorical)
- Shortness of Breath: The level of shortness of breath of the patient. (Categorical)
- Wheezing: The level of wheezing of the patient. (Categorical)
- Swallowing Difficulty: The level of swallowing difficulty of the patient. (Categorical)
- Clubbing of Finger Nails: The level of clubbing of finger nails of the patient. (Categorical)

# Methodology
The project follows these key steps:

1. Data Preprocessing: Cleaning and preparing the data for analysis.
2. Exploratory Data Analysis: Exploring relationship between features and using visualizations techniques to discover insights.
3. Feature Engineering: Selecting and transforming relevant features to enhance model performance. 
4. Model Development: Implementing machine learning algorithms to predict lung cancer risk levels (Low, Medium, High).
5. Model Evaluation: Assessing the model's accuracy and reliability using appropriate metrics.


# 1) Data Preprocesssing:
In the part of the project I loaded the data and checked for duplicate values and null values. Furthermore I explored the data types and discovered that all were numeric with the exception of two. 

df.head() and df.columns are used to explore the feature of the dataset and begin developing questions to explore during EDA. 


# 2) Exploratory Data Analysis:

 ## Exploring the target variables (Low, Medium, High)



![image](https://github.com/user-attachments/assets/46a76331-de7d-409f-a908-e44faf71369f)


- Dataset is balanced. 

### Age and Cancer Risk Level 

![image](https://github.com/user-attachments/assets/d9f779e2-6dc3-4299-b1ed-9fd14e0d9c00)

- Low risk level has younger median age.
- Medium risk level has highest average age.

### Hypothesis Testing: 

- Null: The observed differnece in average age between 'Low', 'Medium' and 'High' lung cancer risk levels is due to random chance. 


- Alternative Hypothesis: The observed difference in cancer risk level scores and average age is not due to random chance. 

Using a Levene's test to check if the three risk groups have equal variance (homogeneity of variance) before trying ANOVA.


![image](https://github.com/user-attachments/assets/1ee4dae7-4846-4baf-af88-a3a345507fcf)


- Can not use ANOVA but can use Welch's ANOVA


### Welch's ANOVA Results:

- Difference in mean age between Low and Medium risk groups is statistically significant p-value = 0.0039 which is lower than threshold of 0.05.

- Differnece in mean age between Low and High risk groups is not statistically significant p-value = 0.08.

- Differnece in mean age between High and Low is also not statistically significant p-value = 0.32.



## Risk Level and Diet:

![image](https://github.com/user-attachments/assets/2667d2b5-85f2-43dc-acd6-101c185f4ff2)


- Low Risk level had the lowest average score for Balanced Diet. This indicates that diet might be a factor in determining Lung Cancer Risk Level.

- Medium Risk Level had the second highest average score for Balanced Diet. 

- High Risk Level had by far the highest average score for Balanced Diet, it was more than double that of Low Risk Level.


- These iinsights show a clear correlation between Lung Cancer Risk Level and Diet. 


## Correlation Matrix:

![image](https://github.com/user-attachments/assets/2f7422bc-9381-45e1-9781-cc61c38367c0)

# Insights based on Correlation Matrix:

Zero Correlation, no linear relationship between the variables.

## 1) Postitive Correlations (as one variable increases so does the other): 
- Cancer Risk Level is most positively correlated with Obesity at 83% and Coughing Blood at 78%.
- Cancer Risk Level and Alchohol Use at 72% 
- Cancer Risk Level and Genetic Risks at 70% 
- Cancer Risk Level and Balanced Diet 71% 
- Cancer Risk Level and Passive Smoker 70% 
- Cancer Risk Level and Occupational Hazards at 71%
- Cancer Risk Level and Chest Pain 65%
- Cancer Risk Level and Air Pollution at 64%
- Cancer Risk Level and Fatigue 63% 
- Cancer Risk Level and Chronic Lung Disease 61%
- Cancer Risk Level and Smoking 52%

## 2) Negative Correlations (as one variable increases the other decreases): 

- Cancer Risk Level and Gender are negatively correlated at 16%. Since females are encoded as 2 this implies that a higher number for Gender correlates with lower Risk Level
- Cancer Risk Level and Age -6% 

## 3) There are many features that are highly correlated which can lead to multicollinearity which can lead to overfitting. Methods to combat this can be PCA, dropping features that are highly correlated or applying Ridge or Lasso regularization. However this might not be an issue if I use decision trees or random forests. 


- Clustering 

# 3) Feature Engineering:

- Risk Levels are mannually encoded to numeric format to prepare for Models:
- Mannually encode these values: High = 2, Medium = 1, Low = 0.

# 4) Model Development:

## Models developed:

- Ordinal Logistic Regression
- Logistic Regression Model
- Random Forest Classifier
- XGBOOST


# 5) Model Evaluation: 
- Ordinal Logistic Regression: Accuracy = 83.6%
- Logistic Regression Model: Accuracy = 88%
- Random Forest Classifier:
- XGBOOST: 


# Results
The predictive power of the best model demonstrates the following metrics: accuracy: , precision:, recall:. in assessing lung cancer risk. These results underscore the model's potential utility in early detection scenarios.

# Key Insights: 

## Random Forest Model Insights:

![image](https://github.com/user-attachments/assets/43f384b7-e1fb-45da-8023-22081af654bf)


## Random Forest Model with Hyperparamater Tunning Insights:

![image](https://github.com/user-attachments/assets/2b754b9f-7458-402b-89ff-7ac3915a26bd)



## XGBOOST Model Insights:

![image](https://github.com/user-attachments/assets/47a172b1-5e28-4259-8d84-7aa35194a7db)


# Key Insights:

- Across all machine learning models, the most influential features in predicting a high lung cancer risk level were obesity, dust allergy, and alcohol use.

- Several contributing factors—such as genetic risk, air pollution, age, and gender—are non-modifiable and outside an individual’s control.

- However, the most impactful and predictive features can be mitigated through lifestyle changes.

- Reducing obesity, limiting alcohol consumption, and avoiding smoking are actionable steps individuals can take to lower their risk of developing lung cancer.

- Clustering techniques proved useful for grouping individuals based on similar feature patterns, offering an additional method to assess lung cancer risk levels.






