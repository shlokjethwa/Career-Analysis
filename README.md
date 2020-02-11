# Career-Analysis
This project predicts mid-career salary of college students after graduation. 
Introduction
As current students of the Information Systems program, and with diverse backgrounds, the main problem that a student faces is to decide in which direction should he/she forward his/her career. This is due to the reason that many of us have done an undergraduate in business, the software side, the electrical side, etc. Therefore this project will help them to anticipate what kind of work pays the most amount of money (P.S Money is very important :-P). This project will show the different kinds of salaries by college attended, program majored and even the region of living. In a nutshell, a student can decide their career plan based on our project.

Questions of Interest

What are the benefits of studying in the Ivy League as compared to other universities?

Which region has the best starting salary in the U.S at graduation and mid-career?

What are the salary figures of students from different universities ten years down the line?

What are the school rankings based on salaries now and even ten years after graduation?

What are the majors that offer the most salary increase in the coming years after graduation?

What are the significant factors that affect mid-career salary and how significant are they?

1. Tyding Data
Read csv file we need and install basic packages
Data source: https://www.kaggle.com/wsj/college-salaries#salaries-by-college-type.csv

Package Installation. Major packages we used in this project is pandas and matplotlib.

We first read data in pandas dataframe and then cast string data from object to string and numeric data to float for further analysis and modification.
Clean data
After reading in data, we need to do a further cleaning to make our data more readable and manipulatable.

2. Exploratary Data Analysis and Data Visualization
2.1 Analysis about types and regions of school
First, we are going to start our analysis with different types of universities. We choose to use mean value of data to represent the average level of categories.

Tidying data for the following analysis
Because latitide and longitude of schools are needed in the following analysis, we decide to extract them at first. As a result, we can improve the analysis corresponsding to regions further.

2.2 Further analysis about regions and school types
After seperate analysis about regions and types of universities, we are curious about the comprehensive effect of the two factors, so we are going to combine them to make a deeper analysis.

Create a new variable 'Increasing rate' to reveal the potential career developing ability.
2.3 Analysis about majors
Since major-choosing is more subjective and isolated from regions and type of schools, we decide to analyze major seperately.
2.4 Visualization using mapbox
For guiding graduates more directly, we use mapbox to create a 'salary map' as a guide to show them which regions have a better developing chance.
3. Regression Model and Hypothesis testing
Null Hypothesis
We are looking at the impacts of:

The salary of mid-career.

Null Hypothesis: None of starting salary, region and school type and student's SAT score have noticeable impacts on the mid-career salary.
To test the null hypothesis, we will perform a Multiple Linear Regression on our dataset by using scikit-learn.

We will use our tidied datasets for the features and the target.

Features: Mid-career salary Target: dependent variables.

Since region and school type are categorical variables, we will create dummy variable for both variabls. To achieve that, we used pd.get_dummies() in this case.

After setting up the data, we will set up X and Y for our use in scikit-learn LinearRegression() function. Then, fit the model.

We want to observe more about this result by p-values, t-values, and std-err. Then, we need Ordinary Least Squares Regression model.
4. Prediction and Machine Learning
Here we will split up the dataset into training and testing data for both variables. The percentage of Test/train split depends on different programmer. For our data, we will use 20% of the data for testing purpose and 80% for training purposes. We will generate mutiple linear regression model using the training data first. Then, we will make the predictions for the testing data. After that, we will compare the predictions with the actual results (Y_test).
From two plots above, we obviously observe that our model predicted the mid-career salary very well for the testing dataset. Our model also provides a score of the actual accuracy (1 is perfect), and our accuracy is around 0.88, which is a consideratable high accuracy score for the model.
