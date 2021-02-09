# EmployeeAttrition_With_Pyspark
![Pyspark](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/employee_attrition.png)

## Business Understanding
#### Project Goal:
The Goal of this project is to predict the Employees of a company that are most likely to leave the company by using the Pyspark.
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

## Categorical and Continious variables:
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

## Continious variables:
![continious](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/continious.png)

* There is a linear relationship between ToralWorkingYears and years at comapny, Years with Current Manager, Years since last promotion, years in current role.
* The Attrition also has linear relation ship with above continious features.



## Feature Engineering

![Correlation](https://github.com/PurushothamVadde/EmployeeAttrition_With_Pyspark/blob/main/images/corelation.png)

## Modeling and Performance Tuning

## Model Evaluation

## Conclusion
