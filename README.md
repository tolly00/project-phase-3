# Telecommunication Customer Churn Prediction
## **Overview**
A telecommunication company, his mame is **SyriaTel**, he wants to be informed whether a customer will ("soon") stop doing business with him.

## **Business and Data Undertanding**

### **Business Problem**
**SyriaTel**, a telecommunications company, is confronted with the challenge of **customer churn**, which occurs when subscribers stop using the company’s services. In the telecom industry, churn has a significant financial impact because acquiring new customers is more expensive than retaining existing ones.

The primary business objective is to **predict which customers are likely to churn**. By identifying at-risk customers early, SyriaTel can take proactive measures such as offering targeted promotions, improving customer service, or personalizing engagement to reduce churn and improve customer retention. This directly contributes to revenue stability and long-term business growth.

### **Stakeholder Audience**

The key stakeholders for this project include:

-   **Executive Management**  
    Interested in understanding the financial implications of churn and how predictive modeling can improve long-term customer retention and profitability.
    
-   **Marketing Department**  
    Needs to identify high-risk customers in order to design and launch targeted retention campaigns, maximizing return on marketing investment.
    
-   **Customer Service Team**  
    Can use the churn predictions to proactively engage with dissatisfied customers, resolve issues, and improve customer satisfaction before they decide to leave.
    
-   **Data Science & Analytics Team**  
    Responsible for building, validating, and maintaining the churn prediction model, ensuring technical accuracy and delivering insights that are actionable for the business.

### **Dataset Choice**

This project uses the **SyriaTel Customer Churn dataset**, which contains information on customer demographics, service subscriptions, call usage, and customer support interactions. The dataset is well-suited for churn prediction as it captures both behavioral and account-level features.

Key attributes include:

-   **Account length:** Duration of the customer’s relationship with SyriaTel.
    
-   **International plan / Voice mail plan:** Indicators of service subscription.
    
-   **Call usage:** Number of calls, minutes, and charges across day, evening, and night periods.
    
-   **Customer service calls:** Frequency of interactions with customer support.
    
-   **Churn (Target Variable):** A binary indicator showing whether a customer has churned (1) or not (0).

-   **and others features...**. This dataset has **3333 rows** and **21 columns**.
    

This combination of features provides valuable insights into customer behavior and service utilization, making it possible to identify patterns that signal potential churn.

## **Modeling**
For this project, the objective was to build a classification model to predict whether a SyriaTel customer will churn. Several machine learning algorithms were tested to identify the best-performing model.
The general workflow was:

1.  **Data Preprocessing:**
    
    -   Handled categorical features (_International Plan_, _Voice Mail Plan_) using OneHotEncoding.
        
    -   Standardized numerical features where necessary.
        
    -   Split the dataset into **train (70%)** and **test (30%)** sets.
        
2.  **Model Selection:**  
    The following algorithms were evaluated:
    
    -   Logistic Regression
    -   Random Forest        
    -   Decision Tree Classifier

### **Confusion matrix for the logistic regression algorithm**
![enter image description here](images/log_matrix.png)

### **Confusion matrix for the Random Forest algorithm**
![enter image description here](images/forest_matrix.png)

### **Confusion matrix for the decision tree algorithm**
![enter image description here](images/tree_matrix.png)

### **The ROC curve graph**
![enter image description here](images/roc_curve.png)

## Evaluation

The goal of this project is to build a predictive model that can identify **SyriaTel customers** at risk of leaving (churn). Three models were tested: **Logistic Regression, Random Forest, and Decision Tree**. Performance was evaluated on accuracy, precision, recall, F1-score, and overfitting tendency.

#### 1- Logistic Regression

- Train Accuracy: 0.78
- Test Accuracy: 0.75

Churn class (1): Precision = 0.33, Recall = 0.69, F1 = 0.45

#### **Analysis**

- The model achieves good recall for churners (69%), meaning it successfully identifies most customers at risk of leaving.

- However, precision is very low (33%), so many loyal customers are incorrectly flagged as churners.

- Accuracy is modest, but the model does not overfit.

#### 2- Random Forest

- Train Accuracy: 1.00
- Test Accuracy: 0.90

Churn class (1): Precision = 0.68, Recall = 0.63, F1 = 0.66

#### Analysis:

- Random Forest delivers the best overall performance, with a strong balance between precision and recall.

- F1-score for churners (0.66) is the highest among all models, showing a good trade-off.

- The model generalizes well, though the perfect training accuracy suggests slight overfitting.

#### 3- Decision Tree

- Train Accuracy: 1.00

- Test Accuracy: 0.88

Churn class (1): Precision = 0.57, Recall = 0.72, F1 = 0.64

#### Analysis:

- The Decision Tree also shows strong recall (72%), slightly higher than Random Forest.

- Precision (57%) is lower, leading to more false positives compared to Random Forest.

- Overfitting is evident (perfect training score vs lower test score).


## Conclusion
Best Overall Model: **Random Forest**

- Balanced precision and recall for churners.

- Best F1-score for churn prediction.

- Generalizes better than Decision Tree while outperforming Logistic Regression.

**If Recall is Priority**: Decision Tree (72% recall) or Logistic Regression (69% recall) may be considered.

**If Business Needs Balance**: Random Forest is recommended as the final predictive model for churn identification.
