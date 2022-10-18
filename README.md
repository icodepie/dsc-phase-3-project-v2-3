# **Overview**

This project analyzes SyriaTel Customer Churn dataset to explore if there are any predictable patterns with cutomer turnover.

# **Business Problem and Data**

SyriaTel is interested in reducing the amount of money lost due to customer turnover. This project seeks to analyze customer data and identify any patterns that lead to customer churn.

# **Data**

For this project I had SyriaTel's customer churn info, "./customer.csv". This data set contained 3 columns that were not necessary for analysis, these columns, "state", "area code", and "phone number". I used pipelines to create transform categorical columns using onehotencoder, "international plan" and "voice mail plan" changing "yes" to 1 and "no" to 0. I also used the same pipeline to scale all the numerical data. I also found the sum of all the charges and the sum of the churned customer charges to see how revenue was impacted.

# **Methods**

The final step in data cleaning was splitting the data using test train plit into feature and target dataframes.

# **Analysis**

For analysis I decided to use 3 models, logistic regression, KNN, and Random Forest Classifier. The steps for modeling went as follows, build a default model of each,run train scores on model,and compare train scores to validation scores. After doing this I decided to create synthetic data with SMOTE and run the models again using imbpipelines. Once running all three models I decided the best models to tune parameters on were logistic regression and rfc. Using gridsearch I used the best parameters on the smoted log model and came up with average prediction results. I then moved on to tuning my RFC Model using RandomSearchCV to save time on finding good params. I ran two searches and created two models picking the least overfit of the two. I ended up with very high training scores of .98 and cross val of .95. On the test scores I ended up with .95 and .93. This led me to choosing this as my final model. I then used this model to get the important features and make recommendations based on these features.

# **Evaluation and Conclusion**

After analyzing and evaluating the data set from Syria Tel we have 2 main recommendations:

Using our prediction models the SyriaTel can predict customers churning before they do and so that syria tell can reach out and offer the following

Offer more competitive day rate package to the customer

Offer a voicemail package to the customer

This would reduce the amount of churned customer which would optimize revenue without changing plans for non churning customers to maximize revenue.
