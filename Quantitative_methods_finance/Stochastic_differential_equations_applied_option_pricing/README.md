### **Option Pricing with Stochastic Differential Equations**

Implementing Black-Scholes, CIR, and Vasicek models using finite difference methods.

Most finance textbooks teach option pricing theory. This project teaches the implementation. 
We built numerical solvers in Python for three canonical models: Black-Scholes (stock options), Cox-Ingersoll-Ross (interest rate derivatives with non-negative rates), and Vasicek (interest rate derivatives allowing negative rates). 
The key insight: different models suit different problems. Black-Scholes works when you assume constant volatility and no dividends. CIR works when you need rates to stay positive (mean-reverting behavior). Vasicek is simpler but allows negative rates, which mattered less before 2015.

We used finite difference methods (FDM) and the Crank-Nicolson scheme to discretize the underlying PDEs into solvable lattices. 
Python + Jupyter + NumPy handles the math; matplotlib visualizes the results in 3D surface plots. The bottleneck is not the theory, it is parameter tuning and ensuring numerical stability when volatility is stochastic.

Real trade-offs: Black-Scholes is elegant but assumes constant volatility (empirically false). CIR prevents negative rates but the square-root diffusion creates numerical instability. Vasicek is unstable with negative rates (post-2008, a real problem). In production, you'd use ensemble methods or regime-switching approaches.

This is coursework, not a trading system. But it is a solid foundation for understanding how derivatives pricing actually works (not analytically, but via the computations behind).

Coauthors: Youssouf Bancé, Youssef Louraoui (Université Paris-Saclay, M2 GRA)
Date: December 2023 | Code: Full reproducibility | Jupyter notebooks available
