### **Credit Portfolio Risk & CDO Tranche Pricing**

Simulating credit losses and pricing structured finance tranches using Monte Carlo methods.

Banks hold thousands of loans and bonds. When borrowers default, how much do they lose? And if you package those loans into slices (tranches), how do you price each slice fairly? 
This project builds a Monte Carlo simulator to answer both questions. We model credit defaults as correlated random events (borrower 1's failure makes borrower 2's failure more likely), then simulate what happens to a portfolio under stress. 
From the loss distribution, we calculate three risk metrics: Expected Loss (average annual loss), Value at Risk (worst-case loss at 95% confidence), and Expected Shortfall (losses beyond worst-case).

For CDO tranching, we go deeper. Senior tranches get paid first and rarely lose money, so they're cheap and safe. Equity tranches absorb first losses and rarely get paid, so they're expensive and risky. We run the portfolio simulation thousands of times, track how cash flows waterfall through each tranche, and price accordingly. 
The convergence graphs show convergence: as simulation runs increase, tranche prices stabilize, proving the model works.

The catch: Accuracy depends on input assumptions (default probabilities, correlations, loss amounts). During crises, correlations spike unexpectedly, making 2008 type events invisible in historical data. This is a classroom model, not a production risk engine.

Co-authors: Youssouf Bancé, Youssef Louraoui (Université Paris-Saclay, M2 GRA)
Date: December 2023 | Method: Monte Carlo simulation + convergence testing | Reproducible notebooks on GitHub
