# machine_learning_project-supervised-learning

## Project Outcomes
- Supervised Learning: use supervised learning techniques to build a machine learning model that can predict whether a patient has diabetes or not, based on certain diagnostic measurements.The project involves three main parts: exploratory data analysis, preprocessing and feature engineering, and training a machine learning model. 

### Project Description:
In this projects, you will apply supervised learning techniques to a real-world data set and use data visualization tools to communicate the insights gained from the analysis.

The data set for this project is the "Diabetes" dataset from the National Institute of Diabetes and Digestive and Kidney Diseases 
The project will involve the following tasks:

-	Exploratory data analysis and pre-processing: We will import and clean the data sets, analyze and visualize the relationships between the different variables, handle missing values and outliers, and perform feature engineering as needed.
-	Supervised learning: We will use the Diabetes dataset to build a machine learning model that can predict whether a patient has diabetes or not, using appropriate evaluation metrics such as accuracy, precision, recall, F1-score, and ROC-AUC. We will select at least two models, including one ensemble model, and compare their performance.

The ultimate goal of the project is to gain insights from the data sets and communicate these insights to stakeholders using appropriate visualizations and metrics to make informed decisions based on the business questions asked."

## Process

### EDA and Preprocessing

I am repeatedly surprised with how much time I spend on this part of the projects. 

For the diabetes data set the biggest hurdle was dealing with the missing values. There were many zeros in the 'Glucose', 'Blood Pressure', 'Skin Thickness', 'Insulin' and 'BMI' columns. While it is possible to have zero pregnancies and there are technically people that are unable to produce insulin, the other columns should not have any zeros in them. With regards to the Insulin Column, almost half of the values were zero, which does not seem accurate. 

I spent a lot of time researching the original data and consulting my nursing resources in order to make sense of the distribution of the numbers. I removed rows that had 3 or more 0 values, in hopes that this would substantially reduce the numbers I had to deal with. It did not. Without having legitimate original data to go off of, I decided to replace the remaining zero values with the means of the columns grouped by age.

Very few outliers in the Insulin column were removed. Because of the density of most of the outliers and the lack of information on the data source, the remainder were dealt with through the use of the Robust Scaler.

### Model Training

Three separate models were utilized for training this data. Each model was evaluated with and Accuracy score, f1 score and AUC score. The first model was a Logistic Regression model with a Randomised Search. The second was a Random Forest Classifier with a Randomized Search and the third was the Voting Classifier, utilizing the Decision Tree, K Neighbors, GaussianNB and Logistic Regression Models. The outcomes were as followed.

Logistic Regression:      
- Accuracy: 0.7631578947368421 
- F1 Score: 0.6493506493506493 
- AUC Score: 0.8368794326241135

Random Forest Classifier: 
- Accuracy: 0.7324561403508771 
- F1 Score: 0.6347305389221558 
- AUC Score: 0.7900057063666748

Voting Classifier:        
- Accuracy: 0.7543859649122807 
- F1 Score: 0.6666666666666666
- AUC Score: 0.8143800440205429

### Conclusion

While I was hoping for some drastic exciting differences in the numbers between the different models, I was a bit disappointed with how marginal the differences in the scores were.

I was surprised to see the Logistic Regression model do better than the emsembles. Logistic regression had the lowest validation error and showed consistency between training and testing. It had the highest values in both the Accuracy score and the AUC score.

With more experience, I think some additional parameter tweaking could be done in order to obtain better results.