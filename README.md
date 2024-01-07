# WQD7005AA
Alternative Assessment 1
The objective of this assignment is to use tools such as SAS e-miner on a e-commerce business dataset to obtain insights and information that can improve satisfaction level of customers.
Two tools are used in this assessment, the first behind SAS e-miner. Sas e-miner is used to perform the application of the decision tree model, bagging with random forest model, and boosting with gradient boosting algorithm. The second tool used is talend preparation, it is used to handle missing values in the dataset so that it is ready to be imported in to SAS e-miner.
The dataset used can be obtain from Kaggle. https://www.kaggle.com/datasets/uom190346a/e-commerce-customer-behavior-dataset?resource=download&select=E-commerce+Customer+Behavior+-+Sheet1.csv


![image](https://github.com/BryanLohKZ/WQD7005AA/assets/155895491/878e4cf4-82bb-4461-b18a-f115b983267c) 
Figure 1 SAS Diagram

The first step is to import the dataset into SAS enterprise miner, it is done using the file import node. 
![image](https://github.com/BryanLohKZ/WQD7005AA/assets/155895491/5a817e20-21cd-4d6b-8059-e911fb2044d6) 
Figure 2 Dataset variables

Above are the variables of the dataset that has been imported into SAS, the variables roles of Customer_ID is change to ID as it is a identifier, and the Satisfaction_level is changed to Target as it is our target variable when applying the decision tree later.

![image](https://github.com/BryanLohKZ/WQD7005AA/assets/155895491/72a8c2af-988f-42e5-ad32-2e66b2852e8e) 

Figure 3 Talend Prep 1

![image](https://github.com/BryanLohKZ/WQD7005AA/assets/155895491/da5fcaec-38df-4ef7-b46e-693c6b255167)    

Figure 4 Talend Prep 2
Before applying the decision tree, missing values are checked. Talend Prep is used to check for missing values, and there are 2 missing values that are found in the satisfaction level column, the 2 rows are then deleted.

![image](https://github.com/BryanLohKZ/WQD7005AA/assets/155895491/14a7015b-d378-43a9-9958-c99bb22fda50) 

Figure 5 Data Partitioning
Before applying the decision tree node, a data partition node is used to partition the dataset and prepare it for the model. The data is split into 70% training, 15% validation, and 15% test. The partitioning method is simple random with a random seed of 12345.
 
Figure 6 Decision Tree Result
 
Figure 7 Decision Tree Train
From the figure above, the decision tree model seems to be predicting the target variable perfectly with 0 false positive and negative.
 
Figure 8 Variable Importance
 
Figure 9 Decision Tree
The figure above is the decision tree map. The map shows us that Customers and Miami, and Chicago has 100% unsatisfied level. Therefore, to improve the satisfaction level, the business owner should investigate the shops in those areas to figure out what is wrong. Going down the map we can see that when customers buy more or equal to 12.5 items, they are satisfied while customers that bought less than 12 have a neutral stance. This information could be used to improve the neutral stance to a satisfied stance if more data is acquired.
 
Figure 10 Random Forest Results
 
Figure 11 RFM Misclassification rate
The Random Forest algorithm is the ensemble method used to demonstrate bagging. The figure above shows the misclassification rate of out of bag, as more trees are created, the misclassification rate decreases. 
 
Figure 12 Fit Statistic of RFM
 
Figure 13 Gradient Boosting Results
The gradient boosting ensemble method is used to strengthen the model by reiterating weaker models such as decision trees to create a stronger predictive strength. However, in this case the decision tree used has already given us a satisfactory result. 
 
Figure 14 Fit Statistic Gradient Boosting

    
Figure 15Gradient boosting Error vs Iteration
