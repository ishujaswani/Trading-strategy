# Trading-strategy

This project develops a trading strategy using Arbitrage Pricing Theory (APT) factors and portfolio optimization, incorporating transaction costs and performance attribution.  A computationally efficient backtester ensures fast results.

## Features and Functionality

* **Arbitrage Pricing Theory (APT) Factor Model:**  The core of the strategy uses APT factors to model asset returns.
* **Portfolio Optimization:**  Employs Markowitz mean-variance optimization, leveraging the Woodbury Matrix Inversion Lemma for computational efficiency, especially with large portfolios.
* **Transaction Cost Inclusion:**  The backtester explicitly accounts for transaction costs, providing a more realistic performance assessment.
* **Performance Attribution:**  Analyzes portfolio returns to identify the key drivers of performance.
* **Efficient Backtesting:**  Uses a computationally optimized backtesting framework for quick analysis of historical data.
* **Data Cleaning:**  Includes robust data cleaning procedures, such as handling missing values and outlier treatment (winsorization).
* **Model Selection:** Uses Lasso and Elastic Net regression, along with non-linear models like XGBoost, for alpha factor selection and model optimization.

## Technology Stack

* **Python:**  Primary programming language.
* **Pandas & NumPy:** For data manipulation and numerical computation.
* **Statsmodels & Scikit-learn:** Statistical modeling and machine learning libraries.
* **XGBoost:** Gradient boosting library for non-linear model fitting.
* **Matplotlib & Seaborn:** Data visualization libraries.
* **Quarto:** For creating reproducible and interactive reports (HTML output found in `_site` directory).

## Prerequisites

* Python 3.11
* Required Python packages:  `pandas`, `numpy`, `statsmodels`, `scikit-learn`, `xgboost`, `matplotlib`, `seaborn`
  ```bash
  pip install pandas numpy statsmodels scikit-learn xgboost matplotlib seaborn
  ```
*  Data files: The project relies on pre-processed data stored in the `pickle_data/FACTOR_MODEL/` directory as compressed pickle files (`.pickle.bz2`).  These files contain pandas DataFrames:  `pandas-frames.{year}.pickle.bz2` and `covariance.{year}.pickle.bz2` for each year (2003-2010).


## Installation Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/ishujaswani/Trading-strategy.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Trading-strategy
   ```
3. Install dependencies (see Prerequisites).

## Usage Guide

The core logic of the trading strategy is implemented in Python scripts. The `_site` directory contains generated HTML documentation created using Quarto.  The main analysis steps are:

1. **Data Loading and Cleaning:** Python scripts load and clean the data from the `.pickle.bz2` files (e.g., as shown in `_site/index.html`).
2. **Factor Model Estimation:**  The `estimate_factor_returns` function (partially shown in `_site/index.html` and fully implemented in the codebase) estimates factor returns.
3. **Portfolio Optimization:** Uses the `optimize_portfolio` function (implemented in `_site/optimisation.html`) which utilizes the Woodbury matrix inversion.
4. **Backtesting:**  The `_site/optimisation.html` file shows how to assemble the backtest.
5. **Reporting:** The Quarto-generated HTML files (`_site/about.html`, `_site/index.html`, `_site/optimisation.html`) provide detailed reports and visualizations of the results.


## Contact/Support Information

For any questions or issues, please contact ishujaswani at the email address provided on their Github profile.
