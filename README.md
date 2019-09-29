Lasso and Ridge regression are linear regression in which regularization is performed. By regularization, overfitting can be prevented.

A normal linear model is as follows (sorry for the unrendered math expressions).

$ y = \Sigma_{i=1}^{n} w_i x_i + w_0$

It has n weights and n-1 number of features excluding the bias term ($w_0$). If there is only one feature, $w_1$ represents slope and $w_0$ represents intercept. The goal of linear regression is to optimize weights so that the cost function is minimized. The cost function shows how far the model is from the actual data. It can be written as follows.

$ L = \Sigma_{j=1}^{m} (\hat{y}^j - y^j)^2 = \Sigma_{j=1}^{m} (\Sigma_{i=0}^n w_i x_i^j - y^j)^2$ 

In the expression above, I have assumed $x_0$ is 1.

If the model is too complicated (e.g. too many features), it causes overfitting. The model tries to follow the  data points too much and "rambles," giving new data points in between inaccurate predictions. 

One of the techniques to prevent this is regularization. This means putting a new term in the cost function to penalize too large weights in the model. The combination of regularization and linear regression is called Lasso and Ridge regression.

**Lasso Regression**

In Lasso Regression, the penalty term is L1 norm of the weights i.e. the sum of the absolute values of the weights.

$ L = \Sigma_{j=1}^{m} (\hat{y}^j - y^j)^2 = \Sigma_{j=1}^{m} (\Sigma_{i=0}^n w_i x_i^j - y^j)^2 + \lambda \Sigma |w_i|$

Lasso stands for Least Absolute Shrinkage and Selection Operator.

**Ridge Regression**

In Ridge Regression, the penalty term is L2 norm of the weights i.e. the sum of the square of the weights.

$ L = \Sigma_{j=1}^{m} (\hat{y}^j - y^j)^2 = \Sigma_{j=1}^{m} (\Sigma_{i=0}^n w_i x_i^j - y^j)^2 + \lambda \Sigma (w_i)^2$

In both of them, if weights take large values the cost function will be penalized. Regularization shrinks weights and decreases model complexity and overfitting. $\lambda$ decides how strong the regularization is. If it's 0, it will be a normal linear regression since the penalty term disappears. If is quite large, the term gets dominant and all the weights will approach 0.

What's interesting in Lasso regression is some features can lead to zero. So Lasso regression is not only good for suppressing overfitting but for feature selection. It's easier to interpret the model if the number of features is less. 

But how do some features get zero in Lasso and not in Ridge? In this article, let me show you an intuitive and visual explanation for that.
