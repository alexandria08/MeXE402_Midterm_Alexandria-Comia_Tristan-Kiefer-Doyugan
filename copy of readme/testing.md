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
- **Independent Variable**: 'Age', BusinessTravel', 'DailyRate', 'Department',
       'DistanceFromHome', 'Education', 'EducationField', 'EmployeeCount',
       'EmployeeNumber', 'EnvironmentSatisfaction', 'Gender', 'HourlyRate',
       'JobInvolvement', 'JobLevel', 'JobRole', 'JobSatisfaction',
       'MaritalStatus', 'MonthlyIncome', 'MonthlyRate', 'NumCompaniesWorked',
       'Over18', 'OverTime', 'PercentSalaryHike', 'PerformanceRating',
       'RelationshipSatisfaction', 'StandardHours', 'StockOptionLevel',
       'TotalWorkingYears', 'TrainingTimesLastYear', 'WorkLifeBalance',
       'YearsAtCompany', 'YearsInCurrentRole', 'YearsSinceLastPromotion',
       'YearsWithCurrManager'

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

   ![dtypes](https://github.com/user-attachments/assets/557efbf9-a12e-4c6c-a243-c5c457185605)

#### Converting Categorical Data
Converting categorical data is an essential step in preparing your dataset for analysis or modeling, especially for machine learning algorithms that require numerical input. 

- **Label Encoding**: I used label encoding to convert the *salary* variable into numerical data, as it is an ordinal variable.

  ![salary](https://github.com/user-attachments/assets/c34f438b-5b6a-4c02-8085-58e57cad8b8a)

     After converting the salary data into numerical values, the values became integers, so I changed the data type from integer to float.

  ![int to float](https://github.com/user-attachments/assets/71e3333c-3a51-4b88-9f05-932f45b434f3)

- **One-Hot Encoding**: I used one-hot encoding to convert the *dept* variable into numerical data, as it is a nominal variable.

  ![hot encoding](https://github.com/user-attachments/assets/136f38ae-fef3-4565-9b6f-ad91e065ee34)

    After converting the dept data into numerical values, the values became bool or binary, so I changed the data type from bool to float.

  ![bool to float](https://github.com/user-attachments/assets/285acd92-7521-4c69-a28f-7b2415ba09c1)

#### Checking for NaN values
This code will help you identify which columns in the dataset have missing values and how many NaN values are present in each column.

  ![nan values](https://github.com/user-attachments/assets/5a276b6c-7613-4130-8a25-e1e550922271)

#### Handling Missing Values
After identifying missing values in the dataset, I use the mean of each respective column to fill any NaN values in specific columns of the dataset_encoded DataFrame.

  ![handle missing values](https://github.com/user-attachments/assets/00eaa29a-c499-497c-9560-492211d06627)

#### Rearranging Columns

## Logistic Regression

### Part 1 - Data Processing
#### Importing Dataset
   We begin by loading the dataset to begin the analysis and modeling process. This line imports the dataset, containing both demographic and job-related attributes, which will be analyzed to identify factors influencing employee attrition.
   
   ![nice](https://github.com/user-attachments/assets/9cf5d17c-8eb8-4430-8335-97949de1417b)

   Another thing to note is that this dataset is clean already, so that's less load for us to work on, hooray for that.
   
   ![yippee-happy](https://github.com/user-attachments/assets/10b55811-660f-4ca2-a61a-ba7a1f4cfcc0)

#### Encoding Binary Categorical Variables
   After importing the dataset, we convert the binary categorical variables (Attrition, Gender, and OverTime) into numeric format for model compatibility. By using *LabelEncoder*, it transforms these variables into binary numeric values (0 or 1). Encoding 'Attrition' is essential as it’s the target variable (dependent), indicating turnover likelihood. 'Gender' and 'OverTime' are independent variables related to demographics and job conditions, impacting attrition.

   ![niceu](https://github.com/user-attachments/assets/9cf5d17c-8eb8-4430-8335-97949de1417b)

#### One-Hot Encoding Non-Binary Categorical Variables
   To prevent ordinal misinterpretation, we encode multi-category categorical variables into a format suitable for logistic regression. One-Hot Encoding converts each unique category into a separate binary column, ensuring categories in BusinessTravel, Department, etc., are treated independently. Dropping the first category (drop_first=True) avoids multicollinearity in the model.

   ![Screenshot 2024-11-01 143637](https://github.com/user-attachments/assets/dfd78d2c-0bcc-49a4-bd2b-b4cc2c4a3a1b)

#### Dropping Non-Informative Columns
   Now, we remove columns that do not contribute meaningful information to attrition prediction. These columns (EmployeeNumber, Over18, StandardHours, EmployeeCount) are not directly related to demographic or job-related factors that might impact turnover, so dropping them reduces data noise and improves model clarity.

   ![Screenshot 2024-11-01 143733](https://github.com/user-attachments/assets/afaad33f-01fc-4496-ab59-1a4566901222)

#### Dataset Inspection
   After all of the things above, we now verify the dataset’s structure, types, and non-null values after preprocessing. This step checks that all variables are encoded properly and validates that columns contain expected data types, facilitating a smooth model training process.

   ![Screenshot 2024-11-01 143832](https://github.com/user-attachments/assets/9bff245b-4a89-4ecb-b253-e1685ff48b03)

   *dataset.head* displays the first 10 rows of the dataset to inspect data entries and also confirm preprocessing steps. This line provides a quick view of the dataset’s initial rows, making it easy to verify that data cleaning, encoding, and transformations (like removing unnecessary columns and encoding categorical variables) have been applied correctly. By reviewing the first few entries, you can confirm data types, assess data quality, and ensure that feature scaling and encoding were successful before proceeding to model training.

   ![Screenshot 2024-11-01 143858](https://github.com/user-attachments/assets/0a9c1cb4-d62c-4adf-8ab0-1eadc515cd3a)

#### Defining Features and Target Variable
   Proceeding with the separation of the dataset into independent variables (X) and the dependent variable (y) as 'Attrition' (dependent variable) indicates employee turnover, while the remaining columns in X include demographic and job-related factors that may influence attrition. Splitting these sets prepares the data for model training and evaluation.
   
   ![Screenshot 2024-11-01 144004](https://github.com/user-attachments/assets/9e7f80cb-2877-4a55-a31a-87f1f206c574)

#### Splitting the Dataset into Training and Test Sets
   After Defining Features and Target Variable, we now divide the data into training and test subsets for model development and validation. *train_test_split* splits the data, using 80% for training the model and 20% for testing. *random_state=0* ensures reproducibility, and an 80-20 split balances training model effectiveness with testing accuracy.

   ![Screenshot 2024-11-01 144004](https://github.com/user-attachments/assets/9e7f80cb-2877-4a55-a31a-87f1f206c574)

#### Scaling the Features
   We continue with standardizing the features to improve logistic regression model performance and ensure consistent scaling across training and test data. StandardScaler scales each feature to have a mean of 0 and a standard deviation of 1, which optimizes logistic regression by giving equal weight to each variable and improving model accuracy.

   ![Screenshot 2024-11-01 144448](https://github.com/user-attachments/assets/71bdf82c-4334-45e3-a988-b2b21c504a61)

#### Training the Logistic Regression Model
   On this part, we train the logistic regression model on the preprocessed training data. *LogisticRegression* learns from the relationships between independent variables (X_train) and the target (y_train). *random_state=0* ensures reproducibility, and logistic regression is chosen for its interpretability and suitability for binary classification tasks like predicting turnover probability.

   ![Screenshot 2024-11-01 144515](https://github.com/user-attachments/assets/6416eebc-80da-4517-bf9f-2676c900c175)

#### Making Predictions
   Here, we generate predictions for the test set, *X_test*, using the trained logistic regression model after scaling the data. This line first applies the StandardScaler transformation (sc.transform(X_test)) to ensure that the test data is scaled in the same way as the training data. The model then uses predict() to output predicted classes (0 for "No Attrition" and 1 for "Attrition") for each instance in the test set. This step is essential for evaluating model performance, as the predicted labels, y_pred, will be compared with the actual labels (y_test) to measure accuracy and other metrics, ensuring reliable assessment of the model's ability to generalize to new data.

   ![Screenshot 2024-11-01 144550](https://github.com/user-attachments/assets/a5ff537f-2591-4ec9-aded-001ebd14e298)

-   This line inspects the predicted labels for the test set. This line allows a quick view of the model’s predictions stored in y_pred, which can reveal the overall distribution of predicted classes (0s and 1s). Checking y_pred helps ensure that predictions align with the expected format before evaluating model performance and comparing with y_test.

   ![Screenshot 2024-11-01 144633](https://github.com/user-attachments/assets/57f1e122-5f34-4454-8736-51c7cab87f3b)



   
