# EmployeeAttrition_With_Pyspark
![Pyspark](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/spark_python.png)

## Business Understanding
#### Project Goal:
The Goal of this project is to predict the Employees that are most likely to leave the company by using the Pyspark.
#### Practical use:
* By Understanding the possible Employee Attrtion the companies can plan the employee retension plans.
* By knowing factors are contributing the Employee Attrition the comapnies can change their work Culture.
* Better understanding of Impact on Productivity, impact on Profit.
* Planning of recruitment of new employees
* Better management of project/ Protfolios in the company.


## Data Understanding
The Employee DataFrame has schema as below:
 > |-- Age: integer (nullable = true)\
 > |-- Attrition: string (nullable = true)\
 > |-- BusinessTravel: string (nullable = true)\
 > |-- DailyRate: integer (nullable = true)\
 > |-- Department: string (nullable = true)\
 > |-- DistanceFromHome: integer (nullable = true)\
 > |-- Education: integer (nullable = true)\
 > |-- EducationField: string (nullable = true)\
 > |-- EmployeeCount: integer (nullable = true)\
 > |-- EmployeeNumber: integer (nullable = true)\
 > |-- EnvironmentSatisfaction: integer (nullable = true)\
 > |-- Gender: string (nullable = true)\
 > |-- HourlyRate: integer (nullable = true)\
 > |-- JobInvolvement: integer (nullable = true)\
 > |-- JobLevel: integer (nullable = true)\
 > |-- JobRole: string (nullable = true)\
 > |-- JobSatisfaction: integer (nullable = true)\
 > |-- MaritalStatus: string (nullable = true)\
 > |-- MonthlyIncome: integer (nullable = true)\
 > |-- MonthlyRate: integer (nullable = true)\
 > |-- NumCompaniesWorked: integer (nullable = true)\
 > |-- Over18: string (nullable = true)\
 > |-- OverTime: string (nullable = true)\
 > |-- PercentSalaryHike: integer (nullable = true)\
 > |-- PerformanceRating: integer (nullable = true)\
 > |-- RelationshipSatisfaction: integer (nullable = true)\
 > |-- StandardHours: integer (nullable = true)\
 > |-- StockOptionLevel: integer (nullable = true)\
 > |-- TotalWorkingYears: integer (nullable = true)\
 > |-- TrainingTimesLastYear: integer (nullable = true)\
 > |-- WorkLifeBalance: integer (nullable = true)\
 > |-- YearsAtCompany: integer (nullable = true)\
 > |-- YearsInCurrentRole: integer (nullable = true)\
 > |-- YearsSinceLastPromotion: integer (nullable = true)\
 > |-- YearsWithCurrManager: integer (nullable = true)\

* There are *Zero* Missig values in the dataset
* we have 35 features inthe dataframe
* We 25 integer and 10 string type features.

## Exploratory Data Analysis
### Categorical Data:
![Categorical](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/Categorical.png)

#### Employee Attrtion Based on Overtime:
We can see that The Attrition rate is higher in the Employees that are working Overtime than employess not working on Overtime.
#### Employee Attrtion Based on Department:
The Attrition rate is higher in Sales and Research Deparments compare to the HR department
#### Employee Attrtion Based on Business Travel:
The Attrition rate is higher in the Employees that are travel frequently than other employees.
#### Employee Attrtion Based on MaritalStatus:
It is clear that the Attrition rate is high in single Employess and very less in Married Employees.
#### Employee Attrtion Based on JobSatisfaction:
The Attrition rate is high in JobSatisfaction level 1 and level 3 compare to other levels.
#### Employee Attrtion Based on JobInvolvement:
The Attrition rate is high in JobInvolvement level 2 and level 3 compare to other levels.
#### Employee Attrtion Based on JobLevel:
The Attrition rate is high in JobLevel level 1 compare to other levels.
#### Employee Attrtion Based on StockOptionlevel:
The Attrition rate is high in StockOptionlevel level 0 compare to other levels.

## Continious variables:
![Categoricalandcontinious](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/continious_categorical.png)

#### Employee Attrtion Based on Department and Monthly Income:
The Attrition is high in Employees with low income compare to higher income in all departments and more in sales department.
#### Employee Attrtion Based on MaritalStatus and Monthly Income:
The Attrition is high in Employees with low income and Single compare to other employees.
#### Employee Attrtion Based on EducationField and Monthly Income:
The Attrtion is high in the Employees with low income in all departments and the income is high in lifesciences and medical Employees category.
#### Employee Attrtion Based on Gender and Monthly Income:
The Attrition rate is high in males Employees and the income also high in male Employees.
#### Employee Attrtion Based on Joblevel and Monthly Income:
The Attrition is high in level 1 and the income is low in level 1 as the level increases the attrion reduces and the income increases.
#### Employee Attrtion Based on OverTime and Monthly Income:
The Attrition is high in people doing overtime with low income.

## Feature Engineering:
* As Part of feature engineering we followed the below steps:
#### Removing Unwanted Features:
* In this step we removed the below unwanted features in the dataframe
  > ('EmployeeCount','EmployeeNumber','Over18','StandardHours')
#### StingIndexer
* The Categorical string features are converted into numercial by using the StingIndexer function
  > ("Attrition","BusinessTravel", "Department","EducationField",  "Gender", "JobRole", "MaritalStatus", "OverTime")

#### Correlation Matrix:
![Correlation](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/corelation.png)

* In the above plot we can see the correlation between all the features after converting all the features into numerical format.
* we can also see there is a linear relationship between ToralWorkingYears and years at comapny, Years with Current Manager, Years since last promotion, years in current role.



#### VectorAssembler

* Each record is converted into the Vector by using the VectorAssembler function.
* The features that are using to build the model are passed as input list to the function along with dataframe.
* below is the list of features that passed to the Vector Assembler function.

> ("Age","DailyRate", "DistanceFromHome", "Education", "EnvironmentSatisfaction", "HourlyRate", "JobInvolvement", "JobLevel", "JobSatisfaction","MonthlyIncome", "MonthlyRate", "NumCompaniesWorked","PercentSalaryHike", "PerformanceRating", "RelationshipSatisfaction","StockOptionLevel", "TotalWorkingYears", "TrainingTimesLastYear","WorkLifeBalance","YearsAtCompany","YearsInCurrentRole", "YearsSinceLastPromotion", "YearsWithCurrManager", "BusinessTravelIndex","DepartmentIndex", "EducationFieldIndex", "GenderIndex", "JobRoleIndex", "MaritalStatusIndex", "OverTimeIndex")

#### Standard Scalar
* The Vectorized features are passed as input to the Standard scalar function so that all the features are scaled at same scale.
* The feature vectors after feature engineering as displayed as below.
![features](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/features.png)

## Modeling and Evaluation:
### Classification models:
By predicting the Employee Attrition using the Classification models and error evaluation metric as Accuracy with **ParamGridBuilder()** i got Accuracy for each model as below.
#### Logistic Regression
* The Accuracy for Train Data is 0.882075
* The Accuracy for Test Data is 0.875610
* The Tuning params For best Model in Logistic Regression is {'ElasticNetParam': 0.0, 'RegParam': 0.0, 'MaxIter': 200}
#### Decision Trees
* The Accuracy for Train Data is 0.871698
* The Accuracy for Test Data is 0.848780
* The Tuning params For best Model in DecisionTrees is {'MaxBins': 60, 'MaxDepth': 4, 'Impurity': 'entropy'}
#### Random Forest
* The Accuracy for Train Data is 0.892453
* The Accuracy for Test Data is 0.865854
* The Tuning params For best Model in RandomForest is {'MaxBins': 5, 'MaxDepth': 6, 'Trees': 200}
#### Gradient Boost Trees
* The Accuracy for Train Data is 0.934906
* The Accuracy for Test Data is 0.873171
* The Tuning params For best Model in GradientBoostTrees is {'MaxBins': 10, 'MaxDepth': 4, 'MaxIterations': 20}

|     Model               | Train Accuracy  | Tuning Parameters                                         |   Test Accuracy  |
| :---------------------- | :---------------| :-------------------------------------------------------- | :----------------|
| Logistic_Regression     | 0.882075        | {'ElasticNetParam': 0.0, 'RegParam': 0.0, 'MaxIter': 200} | **0.875610**     |
| DecisionTrees           | 0.871698        | {'MaxBins': 60, 'MaxDepth': 4, 'Impurity': 'entropy'}     |   0.848780       |
| RandomForest            | 0.892453        | {'MaxBins': 5, 'MaxDepth': 6, 'Trees': 200}               |   0.865854       |
| Gradient Boost Trees    | 0.934906        | {'MaxBins': 10, 'MaxDepth': 4, 'MaxIterations': 20}       | **0.873171**     |

From the all classification model we got the better Accuracy with the **Logistic Regression** and **Gradient Boost Trees**.

## Conclusion

By Using the above Classification Algorithms we are able to predict the Employee Attrition with 0.875 Accuracy.
By this project the companies can plan below operations in better way which will increase the profit and reduce the Employee Dependencies in a company.
* Better understanding of Impact on Productivity, impact on Profit and plan the employee retension plans.
* Planning of recruitment of new employees
* Better management of project/ Protfolios in the company.
