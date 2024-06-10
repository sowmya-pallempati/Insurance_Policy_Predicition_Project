# Insurance_Policy_Predicition_Project

## Problem statement:
Using historical policy data, create a multiclass predictive model to predict the policies that are most likely to be canceled and those most likely to be renewed, as well as understand what variables are most influential in causing a policy cancellation.

## Dataset Description:
The Kangaroo dataset is used for this project, based on 4 years of property insurance policies from 2013 to 2017. The training dataset comprises approximately 1 million policies, each policy represented by a single observation. Notably, there were almost 230,000 policies canceled during the effective term.

**Training Dataset**
Total Rows: 700,232  
Total Features: 16 (a mix of categorical and continuous features)

**Variable descriptions**  

tenure - Number of years with Kangaroo  
claim.ind - Occurrence of claim (0=no, 1=yes)  
n.adults - Number of adults in the property  
n.children - Number of children in the property  
ni.gender - Gender of policyholder  
ni.marital.status - Marital status of policyholder (0=no, 1=yes)  
premium - Price of the policy  
sales.channel - Medium through which policy was purchased  
coverage.type - Type of coverage  
dwelling.type - Type of dwelling  
len.at.res - Length at residence (how long policyholder lived at property)  
credit - Financial credit level of policyholder  
house.color - Color of house  
ni.age - Age of policholder  
year - Year of the policy  
zip.code - Zip code of the property  
cancel - cancelation indicator (0=not cancel, 1=may cancel but can be convinced, 2=cancel). This is the response variable.   

## Features  
**1. Data Cleaning:** Preprocessed and cleaned the dataset to handle missing values(Imputation), outliers, inconsistencies and eliminate unnecessary columns.  
**2. Exploratory Data Analysis (EDA):** Performed In-depth analysis of the data to uncover patterns, trends, and relationships between variables.  
**3. Feature Engineering:** Several feature engineering techniques were applied to prepare the dataset for modeling:  
   * Label Encoding: Converted categorical variables into numerical values to be used in machine learning algorithms.  
   * Min-Max Scaling: Scaled continuous variables to a range between 0 and 1 to ensure equal contribution to the model.  
   * Oversampling: Used techniques like RandomOverSampling to balance the class distribution in the CancellationStatus feature, addressing the issue of class imbalance.

**4. Predictive Modeling:** Several machine learning models were evaluated to predict policy cancellations:
     * Decision Tree Classifier  
     * Random Forest Classifier  
     * Gradient Boosting Classifier  
     * Bagging Classifier  
     * Logistic Regression  
     * Multi-layer Perceptron Classifier  
     * AdaBoost Classifier with specific parameters: AdaBoostClassifier(learning_rate=0.01)  
     * Gaussian Naive Bayes  
     * K-Neighbors Classifier      
Among these, the **Random Forest Classifier** provided the best predictions.  

**5. Model Performance and Feature Importance:**

![image](https://github.com/sowmya-pallempati/Insurance_Policy_Predicition_Project/assets/112984551/fe9eb69b-f2ce-48ba-b82b-79f6a6f5ee2f)    
The Random Forest Classifier achieved a notable F1 score of 0.84 on the test dataset, indicating strong predictive performance.  
   **Top Features**  
   Using permutation importance, we identified the top 5 features that contribute most significantly to the model's predictions:  
     * credit  
     * sales_channel  
     * zipcode  
     * year  
     * age  
  
  ## Business Recommendations and Observations:  
   * We see that people with less credit have a high chance of cancelling the subscription as compared to the people with high credit scores. Taking this into consideration, we should advertise the products to         people with higher credit scores via targeted ads and marketing campaigns. Also, we should investigate further into what is causing low credit customers to cancel their subscription.  
   * We can observe that the more tenure a person has, less likely they cancel the subscription. To improve the number of consumers for the products, we should implement schemes to retain customers for a longer        time. A good step in that direction would be to collect regular feedbacks about products and a discourse on how to improve the user experience.  
   * Another observation we have is that younger customers tend to cancel more than the older customers. May be the products and marketing campaigns aren't as relavant to the younger audience and should be geared      towards the younger population and also keeping the elder customers happy.  
  * Customers aquired through broker are less likely to cancel the subscription than customers through other mediums. We should incentivize broker and encourage them to get more customers. Also, increasing the        number of brokers can help us achieve lower cancellation and higher retention.  
  * The PDP Graph relationship between Zipcode and cancel, we can observe that the line varies in the range of 0 and 0.30, which likely indicates that there is a weak relationship between zip codes and the             likelihood of cancellation.  

