# ARIMA - AutoRegressive Integrated Moving Average 
---
- uses historical time series data to predict future data trends 
- assumption that past values have effect on future values 
- gauges strength of one dependent variable relative to other changing variables 
- AutoRegression: predicts future values based on past values 
- Integrated: data values replaced with difference between data value and the difference between previous values 
- Moving Average: lagging (based on past prices) indicator measuring data value and residual error from the moving average
- `p`: lag order -> number of lags of Y used as predictors in a model
- `d`: degree of differencing -> times the raw observations are differenced 
    - subtract previous value from current value 
    - minimum number of differencing needed to make the series stationary 
- `q`: order of the moving average -> moving average window size
- ARIMA(p,d,q):
    - `(0,0,0)` = errors uncorrelated across time
        - white noise
    - `(1,0,0)` = first-order autoregressive model 
        - stationary and autocorrelated
    - `(0,1,0)` = random walk
        - `y` is not stationary 
    - `(0,0,1)` = no lag order, no differencing, lags at 1  
    - `(1,1,0)` = differenced first-order autoregressive model
        - errors of random walk are autocorrelated 
        - add one lag of the dependent variable to prediction equation 
        - regress the first difference of `y` by lagging one period
        
        
### AutoCorrelation Function
- how data points of the same time series correlate to one another over a lag
- used alongside ARIMA to help find patterns from historical data
- ignore the first value -> comparing itself to only itself 
- +1 = perfectly positive correlation 
- -1 = perfectly negative correlation 
    
    
### Statsmodels `ARIMA()`:
- ARIMA(observed time series, order = (p,d,q))
- incorporates both exogenous regressors and trend components through 'regression with ARIMA errors'
- differs from `SARIMAX` which treats trend components separately from exogenous regressors 
    
    
### Sklearn's `.fit()`:
- trains model using input training and data 
- clears any attributes already stored on the estimator 
- perform parameter and data validation 
- estimate the attributes out of the input data 
- store the model attributes 
- return fitted estimator 



# References
--- 
- [Duke: ARIMA models for time series forecasting](https://people.duke.edu/~rnau/411arim.htm)
- [Investopedia: ARIMA](https://www.investopedia.com/terms/a/autoregressive-integrated-moving-average-arima.asp)
- [GeeksforGeeks: AutoCorrelation](https://www.geeksforgeeks.org/autocorrelation/)
- [statsmodels.tsa.arima.model.ARIMA](https://www.statsmodels.org/stable/generated/statsmodels.tsa.arima.model.ARIMA.html)
- [Toward Data Science: .fit(), .predict(), .fit_predict()](https://towardsdatascience.com/fit-vs-predict-vs-fit-predict-in-python-scikit-learn-f15a34a8d39f)