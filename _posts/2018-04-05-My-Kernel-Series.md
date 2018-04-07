---
layout: post
title:  "My Kernel Series"
date:   2018-04-05
tags: [Kernel, Python, Notebook, House Pricing, Kaggle, Competition, Linear Regression]
---

# My Kernel Series
For Kaggle House Pricing Competition
Under Construction...

1. Minimal [Kernel](https://www.kaggle.com/mineshjethva/let-s-do-the-minimal) LB: 0.60109
  * NaN =&gt; Median
  * LinearRegression

2. Minimal + Normalized X [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x) LB: 0.30013
  * LinearRegression(Normalized X)

3. Minimal + Normalized X,y [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-y) LB: 0.14305
  * y = log2(y)

4. Minimal + Normalized X skew,y [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y) LB: 0.14104
  * X = log2(X) if abs(skew) &gt; 1.7 &amp; no Inf issues

5. Minimal + Normalized X skew,y + filter low Var [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-exploratory) LB: 0.13764
  * filter X if Variance &lt; 0.2 and not correlated with target y

6. Normalized X,y + dummy [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-categoricals) LB: 0.13817
  * dummy categorical features
  * ElasticNetCV

7.  Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.1 LB: 0.13343
 * all previous things plus  
 * ElasticNetCV alpha optimization

8. Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.5 LB 0.12811
 * ElasticNetCV L1_ratio = 0.1
 * ElasticNetCV alpha optimization
 * Bagged with **5.** Minimal + Normalized X skew,y + filter low Var [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-exploratory) LB: 0.13764

9. Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.7 LB 0.12408
 * ElasticNetCV L1_ratio = 1
 * ElasticNetCV alpha optimization
 * Bagged with **5.** Minimal + Normalized X skew,y + filter low Var [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-exploratory) LB: 0.13764 and **8.** Beginner ElasticNet [Kernel](https://www.kaggle.com/mineshjethva/beginner-elasticnet) Ver.5 LB 0.12811


Under Construction...
Next things in the list are:

 * NaN Imputation
 * Outlier Remove
 * Ensemble
