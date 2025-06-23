# MSCS_634_Lab_4: Regression Analysis with Regularization
Name: Nischal Joshi
Course: MSCS 634: Advanced Big Data and Data Mining.
Lab Title: Regression Models and Regularization Techniques

## Purpose of the Lab 
The laboratory assignment explores different regression techniques, from basic linear models to more advanced polynomial and regularized regression methods. 
The main objective of this lab work is to:
- Run Simple, Multiple, and Polynomial Linear Regression models.
- Apply Ridge and Lasso Regression to understand the role of regularization to prevent overfitting.
- Compare model performances with the standard metrics (MAE, MSE, RMSE, R²).
- Visualize predictions and trends in the data for better intuition.
- Contrast the advantages and disadvantages of different regression techniques on the Diabetes dataset.- Run Simple, Multiple, and Polynomial Linear Regression models.
- Apply Ridge and Lasso Regression to understand the application of regularization to prevent overfitting.
- Evaluate model performance using traditional metrics (MAE, MSE, RMSE, R²).
- Graph model predictions and data trends for better understanding.
- Contrast and analyze the shortcomings and strengths of different regression techniques on the Diabetes dataset.

## Key Insights Gained from the Regression Analysis

- **Datset Insight:**
The dataset is provided as a Bunch object (a dictionary-like object).
'data' contains the features (independent variables).
'target' contains the dependent variable (disease progression).
'feature_names' provides the names for each feature.'

No cleaning is explicitly needed for this dataset.
In case of missing values some common strategies are:
X.fillna(X.mean(), inplace=True) for numerical features.
X.dropna(inplace=True) to drop rows with missing values.

- **Complexity of Disease Progression:** 
The Diabetes dataset highlights that disease progression is a complex phenomenon not easily captured by a single feature. Multiple features are crucial for a more accurate predictive model, as evidenced by the significantly higher R-squared of Multiple Linear Regression compared to Simple Linear Regression.

- **Non-linearity and Overfitting:** 
Polynomial Regression demonstrated how non-linear relationships are able to be captured. However, raising the polynomial degree too high will very soon lead to overfitting, where the model is a good fit to the training set but not to unseen test sets. This points up the importance of having a good model complexity.

- **Power of Regularization:** 
Ridge Regression and Lasso Regression are strong in improving model generalization and preventing overfitting.
- **Ridge Regression** effectively shrinks coefficients, making the model more resistant to multicollinearity and decreasing variance.
- **Lasso Regression** not only regularizes but also selects features automatically by forcing less important feature coefficients towards zero. This makes Lasso particularly valuable for data sets where it is essential to find most important features.

- **Optimal Model Performance:** 
As per the metrics, Lasso Regression with alpha = 0.1 had the best R-squared (0.4719) and lowest error metrics (MAE: 42.85, MSE: 2798.19), slightly better than Ridge and significantly better than basic linear models. This shows its strength in feature selection in this dataset.

- **Regularization Alpha Interpretation:**
Understanding how different `alpha` values affect coefficient shrinkage and feature selection in Ridge and Lasso was a key takeaway. Comparing the R-squared change and the values of coefficients for different alphas supported this idea.

- **Visualization Selection:**
Plotting actual vs. predicted values is more effective for multiple regression than trying to plot against a single feature. For regularization, plotting the size of coefficients is effective to show Lasso's sparsity.

- **Convergence Warnings in Lasso:**
To avoid the convergence warning in Lasso, I increased `max_iter` parameter to ensure the model converges well, which is normal when dealing with Lasso's optimization algorithm.

