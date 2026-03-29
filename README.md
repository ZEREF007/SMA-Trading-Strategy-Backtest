# Trading Strategy: SMA (Simple Moving Average) Crossover Backtesting

This notebook demonstrates a quantitative trading strategy using Simple Moving Averages (SMA) and provides tools for backtesting and optimization.

## Introduction

The SMA crossover strategy is a trend-following momentum strategy that utilizes two Simple Moving Averages: a leading (short-term) SMA and a lagging (long-term) SMA.

- **LONG**: Go long when the leading SMA crosses above the lagging SMA.
- **SHORT**: Go short when the leading SMA crosses below the lagging SMA.

## Key Considerations For Future Backtesting:

- **Slippage**: Latency, spread, volatility, liquidity.
- **Infrastructure Cost**: Hosting, etc.
- **Commissions**: Can significantly impact profitability.
- **Shorting**: Costs and legal restrictions.
- **Market Impact**: The effect of trades on market prices.

## Data Download and Visualization

Historical daily OHLCV (Open/High/Low/Close/Volume) data is downloaded from Yahoo Finance for a specified ticker (e.g., BTC-USD).

The notebook includes interactive OHLCV charts and daily closing price change summaries to help visualize and understand the data.

## Backtesting the Strategy

The `test_ma` function implements the SMA crossover logic, generating buy/sell signals based on the difference between the leading and lagging SMAs and a defined `threshold`.

- **`lead`**: Short-term moving average days.
- **`lag`**: Long-term moving average days.
- **`threshold`**: Sensitivity parameter; a smaller value means more sensitivity and potentially more trades.

The strategy's performance (`Strategy`) is then compared against a simple buy-and-hold approach (`Buy-Hold`).

## Optimizing Lead/Lag Parameters

The notebook allows for iterating through various combinations of `lead` and `lag` periods to identify optimal parameters that maximize the strategy's PnL (profit and loss) compared to a buy-and-hold strategy.

A heatmap visualization is used to display the PnL differences across different `lead` and `lag` combinations, making it easy to spot high-performing parameter sets.

## Performance Details

Finally, a detailed performance report of the selected SMA strategy is generated using `pyfolio`, providing various metrics such as returns, drawdowns, and risk analysis.
