Robust Portfolio Optimization for the Energy Sector

This project implements a robust portfolio optimization model focusing on the energy sector. The portfolio includes a mix of traditional energy stocks, renewable energy stocks, futures contracts, and hedging instruments. The goal is to maximize returns while minimizing risk, accounting for worst-case scenarios using Monte Carlo simulations and GARCH modeling for volatility.

Project Overview

This project uses historical financial data to optimize a portfolio of energy sector assets. The key steps involved in the project are:

Data Collection: Fetching historical price data for energy-related stocks, benchmark indices (S&P 500), and futures contracts (Crude Oil and Natural Gas) using Yahoo Finance.
Return Calculations: Calculating both simple and logarithmic returns from the price data.
Risk-Free Rate Integration: Incorporating the 10-year treasury rate as the risk-free rate from FRED.
Monte Carlo Simulation: Estimating beta and expected returns for each asset using the CAPM model and Monte Carlo simulations.
GARCH Modeling: Simulating volatility for each asset using a GARCH(1,1) model.
Robust Optimization: Using a robust Markowitz portfolio optimization to find optimal asset weights that maximize worst-case returns while minimizing risk.

Key Features

Asset Universe:
Traditional energy companies: NEE, XOM, CVX, COP, ENB, SRE
Renewable energy companies: BEP, FSLR, ICLN, XLE
Futures contracts: Crude Oil (CL=F), Natural Gas (NG=F)
Hedging instrument: ProShares Short S&P 500 (SH)

Data Collection:
Stock price data is pulled from Yahoo Finance.
Risk-free rate data is fetched from FRED.

Monte Carlo Simulation for CAPM:
Using Monte Carlo simulations, we estimate the beta and expected returns for each asset.
The simulations are used to calculate confidence intervals for beta and expected returns, accounting for uncertainty in the future market environment.

GARCH Model for Volatility:
GARCH(1,1) is applied to model the volatility of each asset.
Volatility simulations generate upper and lower confidence intervals to handle worst-case volatility scenarios.

Portfolio Optimization:
We use CVXPY to perform robust portfolio optimization, maximizing returns based on the lower bound of CAPM expected returns and minimizing risk based on the worst-case volatility from GARCH.
The portfolio is constrained to a long-only strategy (no short-selling) with weights summing to 1.

Files

price_data_6_months.csv: Historical adjusted price data for all assets over the selected 6-month period.
simple_returns.csv: Simple returns for all assets, including the risk-free rate.
log_returns.csv: Logarithmic returns for all assets.
log_returns_scaled.csv: Scaled logarithmic returns for further analysis.
interest_rate_data.csv: Historical risk-free rate data (10-year treasury) from FRED.

Key Results

Optimal Portfolio Weights: The robust optimization process outputs optimal portfolio weights for each asset.
Expected Portfolio Return: The expected return of the optimized portfolio based on Monte Carlo simulations.
Portfolio Risk (Standard Deviation): The overall risk of the portfolio calculated using the covariance matrix and optimized weights.
Dependencies

To run the project, you'll need the following Python libraries:

numpy
pandas
yfinance
pandas_datareader
statsmodels
arch
cvxpy
matplotlib
You can install the required libraries using pip:

bash
Copy code
pip install numpy pandas yfinance pandas_datareader statsmodels arch cvxpy matplotlib
Running the Project

To run the optimization and view the results, execute the provided Jupyter notebook in the repository. The notebook walks through each step, from data collection to the final portfolio optimization.

Conclusion

This project demonstrates a comprehensive approach to robust portfolio optimization, taking into account worst-case scenarios for both returns and volatility. The energy sector is a volatile market, and this model aims to construct a portfolio that is resilient in the face of market uncertainties.
