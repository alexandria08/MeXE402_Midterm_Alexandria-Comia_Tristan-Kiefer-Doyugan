# MeXE402_Midterm_Alexandria-Comia_Tristan-Kiefer-Doyugan

<div align="center">
 
# **Linear Regression and Logistic Regression**

</div>

## Introduction
<div align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Welcome to the basics of Linear and Logistic Regression! In this section, we’ll explore the fundamental concepts and applications of these two widely used regression techniques. 
</div>

- **Linear Regression**: Linear regression is a technique used to model the relationship between a continuous dependent variable and one or more independent variables. 

- **Logistic Regression**: Logistic regression is used for classification problems, where the dependent variable is categorical (often binary). It models the probability that a given input point belongs to a particular category.

## Dataset Description

### Linear Regression
- **Title**: Employee Satisfaction Analysis
- **Purpose**: This dataset aims to analyze factors that influence employee satisfaction, with a focus on understanding and predicting satisfaction levels based on various workplace-related attributes. 
- **Feature Names**:
  
<div align="center">
 
|**Features** |  |
| --------------- | --------------- |
| Emp ID    | Employee ID   |
|satisfaction_level    | Employee's self-reported job satisfaction level    |
| last_evaluation    | Employee's most recent performance evaluation score    |
| number_project    | Number of projects the employee is currently working on    |
| average_montly_hours    | Average number of hours worked per month by the employee    |
| time_spend_company    | Number of years the employee has spent with the company    |
| work_accident    | Indicates whether the employee has experienced a work accident    |
| promotion_last_5years    | Indicates whether the employee has received a promotion in the last 5 years    |
| dept    | The department or division in which the employee works    |
| salary    | Employee's salary level    |

</div>

- **Dependent Variable**: satisfaction_level
- **Independent Variable**: last_evaluation, number_project, average_montly_hours, work_accident, promotion_last_5years, dept, salary

### Logistic Regression
- **Title**: IBM HR Analytics Attrition Dataset
- **Purpose**: This dataset aims to analyze factors that influence employee attrition, focusing on understanding how various attributes affect an employee's likelihood to leave the organization.
- **Feature Names**:

  <div align="center">
 
|  |  |**Features**  |  |  |  
| --------------- | --------------- | --------------- | --------------- | --------------- |
| Age    | EducationField   | JobLevel  | Over18  | YearsWithCurrManager  |
| Attrition    | EmployeeCount    | JobRole  | OverTime  | TotalWorkingYears  |
| BusinessTravel    | EmployeeNumber    | JobSatisfaction  | PercentSalaryHike  | TrainingTimesLastYear  |
| DailyRate   | EnvironmentSatisfaction    | MaritalStatus  | PerformanceRating  | WorkLifeBalance  |
| Department    | Gender    | MonthlyIncome  | RelationshipSatisfaction  | YearsAtCompany  |
| DistanceFromHome    | HourlyRate    | MonthlyRate  | StandardHours  | YearsInCurrentRole  |
| Education    | JobInvolvement   | NumCompaniesWorked  | StockOptionLevel  | YearsSinceLastPromotion  |


</div>

- **Dependent Variable**: Attrition
- **Independent Variable**: BusinessTravel, Department, EducationField, Gender, JobRole, MaritalStatus, OverTime

## Project Objectives

The objective of this project is to analyze the factors influencing *employee satisfaction* and *employee attrition* within organizations, aiming to enhance overall organizational performance.

   1. **Employee Satisfaction Analysis (Linear Regression):**
      - Identify and quantify relationships between workplace attributes and employee satisfaction.
      - Develop a predictive model to estimate satisfaction levels based on variables
   2. **Employee Attrition Analysis (Logistic Regression):**
      - Analyze demographic and job-related factors affecting the likelihood of employee attrition.
      - Create a predictive model estimating the probability of turnover based on variables
## Methodology

## Linear Regression

### Part 1 - Data Processing
#### Importing Dataset
   To import the dataset, I uploaded my CSV file, used the pandas library to handle data as a DataFrame, and applied the pd.read_csv() function to read the file. This function loads the data into a structured format, converting it into a pandas DataFrame for easy data manipulation and analysis.

   ![import again](https://github.com/user-attachments/assets/9cf5d17c-8eb8-4430-8335-97949de1417b)

#### Rearranging Columns
   Reorder the dataset so that the dependent variable, satisfaction_level, is the last column. Then, use dataset_reordered.head() to display the rows and columns of the dataset, confirming it has been loaded correctly and allowing you to preview the data.

   ![moving](https://github.com/user-attachments/assets/9ec9c908-d036-45dc-aa81-31e7ecc02576)

#### Checking Data Types
Each column in a DataFrame can have a different data type, which affects how you can manipulate and analyze the data. In this dataset, there are two common data types: object (typically used for string data) and float (used for numeric data).

   


