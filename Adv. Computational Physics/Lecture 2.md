**Name:** Stanley Goodwin
**Date:** 1/24/2025

---
### Error in Trapezoid Summation
Consider the integral:
$$\int_a^b f(x)\ dx$$
Let $x_k=a+kh$, and consider a particular slice of the integral between $x_{k-1}$ and $x_k$.
Performing a Taylor expansion of $f(x)$ about the point $x_{k-1}$:
$$f(x)=\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{n!}(x-x_{k-1})^n$$
Calculating the individual slice of the integral, we see that:
$$\begin{align}
\int_{x_{k-1}}^{x_k} f(x)\ dx
&=\int_{x_{k-1}}^{x_k}\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{n!}(x-x_{k-1})^n dx\\
&=\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{n!}\int_{x_{k-1}}^{x_k}(x-x_{k-1})^n\ dx\\
&=\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{(n+1)!}\left.(x-x_{k-1})^{n+1}\right|_{x_{k-1}}^{x_k}\\
&=\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{(n+1)!}(x_k-x_{k-1})^{n+1}\\
&=\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{(n+1)!}h^{n+1}\\
\end{align}$$
After adjustment shown by Lanata, we get that:
$$\begin{align}
\epsilon=-\dfrac{f'(b)-f'(a)}{12}h^2
\end{align}$$
### Error in Simpson Summation
$$\epsilon=\dfrac{f^{(3)}(b)-f^{(3)}(a)}{180}h^4$$

