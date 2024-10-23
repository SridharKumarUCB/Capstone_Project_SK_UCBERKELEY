# Develop a model to accurately predict fraudulent credit card transactions By: Sridhar Kumar

PROBLEM STATEMENT: 

The Research goal is to develop a model to accurately predict fraudulent credit card transactions. 

Research Motivation: Financial fraud has significant negative economic impacts, affecting both businesses and consumers. If unanswered, businesses may face financial losses and damage to their reputations. While on the other hand, consumers could suffer from identity theft and financial insecurity. By predicting fraudulent transactions, my analysis will enable financial institutions to implement proactive measures, reduce fraud losses and enhance overall customer trust. More importantly, this analysis will allow stakeholders to understand risks and develop actionable strategies.

DATA UNDERSTANDING:

The first step was to understand the dataset and explore what information it contains, and how this could be used to inform better business understanding. The steps involved were:

1. Load Data
2. Preview Data
3. Assess the data
4. Check for null values
5. Exploratory Data Analysis (EDA)

The data was Sourced From Kaggle: (https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)

Brief Description of dataset: This dataset contains credit card transactions from September 2013 by European cardholders. It comprises transactions from two days, totaling 284,807 transactions with 492 identified as fraud. This dataset was noted as being a highly unbalanced dataset with fraudulent transactions only accounting for 0.172% of all transactions. In order to combat the imbalance in this dataset, I will use downsampling. This approach helps avoid potential bias in the model's learning. An imbalanced dataset may yield high accuracy for the model, but it will perform poorly in detecting fraud. This is primarily because it will be trained on data that is predominantly non-fraudulent.

We provided an example of a biased model using SVM (Support Vector Machine). The SVM model achieved a high accuracy of 99.93%, but this is very misleading because the dataset was not balanced. Looking at the confusion matrix, it correctly identified 77 out of the 98 fraudulent cases, but it also misclassified 21 fraud cases as non-fraudulent; this resulted in a recall of 79% for the minority class. Again, this test shows how crucial it is to balance datasets, especially for cases where the data is usually unbalanced like Credit Fraud Detection.

Before we discuss the findings, it is important to understand the metrics used to evaluate the models: Accuracy, Precision, Recall, and F1 score. The accuracy is an overall test of how good the model is. Precision indicates the proportion of true positive predictions out of all positive predictions. Recall measures the proportion of true positives out of actual positives. The F1 Score is the balanced measure of precision and recall. 

DATA ANALYSIS FINDINGS:

Several models were evaluated based on their accuracy, precision, and recall, which are essential metrics in the context of fraud detection. The first model was a baseline model, and we chose Logistic Regression for its simplicity and interpretability. It achieved an accuracy of 0.9340, with a strong precision of 0.97 for identifying fraudulent transactions. However, its recall of 0.87 indicated that some fraudulent cases were missed, which is a critical consideration in fraud detection. Next, we examined the Random Forest model, which provided an accuracy of 0.9289. While it exhibited high precision, its recall was similarly affected, with some fraudulent transactions going undetected. The Improved Random Forest model had comparable performance, also achieving an accuracy of 0.9289. Although it maintained high precision, it showed a slight decrease in recall, further limiting its effectiveness in capturing all instances of fraud. The XGBoost model demonstrated strong performance, matching the accuracy of the Logistic Regression model at 0.9340. Its precision and recall were balanced, making it a solid option for fraud detection.


COMPARING MODELS:

