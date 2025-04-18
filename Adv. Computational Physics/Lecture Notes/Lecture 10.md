**Name:** Stanley Goodwin
**Date:** 4/4/2025

---
## Gaussian Process Regression with Custom Kernels
### Regression in Physics
Regression is the process of approximating a function from a finite data set.
### The Curse of Dimensionality
As you add dimensions, the number of points increases exponentially.
The only way to overcome it is to imbue "prior knowledge" about the function we aim to learn with our regression model.

### Prior Probability Distribution
A prior represents our initial belief about the function before seeing data.
We constrain the function space in a controlled fashion.
 - We can assume it's a linear combination of basis functions with coefficients.
 - These coefficients come from a probability distributions.
These features define an ensemble of possible functions before data is observed.

#### Example
We start with a polynomial function of degree 5 over interval $x\in[-1,1]$:
$$f(x)=c_0+c_1x+c_2x^2+c_3x^3+c_4x^4+c_5x^5$$
where $c_i$ are random variables with distribution calculated such that the function and its derivative are more likely to be within the controlled range.
$$p[f]\propto\exp\left(-\dfrac{t}{2}\int_{-1}^1f(x)^2\ dx-\dfrac{\kappa}{2}\int_{-1}^1f'(x)^2\ dx\right)$$
Where $t,\kappa$ are "hyperparameters" to help control the probability calculation.
The function term makes it more likely in the interval, derivative term constraints it to be smooth.

### Posterior Probability Distribution
The posterior favors functions that pass near to the observed points while account for uncertainty.
The posterior mean gives the most probable function, variance quantifies uncertainty.
The larger the standard deviation, the function is less constrained by corresponding observation.
The combination of data and our prior defines an updated ensemble probability distribution.

The posterior distribution is derived from Bayes Theorem as:
$$p(f|D)=p[f]\cdot\dfrac{p(D|f)}{p(D)}\propto p[f]\cdot e^{\sum\tfrac{1}{2\sigma_\alpha^2}\left(f(x_\alpha)-f_\alpha\right)^2}$$
where $D$ is the data and $f$ is the chosen function.

---

### Mathematical Encoding of the Prior
We can represent functions as a sum over a set of basis functions $T_s(x)$:
$$\begin{align}
f(x)&=\sum_{s=1}^S\xi_sT_s(x)
\end{align}$$
The prior is a probability distribution over the coefficients $\xi_s$:
$$\begin{align}
p(\xi)&\propto e^{-S[f]}\\
S[f]&=\dfrac{1}{2}\sum_{s,s'=1}^SA_{ss'}\xi_s\xi_{s'}
\end{align}$$
For example, action could be determined in terms of hyperparameters as the following:
$$\begin{align}
S[f]&=\int_D\left[\dfrac{t}{2}f(x)^2+\dfrac{\kappa}{2}(\vec\nabla f)^2+\dfrac{\epsilon}{2}\sum_s\xi_s^2\right]
\end{align}$$
From the prior, we define a kernel function which represents how function values at different points are correlated and fully encodes our prior information:
$$\begin{align}
K(x,x')&=\braket{f(x)f(x')}=\sum_{s,s'=1}^S[A^{-1}]_{ss'}T_s(x)T_{s'}(x')
\end{align}$$
Given a dataset composed by $(x_\alpha,E_\alpha,\sigma_\alpha)$, we calculate the kernel matrix as follows:
$$\begin{align}
\bar{K}_{\alpha\beta}&=K(x_\alpha,x_\beta)+\sigma_\alpha^2\delta_{\alpha\beta}
\end{align}$$
The posterior expectation value and variance of $f(x)$ are given by:
$$\begin{align}
\braket{f(x)}&=\sum_{\alpha,\beta}K(x,x_\alpha)[\bar{K}^{-1}]_{\alpha\beta}E_\beta\\
\sigma^2_\text{post}(x)&=K(x,x)-\sum_{\alpha,\beta}K(x,x_\alpha)[\bar{K}^{-1}]_{\alpha\beta}K(x_\beta,x)
\end{align}$$
