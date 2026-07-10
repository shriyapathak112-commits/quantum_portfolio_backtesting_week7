# Research Paper Draft: Portfolio Risk Quantification via Quantum Amplitude Estimation

**Author:** Quantum Research Intern : Shriya Pathak 
**Research Focus Area:** Quantum Financial Engineering  
**Version:** 1.0 (Sprint Milestone Review)  

---

## Abstract
This paper presents an empirical analysis comparing classical estimation frameworks against quantum state phase estimation algorithms for calculating financial market risk. Specifically, we investigate Value at Risk (VaR) and Conditional Value at Risk (CVaR) under standard geometric Brownian asset movements. We validate a native quadratic scaling efficiency speedup ($O(1/\varepsilon)$ vs $O(1/\varepsilon^2)$) using a gate-based simulation pipeline.

---

## 1. Mathematical Framework of Quantum Risk Analytics
In a digital quantum architecture, a continuous financial random variable representing portfolio loss distributions must be mapped onto a discrete quantum state. We achieve this by mapping asset returns onto an $n$-qubit system where the probability amplitudes of the basis states reflect the underlying probability density function. 

The structural state preparation operator creates an entangled state vector:

$$\lvert \Psi \rangle = \sqrt{1 - a}\lvert \Psi_0 \rangle + \sqrt{a}\lvert \Psi_1 \rangle$$

Where:
* $\lvert \Psi_1 \rangle$ represents the target "objective" state containing all basis paths where portfolio loss exceeds a pre-defined critical threshold.
* $\lvert \Psi_0 \rangle$ represents the safe operating parameters of the portfolio distribution.
* $a \in [0, 1]$ represents the exact, unknown cumulative risk probability to be estimated.

---

## 2. Classical Monte Carlo Baseline
Classical asset pricing models rely on generating a sequence of pseudo-random paths to approximate expected metrics. By invoking the Central Limit Theorem (CLT), the convergence error bounds ($\varepsilon$) are strictly governed by standard deviation over the square root of the sample size:

$$\varepsilon = O\left(\frac{1}{\sqrt{N}}\right) \implies N = O\left(\frac{1}{\varepsilon^2}\right)$$

This inverse-square relationship represents a major hardware bottleneck for risk management. For example, reducing a pricing tracking error by a factor of 10 requires an expensive 100x surge in high-performance computing (HPC) server workloads.

---

## 3. Quantum Amplitude Estimation (QAE) Architecture
Quantum Amplitude Estimation breaks this classical scaling limit by removing random sampling dependencies. Instead, it utilizes iterative quantum oracle reflections (Grover tuning loops) to linearly amplify the probability amplitude $a$ of the state $\lvert \Psi_1 \rangle$. 

Through successions of the unitary quantum operator $\mathcal{Q} = -\mathcal{A}\mathcal{S}_0\mathcal{A}^{-1}\mathcal{S}_{\chi}$, the convergence error limits shift from a quadratic dependency to a linear function:

$$\varepsilon = O\left(\frac{1}{N}\right) \implies N = O\left(\frac{1}{\varepsilon}\right)$$

This provides the foundational **quadratic speedup**, drastically minimizing the operational path counts required to evaluate complex financial derivatives.

---

## 4. Empirical Simulation & Experimental Results
Our benchmarking experiment validated these theoretical complexity scaling laws under a fixed target precision window of $\varepsilon = 0.005$ at a 95% Confidence Interval.

### Core Metrics Summary
* **Value at Risk (VaR):** **0.2787** (Maximum expected losses will not exceed 27.87% of asset holdings).
* **Conditional Value at Risk (CVaR):** **0.3630** (Expected tail loss during extreme market liquidations).

### Performance Vectors
* **Classical Pipeline Evaluations:** **40,000 sampling paths** were executed to stabilize the tracking boundaries.
* **Quantum Circuit Evaluations:** **200 oracle iterations** were executed using a Qiskit `StatevectorSampler` architecture.
* **Empirical Reduction Speedup:** Confirmed an exact **200.0x speedup**, validating the transition from quadratic to linear evaluation scaling.

---

## 5. Industrial Financial Applications
* **Intraday Liquidity Stress Testing:** Transitioning risk processing blocks from long overnight server queues into real-time operational metrics.
* **Tail-Risk (CVaR) Arbitrage Asset Allocation:** Accurately mapping out thin, extreme market tail distributions without the high processing costs of traditional systems.
  ## 6. Large-Scale Backtesting Framework & Implementation
*(Note: Use this brief section to connect your physical backtest setup to the paper before presenting the raw charts/data)*

To validate the empirical performance of the proposed models, a large-scale simulation framework was executed using daily historical asset returns spanning a comprehensive multi-year evaluation window (2020–2024). The optimization configurations utilize a rolling 252-day lookback window (commencing in 2019) for periodic annual strategic rebalancing across an eight-asset liquid equity universe.

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