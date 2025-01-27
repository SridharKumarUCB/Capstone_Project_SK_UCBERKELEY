# UC Berkeley Capstone Project By: Sridhar Kumar
(Jupyter Notebook Link: https://github.com/SridharKumarUCB/Capstone_Project_SK_UCBERKELEY/blob/main/DetectingCreditCardFraud_SridharKumar_UC_Berkeley.ipynb)

PROBLEM STATEMENT: 

The research goal is to develop a model to accurately predict fraudulent credit card transactions. 

Research Motivation: Financial fraud has significant negative economic impacts, affecting both businesses and consumers. If unanswered, businesses may face financial losses and damage to their reputations. While on the other hand, consumers could suffer from identity theft and financial insecurity. By predicting fraudulent transactions, our analysis will enable financial institutions to implement proactive measures, reduce fraud losses and enhance overall customer trust. More importantly, this analysis will allow stakeholders to understand risks and develop actionable strategies.

DATA UNDERSTANDING:

The first step was to understand the dataset and explore what information it contains, and how this could be used to inform better business understanding. The steps involved were:

1. Load Data
2. Preview Data
3. Assess the data
4. Check for null values
5. Exploratory Data Analysis (EDA)

The data was Sourced From Kaggle: (https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)

Brief Description of dataset: This dataset contains credit card transactions from September 2013 by European cardholders. It comprises transactions from two days, totaling 284,807 transactions with 492 identified as fraud. This dataset was noted as being a highly unbalanced dataset with fraudulent transactions only accounting for 0.172% of all transactions. In order to combat the imbalance in this dataset, we will use downsampling. This approach helps avoid potential bias in the model's learning. An imbalanced dataset may yield high accuracy for the model, but it will perform poorly in detecting fraud. This is primarily because it will be trained on data that is predominantly non-fraudulent.

We provided an example of a biased model using SVM (Support Vector Machine). The SVM model achieved a high accuracy of 99.93%, but this is very misleading because the dataset was not balanced. Looking at the confusion matrix, it correctly identified 77 out of the 98 fraudulent cases, but it also misclassified 21 fraud cases as non-fraudulent; this resulted in a recall of 79% for the minority class. Again, this test shows how crucial it is to balance datasets, especially for cases where the data is usually unbalanced like Credit Fraud Detection.

Before we discuss the findings, it is important to understand the metrics used to evaluate the models: Accuracy, Precision, Recall, and F1 score. The accuracy is an overall test of how good the model is. Precision indicates the proportion of true positive predictions out of all positive predictions. Recall measures the proportion of true positives out of actual positives. The F1 Score is the balanced measure of precision and recall. 


Things To Note:

Recall is a big concern in fraud detection because it indicates the model's ability to correctly identify fraudulent transactions. A model with low recall can lead to significant financial losses and increases the risk due to false negatives. In fraud detection, the cost of failing to catch a fraudulent case is much higher than misclassifying a legitimate transaction, making high recall crucial. Accuracy is a good measure of how effective a model is, though it is not the sole focus. While precision (accuracy of positive predictions) and the F1-score (balance of precision and recall) are important, it should be secondary to recall.

DATA ANALYSIS FINDINGS:

Several models were evaluated based on the essential metrics discussed above in the context of fraud detection. The first model was a baseline model, and we chose Logistic Regression for its simplicity and interpretability. It achieved an accuracy of 0.9340, with a strong precision of 0.97 for identifying fraudulent transactions. However, its recall of 0.87 meant that some fraudulent cases were being missed; this is an important factor in fraud detection. Next we examined the Random Forest model, which provided an accuracy of 0.9289. Though it had high precision, its recall was affected, with some fraudulent transactions going undetected. We then tried to improve this model. The improved Random Forest model had comparable performance, achieving an accuracy of 0.9289. It maintained a very high precision which was good, but it showed a slight decrease in recall; this further limits its effectiveness in capturing all instances of fraud. We then tests the XGBoost model. It matched the accuracy of the Logistic Regression model at 0.9340. Its precision and recall were balanced, making it a solid option for fraud detection. The final model tested was the LightGBM model. By far, the LightGBM model showed the most impressive performance. It achieved an accuracy of about 95%, and its confusion matrix showed that the model performed very well. The model had high precision and recall for both classes. To be specific, the precision values were 0.93 for Class 0 and 0.97 for Class 1, with F1-scores of 0.95 for each class. However, it is important to note that (some) warnings occurred during model training (related to the parameters min_data_in_leaf and min_child_samples). The warning seemed to indicate that the min_child_samples was being ignored due to its lower value, but we had difficulty resolving the warnings. Despite these warnings, the model's metrics remained consistent across multiple runs. Therefore, while acknowledging the warnings, we feel confident in the model's results.

COMPARING MODELS / CONCLUSION:

If the goal was to minimize false positives while also maintaining a good recall score, the Random forest model is a good choice. This is because it has very good precision. On the other hand, it is also important to realize that its lower recall, compared to the other models, may result in missing potential fraudulent transactions. 

If there was an increased focus on trying to maximize fraud detections, then LightGBM and XGBoost are great choices. This is specifically due to the fact that they achieve higher recall while also maintaining precision. It seems to be better at balancing the task of identifying fraud and minimizing potential false positives. 

Best Model: Since the research goal was to develop a model that accurately predicts fraudulent credit card transactions, the best model should be a model that balances precision and recall. The model that executed this the best was the LightGBM model. The main strengths of the model was its ability to reduce false positives while also capturing a large portion of fraudulent cases. This makes this model a great choice for practical deployment, aiding to the research motivation. The model also has a high accuracy (about 95%). Overall, the LightGBM model seems best in distinguishing between fraud and non-fraudulent transactions. Therefore, answering the research objective effectively. 

FUTURE WORK:

Some future work would definitely involve resolving the warning messages from the LightGBM model. It would also be worthwhile to look into ensemble techniques and see if that improves the metrics (maybe even combining LightGBM with neural networks). Taking a step back to the EDA process, a deeper dive into advanced feature engineering may prove worthwhile. Ultimately, these explorations could lead to a more powerful fraud detection system capable of adapting to evolving fraudulent behaviors.
