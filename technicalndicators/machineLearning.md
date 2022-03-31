# **Machine Learning**
---



# Baseline Model - Accuracy Distribution 
---
- Sklearn's `accuracy_score`:
    - fraction of labels correctly classified by classification model 
    - takes true labels and predicted labels as arguments 
    - returns accuracy as a float value 
- Control group to refer back to as model becomes more complex 

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
- AutoCorrelation Function
    - how data points of the same time series correlate to one another over a lag
    - vary the lag to see relationship between past and future values 
    - used alongside ARIMA to help find repeating periodic patterns 
    - looking for patterns from historical data 
    - ignore the first value -> comparing itself to only itself 
    - +1 = perfectly positive correlation 
    - -1 = perfectly negative correlation 
-    
    






# Sentiment Analysis






# XGBoost Feature Selection 







---
# References
- [Data Science Parichay: Sklearn's accuracy_score](https://datascienceparichay.com/article/get-accuracy-of-predictions-in-python-with-sklearn/)
- [Investopedia: ARIMA](https://www.investopedia.com/terms/a/autoregressive-integrated-moving-average-arima.asp)
- [GeeksforGeeks: AutoCorrelation](https://www.geeksforgeeks.org/autocorrelation/)