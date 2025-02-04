**Name:** Stanley Goodwin
**Date:** 1/17/2025

---
## Numerical Integration (1 variable)
### Riemann Summation (Degree 0)
There are types of common integration: Left, Right, and Middle.
$$\text{Riemann Sum}=\sum_i f(x_i)\Delta x_i$$
Assuming that $\Delta x_i$ is constant (which is common), we can write that:
$$\begin{align}
\text{Left Sum}&=\sum_{i=0}^{\tfrac{b-a}{n}-1} f(a+i\Delta x)\Delta x & \Delta x = \dfrac{b-a}{n}\\
\text{Right Sum}&=\sum_{i=1}^{\tfrac{b-a}{n}} f(a+i\Delta x)\Delta x & \Delta x = \dfrac{b-a}{n}\\
\text{Middle Sum}&=\sum_{i=0}^{\tfrac{b-a}{n}-1} f\left(a+\left(i+\tfrac{1}{2}\right)\Delta x\right)\Delta x & \Delta x = \dfrac{b-a}{n}\\
\end{align}$$
Error decreases as $\sim O(1/n)$.
### Trapezoidal Rule (Degree 1)
The rule comes from taking the arithmetic mean of the Left Sum and Right Sum:
$$\begin{align}
\text{Trapeziodal Sum}&=
\dfrac{f(b)+f(a)}{2}\Delta x+\sum_{i=1}^{\tfrac{b-a}{n}-1} f(a+i\Delta x)\Delta x& \Delta x = \dfrac{b-a}{n}\\
\end{align}$$
Error decreases as $\sim O(1/n^2)$.
### Simpson's Rule (Degree 2)
This is a more advanced version that follows a much more complicated rule, but it is much better.
$$\begin{align}
\text{Simpson Sum}&=\dfrac{\Delta x}{3}\left(x_0+4x_1+2x_2+4x_3+\dots + 4x_{n-2}+2x_{n-1}+x_n\right) & \Delta x = \dfrac{b-a}{n}
\end{align}$$
Error decreases as $\sim O(1/n^4)$, but the number of slices *has* to be an even number.

