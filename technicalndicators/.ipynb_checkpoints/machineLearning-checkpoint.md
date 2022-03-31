# **Machine Learning**
---



# Baseline Model - Accuracy Distribution 
---
- Sklearn's `accuracy_score()`:
    - fraction of labels correctly classified by classification model 
    - takes true labels and predicted labels as arguments 
    - returns accuracy as a float value 
- Control group to refer back to as model becomes more complex 

# ARIMA - AutoRegressive Integrated Moving Average 
---
- uses historical time series data to predict future data trends 
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
    - used alongside ARIMA to help find patterns from historical data
    - ignore the first value -> comparing itself to only itself 
    - +1 = perfectly positive correlation 
    - -1 = perfectly negative correlation 



# Sentiment Analysis
---




# XGBoost Feature Selection 
---
- optimized distributed gradient boosting library 
- implements machine learning under *Gradient Boosting* framework
    - technique used for predictive models mostly with regression/classification procedures 
    - often setup in *decision tree* format 
        - `j` = tree number terminal nodes 
            - controls number of times variables in a model interact 
            - `j-1` = number of interactions
            - too little or too many interactions isn't good 
    - *regularization* to prevent overfitting
        - eliminate degradating by constraining fitting procedure
        - `M` = common param -> denotes number of iterations of GB
            - number of decision trees in entire model where the decision tree is the base learner 
        - larger number of GB iterations reduces training errors 
        - too many GB iterations = overfitting 
        - depth of trees another regularization parameter 
- 






---
# References
- [Data Science Parichay: Sklearn's accuracy_score](https://datascienceparichay.com/article/get-accuracy-of-predictions-in-python-with-sklearn/)
- [Investopedia: ARIMA](https://www.investopedia.com/terms/a/autoregressive-integrated-moving-average-arima.asp)
- [GeeksforGeeks: AutoCorrelation](https://www.geeksforgeeks.org/autocorrelation/)
- [Duke: ARIMA](https://people.duke.edu/~rnau/411arim.htm)
- [statsmodels.tsa.arima.model.ARIMA](https://www.statsmodels.org/stable/generated/statsmodels.tsa.arima.model.ARIMA.html)
- [Toward Data Science: .fit(), .predict(), .fit_predict()](https://towardsdatascience.com/fit-vs-predict-vs-fit-predict-in-python-scikit-learn-f15a34a8d39f)
- [XGBoost Documentation](https://xgboost.readthedocs.io/en/stable/)
- [CFI: Gradient Boosting](https://corporatefinanceinstitute.com/resources/knowledge/other/gradient-boosting/)
- 
