**Name:** Stanley Goodwin
**Date:** 1/31/2025

---
## Ordinary Differential Equations
### Euler's Method (RK 1)
The general form can be written as:
$$\begin{align}
y(t+\delta t)=y(t)+\dot{y}(t)\delta t+O(\delta t^2)
\end{align}$$
Substituting from earlier, we can also write it as:
$$\begin{align}
\dfrac{dy}{dx}=f(x,y)\implies y(t+\delta t)=y(t)+f(y,t)\delta t+O(\delta t^2)
\end{align}$$
### Midpoint Method (RK 2)
The general form can be written as:
$$\begin{align}
y(t+\delta t)=y(t)+\dot{y}\left(t+\tfrac{\delta t}{2}\right)\delta t+O(\delta t^3)
\end{align}$$
### Runge-Kutta 4 (RK 4)
The general form can be written as:
$$\begin{align}
k_1&=f\left(t,y(t)\right)\cdot\delta t\\
k_2&=f\left(t+\tfrac{1}{2}\delta t,y(t)+\tfrac{1}{2}k_1\right)\cdot\delta t\\
k_3&=f\left(t+\tfrac{1}{2}\delta t,y(t)+\tfrac{1}{2}k_2\right)\cdot\delta t\\
k_2&=f\left(t+\delta t,y(t)+k_3\right)\cdot\delta t\\
y(t+\delta t)&=y(t)+\dfrac{1}{6}\left(k_1+2k_2+2k_3+k_4\right)+O(\delta t^4)
\end{align}$$
