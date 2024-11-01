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
      - 
## Methodology for Linear Regression

## Part 1 - Data Processing

### Importing Dataset
   To import the dataset, I uploaded my CSV file, used the pandas library to handle data as a DataFrame, and applied the pd.read_csv() function to read the file. This function loads the data into a structured format, converting it into a pandas DataFrame for easy data manipulation and analysis.

   ![import again](https://github.com/user-attachments/assets/9cf5d17c-8eb8-4430-8335-97949de1417b)

### Rearranging Columns
   Reorder the dataset so that the dependent variable, satisfaction_level, is the last column. Then, use dataset_reordered.head() to display the rows and columns of the dataset, confirming it has been loaded correctly and allowing you to preview the data.

   ![moving](https://github.com/user-attachments/assets/9ec9c908-d036-45dc-aa81-31e7ecc02576)

### Checking Data Types
Each column in a DataFrame can have a different data type, which affects how you can manipulate and analyze the data. In this dataset, there are two common data types: object (typically used for string data) and float (used for numeric data).

   ![dtypes](https://github.com/user-attachments/assets/557efbf9-a12e-4c6c-a243-c5c457185605)

### Converting Categorical Data
Converting categorical data is an essential step in preparing your dataset for analysis or modeling, especially for machine learning algorithms that require numerical input. 

- **Label Encoding**: I used label encoding to convert the *salary* variable into numerical data, as it is an ordinal variable.

  ![salary](https://github.com/user-attachments/assets/c34f438b-5b6a-4c02-8085-58e57cad8b8a)

     After converting the salary data into numerical values, the values became integers, so I changed the data type from integer to float.

  ![int to float](https://github.com/user-attachments/assets/71e3333c-3a51-4b88-9f05-932f45b434f3)

- **One-Hot Encoding**: I used one-hot encoding to convert the *dept* variable into numerical data, as it is a nominal variable.

  ![hot encoding](https://github.com/user-attachments/assets/136f38ae-fef3-4565-9b6f-ad91e065ee34)

    After converting the dept data into numerical values, the values became bool or binary, so I changed the data type from bool to float.

  ![bool to float](https://github.com/user-attachments/assets/285acd92-7521-4c69-a28f-7b2415ba09c1)

### Rearranging Columns
After performing one-hot encoding, the dependent variable is not positioned as the last column. Therefore, I rearranged the columns to move the dependent variable, satisfaction_level, to the last column.

  ![hot move](https://github.com/user-attachments/assets/f4298b3a-7006-4fe5-8987-83067fc0f938)

### Checking for NaN values
This code will help you identify which columns in the dataset have missing values and how many NaN values are present in each column.

  ![nan values](https://github.com/user-attachments/assets/5a276b6c-7613-4130-8a25-e1e550922271)

### Handling Missing Values
After identifying missing values in the dataset, I use the mean of each respective column to fill any NaN values in specific columns of the dataset_encoded DataFrame.

  ![handle missing values](https://github.com/user-attachments/assets/00eaa29a-c499-497c-9560-492211d06627)

### Checking for Duplicates
Checking for duplicates is a critical part of the data cleaning process to ensure high-quality, reliable data for analysis or modeling.

  ![duplicates](https://github.com/user-attachments/assets/bf6a3171-a9b2-4f67-853a-33ffa3f629ad)

### Removing Duplicates
 After checking, I found that the dataset contained 787 duplicate entries. I removed these duplicates to enhance the quality and reliability of the data.

  ![removing duplicates](https://github.com/user-attachments/assets/925aba8f-2abc-40c4-bc07-17591f2983df)

### Getting the inputs and outputs
  This method from the pandas library is to select specific rows and columns from a DataFrame.

- **X for independent variables**
The code extracting a subset of the dataset_cleaned DataFrame that includes all rows and all columns except the first and the last.

- **y for dependent variable**
The code extracts all values from the last column of the cleaned dataset and stores them in the variable y.
  

## Methodology for Logistic Regression
