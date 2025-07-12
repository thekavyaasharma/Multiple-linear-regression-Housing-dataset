# Multiple Linear Regression Model: Predicting House Prices 

This project focuses on predicting housing prices in the Delhi region using multiple linear regression models. The goal is to identify key factors influencing house prices and to build an accurate predictive model.

## Problem Statement

A real estate company in the Delhi region aims to optimize property sale prices by understanding the important factors that affect them. This involves:
* Identifying variables that significantly influence house prices (e.g., area, number of rooms, bathrooms, etc.).
* Developing a linear model to quantitatively relate house prices with these identified variables.
* Assessing the accuracy of the model in predicting house prices.

## Dataset

The dataset used is `Housing.csv`, containing various attributes of properties in the Delhi region. It includes both numerical and categorical features.

### Key Features:
The dataset includes features such as:
* `price`: The target variable, representing the sale price of the property.
* `area`: Size of the property.
* `bedrooms`: Number of bedrooms.
* `bathrooms`: Number of bathrooms.
* `stories`: Number of stories.
* `mainroad`: Proximity to a main road (Yes/No).
* `guestroom`: Presence of a guestroom (Yes/No).
* `basement`: Presence of a basement (Yes/No).
* `hotwaterheating`: Hot water heating availability (Yes/No).
* `airconditioning`: Air conditioning availability (Yes/No).
* `parking`: Number of parking spaces.
* `prefarea`: Whether it's a preferred area (Yes/No).
* `furnishingstatus`: Furnishing status (furnished, semi-furnished, unfurnished).

The dataset consists of 545 entries and 13 columns.

## Methodology

The project employs **Multiple Linear Regression** to model the relationship between house prices and various independent variables. Two primary approaches for feature selection have been explored: Manual Feature Elimination and Recursive Feature Elimination (RFE).

### What is Linear Regression?

Linear Regression is a statistical method used to model the relationship between a dependent variable (the one you want to predict) and one or more independent variables (the factors affecting the prediction). For simple linear regression (one independent variable), the relationship is represented as a straight line. For multiple linear regression, it models the relationship using a linear equation that combines multiple independent variables.

The general equation for a multiple linear regression model is:

$Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \beta_n X_n + \epsilon$

Where:
* $Y$: The dependent variable (e.g., house price).
* $\beta_0$: The Y-intercept (the value of Y when all X are 0).
* $\beta_1, \beta_2, ..., \beta_n$: The coefficients for each independent variable, representing the change in Y for a one-unit change in the respective X, holding other variables constant.
* $X_1, X_2, ..., X_n$: The independent variables (e.g., area, bedrooms, bathrooms).
* $\epsilon$: The error term, representing the unobserved factors affecting Y.

### Steps Involved:

1.  **Data Loading and Understanding**: Initial loading and exploration of the `Housing.csv` dataset, checking for null values and data types.
2.  **Exploratory Data Analysis (EDA)**: Visualizing numerical variables using scatter plots and pair plots, and categorical variables using box plots, to understand their distribution and relationship with the price.
3.  **Data Preprocessing**:
    * Converting categorical variables (e.g., `mainroad`, `furnishingstatus`) into numerical representations using mapping and creating dummy variables.
    * Splitting the data into training and testing sets (70% training, 30% testing).
    * Scaling numerical features using `MinMaxScaler` to bring them to a comparable scale.
4.  **Feature Selection**:
    * **Recursive Feature Elimination (RFE)**: Used to select the top 'n' features that are most relevant to predicting house prices.
    * **Manual Feature Elimination**: Involves iteratively building OLS models and eliminating features based on high p-values and VIF (Variance Inflation Factor) to ensure statistical significance and absence of multicollinearity.
5.  **Model Building**: Constructing the linear regression model using the selected features.
6.  **Model Evaluation**:
    * Calculating the R-squared value to assess how well the model explains the variance in house prices.
    * Visualizing the residuals (the difference between actual and predicted prices) to check for linearity and homoscedasticity.

## Results

Both approaches resulted in robust linear regression models capable of predicting housing prices. The evaluation metrics primarily focused on R-squared, indicating the proportion of variance in the dependent variable that can be predicted from the independent variables.

* The model developed using **Recursive Feature Elimination (RFE)** achieved an R-squared score of **0.655** on the test set. This means approximately 65.5% of the variance in housing prices can be explained by the selected features.
* The model built using **Manual Feature Elimination** also demonstrated strong performance, with the final R-squared values indicating a good fit to the data.

The residual analysis confirmed that the errors are normally distributed and randomly scattered, suggesting that the linear regression assumptions are met.

## Files in this Repository

* `Housing.csv`: The dataset containing housing price information.
* `housing-price-prediction-RFE.ipynb`: Jupyter Notebook detailing the housing price prediction using Linear Regression with Recursive Feature Elimination.
* `mutiple_LinRegModel.ipynb`: Jupyter Notebook detailing the multiple linear regression model with manual feature elimination.

## Technologies Used

* Python
* Jupyter Notebook
* Pandas (for data manipulation)
* Numpy (for numerical operations)
* Scikit-learn (for machine learning models and preprocessing)
* Statsmodels (for OLS regression and statistical tests)
* Matplotlib (for data visualization)
* Seaborn (for enhanced data visualization)
