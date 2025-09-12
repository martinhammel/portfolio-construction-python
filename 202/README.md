Style Analysis and Style Drift with QQQ

This project applies Sharpe Style Analysis to the Nasdaq-100 ETF (QQQ) to see how its exposures to sector and factor ETFs evolve over time. The method constrains weights to be positive and sum to one, so they can be interpreted as portfolio allocations.

What I Did:

Prepared the data

Pulled monthly adjusted prices for QQQ and a set of building block ETFs (SPYG, SPYV, OEF, IWM, XLK, XLC, XLY, SPY) from Yahoo Finance.

Converted prices into monthly returns with resample('M').last().pct_change().

Ran style analysis

Used an optimizer (SLSQP) to find long-only weights that minimize tracking error between QQQ and the ETF portfolio.

Reported static weights, monthly tracking error, and style R^2.

Extended the analysis to a rolling 60-month window to capture time-varying exposures.

Interpreted results

Static analysis: QQQ looks like ~50% Technology (XLK), ~25% Growth (SPYG), with smaller tilts to Consumer Discretionary (XLY) and Communication Services (XLC).

Rolling analysis: From 2019 onward, exposures stabilize around Technology + Growth, consistent with QQQ’s composition. Early estimates (pre-2018) are noisier due to overlapping benchmarks.

Key Takeaways:

QQQ’s style is dominated by Technology and Growth, with secondary contributions from XLY and XLC.

The Growth/Tech tilt is persistent over time, even if smaller sector weights shift.

Rolling style analysis is a practical way to visualize style drift, though early-window noise should be interpreted with caution.