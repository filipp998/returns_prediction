# returns_prediction
Various methods (classical ML, neural networks and time series) are used and compared to predict returns of a stock in both classification and regression.
I take just one stock - Apple (data downloaded from Yahoo Finance) for the period from the beginning of 2005 till end of June in 2021.
For regression our target is simply the percentage return of the adjusted closing price and we aim to predict it and for classification we aim to predict whether the return on the next day will be positive or negative (0 if negative, 1 if positive).

Predictions are done in the following fashion: we forecast the next day return using the information about past days, then add this 
