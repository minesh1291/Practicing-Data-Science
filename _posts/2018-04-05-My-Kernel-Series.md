---
layout: post
title:  "My Kernel Series"
date:   2018-03-27
tags: [Kernel, Python, Notebook, House Pricing, Kaggle]
---

# My Kernel Series
Under Construction...

1. Minimal [Kernel](https://www.kaggle.com/mineshjethva/let-s-do-the-minimal) LB: 0.60109
  * NaN =&gt; Median
  * LinearRegression

2. Minimal + Normalized X [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x) LB: 0.30013
  * NaN =&gt; Median
  * LinearRegression(Normalized X)

3. Minimal + Normalized X,y [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-y) LB: 0.14305
  * NaN =&gt; Median
  * LinearRegression(Normalized X)
  * y = log2(y)

4. Minimal + Normalized X skew,y [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y) LB: 0.14104
  * NaN =&gt; Median
  * LinearRegression(Normalized X)
  * y = log2(y)
  * X = log2(X) if abs(skew) &gt; 1.7 &amp; no Inf issues

5. Minimal + Normalized X skew,y + filter low Var [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-exploratory) LB: 0.13764
  * NaN =&gt; Median
  * LinearRegression(Normalized X)
  * y = log2(y)
  * X = log2(X) if abs(skew) &gt; 1.7 &amp; no Inf issues
  * filter X if Variance < 0.2 and not correlated with target y

6. Normalized X,y + dummy [Kernel](https://www.kaggle.com/mineshjethva/the-minimal-normalize-x-skew-y-categoricals) LB: 0.13817
  * NaN =&gt; Median
  * LinearRegression(Normalized X)
  * y = log2(y)
  * X = log2(X) if abs(skew) &gt; 1.7 &amp; no Inf issues
  * dummy categorical features
  * ElasticNetCV

6. Minimal + Normalized X + NaN Imput [Kernel]() LB: ...
  * NaN =&gt; Most Freq
  * LinearRegression(Normalized X)
 
