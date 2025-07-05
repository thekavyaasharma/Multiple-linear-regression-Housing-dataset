# Multiple Linear Regression Model: Predicting House Prices 

Welcome to this project! Here, we dive into the world of real estate data to understand what truly drives house prices in the Delhi region. Our goal is to build a smart model that helps a real estate company price properties effectively.

## What's Inside?

This Jupyter notebook `mutiple_LinRegModel.ipynb` focuses on building a **Multiple Linear Regression Model**. It's a journey to uncover the hidden relationships between house prices and key factors like area, number of bedrooms, and parking availability.

## Multiple Linear Regression: A Simple Explanation 📈

Imagine you want to predict a house's price. You know that things like its size (area), the number of bedrooms, and whether it has parking all play a role. Multiple Linear Regression is a statistical tool that helps us quantify these relationships.

Think of it like this:
`House Price = (Factor A * Area) + (Factor B * Bedrooms) + (Factor C * Parking) + ... + Some Base Price`

Our model finds the best "factors" (coefficients) for each variable to predict the house price accurately. It's a straightforward yet powerful way to see how different features contribute to the final price.

## Our Approach: Smart Feature Selection

Building a good model isn't just about throwing all data in; it's about picking the right ingredients. In this project, we used two key techniques for feature selection to make our model robust and easy to understand:

### 1. Feature Elimination based on P-values (Significance)

This technique is like carefully selecting the most impactful features for our model based on their statistical significance. We start with a set of potential factors (like area, bedrooms, bathrooms, stories, main road access, guest room, basement, hot water heating, air conditioning, parking, preferred area, and furnishing status). We then evaluate the p-value for each feature, which tells us how likely it is that the observed relationship happened by chance. Features with high p-values (indicating low significance) are systematically removed. This ensures our model is lean, accurate, and focuses on what truly matters, keeping only the variables that have a strong, statistically significant relationship with house prices.

### 2. Variance Inflation Factor (VIF)

Sometimes, independent variables in our model can be related to each other. This is called multicollinearity, and it can make our model less reliable and harder to interpret. The Variance Inflation Factor (VIF) helps us detect this. A high VIF for a variable indicates it's highly correlated with one or more other independent variables in the model. By checking VIF, we can identify and address these issues, making sure our model's predictions are stable and trustworthy. If two variables tell us similar things, VIF helps us decide which one to keep or if we need to adjust our approach. We iteratively remove variables with high VIF values to reduce redundancy and improve the model's reliability.

## Steps Followed in This Model 🛠️

Here's a clear outline of how we built and refined our Multiple Linear Regression model:

1.  **Read and Understand the Data:** We started by loading the `Housing.csv` dataset. This dataset is crucial as it contains the property prices and various features for houses in the Delhi region, which we use to **train and test our model**. We also got a good grasp of its structure, checked for any missing values, and understood the data types.
2.  **Visualizing the Data:** We used visualizations to explore relationships between variables and identify initial patterns.
3.  **Data Preparation:** This involved preparing the categorical variables for modeling.
4.  **Splitting Data for Training and Testing:** We divided our dataset into training and testing sets to evaluate how well our model performs on new, unseen data.
5.  **Feature Scaling:** Numerical features were scaled to ensure that no single feature dominates the model due to its larger values.
6.  **Building the Model:** We built the initial linear regression model using selected features.
7.  **Feature Selection (P-values and VIF):** We iteratively refined the model by:
    * Evaluating the statistical significance of each variable using **p-values**.
    * Checking the **Variance Inflation Factor (VIF)** for multicollinearity among the independent variables.
    * Removing variables that were not statistically significant (high p-value) or had high VIF values, leading to a simpler and more robust model.
8.  **Residual Analysis:** We analyzed the differences between our model's predictions and the actual house prices to ensure the model's assumptions hold true and to identify any patterns in the errors.
9.  **Making Predictions and Evaluation:** Finally, we used our refined model to predict house prices on the test set and evaluated its accuracy and performance using relevant metrics.

---
