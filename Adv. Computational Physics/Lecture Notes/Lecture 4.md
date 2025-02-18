**Name:** Stanley Goodwin
**Date:** 2/7/2025

---
## Root Finding
Finding when a function $f(x)=0$.

### Relaxation Method
Start from an initial guess $x=x_0$. The function $f(x)=0\implies f(x)+x=x$, and so:
$$x_{n+1}=f(x_n)$$
It doesn't always converge (multiple solutions), dependent on the initial guess.
Systems of many variables tend to do better with this method.

### Binary Search Method
Given a continuous function $f(x)$, if we want to find a numerical value $f(x)=a$, we can choose an interval $x\in[x_1,x_2]$, where the solution must lie.

Given $x_1$ and $x_2$, calculate the midpoint $x'=\dfrac{x_2+x_1}{2}$, then $f(x')$.
If $f(x')$ has the same sign as $f(x_1)$, then $x_1\rightarrow x'$.
If $f(x')$ has the same sign as $f(x_2)$, then $x_2\rightarrow x'$.
If $|x_2-x_1|<\delta$, then end the loop.

### Newton's Method
We can use the Jacobian matrix to find an estimate of the root.
Assuming that $f(x)$ is differentiable, start from an initial guess $x=x_0$.
$$x_{n+1}=x_n-\dfrac{f(x_n)}{f'(x_n)}$$
For higher-dimension inputs, we can write it as the following instead:
$$\vec{x}_{n+1}=\vec{x}_n-[J(x_n)]^{-1}\vec{F}(x_n)$$
### Secant Method
For cases when we don't necessarily have the derivative, we can approximate it using secants.
Start from an initial guesses $x_0$ and $x_1$, then:
$$x_{n+1}=x_n-\dfrac{f(x_n)}{f(x_n)-f(x_{n-1})}(x_n-x_{n-1})$$
This is effectively the finite version of Newton's method.

## Shooting Method
Binary Partition to get a solution to a differential equation by finding which side satisfies quicker.

