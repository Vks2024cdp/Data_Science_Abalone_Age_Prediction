# Data_Science_Abalone_Age_Prediction

## Introduction
This project aims to predict the age of abalone using physical measurements from the Abalone dataset. 

I implemented two regression models:
  * K-Nearest Neighbors (KNN) Regression
  * Linear Regression

I also explored the correlation between features and age to evaluate the strength of predictors.
  
## Objective:
The primary objectives of this project is to:
  * Download and load the Abalone dataset.
  * Perform basic exploratory data analysis.
  * Preprocess categorical features for regression modeling.
  * Build and train a linear regression model.
  * Evaluate the performance of your models using a suitable metric.
  * Understand the basic principles of KNN and or linear regression.

By systematically collecting and analyzing this data, the project aims to provide valuable insights for consumers looking to maximize savings during the Hari Raya promotional period, while also demonstrating effective web scraping techniques for retail price comparison.

## Dataset Description
The dataset contains physical measurements of abalone and includes the following features:

## Feature	Description
  * Sex: M (Male), F (Female), I (Infant)
  * Length: Longest shell measurement (mm)
  * Diameter: Perpendicular to length (mm)
  * Height: With meat in shell (mm)
  * Whole weight: Whole abalone (grams)
  * Shucked weight: Weight of meat (grams)
  * Viscera weight: Gut weight after bleeding (grams)
  * Shell weight: After being dried (grams)
  * Rings: Number of rings (our target variable)

## Tools & Libraries
  * Python 3.x
  * Pandas
  * NumPy
  * Seaborn
  * Matplotlib
  * Scikit-learn

## Steps Performed
### 1. Load and Prepare the Data
* Downloaded the Abalone dataset from the UCI Machine Learning
Repository. Link: https://archive.ics.uci.edu/ml/datasets/abalone
* Loaded the abalone.data file into a Pandas DataFrame.
* Added column headers manually.
* Derived the Age column using the formula: Age = Rings + 1.5.

### 2. Data Exploration
* Inspected the data using .head(), .info(), and .describe().
* Checked for missing values or anomalies.

### 3. Data Preprocessing
* Encoded the categorical Sex column using one-hot encoding (Sex_M, Sex_F, Sex_I)
* Ensured all features were numeric for modeling.

### 4. Correlation Analysis
Created a correlation heatmap to assess how strongly each feature relates to Age.
Found that:
* Length, Diameter, Shell weight and Whole weight had moderate positive correlation with Age.
* Sex had a strong negative correlation with Age.
![VKS - Correlation Analysis](/Data/Correlation_heatmap.png)

### 5. Feature Selection
* Considered removing weak or highly correlated features (e.g., Sex_* columns, highly multicollinear variables like Length, Diameter, Height) for model simplicity.
* Tried both full feature set and reduced feature set to compare model performance.

### 6. Modeling
* K-Nearest Neighbors (KNN) Regression
  ** Used KNeighborsRegressor from sklearn.
  ** Set k=3 (neighbors).
  ** Trained and tested the model using an 80-20 train-test split.

* Linear Regression
  ** Used LinearRegression from sklearn.
  ** Evaluated on the same train-test split for comparison.

## Evaluation Metrics
  I used the following metrics:
  * Root Mean Squared Error (RMSE)
  * R² Score
  * Lower RMSE and higher R² indicate better model performance.

## Key Findings
* Shell weight, Whole weight, and Length were strong predictors of abalone age.
* The Sex variable did not contribute significantly and could be excluded for simpler models.
* Linear Regression may suffer from multicollinearity due to highly correlated features like Length, Diameter, and Height.
* KNN worked well but may be sensitive to feature scaling (standardization recommended).

