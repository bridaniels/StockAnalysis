# XGBoost
---

- optimized distributed gradient boosting library 
- implements machine learning under *Gradient Boosting* framework
- Parallel Tree Boosting (GBDT, GBM) to solve larger datasets 
    - solves various tree problems at the same time 
    - sums up results from each tree to get answer 
    - takes various weaker models and brings them together for a stronger answer 

- Gradient Boosting
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
        
- Boosting
    - sequential technique
    - combines weak learners to improve prediction accuracy 
        - weak learners just slightly better than random guessng 
    - at time `t`, outcomes are weighed based on outcomes of `t-1`
        - correct predictions given lower weight
        - miss-classified predictions given higher weight 
    - building a weak model, making conclusions about various feature performance/parameters and using those conclusions to have a stronger model 
        
- XGBClassifier: 
    - extracts important features used for neural networks 
    - Machine Learning Model to fit data 
        - `model = xgboost.XGBClassifier()`
        - `model.fit(X_train, y_train)`
    - Predict output by passing `X_test` and stored real target in `expected_y`
        - `expected_y = y_test`
        - `predicted_y = model.predict(X_test)`
    - Print Classification Report and Confusion Matrix for Classifier 
        - `print(metrics.classification_report(expected_y,predicted_y))`
        - `print(metrics.confusion_matrix(expected_y, predicted_y))` 

# XGBoost:
- base learners: tree ensembles
    - set of Classification and Regression Trees (CART)
    - trees grown one after another to reduce misclassification in future iterations 
    - each tree gives a different prediction score based on data seen 
    - scores of each tree summed up to get the final score 
- Tuning Params: 
    - `learning_rate`: step size shrinkage -> prevents overfitting -> range is [0,1]
    - `max_depth`: how deep each tree can grow during boosting round
    - `subsample`: % of samples used per tree (low might be underfitting)
    - `colsample_bytree`: % features used per tree (high might be overfitting)
    - `n_estimators`: number of trees you want to build 
    - `objective`: determines loss function 
        - `reg:linear` for regression 
        - `reg:squarederror` loss function for regression predictive modeling problems
        - `reg:logistic` for classification w/ only decision
        - `binary:logistic` for classification w/ probability
    - `gamma`: wether given node will split based on expected reduction in loss after split 
        - higher value = fewer splits 
        - only for tree-based learners
    - `alpha`: L1 regularization on leaf weights (large value = more regularization)
    - `lambda`: L2 regularization on leaf weights -> smoother than L1 regularization 
        
        
        
        

# References
---
- [XGBoost Documentation](https://xgboost.readthedocs.io/en/stable/)
- [CFI: Gradient Boosting](https://corporatefinanceinstitute.com/resources/knowledge/other/gradient-boosting/)
- [XGBoost: XGBClassifier](https://www.projectpro.io/recipes/use-xgboost-classifier-and-regressor-in-python)
- [XGBoost: Intro](https://www.datacamp.com/community/tutorials/xgboost-in-python)
- [XGBoost: reg:squarederror](https://machinelearningmastery.com/xgboost-loss-functions/)