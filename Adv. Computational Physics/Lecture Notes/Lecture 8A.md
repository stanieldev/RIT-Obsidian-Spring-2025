**Name:** Stanley Goodwin
**Date:** 3/7/2025

---
### Recap of Probability Theory
#### Types of Random Variables
 - Continuous Random Variables: $x\sim P(x)$
 - Discrete Random Variables: $\alpha\sim P(\alpha)$

#### Conditional Probability
**Bayes Theorem**
$$\begin{align}
P(A)P(B|A)&=P(B)P(A|B)
\end{align}$$
Bayesian Statistics better describes information and entropy.

#### Sum of Random Variables
Suppose 2 independent random variables, $x_1\in P_1$ and $x_2\in P_2$.
$$\begin{align}
s&=x_1+x_2\\
\braket{s}&=\braket{x_1}+\braket{x_2}\\
\braket{s^2}&=\braket{x_1^2}+\braket{x_2^2}+2\braket{x_1x_2}\\
\end{align}$$
We can find standard deviation:
$$\begin{align}
\braket{s^2}-\braket{s}^2&=\braket{x_1^2}+\braket{x_2^2}+2\braket{x_1x_2}-(\braket{x_1}+\braket{x_2})^2\\
\braket{s^2}-\braket{s}^2&=\braket{x_1^2}+\braket{x_2^2}+2\braket{x_1x_2}-\braket{x_1}^2-2\braket{x_1}\braket{x_2}-\braket{x_2}^2\\
\braket{s^2}-\braket{s}^2&=\braket{x_1^2}-\braket{x_1}^2+\braket{x_2^2}-\braket{x_2}^2+2\braket{x_1x_2}-2\braket{x_1}\braket{x_2}\\
\Aboxed{\sigma_{s}^2&=\sigma_{x_1}^2+\sigma_{x_2}^2+2\left(\braket{x_1x_2}-\braket{x_1}\braket{x_2}\right)}
\end{align}$$
Since the events are independent, then:
$$\begin{align}
\sigma_{s}^2&=\sigma_{x_1}^2+\sigma_{x_2}^2+2\braket{x_1x_2}-2\braket{x_1}\braket{x_2}\\
&=\sigma_{x_1}^2+\sigma_{x_2}^2+2\braket{x_1}\braket{x_2}-2\braket{x_1}\braket{x_2}\\
\Aboxed{\sigma_{s}^2&=\sigma_{x_1}^2+\sigma_{x_2}^2}
\end{align}$$
We can also look at scaling a random variable. Then:
$$\begin{align}
s&=nx\\
\braket{s}&=n\braket{x}\\
\sigma_{s}^2&=n\sigma_{x}^2
\end{align}$$





