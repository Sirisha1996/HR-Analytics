# HR-Analytics

Problem Statement:
1.	The main Objective of this project is to predict which employee is looking for job change 
2.	To predict the percentage of candidates leaving job and anticipate the pool required to fill these positions 
3.	Also, to analyze where HR team needs to improve candidate experience in organization to decrease the attrition rate of the company 
Business Case Study:

A large company named XYZ, employs, at any given point of time, around x employees. However, every year, around ~15% of its employees leave the company and need to be replaced with the talent pool available in the job market. The management believes that this level of attrition (employees leaving, either on their own or because they got fired) is bad for the company, because of the several reasons. Few are listed below 
•	The former employees’ projects get delayed, which makes it difficult to meet timelines, resulting in a reputation loss among consumers and partners
•	A sizeable department has to be maintained, for the purposes of recruiting new talent
•	More often than not, the new employees have to be trained for the job and/or given time to acclimatize themselves to the company
Hence, the management has contracted an HR analytics firm to understand what factors they should focus on, in order to curb attrition. In other words, they want to know what changes they should make to their workplace, in order to get most of their employees to stay. Also, they want to know which of these variables is most important and needs to be addressed right away.

Overview:

We are splitting the datasets as training and testing. We have analyzed, cleaned, and preprocessed the dataset. Performed classification using 4 models Logistic Regression, SVM, Random Forest, and XGBoost algorithms. Implemented hyper tuning parameters for Random Forest and Logistic Regression and implemented SMOTE. Performance is evaluated based on various parameters such as accuracy, precision, recall and ROC AUC Score.

We are building different machine learning models to predict if an employer is willing to stay or leave and the results thus obtained will be used by the management to understand what changes they should make to their workplace, in order to get most of their employees to stay.


Data Preprocessing:

  Dealing with the missing values:
	We kept categorical data where we can, as perhaps the fact that we do not have a company size or the company type could actually tell us something.
	Additionally, we will keep the null gender values as of these, 30% have a target of 1 in the dataset, so this could be a telling data point, even if we don't quite understand it yet.
	As a reminder: Target: 0 – Not looking for job change, 1 – Looking for a job change
