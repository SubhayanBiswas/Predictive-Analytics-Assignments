# Predictive Analytics Coursework

This repository contains primary projects focused on exploratory data analysis, the fundamental properties of linear regression, and advanced model diagnostics. The projects utilize various datasets (Boston Housing, Credit, and fgl) and Monte Carlo simulations to demonstrate key statistical concepts and modeling techniques.

---

## Project 1: Boston Housing Exploratory Analysis

### Overview
This project contains an introductory analysis of the 'Boston' housing dataset, originally from the MASS Library of R. The notebook walks through data loading, inspection, and visualization to understand the relationships between the median value of owner-occupied homes and various predictors.

### Key Variables Analyzed
* **`medv`**: Median value of owner-occupied homes in $1000s (Response Variable).
* **`crim`**: Per capita crime rate by town.
* **`nox`**: Nitrogen oxides concentration (parts per 10 million).
* **`black`**: Proportions of blacks by town ($1000(Bk - 0.63)^2$).
* **`lstat`**: Lower status of the population (percent).

### Analysis Workflow
1.  **Data Ingestion**: Loading raw CSV data into a Pandas DataFrame.
2.  **Structure & Class Report**: Identifying dataset dimensions and variable types using `df.info()`.
3.  **Subsetting**: Creating a focused mini-dataset with specific predictors (`medv`, `crim`, `nox`, `black`, `lstat`).
4.  **Exploratory Visualization**: Generating scatter plots to observe correlations between median home values (`medv`) and the selected predictors.

---

## Project 2: Linear Regression - Simulation & Application

### Overview
This project explores the theoretical foundations of Ordinary Least Squares (OLS) regression. It combines simulation studies to validate statistical properties with a practical application of simple linear regression on the Boston Housing dataset.

### Core Problems Addressed
**1. Population vs. Sample Regression Lines**
* Demonstrates that while the population regression line is fixed ($Y = 2 + 3x$), the least squares regression lines vary from sample to sample due to random error.
* Visualizes 5 distinct least squares lines plotted against the true population line to show sampling variability.

**2. Minimizing Residual Sum of Squares (RSS)**
* Conducts a grid search over a range of $\beta_0$ (intercept) and $\beta_1$ (slope) values.
* Mathematically verifies that the OLS estimates obtained via `scikit-learn` correspond exactly to the minimum RSS on the calculated error surface.

**3. Unbiased Nature of OLS Estimators**
* Performs a Monte Carlo simulation with 1,000 iterations.
* Confirms that the average of the estimated coefficients ($\hat{\beta_0}, \hat{\beta}$) converges to the true population parameters ($2, 3$), demonstrating that OLS estimators are unbiased.

**4. Comparative Regression Models**
* Fits four separate simple linear regression models to the Boston Housing data using `crim`, `nox`, `b` (proportion of blacks), and `lstat` as single predictors for `medv`.
* Compares models based on goodness-of-fit ($R^2$) to determine that `lstat` is the most useful individual predictor ($R^2 \approx 0.54$).

---

## Project 3: Qualitative Predictors & Interactions

### Overview
This project demonstrates the inclusion of qualitative (nominal) predictors and evaluates the impact of ignoring interaction terms in multiple linear regression models.

### Core Problems Addressed
**1. Qualitative Predictors in Regression**
* Regresses credit card `Balance` on combinations of `Gender`, `Ethnicity`, and `Income` using the Credit dataset.
* Compares the goodness of fit across multiple models using AIC, BIC, and Adjusted R-squared metrics to select the most optimal model.
* Predicts the credit card balance for specific demographics (e.g., a female Asian) based on the chosen multiple regression model.

**2. Impact of Ignoring Interaction Terms**
* Conducts Monte Carlo simulations running 1000 iterations to compare a true model featuring an interaction term ($x_1 * x_2$) against a naive model without it.
* Calculates and compares the Mean Squared Error (MSE) for both models under varying parametric configurations.
* Demonstrates that ignoring a large interaction term significantly increases the naive model's MSE.

---

## Project 4: Model Diagnostics & Multicollinearity

### Overview
This project focuses on variable selection, identifying multicollinearity among predictors, and detecting anomalous data points (outliers) in multiple linear regression.

### Core Problems Addressed
**1. Variable Selection**
* Uses the fgl (glass) dataset to regress Refractive Index (`RI`) on different metallic oxides.
* Identifies `Fe` and `Si` as the strongest predictors for the refractive index based on p-values from the OLS regression summary.

**2. Detecting Multicollinearity**
* Examines the Credit dataset by plotting `Age` vs. `Limit` and `Rating` vs. `Limit` to visually assess correlations.
* Observes that while `Rating` is a highly significant predictor of `Balance`, `Limit` becomes insignificant when combined with `Rating` in a model, hinting at redundancy.
* Confirms severe multicollinearity between `Rating` and `Limit` by calculating the Variance Inflation Factor (VIF).

**3. Outlier Detection**
* Fits a multiple linear regression model predicting the median value of homes (`medv`) using `crim`, `nox`, `black`, and `lstat` from the Boston dataset.
* Detects regression outliers by calculating studentized residuals and flagging observations with an absolute value greater than 3.

---

## Dependencies
To run these notebooks, you will need the following Python libraries installed:
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scipy`
* `sklearn` (scikit-learn)
* `statsmodels`
* `ISLP`
