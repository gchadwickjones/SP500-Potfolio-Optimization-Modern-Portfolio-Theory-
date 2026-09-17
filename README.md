# Modern Portfolio Theory: Mean Variance Optimization
This project applies modern portfolio theory to a selection of S&P 500 stocks to build portfolios of different risk profiles by investigating their relationship with risk and return. 

I began by using historical stock information to calculate daily returns, volatility, correlation and covariance, before applying mean-variance optimization to generate the efficient frontier. 

Six stocks were selected for the portfolio from different industries and sectors, with relatively low correlations. These stocks are:
<img width="2850" height="760" alt="stock_selection" src="https://github.com/user-attachments/assets/cb4eccb3-a606-4ad9-a93f-9af113311803" />

The selected stocks had correlations ranging from approximately `0.13` to `0.33` and they were selected from different industries and sectors. These relatively low correlations mean that the stocks do not 
move together in response to the same market forces, allowing for diversification in the portfolio. 

An initial unconstrained optimisation resulted in a portfolio that was heavily weighted to `NVIDIA` due to its historical high returns, though placing such weight on a singular stock would have high risk by nature
Therefore, a maximum portfolio weight of `50%` was introduced to encourage greater diversification. 

The final analysis uses this constrained efficient frontier to generate low-risk, medium-risk and high-risk portfolios, which aim to maximise their returns while minimising their volatility. 

## Objective
The main objectives of this analysis were to:
* Investigate the historical relationship between risk and return across S&P 500 stocks
* Identify stocks with relatively low correlations
* Use mean-variance optimisation to generate an efficient frontier
* Reduce excessive concentration in a single stock through portfolio constraints
* Compare portfolios with different levels of risk and expected return

## Methodology

The analysis consisted of the following stages:
1. Clean and prepare the historical stock price data
2. Convert the dataset from long format to wide format
3. Calculate daily returns, volatility and correlation
4. Select six stocks with relatively low correlations
5. Calculate the covariance matrix and annualise returns and covariance
6. Simulate 10,000 random portfolios
7. Generate an efficient frontier using mean-variance optimisation
8. Introduce a maximum 50% allocation per stock
9. Select representative low-risk, medium-risk and high-risk portfolios
10. Compare the expected return, volatility and asset allocation of each portfolio

## Mean variance optimization
The selected stocks were used to calculate the covariance matrix and generate 10,000 randomly weighted portfolios.
Mean variance optimization was then used to create an efficient frontier that represented difference combinations of expected return and volatility.

The initial unconstrained optimization resulted in a portfolio that was heavily weighted towards `NVIDIA`. Although this was mathematically valid under the original constraints (or lack thereof), it provided
very little diversification which defeats the purpose of a portfolio.

A maximum allocation of `50%` per stock was therefore introduced to the portfolio simulation function, which encouraged diversification and stopped `NVIDIA` from being overly represented in the portfolio.

## Portfolio Risk Profiles
The constrained efficient frontier was used to select three different portfolios:
- **Low risk:** portfolio with the lowest volatility
- **Medium risk:** portfolio from the middle of the generated efficient frontier
- **High risk:** portfolio with the highest expected return

The portfolios demonstrated how the allocation of assets within a portfolio changed as the relative risk, and subsequently the higher returns, increased. 
The high risk portfolio allocated a weight of `50%` to `NVIDIA`, which is the maximum allowed under the constrained efficient frontier, while the lower-risk portfolio placed greater weight on stocks such as `Northrop Grumman` and `DXC Technology`.
<img width="2850" height="1215" alt="portfolio_options" src="https://github.com/user-attachments/assets/dc0a686d-4bb9-4aa1-8426-fbff67d77351" />

## Conclusion
This analysis demonstrates how historical stock returns, volatility and correlation can be used to create portfolios using mean variance optimization. \
Six stocks with relatively low correlations were selected to create an efficient frontier. The initial unconstrained optimization created a hgihly concentrated portfolio, so a constraint of `50%` was added as the maximum allocation allowed for a single stock within the portfolio. This encouraged greater diversification. \

Three representative portfolios were then selected from the constrained efficient frontier to demonstrate the different trade off between returns and volatility. As the expected returns of a portfolio increases, so does its volatility. This analysis was successful at maximising the returns of a selection of stocks by allocating ideal weights to minimise volatility. \
The results are based on historical data and should therefore not be interpreted as predictions of future performance.

## Tools & Technologies
* Python
* pandas
* NumPy
* Matplotlib
* Plotly
* CVXOPT
* Jupyter Notebook
* Mean-Variance Optimisation
* Modern Portfolio Theory

