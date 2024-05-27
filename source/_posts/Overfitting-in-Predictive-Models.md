---
title: Overfitting in Predictive Models
date: 2024-05-27
tags: 
    - Book
    - DS
    - Overfitting
mathjax: true
---

Why is overfitting important?

We always look at **prediction error** when build a prediction model. Prediction error can be explained by bias + variance errors.  

<u>Bias</u>: the difference between the forecast ($\hat{y}$) and the actual ($y$) that we are trying to predict.  
<u>Variance</u>: the variability of the forecasted value and gives an estimate of the spread of the model data.  

**Underfitting**: high bias, low variance.  
Not able to capture the trend of data, happen due to insufficient data or too few features.  

**Overfitting**: low bias, high variance.  
Models fit the train data too well, perform badly on test data.  
Models fit the noise rather than the trend of data. 

------ 

<span style="color:red">Q: How can you avoid overfitting in predictive models?</span>

A: A model is overfitting when it describes the noise in the data rather than the underlying relationship.  
Solutions:  
1. Reduce model complexity. e.g. Run forward stepwise regression. Add predictor to the model which has the smallest p-value, until the stopping criterion is met.  
2. Regularization. Ridge and Lasso.  

<span style="color:red">Q: Explain a little more about Ridge and Lasso Regularization?</span> 

A: At a high level, in ridge, loss function or the residual sum of square errors is minimized by adding a shrinkage quantity. Ridge regression makes use of lambda ($\lambda$), act as a tuning parameter for the model.  

**Lambda increases, the coefficient estimates tend towards zero.**


