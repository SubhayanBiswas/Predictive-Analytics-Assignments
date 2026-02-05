# Predictive Analytics Coursework

This repository contains two primary projects focused on exploratory data analysis and the fundamental properties of linear regression. The projects utilize the Boston Housing dataset and Monte Carlo simulations to demonstrate key statistical concepts and modeling techniques.

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

## Dependencies
To run these notebooks, you will need the following Python libraries:
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scipy`
* `sklearn` (scikit-learn)

## Usage
Clone the repository and run the notebooks via Jupyter Lab or
