# returns_prediction
Various methods (classical ML, neural networks and time series) are used and compared to predict returns of a stock in both classification and regression.
I take just one stock - Apple (data downloaded from Yahoo Finance) for the period from the beginning of 2005 till end of June in 2021.
For regression our target is simply the percentage return of the adjusted closing price and we aim to predict it and for classification we aim to predict whether the return on the next day will be positive or negative (0 if negative, 1 if positive).

Predictions are done in the following fashion: 

***For ML algorithms :***
For each day the features are 5 days lagged returns. I simply use basic functionality of sklearn and keras to perform all the needed operations. Of course, the model is fitted only to training set and then predictions are made using the test set.

***For Time Series Analysis :***
Here the features are determined via examining ACF and PACF of the returns. Then I again firstly fit the ARMA type of model to training set and then make one step predictions using the training and test sets. Here comes a little fun: to make a "fair" competition between the ML and time series models we want them to perform the same exact task. The problem is that the data we used for ML algorithms is not suitable for ARMA model. So to accomplish this task I first fit ARMA model to the training set, then store coefficients and then manually (in a loop) compute new predictions using the test data and these coefficients by applying the mathematical formula of the ARMA model. In the process I also realize that white noise in the ARMA specification should have approximately the same variance as the returns in order not to overpower them and not to absolutely dominate anything.

To summarize, this mini-project is intended to make the ***comparison*** between various models and their efficiencies **using the specific forecasting method**.


