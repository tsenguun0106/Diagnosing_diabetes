# Diabetes prediction analysis
In this project, I implemented the diabetes diagnosis prediction machine learning model based on individual's various characteristics. 

## Part 1. Data cleaning and transformation

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

I conducted the exploratory data analysis for the following variables: upper blood pressure, lower blood pressure, alcohol consumption, smoking, weight, glucose level, and phisycal activity. I used the box plot for upper and lower blood pressures. Diabetic people tend to have higher upper and lower blood pressures. For alcohol and smoking, diabetic people have slightly higher rates for alcohol consumption and smoking compared with non-diabetic people. 

Visualization for weight distribution across diabetic and non-diabetic people indicates that diabetic people tend to have higher weights  relative to non-diabetic people. Moreover, visulation for glucose level distribution demonstrates that diabetic people have higher glucose level in average than non-diabetic people. Furthermore, physical activity visualization showed that non-diabetic people are more physically active than non-diabetic people in average. 

## Part 3. Machine learning model building for diabetes diagnosis

1. Logistic regression model: \
I built the logistic regression model as the first machine learning model. Target variable is the dummy variable indicating diabetic or non-diabetic. Regressors or explanatory variables are smoking, alcohol consumption, upper blood pressure, lower blood pressure, cholesterol level, glucose level, height, gender, age, and weight. 

2. Random Forest Classifier model: \
I used the Random Forest Classifier model as the second machine learning model for diagnosing the diabetes. Target variable is the dummy variable indicating diabetic or non-diabetic. Regressors or explanatory variables are smoking, alcohol consumption, upper blood pressure, lower blood pressure, cholesterol level, glucose level, height, gender, age, and weight. Max depth of each tree in the forest is 19 and random state seed value is 0. Furthermore, I plotted the feature importances for explanatory variables from this Random Forest Classifier model. The model indicated that glucose level, age, weight, physical activity, lower blood pressure, upper blood pressure, and gender are important variables in diagnosing the diabetes. 
