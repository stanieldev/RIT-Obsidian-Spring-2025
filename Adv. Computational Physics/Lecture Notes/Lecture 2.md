**Name:** Stanley Goodwin
**Date:** 1/24/2025

---
## Numerical Integration (1 variable)
### Error in Trapezoid Summation
Consider an integral bounded by $x=a$ and $x=b$:
$$\begin{align}
\int_a^b f(x)\ dx&\simeq
\dfrac{f(b)+f(a)}{2}\delta x+\sum_{k=1}^{N-1}f(a+k\cdot\delta x)\cdot\delta x
\end{align}$$
To calculate the error, consider the integral above.
Let $x_k=a+kh$, and consider a particular slice of the integral between $x_{k-1}$ and $x_k$.

Performing a Taylor expansion of $f(x)$ about the point $x_{k-1}$:
$$\begin{align}
f(x)=\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{n!}(x-x_{k-1})^n
\end{align}$$
Calculating the individual slice of the integral, we see that:
$$\begin{align}
\int_{x_{k-1}}^{x_k} f(x)\ dx
&\simeq\int_{x_{k-1}}^{x_k}\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{n!}(x-x_{k-1})^n dx\\
&\simeq\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{n!}\int_{x_{k-1}}^{x_k}(x-x_{k-1})^n\ dx\\
&\simeq\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{(n+1)!}\left.(x-x_{k-1})^{n+1}\right|_{x_{k-1}}^{x_k}\\
&\simeq\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{(n+1)!}(x_k-x_{k-1})^{n+1}\\
&\simeq\sum_{n=0}^\infty\dfrac{f^{(n)}(x_{k-1})}{(n+1)!}(\delta x)^{n+1}\\
\end{align}$$
Taylor expanding from $x_k$ instead, we find that:
$$\begin{align}
\int_{x_{k-1}}^{x_k} f(x)\ dx
&\simeq\sum_{n=0}^\infty(-1)^n\dfrac{f^{(n)}(x_{k})}{(n+1)!}(\delta x)^{n+1}\\
\end{align}$$
Taking the average of both of those equations, we get:
$$\begin{align}
\int_{x_{k-1}}^{x_k} f(x)\ dx
&\simeq\dfrac{1}{2}\sum_{n=0}^\infty\dfrac{\left[f^{(n)}(x_{k-1})+(-1)^nf^{(n)}(x_{k})\right]}{(n+1)!}(\delta x)^{n+1}
\end{align}$$
Finding the total integral, we can write that:
$$\begin{align}
\int_a^b f(x)\ dx
&\simeq\dfrac{1}{2}\sum_{k=1}^N\sum_{n=0}^\infty\dfrac{\left[f^{(n)}(x_{k-1})+(-1)^nf^{(n)}(x_{k})\right]}{(n+1)!}(\delta x)^{n+1}\\
I(a,b)&\simeq\sum_{k=1}^N\dfrac{f(x_{k-1})+f(x_{k})}{2}\delta x
-\dfrac{\left[f'(b)-f'(a)\right]}{4}(\delta x)^{2}\\
&+\sum_{k=1}^N\dfrac{\left[f''(x_{k-1})+f''(x_{k})\right]}{12}(\delta x)^{3}
+O(\delta x^4)
\end{align}$$
The first component is the trapezoid integration, and so remainder is the error.
$$\begin{align}
\delta I(a,b)&\simeq\sum_{k=1}^N\dfrac{\left[f''(x_{k-1})+f''(x_{k})\right]}{12}(\delta x)^{3}
+O(\delta x^4)
\end{align}$$
Finally, after some more arithmetic changes:
$$\begin{align}
\epsilon=-\dfrac{f'(b)-f'(a)}{12}h^2
\end{align}$$
### Error in Simpson Summation
Similar to Trapezoid, but higher order since Simpson's rule applies to parabolas.
$$\epsilon=\dfrac{f^{(3)}(b)-f^{(3)}(a)}{180}h^4$$
## Ordinary Differential Equations

### First-Order Differential Equations
The general form can be written as:
$$\begin{align}
\dfrac{dy}{dx}=f(x,y)
\end{align}$$
So solve we must have the initial condition $(x_0,y(x_0))$.
### Second-Order Differential Equations
The general form can be written as:
$$\begin{align}
\dfrac{d^2x}{dt^2}=f(x,\dot{x},t)
\end{align}$$
So solve we must have the initial conditions $(t_0,x(t_0),\dot{x}(t_0))$.
### Euler's Method
The general form can be written as:
$$\begin{align}
y(t+\delta t)=y(t)+\dot{y}(t)\delta t+O(\delta t^2)
\end{align}$$
Substituting from earlier, we can also write it as:
$$\begin{align}
\dfrac{dy}{dx}=f(x,y)\implies y(t+\delta t)=y(t)+f(y,t)\delta t+O(\delta t^2)
\end{align}$$
