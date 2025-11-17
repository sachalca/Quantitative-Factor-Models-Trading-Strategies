This project compares two systematic equity trading approaches using Python and SQL. Data is pulled from an MSSQL database, cleaned, normalized by date, 
and used to generate monthly signals that drive a long/short backtest.

The first strategy builds a value, momentum and quality composite factor model. The factor group weights are optimized with SciPy’s COBYLA method to maximize the annualized Sharpe ratio. 
The strategy rebalances monthly and takes long positions in the highest-scoring stocks and short positions in the lowest. In testing, it produced a 2.09% cumulative return and a Sharpe ratio of 0.608.

The second strategy trains a Random Forest Regressor each month using a rolling historical window of momentum features. It predicts next-month cross-sectional returns and constructs long and short baskets 
from the highest and lowest predictions. This model performed significantly better, reaching a 127.09% cumulative return and a Sharpe ratio of 1.689.

Both strategies use the same backtesting logic: monthly rebalancing, long 15 and short 5, equal weighting, no lookahead bias, and return attribution based on the following month’s actual performance.

The project demonstrates end-to-end implementation of data ingestion, preprocessing, signal creation, model training, portfolio construction, and performance evaluation, 
providing a compact framework for exploring systematic trading ideas.
