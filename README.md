# Python-Vasicek-Model-LIBOR
This study evaluates the financial viability of a five-year interest rate swap in which Party A agrees to pay a fixed annual rate of 3.3% while receiving a floating rate tied to 3-month LIBOR, capped at 5%.


This Python script evaluates the financial viability of a five-year fixed-for-floating interest rate swap, where the fixed-rate payer agrees to pay 3.3% annually and receive a 3-month LIBOR rate capped at 5%. The analysis uses the Vasicek model to simulate 1,000 interest rate paths, based on an initial LIBOR of 3.45%, a long-term mean of 3.0%, volatility of 1%, and a mean reversion speed of 0.2.

LIBOR paths are generated quarterly over five years using the Vasicek stochastic differential equation. The script calculates quarterly cash flows for both swap legs: fixed payments are made semi-annually, floating payments are received quarterly and subject to the 5% cap. A 0.1% annual management fee is also deducted. The Net Present Value (NPV) of each path is then computed using LIBOR as the discount rate.

The hypothesis assumed that because LIBOR starts above the fixed rate, the swap would generate early profits, with the 5% cap acting as protection against rare rate spikes. However, simulation results disprove this expectation. LIBOR’s mean reversion toward 3.0% occurred faster than anticipated, dropping below the fixed rate by year 2. As a result, early gains were outweighed by later losses.

The mean NPV across all simulations is –$67,750, with only 46.3% of scenarios resulting in profit. The 5% cap was triggered in just 7.5% of cases, offering minimal protection. The NPV distribution is left-skewed, indicating frequent small-to-moderate losses and a few extreme ones, while gains were limited and infrequent.

These results show that even a slight downward trend in interest rates can undermine the profitability of fixed-rate payer positions. The cap, though present, is ineffective in low-volatility environments where extreme upward deviations in rates are rare.

This analysis emphasizes the risks of betting on static or rising rates in a mean-reverting, low-volatility context. For future strategies, instruments like floors or collars could better stabilize cash flows. Alternatively, reversing the position becoming the floating-rate payer might benefit more from anticipated downward trends. The Vasicek model proves useful for stress-testing swap structures under dynamic rate environments, and further extensions could include macroeconomic shocks or credit risk.
