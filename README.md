# Data-Science-Project---Analysis-of-life-ladder-using-various-regression-model

# SC1015 Mini Project

## About

This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which focuses on the World Happiness Report. 

Our group was interested in Singapore's happiness score of 6.4, which was the highest amongst our immediate regional neighbours.

We wanted to abstract and utilise the important factors that affect a country's happiness score and use them to predict future data by training a model.
  
## Contributors

School of Computer Science and Engineering \
Nanyang Technological University \
Lab: DFS 2 \
Group: 3

Members: 
1. Darren Choo ([@Darren-choo](https://github.com/Darren-choo))
2. Cheong Jin Hui ([@jinhui18](https://github.com/jinhui18))
3. Darren Wong ([@darrenwwx](https://github.com/darrenwwx))

## Table of Contents:
1. [Problem Formulation](#Problem-Formulation)
2. [Regression models and Cross-validation techniques used](#Regression-models-and-Cross-validation-techniques-used)
3. [Data Preparation and Cleaning](#Data-Preparation-and-Cleaning)
4. [Exploratory Data Analysis](#Exploratory-Data-Analysis)
5. [Machine Learning](#Machine-Learning)
6. [Data Driven Insights and recommendations](#Data-Driven-Insights-and-recommendations)
7. [Key Learning Points](#Key-Learning-Points)
8. [References](#References)

## Problem Formulation
- To find out what variables are the most important in predicting life ladder (The rankings of national happiness are based on the ladder score).
- To build a model that best predicts the life ladder of different countries considering various regression models.

## Regression models and Cross-validation techniques used

###  Regression models
- Multivariate Linear Regression 
- Random Forest Regression
- eXtreme Gradient Boosting Regression

### Cross-validation techniques
- Hold-out cross-validation
- K-fold cross-validation

## Data Preparation and Cleaning
In this section, we prepared and cleaned the dataset to help us retrieve variables that are useful for our project.

Carried out the following tasks:

- **Identifying** irrelevant and relevant variables in our dataset. 
- **Visualised** missing data using the missingno Library.
- **Dropping** variables with more than 60% of missing data and irrelevant variables according to our research. 10 variables were dropped.
- **Filled** up the rest of the variables with missing data the **median** value.


## Exploratory Data Analysis
In this section, we went on to analysed the relationship of the remaining variables with life ladder.

Carried out the following tasks:
- Analysed the correlation between the variables and Life Ladder.
  - Identified the variables with high and low correlation with life ladder. 
  - We decide to include those variables with high correlation in our regression model to predict life ladder.
  - We identified 3 variables with an extremely weak correlation with life ladder and decide to look further into them to decide if we want to drop them.
- Compared explained variance between the three variables with low correlation using univariate linear regression.
  - The same 3 variables had the lowest explained variance values, thus we decided to drop them as them most likely had the least impact on life ladder.
- Analysed and Compared correlations before and after outlier removal.
  - Evaluated that removal of outliers worsened the relationship between our variables and life ladder.
  - Decided not to drop the outliers.
- Compared explained variance when using Holdout cross-validation and K-fold cross-validation. 
  - We decided to use k-fold CV as it's accuracy is better.

## Machine Learning

>|**Regression models**|**Hold-out cross validation**|**K-fold cross validation**|
>|---|---|---|
>|Multivariate Linear Regression| Explained Variance Score of **0.721** |Explained Variance Score of **0.753** |
>|Random Forest Regressor|Explained Variance Score of **0.863** |Explained Variance Score of **0.876** |
>|eXtreme Gradient Boosting Regression|Explained Variance Score of **0.791** |Explained Variance Score of **0.845** |
> ### Comparison of explained variance between the three models using k-fold CV
> ![alt text](https://github.com/Darren-Choo/SC1015-DataSci-AI_Python/blob/main/Images/Explained_Variance_models.png)
#### <br>

## Data Driven Insights and recommendations
- Random forest regression is the best model to predict life ladder across all the 3 models we used.
- Looking at the correlation and explained variance values of the variables in our dataset, we found the 3 most important variables in predicting life ladder.
  - Log GDP Per Capita
  - Social Support
  - Health Life Expectancy at birth
- Singapore should focus on improving these 3 components to achieve the highest increase in life ladder.

## Key Learning Points
- Handling datasets with missing and irrelevant data.
- Learnt new visualisation techniques like missingno library.
- Learnt to apply K-fold cross-validation to increase the accuracy of our models.
- Learnt new regression models like random forest and eXtreme gradient boosting regression.

## References
- https://worldhappiness.report/
- https://www.kaggle.com/code/javadzabihi/happiness-2017-visualization-prediction
- https://towardsdatascience.com/battle-of-the-ensemble-random-forest-vs-gradient-boosting-6fbfed14cb7
- https://machinelearningmastery.com/extreme-gradient-boosting-ensemble-in-python/
- https://machinelearningmastery.com/k-fold-cross-validation/
