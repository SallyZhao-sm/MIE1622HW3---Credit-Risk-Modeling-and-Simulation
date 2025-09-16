# MIE1622HW3---Credit-Risk-Modeling-and-Simulation

This project models a credit-risky portfolio of 100 corporate bonds using structural credit risk models with credit-state migrations. Monte Carlo simulation and Normal approximations are applied to estimate portfolio losses and risk measures.

## Methods
- **Scenario Generation**
  - Monte Carlo Approximation 1: 5000 in-sample scenarios (1000 systemic × 5 idiosyncratic)
  - Monte Carlo Approximation 2: 5000 in-sample scenarios (5000 systemic × 1 idiosyncratic)
  - True Distribution: 100,000 out-of-sample scenarios
- **Normal Model**: Approximations based on mean and variance from simulated losses  
- **Portfolios**:
  1. One unit invested in each bond
  2. Equal dollar amount invested in each bond  

## Risk Metrics
- Value-at-Risk (VaR) and Conditional VaR (CVaR) at **99%** and **99.9%**
- Compared in-sample estimates vs. out-of-sample "true" distribution
- Repeated experiments 100 times to measure sampling error variance

## Results
- **Sampling Error**:  
  - Portfolio 1 showed large variability, with some errors exceeding 100%.  
  - Portfolio 2 produced more stable estimates but underestimated risk at extreme quantiles (99.9%).  
- **Model Error**:  
  - Normal models often underestimated tail risk, especially at 99.9%.  
  - At 99%, Normal approximations sometimes overestimated risk in Portfolio 1.  
- **Practical Implications**:  
  - Overestimation → excessive capital reserves, lowering efficiency  
  - Underestimation → insufficient buffers, liquidity risk  

## Strategies to Reduce Errors
- Increase scenario size to reduce variance  
- Use **stratified sampling** and **importance sampling** to improve tail estimates  
- Apply **Extreme Value Theory (EVT)** for tail modeling  
- Combine Monte Carlo with analytical stress scenarios (hybrid approach)  

## Skills Demonstrated
- Credit risk modeling with structural models  
- Monte Carlo simulation and statistical error analysis  
- VaR and CVaR computation at high quantiles  
- Error decomposition: sampling vs. model error  
- Python implementation with `numpy`, `pandas`, `scipy`, and visualization  
