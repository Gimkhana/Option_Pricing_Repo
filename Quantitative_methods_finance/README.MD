[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)](https://www.python.org/)

# Option Pricing with Numerical Methods

**Solving financial PDEs for derivatives pricing. Comparing Black-Scholes, CIR, and Vasicek models using Finite Difference and Crank-Nicolson methods.**

---

Implements three major option pricing models using numerical methods to solve partial differential equations (PDEs) in Python + Jupyter.

**Models included:**
- **Black-Scholes** (stock options, Finite Difference)
- **CIR** (interest rates, Crank-Nicolson)
- **Vasicek** (bond options, Crank-Nicolson)

---

## Application

Analytical solutions don't always exist for complex derivatives. Numerical methods bridge the gap between theory and practice.

| Model | Use Case | Key Insight |
|-------|----------|------------|
| **Black-Scholes** | European stock options | Closed-form exists, but FDM shows robustness |
| **CIR** | Interest rate derivatives | Square-root diffusion prevents negative rates |
| **Vasicek** | Bond pricing | Mean-reverting interest rates |

---

## Key challenges

✓ **Parameter tuning** — Grid search + hyperparameter optimization needed  
✓ **Computational cost** — NumPy vectorization, GPU acceleration help  
✓ **Numerical stability** — Crank-Nicolson balances accuracy + efficiency  

---


## Models used

### Black-Scholes (Finite Difference)

**Solves:** European call/put option pricing  
**Method:** Explicit/implicit finite difference  
**Key output:** 3D surface (stock price × time → option value)

**Assumptions:**
- Constant volatility
- No dividends
- European exercise only

---

### Cox-Ingersoll-Ross (Crank-Nicolson)

**Solves:** Interest rate derivatives (bond options)  
**Method:** Crank-Nicolson (average of explicit + implicit)  
**Key output:** Interest rate evolution with mean reversion

**Advantages:**
- Guarantees non-negative rates (square-root diffusion)
- Mean-reverting behavior matches empirical data

---

### Vasicek (Crank-Nicolson)

**Solves:** Zero-coupon bond pricing  
**Method:** Crank-Nicolson  
**Key output:** Bond price surface (interest rate × time to maturity)

**Trade-off:**
- ✓ Simple, closed-form exists
- ✗ Allows negative rates (unrealistic in some markets)

---

## Results and findings

### Black-Scholes surface

Out-of-the-money options show minimal value; in-the-money calls rise linearly. Time decay accelerates near expiration.

### CIR mean reversion

Interest rates oscillate around long-term average θ. Volatility depends on rate level (square-root property).

### Vasicek bond prices

As maturity approaches, bond price converges to par value. Interest rate sensitivity decreases with time.

---

## Libraries used

- **NumPy** — Array operations, random generation
- **SciPy** — Banded matrix solver (sparse systems)
- **Matplotlib** — 3D visualization
- **Jupyter** — Interactive notebooks + inline visualization

---

## Known limitations

1. **Black-Scholes:** Assumes constant volatility (doesn't capture volatility smile/skew)
2. **CIR:** Parameter calibration challenging; non-linearity can cause convergence issues
3. **Vasicek:** Allows negative rates; less realistic in current markets

---

## Recommendations for improvement

- **Parameter tuning:** Implement grid search or Bayesian optimization
- **Stability:** Add variance reduction techniques for Monte Carlo
- **Validation:** Compare against Bloomberg/market prices

---

## References

- Hull, J. C. (2017). *Options, Futures, and Other Derivatives*, 10th ed.
- Black, F., & Scholes, M. (1973). "The Pricing of Options and Corporate Liabilities."
- Cox, J. C., et al. (1985). "A Theory of the Term Structure of Interest Rates."
- Vasicek, O. A. (1977). "An Equilibrium Characterization of the Term Structure."

---

## Authors

**Youssef Louraoui** — M2 Risk & Asset Management, Université Paris-Saclay  
**Youssouf Bancé** — M2 Risk & Asset Management, Université Paris-Saclay

---

**Date:** December 2023 | **Status:** Academic project | **Reproducibility:** Full code provided