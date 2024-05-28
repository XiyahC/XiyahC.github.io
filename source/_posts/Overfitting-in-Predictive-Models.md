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
*It's always good to add self experience to these questions.

<span style="color:red">Q: How can you avoid overfitting in predictive models?</span>

A: A model is overfitting when it describes the noise in the data rather than the underlying relationship.  
Solutions:  
1. Reduce model complexity. e.g. Run forward stepwise regression. Add predictor to the model which has the smallest p-value, until the stopping criterion is met.  
2. Regularization. Ridge and Lasso.  

<span style="color:red">Q: Explain a little more about Ridge and Lasso Regularization?</span> 

A: At a high level, in ridge, loss function or the residual sum of square errors is minimized by adding a shrinkage quantity. Ridge regression makes use of lambda ($\lambda$), act as a tuning parameter for the model.  

**Lambda increases, the coefficient estimates tend towards zero.**

Lasso has the capability of selecting variables by penalizing the high value coefficients. Ridge regression will shrink them close to zero but not necessarily make them zero, lasso will make them actually zero. In other words, the ridge regression model will include almost all predictors whereas lasso will perform feature selection.  

<span style="color:red">Q: Are there any other ways you can think of using which you can prevent overfitting in models?</span>

A: cross-validation, generate multiple smaller train-test splits, e.g. k-fold, can be used to tune the parameters. By generalizing well, can avoid potential overfitting.

----

Some extra questions:

- What is the difference between forward stepwise and backward stepwise regression? (One is by adding predictors, the other is by subtracting predictors?)

The forward selection approach starts with nothing and adds each new variable incrementally, testing for statistical significance. The backward elimination method begins with a full model loaded with several variables and then removes one variable to test its importance relative to overall results.

- Why does Lasso tend to shrink estimates to zero whereas Ridge shrinks close to zero but not zero?

Because the **shape of the constraint** in LASSO is a diamond, the least squares solution obtained might touch the corner of the diamond such that it leads to a shrinkage of some variable. However, in ridge regression, because it is a circle, it will often not touch the axis.

![LassoRidge](https://ars.els-cdn.com/content/image/3-s2.0-B9780128136577000340-f21-05-9780128136577.jpg)