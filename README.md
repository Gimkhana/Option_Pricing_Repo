### **Master README: Option Pricing Repository**

This repository elaborates on derivatives pricing, portfolio insurance, and money market modeling.
It covers five research projects spanning derivatives pricing, credit risk, portfolio management, and fixed-income modeling. Each tackles a real market problem using numerical methods and Monte Carlo simulation. 
Every model assumes something false. Black-Scholes = constant volatility. Vasicek = negative rates possible. Understand the gap between theory and reality. They're academic foundations, not production systems, but they illustrate how quantitative finance actually works.

**1. Option Pricing with Stochastic PDEs**
Black-Scholes, Cox-Ingersoll-Ross, and Vasicek models using finite difference methods (Crank-Nicolson discretization). Key takeaway: different models suit different problems. Black-Scholes assumes constant volatility (empirically false). CIR prevents negative rates but creates numerical instability. Vasicek is simpler but allows unrealistic negative rates. In production, you'd use ensemble methods or regime-switching.

Skill: Python, NumPy, SciPy, Jupyter | Data: Synthetic underlying prices | Output: 3D surface plots of option values

**2. Credit Portfolio Risk & CDO Tranching**
Monte Carlo simulator for credit losses and structured finance pricing. Models correlated defaults across thousands of loans, then waterfalls cash flows through senior/mezzanine/equity tranches. Convergence graphs prove model stability as simulation runs increase. Risk metrics: Expected Loss (average), Value at Risk (95th percentile), Expected Shortfall (tail risk).

Limitation: Accuracy depends on default probability assumptions and correlation estimates. Crisis events (2008, 2020) break historical correlations, making them invisible in backtests.

Skill: Python, NumPy, Matplotlib, Jupyter | Method: Monte Carlo + convergence testing | Insights: Correlation spike during crises; equity tranches absorb losses first

**3. MONIA Forward Rate Curve Construction**
Central bank research (Bank Al-Maghrib, Morocco) on LIBOR transition for interbank lending. Developed forward yield curves using compounding-in-arrears methodology on alternative reference rates. First-of-its-kind for Moroccan markets (as of 2021).

Key Finding: Paradigm shift from declarative rates (published by banks) to effective rates (actual transaction data). Moroccan market too shallow for maturities >12 months; longer rates become unstable.

Tech: Microsoft Excel, sensitivity analysis | Data: MONIA repo rates (2020-2021) | Co-authors: A. Feral (PhD), A. Rafiki (BAM) | Output: Published working paper on ResearchGate

**4. CPPI vs. OBPI Portfolio Insurance Strategies**
Monte Carlo comparison of two portfolio insurance methods under Black-Scholes and Lévy jump-diffusion models. CPPI (rebalance mechanically) vs. OBPI (buy puts to protect downside).

Critical Finding: Lévy processes capture market jumps (3-5% overnight moves) that Black-Scholes misses because it assumes smooth log-normal prices. In 2020-style crashes, Lévy models show spikes; Black-Scholes smooths them away, underestimating tail risk.

Data: S&P 500 (11.22% avg return, 17.83% volatility), US 10Y Treasury (2.15% yield, 0.07% volatility), negative correlation (-0.023) → diversification benefit.

Tech: R, Monte Carlo simulation, GARCH volatility forecasting | Data: 2013-2023 from Refinitiv Eikon | Output: Published comparative analysis on ResearchGate

**Authors**

Youssef LOURAOUI — youssef.louraoui@essec.edu
Youssouf BANCÉ — youssouf.bance@essec.edu

Université Paris-Saclay, M2 Risk & Asset Management (GRA) | Academic year 2023-2024

Status: Research-ready | Reproducibility: Full code + notebooks + data
