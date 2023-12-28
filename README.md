# Diabetes prediction analysis
In this project, I implemented the diabetes diagnosis prediction machine learning model based on an individual's various characteristics. 

**Problem statement:** Doctors need to diagnose diabetes based on an individual's characteristics such as blood pressure and cholesterol levels. Here, I create and train the ML model to automate this diabetes diagnosis process. 

## Part 1. Data cleaning and transformation

The following characteristics of an individual are provided in the data:

<img src="https://github.com/tsenguun0106/Diagnosing_diabetes/assets/60633314/a233f030-9611-40d9-94f7-5b3786f69672" width="350px">



<!---
### Variables:
1. id - identification number for the individual
2. cholesterol - cholesterol level
3. gluc - glucose level
4. smoke - dummy variable for smoking or not
5. alco - dummy variable for alcohol drinking or not
6. active - dummy variable for actively doing physical activities or not
7. pressure - upper and lower blood pressure measures
8. age - age of individual
9. height - height of individual
10. weight- weight of individual
11. gender - gender of individual
12. diabetes - dummy variable for whether an individual has diabetes or not
--->

### One-hot-encoding for categorical variables:
One-hot-encoding feature transformation is conducted for all categorical variables. 
One-hot-encoded categorical variables:
1. cholesterol - three labels: high, low, and medium
2. glucose - three labels: high, low, and medium \
To reduce the code repetition, I created the function which conducts one-hot-encoding transformation. 

### Upper and lower blood pressure measurements cleaning:
The format of upper and lower blood pressure measurements in the dataset is "120/80". The value before "/" is for the upper blood pressure measurement, and the value after "/" is for the lower blood pressure measurement. I separated this variable into two variables. The first variable indicates the upper blood pressure measurement, and the second variable demonstrates the lower blood pressure measurement. 


### Gender label cleaning:
Gender was labelled inconsistently. For female, it was labelled as "female" or "f". For male, it was labelled as "male" or "m". I labelled female only as "f", and labelled male only as "m". Then, I conducted the one-hot-encoding for this gender variable. 

### Age values cleaning:
Some of age values were measured in years, but other age values were measured in days. I transformed the age variable such that all age values are measured in years. 

### Missing value imputation for weight variable
Weight column in the dataset had many missing values. Dropping missing weight values will result in the significant reduction of sample size. Thus, I imputed missing values for the weight column in the dataset. The imputation method was to replace the missing values with the mean of non-missing weight values. 

## Part 2. Exploratory data analysis and visualization

I conducted the exploratory data analysis for the following variables: upper blood pressure, lower blood pressure, alcohol consumption, smoking, weight, glucose level, and phisycal activity. I used the box plot for upper and lower blood pressure levels. Diabetic people tend to have higher upper and lower blood pressure levels. 

<img src="https://github.com/tsenguun0106/Diagnosing_diabetes/assets/60633314/4f965302-b88d-4667-9ff1-9a0867500724" width="350px">

.

<img src="https://github.com/tsenguun0106/Diagnosing_diabetes/assets/60633314/b59434e6-ac00-466e-97f5-75e01f407c02" width="350px">

For alcohol and smoking, diabetic people have slightly higher rates of alcohol consumption and smoking compared with non-diabetic people. 

<img src="https://github.com/tsenguun0106/Diagnosing_diabetes/assets/60633314/6b337d64-db36-48ea-8da0-a4d0976fea1e" width="450px">

.

<img src="https://github.com/tsenguun0106/Diagnosing_diabetes/assets/60633314/b5e08891-7310-40ff-a72c-2aae68344467" width="350px">


Visualization for weight distribution across diabetic and non-diabetic people indicates that diabetic people tend to have higher weights  relative to non-diabetic people. Moreover, visualization for glucose level distribution demonstrates that diabetic people have higher glucose levels on average than non-diabetic people. Furthermore, physical activity visualization showed that non-diabetic people are more physically active than non-diabetic people on average. 

<img src="https://github.com/tsenguun0106/Diagnosing_diabetes/assets/60633314/acab9f73-fc86-4f56-a44c-994dd9f2f16c" width="300px">

The following chart demonstrates that diabetic people tends to be with higher levels of cholesterol compared with non-diabetic people. 

<img src="https://github.com/tsenguun0106/Diagnosing_diabetes/assets/60633314/5bdcf047-6b8c-4820-8713-1851100f233b" width="300px">


## Part 3. Machine learning model building for diabetes diagnosis

1. Logistic regression model:
I built the logistic regression model as the first machine learning model. Target variable is the dummy variable indicating diabetic or non-diabetic. Regressors or explanatory variables are smoking, alcohol consumption, upper blood pressure, lower blood pressure, cholesterol level, glucose level, height, gender, age, and weight. 

3. Random Forest Classifier model: 
I used the Random Forest Classifier model as the second machine learning model for diagnosing the diabetes. Target variable is the dummy variable indicating diabetic or non-diabetic. Regressors or explanatory variables are smoking, alcohol consumption, upper blood pressure, lower blood pressure, cholesterol level, glucose level, height, gender, age, and weight. Max depth of each tree in the forest is 19 and random state seed value is 0. Furthermore, I plotted the feature importances for explanatory variables from this Random Forest Classifier model. The model indicated that glucose level, age, weight, physical activity, lower blood pressure, upper blood pressure, and gender are important variables in diagnosing the diabetes. 
