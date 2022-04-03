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
•	We kept categorical data where we can, as perhaps the fact that we do not have a company size or the company type could actually tell us something.
•	Additionally, we will keep the null gender values as of these, 30% have a target of 1 in the dataset, so this could be a telling data point, even if we don't quite understand it yet.
•	As a reminder: Target: 0 – Not looking for job change, 1 – Looking for a job change

Added a new category 'unknown' to replace Null values in the data for few categorical columns company_size, company_type, major_discipline and gender and then dropped the null values which has very less percentage. 
Dropped null values of the columns which has  missing values less than 5% from the total rows. (last_new_job,experience,enrolled_university,education level)
Dummy variables like (NA, Unknown ) are replaced for the null values whose missing values are more than 5% rather than going for mode or mean as this doesn’t give significance in taking mode in city , city development idex columns 

  Encoding Categorical Variables:
•	We have converted the categorical features 'city', 'gender', 'relevent_experience', 'enrolled_university', 'education_level', 'major_discipline'

From the below graphs we can infer the below insights:
•	The proportion of men who are not looking for a job change far exceeds the proportion of men who are looking for a job change
•	most candidates with relevant experience do not look for job changes in a large proportion
•	in the types of registered courses, most people are not registered for courses and are not willing to look for job changes
•	Most of these groups have a high degree of education 
•	The candidate's major is basically STEM. This shows that many people are not changing industries.
•	Among the groups that do not plan to change jobs, the number of their employer companies is basically between 50-500.
•	The proportion of unchanged jobs exceeds the proportion of changed jobs, and employees who have just joined the company for about a year are less willing to change jobs

We have an imbalanced dataset where there are  many more non job-seekers than job-seekers.
We note that most job-seekers are Male. This is not all that surprising as in this dataset Males make up the majority of the sample population.
What is more interesting though is the City Development Index (CDI) chart. There we see that there are two peaks for job-seekers. The peaks are at high and low CDI scores.
We can ponder why this might be; in high CDI areas perhaps, there are a lot of opportunities and therefore people feel encouraged to seek better roles.
Perhaps in lower CDI areas candidates want to improve their circumstances by searching for new jobs, maybe in new areas.
It is also interesting to see that job-seekers have changed job more often that non-job seekers within that past 1 year, and also those that have never looked for a job also seem to be ready for a new challenge.

ML Models Implementation:

Our problem is binary classification, so we have decided to implement four classification models. The classification has two phases, a training phase, and a testing phase. In the training phase, the classifier trains its model on a given dataset, and in the testing phase, it tests the classifier performance. Performance is evaluated based on various parameters such as accuracy, precision, recall and ROC AUC Score. 
Basic training of the model without hyper-parameter tuning:

Support Vector Machine (SVM / SVC):
Support Vector Machine (SVM) is a supervised machine learning algorithm that can be used for both classification or regression challenges. After giving an SVM model sets of labeled training data for each category, they’re able to categorize new data. We picked up SVM because it is more memory efficient and works relatively effectively when there is segregation between classes.

Decision Tree:
We picked this model as when compared to other algorithms it requires less effort for data preparation during pre-processing. It also doesn’t require any scaling of data.

Random Forest:
As the Random Forest Algorithm combines the output of multiple (randomly created) Decision Trees to generate the final output, we also opted for Random Forest. As it is more efficient when compared to decision trees.

Logistic Regression:
As the target variable is categorical in nature, we opted for the Logistic Regression model. This model helps in predicting the probability whether a given data entry belongs to the category numbered as “1”. Just like Linear regression assumes that the data follows a linear function, Logistic regression models the data using the sigmoid function. It has a good accuracy for many simple data sets and it performs well when the dataset is linearly separable and also it is very fast at classifying unknown records.

XGBoost:
It is an efficient implementation of the stochastic gradient boosting algorithm and offers a range of hyperparameters that give fine-grained control over the model training procedure.

By using SMOTE, which is Synthetic Minority Oversampling Technique, we have dramatically improved our results since the data has apparently balanced 
Our final Logistic Regression model performs well on all metrics, particularly recall which we used as comparison metric as this is a blended weight of accuracy and precision.   But without sacrificing performance in other metrics. With the highest recall & ROC AUC scores, this model would certainly be valuable for this HR department. It has the added advantage of being very quick to train, too.
The only downside with the model is that it often predicts that a person is looking for a new role even if they are not. However, on balance, this model should be is still worthy of selection.
Conclusion:
Finally, we performed several machine learning algorithms to try to predict whether or not someone would be a job seeker or not. We looked at:
•	SVM
•	Decision Trees
•	Random Forests
•	Logisitic Regression
•	XGBoost
we used SMOTE, and re-trained Logistics Regression & Random Forest models. The Logistic Regression model performed great and we would select this Model 

Decision Making :
This model (Logistic  Regression ) will perform well when deployed in the workflow of the organization as well as the real world applications for HR analytics 
Considering this as a HR problem, one way we can look at it is by reducing the number of false positives Because, the company might be interested in only those people who are switching the jobs, and in order to increase the retention rate of their employees, company might be incurring extra costs and increased expenditures by design various programs, sessions, events..etc to build up the morale of people switching jobs

