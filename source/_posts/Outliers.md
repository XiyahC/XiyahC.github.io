---
title: Some Applied Statistics Notes about Outliers
date: 2023-12-12
tags: 
   - DS Prep
   - outliers
mathjax: true
---

From JHU AMS class EN.553.613 ASDA 2023 Fall.

Notice Outliers:

1. Plot residuals($e_i=y_i-\hat{y_i}$) vs. $X$ or $\hat{y}$
2. box plot
3. dot plot
4. stem plot
5. If > 4|$e_i^\*$|, where

   $e_i^\*=\frac{(e_i-\bar{e})}{\sqrt{MSE}}=\frac{e_i}{\sqrt{MSE}}=semistudentized\;residuals$, where

   $MSE=\frac{SSE}{n-p}=\frac{\sum_{i=1}^{N}(y_i-\hat{y_i})^2}{n-p}$, where

   p is the number of the estimators.

6. We have

   $var(e_i)=\theta^2(1-h_{ii})$,

   $cov(e_i, e_j)=-\theta^2h_{ij}$,

   $h_{ij}=X_i(X^TX)^{-1}X_j^T$,

   $h_{ii}(leverage)=X_i(X^TX)^{-1}X_i^T$.

   By the rule of thumb, we can detect outlier with respect to X while $h_{ii} > \frac{2p}{n}$. We say that $h_{ii} > 0.5$ as high leverage, $0.2 < h_{ii} < 5$ as moderate leverage.

7. ESR = $t_i$ can only detect outliers with respect to $X$.

Test for Outliers:

1. Bonferroni Correction:

   $|t_i| = |\frac{d_i}{s(d_i)}| > t(1-\frac{\alpha}{2n}, n-p-1)$, outlier.

   where $d_i = \frac{e_i}{(1-h_{ii})}$.
