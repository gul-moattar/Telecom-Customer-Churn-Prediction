# Telecom-Customer-Churn-Prediction
Submit AI task-02
## **MAIN FOCUS OF THE PROJECT** : (Telecom Customer Churn Prediction)

*   Accurately classifies whether a customer is likely to churn.
*   Provides interpretable insights into the drivers of churn.
*   Offers actionable recommendations for business teams.


### Objective:
In this project, ere we are creating an ML model to helping the Telecom company, predict whether a customer will churn (leave the telecom service) or not, using historical customer data`So they can identify at-risk customers and take strategic actions to retain them.


### Problem Statement :

Telecom companies face a significant challenge with customer retention, as acquiring new customers is costlier than retaining existing ones. A large number of customers are leaving the service due to reasons such as poor service, high charges, or better offers from competitors.

* My role is to develop a (ML)model that:

- ✔ Predict which customers are likely to leave (churn)  
- ✔ Explain which things (features) are causing customers to leave  
- ✔ Give helpful suggestions to the business team so they can keep their customers.

## Dataset Information:

You can typically use a dataset like the one from Kaggle – Telco Customer Churn. It contains customer demographics, account info, service details, and churn status.

| Column Name        | Description                                                                 |
| ------------------ | --------------------------------------------------------------------------- |
| `customerID`       | Unique customer identifier                                                  |
| `gender`           | Male or Female                                                              |
| `SeniorCitizen`    | Whether the customer is a senior citizen (1: Yes, 0: No)                    |
| `Partner`          | Whether the customer has a partner                                          |
| `Dependents`       | Whether the customer has dependents                                         |
| `tenure`           | Number of months the customer has stayed with the company                   |
| `PhoneService`     | Whether the customer has phone service                                      |
| `MultipleLines`    | Whether the customer has multiple lines                                     |
| `InternetService`  | Type of internet service: DSL, Fiber optic, or None                         |
| `OnlineSecurity`   | Whether the customer has online security                                    |
| `OnlineBackup`     | Whether the customer has online backup                                      |
| `DeviceProtection` | Whether the customer has device protection                                  |
| `TechSupport`      | Whether the customer has tech support                                       |
| `StreamingTV`      | Whether the customer has streaming TV                                       |
| `StreamingMovies`  | Whether the customer has streaming movies                                   |
| `Contract`         | Type of contract: Month-to-month, One year, Two year                        |
| `PaperlessBilling` | Whether the customer uses paperless billing                                 |
| `PaymentMethod`    | Payment method (e.g., Electronic check, Credit card)                        |
#2. Encode categorical columns

# -> Step: Understanding Data Types Before Encoding


 here we checked the data types of all columns using:
# df.dtypes

 Now based on the output, we observed the following:

# ✔ Columns that are already numeric (no need to convert):
 - SeniorCitizen (int64)
 - tenure (int64)
 - MonthlyCharges (float64)
 - TotalCharges (object → needs conversion to float)

# Columns that need to be converted to numeric form:
# These are object (text) type columns and need encoding:
 - gender                (Male/Female)
 - Partner               (Yes/No)
 - Dependents            (Yes/No)
 - PhoneService          (Yes/No)
 - MultipleLines         (Yes/No/No phone service)
 - InternetService       (DSL/Fiber optic/No)
 - OnlineSecurity        (Yes/No/No internet service)
 - OnlineBackup          (Yes/No/No internet service)
 - DeviceProtection      (Yes/No/No internet service)
 - TechSupport           (Yes/No/No internet service)
 - StreamingTV           (Yes/No/No internet service)
 - StreamingMovies       (Yes/No/No internet service)
 - Contract              (Month-to-month/One year/Two year)
 - PaperlessBilling      (Yes/No)
 - PaymentMethod         (Bank transfer/Credit card/etc.)
 - Churn                 (Yes/No) ➝ Target column

# Note:
# - customer-ID should be dropped beacuse it is unique identifier.
# - - TotalCharges must be converted from object to float.

# **Step 6: Model Interpretability**

* Once we’ve trained our machine learning models (e.g., Logistic Regression, Random Forest, XGBoost), it’s important.

*  To understand why the model makes certain predictions — this is called model interpretability.
**Step 6: Model Interpretability with SHAP**

* Once your model (like XGBoost or Random Forest) makes accurate predictions, it’s important to understand why it made those predictions — especially in real business applications like customer churn.

*  (SHapley Additive exPlanations)

1. Tells you which features are pushing the prediction toward churn or retention.

2. Helps build trust in the model.

3. Provides business insights for decision-making.
   # **Step 7: Business Insights Based on Model Results**

Business Insights
 1. Contract Type Strongly Influences Churn
Customers on Month-to-Month contracts have the highest churn rate.

Those on 1- or 2-year contracts are significantly less likely to churn.

✅ Business Action:
Offer incentives (discounts, perks) to encourage customers to switch to longer contracts.

2. Tenure is a Key Loyalty Indicator
Customers with short tenure (new customers) are more likely to churn.

Long-term customers are loyal and stable.

✅ Business Action:
Create onboarding campaigns and early engagement programs to retain new users during their first few months.

3. High Monthly Charges Increase Churn
Customers with higher monthly charges tend to leave more.

Especially true when combined with poor service or basic contract terms.

✅ Business Action:
Introduce value-added services, custom plans, or bundled packages for high-paying customers to justify costs.

 4. Technical Support Reduces Churn
Customers who have Tech Support, Device Protection, or Online Security are less likely to churn.

These services build trust and stickiness.

✅ Business Action:
Promote these services during customer sign-up or offer free trials to boost adoption.

 5. Paperless Billing & Electronic Checks = Higher Churn
Customers using paperless billing or electronic check payment methods churn more often.

✅ Business Action:
Consider personalized billing options or loyalty points for consistent payments to reduce frustration or improve satisfaction.

 6. Gender and Seniority Have Minimal Impact
Gender and whether a customer is a senior citizen had little influence on churn based on SHAP results.

✅ Business Action:
Focus marketing and retention on usage patterns and contract behavior, rather than demographics.

 Overall Recommendation:
Use the model to score customers weekly or monthly, identify high-risk churners, and feed them into automated retention campaigns via email, SMS, or CRM systems.
| `MonthlyCharges`   | The amount charged to the customer monthly                                  |
| `TotalCharges`     | The total amount charged to the customer                                    |
| `Churn`            | Whether the customer left in the last month (Yes or No) — **Target column** |
