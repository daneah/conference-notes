# "Predicting the future with statistical and machine learning models" by Rebeca Sarai

## Time series

Sequence of measurements of the same set of variables over time.
There are many components:

* Observed pattern
* Trend
* Seasonality
* Random factor


## Use case

Predicting bitcoin's price.
Using data from a Kaggle competition: open, close, and market cap.


## ARIMA

Auto-Regressive Integrated Moving Average.
Statistical model for time series forecasting.
Assesses the stationarity of the process-properties of the series that are not time-dependent.

Need to determine:

* Order of autoregression
* Degree of differencing
* Order of moving average

Can tweak these and look at various metastats to determine if the model is appropriate.
ARIMA works best when data exhibits stability over time with few outliers;
didn't work well for bitcoin price forecasting.


## Prophet

Timeseries forecasting tool built by Facebook.
Doesn't require timeseries to have stationarity.
Fits bitcoin price much better, but still not perfect.


## Neural networks

Long short-term memory (LSTM) retains memory cells as long-term or short-term.
Recurrent neural network (RNN) that can use previous information to predict future information.
Fits very well to bitcoin price.


## Miscellaneous

`statsmodels` library for doing ARIMA
`keras` with TensorFlow backend for LSTM implementation
