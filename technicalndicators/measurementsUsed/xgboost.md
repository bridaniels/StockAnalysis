# XGBoost
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
        
        
        
        
        
        
        

# References
- [XGBoost Documentation](https://xgboost.readthedocs.io/en/stable/)
- [CFI: Gradient Boosting](https://corporatefinanceinstitute.com/resources/knowledge/other/gradient-boosting/)