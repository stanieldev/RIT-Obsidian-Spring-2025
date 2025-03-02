**Name:** Stanley Goodwin
**Date:** 3/7/2025

---
### Problem 1
Use the WKB approximation to find the allowed energies ($E_n$) of an infinite square well with a shelf of height $V_0$ extending half-way across:
$$\begin{align}
V(x)&=\begin{cases}
V_0,&0<x<a/2\\
0,&a/2<x<a\\
\infty,&x<0,x>a\\
\end{cases}
\end{align}$$
Express your results for $E_n$ in terms of $V_0$ and $E_n^0=\dfrac{(n\pi\hbar)^2}{2ma^2}$, the $n$-th allowed energy for the infinite square well with no shelf. Evaluate the semiclassical limit $\lim_{n\rightarrow\infty}E_n$.
$$\begin{align}
\dots
\end{align}$$

---
### Problem 2
#### Problem 2.1
Use the WKB approximation to calculate the approximate transmission coefficient $T$ for a particle of energy $E$ that encounters a finite barrier of height $V_0>E$ and width $2a$.
$$\begin{align}
\dots
\end{align}$$

---
#### Problem 2.2
Show how the exact answer
$$\begin{align}
T&=\left(1+\dfrac{V_0^2}{4E(V_0-E)}\sinh^2\left[\dfrac{2\alpha}{\hbar}\sqrt{2m(V_0-E)}\right]\right)^{-1}
\end{align}$$
compares to the WKB result for small tunneling probability.
$$\begin{align}
\dots
\end{align}$$

---
### Problem 3
In class we found the coupled equations for a time-dependent perturbation $\hat{H}'$:
$$\begin{align}
\dot{c}_a&=-\dfrac{i}{\hbar}H'_{ab}e^{-i\omega_0t}c_b\\
\dot{c}_b&=-\dfrac{i}{\hbar}H'_{ba}e^{i\omega_0t}c_a\\
\end{align}$$
---
#### Problem 3.1
Solve these equations for $c_{a,b}(t)$ exactly for a time-independent perturbation, i.e. for $\hat{H}_{ab}'(t)=V_{ab}$.
$$\begin{align}
\dots
\end{align}$$

---
#### Problem 3.2
Show that in this case $|c_a(t)|^2+|c_b(t)|^2=1$
$$\begin{align}
\dots
\end{align}$$

---
### Problem 4
If $\hat{H}_a'\ne0$ and $\hat{H}_b'\ne0$, the coupled equations for a time-dependent perturbation $\hat{H}'$ become:
$$\begin{align}
\dot{c}_a&=-\dfrac{i}{\hbar}\left[H'_{aa}c_a+H'_{ab}e^{-i\omega_0t}c_b\right]\\
\dot{c}_b&=-\dfrac{i}{\hbar}\left[H'_{bb}c_b+H'_{ba}e^{i\omega_0t}c_a\right]\\
\end{align}$$
---
#### Problem 4.1
Using these equations find $c_a^{(1)}(t)$ and $c_b^{(1)}(t)$ (i.e. first-order perturbation theory results) for the initial conditions $c_a(t)=1$ and $c_b(t)=0$, show that:
$$|c^{(1)}_a(t)|^2+|c^{(1)}_b(t)|^2=1$$
to first order in $\hat{H}'$.

---
#### Problem 4.2
Defining the variables
$$\begin{align}
d_a&=\exp\left(-\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)c_b\\
d_b&=\exp\left(+\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)c_a\\
\end{align}$$
show that coupled equations
$$\begin{align}
\dot{d}_a&=-\dfrac{i}{\hbar}e^{+i\phi}\hat{H}_{ab}'e^{-i\omega t}c_b\\
\dot{d}_b&=-\dfrac{i}{\hbar}e^{-i\phi}\hat{H}_{ba}'e^{+i\omega t}c_a\\
\end{align}$$
can be obtained, where
$$\begin{align}
\phi(t)&=\dfrac{1}{\hbar}\int_0^t\left[\hat{H}_{aa}'(\tau)-\hat{H}_{bb}'(\tau)\right]\ d\tau
\end{align}$$

---
#### Problem 4.3
Use the results of 4.2 above to obtain the results found in 4.1.