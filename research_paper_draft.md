## 7. Results & Analysis

This section presents the quantitative findings from the comprehensive backtesting framework evaluated over the 2020–2024 trading window. Performance and tail-risk dimensions are assessed across four primary structures: the Equal Weight portfolio, the Classical Markowitz Mean-Variance framework, the proposed Hybrid Quantum (QUBO-formulated) strategy, and the baseline S&P 500 market index.

### 7.1 Capital Appreciation & Growth Velocity
Empirical metrics demonstrate a clear divergence in raw alpha generation and structural asset expansion:
* **The Hybrid Quantum Strategy** exhibited the highest nominal rate of return, yielding an annualized Compound Annual Growth Rate (CAGR) of **35.69%**. This represents an outperformance of **22.83%** over the benchmark S&P 500 index (**12.86%**) and a margin of **13.00%** over the Classical Markowitz setup (**22.69%**).
* **The Equal Weight Portfolio** demonstrated strong tracking capabilities, registering a baseline CAGR of **28.32%**.

### 7.2 Risk-Adjusted Return Architecture
Normalizing returns against systemic price fluctuations reveals different profiles of economic efficiency:
* **The Equal Weight Strategy** maximized capital usage efficiency, achieving a leading Sharpe Ratio of **1.04** and a Sortino Ratio of **1.35**. 
* **The Hybrid Quantum Strategy** yielded a Sharpe Ratio of **0.76** and a Sortino Ratio of **1.11**. While its alpha velocity remained strong, its overall efficiency ranking was impacted by an annualized volatility profile of **43.01%**, compared to the Equal Weight framework’s variance of **24.44%**.
* **Active Tracking Metrics**: Active returns relative to the benchmark show that the Equal Weight framework maximized its relative execution boundary with an Information Ratio of **1.70**, followed by the Hybrid Quantum formulation at **0.82**, and the Markowitz portfolio at **0.63**.

### 7.3 Downside Trajectory & Tail Risk Profiles
Extreme stress conditions and maximum loss parameters were quantified using Value at Risk (VaR) and Conditional Value at Risk (CVaR) models at a 95% confidence threshold:
* **Tail Vulnerability**: The Hybrid Quantum framework presented a high-volatility tail, with a single-day 95% VaR of **-4.31%** and an Expected Shortfall (CVaR) of **-6.02%**.
* **Drawdown Dynamics**: Peak-to-trough capital contractions show that the Hybrid Quantum asset matrix experienced a Maximum Drawdown of **-61.13%**, resulting in a Calmar Ratio of **0.58**. The Equal Weight configuration limited capital compression to **-29.79%**, yielding a Calmar Ratio of **0.95**.

## 8. Discussion

The quantitative results offer deeper insights into the operational characteristics and structural trade-offs embedded within classical, heuristic, and quantum-inspired portfolio management models.

### 8.1 The Quantum Alpha-Volatility Trade-Off
The empirical data shows that framing asset optimization as a Quadratic Unconstrained Binary Optimization (QUBO) problem creates a highly responsive asset layout. By prioritizing non-linear risk and return relationships, the hybrid quantum configuration identified aggressive growth paths that outpaced classical optimization by a substantial margin. 

However, this increased growth rate introduces a distinct trade-off. The optimization process frequently concentrates capital into highly responsive, high-beta assets. This trend is clearly visible in the strategy's high annualized volatility (**43.01%**) and deep drawdown profile (**-61.13%**).

### 8.2 Asset Concentration vs. Equal Diversification
The strong performance of the simple Equal Weight model (Sharpe: 1.04, Max DD: -29.79%) highlights the limits of mathematical optimization when applied to historical lookback datasets. This reflects a well-known theme in quantitative finance: optimization routines are often highly sensitive to estimation errors in historical covariance matrices. 

While the Markowitz framework (Sharpe: 0.66) and the Hybrid Quantum setup optimized positions using past lookback data, the naive Equal Weight model avoided concentration risk altogether. This structural choice provided a smoother and more reliable downside path during localized market adjustments over the evaluated timeframe.

### 8.3 Operational Stability and Systemic Stress Response
Analyzing risk profile instability confirms that the Hybrid Quantum strategy experiences sharp shifts in its asset configuration over time (**15.68%** instability score). Under normal market conditions, this agility helps capture alpha. 

However, during systemic market stress—such as the worst 1% of trading days for the S&P 500—the model shows exposure to market-wide liquidations, experiencing a stress impact loss of **-6.02%**. Interestingly, this still managed to outperform the Classical Markowitz model, which dropped further to **-6.96%** under identical conditions.

### 8.4 Conclusion and Structural Recommendations
The choice between these models ultimately depends on the specific risk parameters of the investment fund:
1. For portfolios aiming to maximize long-term wealth expansion where deep drawdowns are acceptable, the **Hybrid Quantum optimization routine** provides an effective framework for generating alpha.
2. For portfolios bound by strict risk mandates or maximum loss limits, a blended approach is more appropriate. Combining the tail-risk protection of an **Equal Weight allocation** with the selective growth targeting of the **Quantum QUBO model** can help balance overall performance with capital preservation..