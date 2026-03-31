# Airbus Option Pricing — Black-Scholes & Monte Carlo

This project implements and compares two pricing approaches for European options on Airbus stock (AIR.PA):

- Black-Scholes analytical model
- Monte Carlo simulation

The objective is to understand how option prices behave under different assumptions
and to analyze the consistency between analytical and numerical methods.

---

## Context

This project extends a previous work on market risk simulation using Monte Carlo methods on the SPY ETF:

https://github.com/nicolasmarveaux456-hue/montecarlo-spy-risk

While the previous project focused on market risk (VaR, Expected Shortfall),
this project focuses on derivative pricing.

---

## Market Data & Model Inputs

- Underlying: Airbus (AIR.PA)
- Data source: Yahoo Finance
- Spot price (S0): latest adjusted close

Volatility estimation:
- σ20: 20-day rolling historical volatility (annualized)
- σ60: 60-day rolling historical volatility (annualized)

Model parameters:
- Risk-free rate: r = 2%
- Maturities:
  - T = 30 days
  - T = 90 days

---

## Methodology

The project is structured into three main components:

### 1. Black-Scholes pricing
- Implementation of analytical formulas for European call and put options
- Pricing across multiple strikes and maturities

### 2. Option Greeks
- Analytical computation of Delta, Gamma, Vega and Theta
- Visualization of sensitivities around the at-the-money region

### 3. Monte Carlo simulation
- Simulation of terminal stock prices under the Black-Scholes assumptions
- Estimation of option prices via discounted expected payoff
- Convergence analysis towards Black-Scholes prices

---

## Key Results

- Call prices decrease with strike, while put prices increase, consistent with theory
- Higher volatility increases both call and put prices
- Longer maturities increase option values
- Monte Carlo prices converge to the Black-Scholes benchmark as the number of simulations increases
- Greeks highlight the sensitivity of option prices to underlying parameters

---

## Model Limitations

Black-Scholes assumptions:
- Constant volatility
- Lognormal price dynamics
- No dividends
- No transaction costs
- European exercise only

Monte Carlo:
- Computational cost increases with precision
- Convergence is gradual (proportional to 1/√N)

---

## Project Structure

notebooks/
- 01_black_scholes.ipynb
- 02_greeks.ipynb
- 03_monte_carlo.ipynb
- 99_summary.ipynb

---

## How to Run

1. Clone the repository

2. Install dependencies:

pip install numpy pandas matplotlib scipy yfinance

3. Run the notebooks in order:

01 → 02 → 03 → 99

---

## Skills Demonstrated

- Quantitative finance
- Option pricing models
- Black-Scholes framework
- Monte Carlo simulation
- Python (NumPy, Pandas, Matplotlib, SciPy)
- Financial data analysis (yfinance)

---
