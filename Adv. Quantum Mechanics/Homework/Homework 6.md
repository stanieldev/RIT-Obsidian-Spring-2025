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
\int p(x)\ dx&=\int_{-\infty}^0 p(x)\ dx+\int_{0}^{a/2} p(x)\ dx+\int_{a/2}^a p(x)\ dx+\int_{a}^\infty p(x)\ dx\\
&=\int_{-\infty}^0 0\ dx+\int_{0}^{a/2}\sqrt{2m(E-V_0)}\ dx+\int_{a/2}^a \sqrt{2mE}\ dx+\int_{a}^\infty 0\ dx\\
n\pi\hbar&=\dfrac{a}{2}\sqrt{2m(E-V_0)}+\dfrac{a}{2}\sqrt{2mE}\\
n\pi\hbar\sqrt{\dfrac{2}{ma^2}}&=\sqrt{E-V_0}+\sqrt{E}\\
\dfrac{2(n\pi\hbar)^2}{ma^2}&=2E-V_0+2\sqrt{E}\sqrt{E-V_0}\\
\dfrac{(n\pi\hbar)^2}{ma^2}-E+V_0/2&=\sqrt{E}\sqrt{E-V_0}\\
\left(\dfrac{(n\pi\hbar)^2}{ma^2}+\dfrac{V_0}{2}\right)^2&=2E\dfrac{(n\pi\hbar)^2}{ma^2}\\
E_n&=\left(\dfrac{(n\pi\hbar)^2}{ma^2}+\dfrac{V_0}{2}\right)^2\dfrac{ma^2}{2(n\pi\hbar)^2}\\
E_n&=\left(\dfrac{(n\pi\hbar)^2}{ma^2}\dfrac{ma^2}{(n\pi\hbar)^2}+\dfrac{V_0}{2}\dfrac{ma^2}{(n\pi\hbar)^2}\right)^2\dfrac{ma^2}{2(n\pi\hbar)^2}\dfrac{(n\pi\hbar)^2}{ma^2}\\
E_n&=\left(1+\dfrac{V_0}{4}\dfrac{2ma^2}{(n\pi\hbar)^2}\right)^2\dfrac{(n\pi\hbar)^2}{2ma^2}\\
\Aboxed{E_n&=\left(1+\dfrac{V_0}{4E_n^0}\right)^2E_n^0}
\end{align}$$
We can then evaluate the limit:
$$\begin{align}
\lim_{n\rightarrow\infty}E_n&=\lim_{n\rightarrow\infty} \left(1+\dfrac{V_0}{4E_n^0}\right)^2E_n^0\\
&=\lim_{n\rightarrow\infty} \left(1+2\cdot\dfrac{V_0}{4E_n^0}+\dfrac{V_0^2}{16(E_n^0)^2}\right)E_n^0\\
&=\lim_{n\rightarrow\infty}E_n^0+\dfrac{V_0}{2}+\dfrac{V_0^2}{16(E_n^0)}\\
\lim_{n\rightarrow\infty}E_n&=\lim_{n\rightarrow\infty}E_n^0+\dfrac{V_0}{2}\\
\end{align}$$
So in the limit of large $n$, we get:
$$\begin{align}
\Aboxed{E_n&\approx E_n^0+\dfrac{V_0}{2}}\\
\end{align}$$
Since energy scales with $n^2$, we can also (for $n\rightarrow\infty$) write:
$$\begin{align}
\Aboxed{E_n&\approx E_n^0}\\
\end{align}$$

---
### Problem 2
#### Problem 2.1
Use the WKB approximation to calculate the approximate transmission coefficient $T$ for a particle of energy $E$ that encounters a finite barrier of height $V_0>E$ and width $2a$.
$$\begin{align}
\gamma&=\dfrac{1}{\hbar}\int_{-a}^{a}\left|\sqrt{2m(E-V_0)}\right|\ dx\\
&=\dfrac{1}{\hbar}\int_{-a}^{a}\left|i\sqrt{2m(V_0-E)}\right|\ dx\\
&=\dfrac{1}{\hbar}\sqrt{2m(V_0-E)}\int_{-a}^{a}dx\\
\Aboxed{\gamma&=\dfrac{2a}{\hbar}\sqrt{2m(V_0-E)}}
\end{align}$$
We can then find the transmission as:
$$\begin{align}
T&=e^{-2\gamma}\\
&=e^{-2\tfrac{2a}{\hbar}\sqrt{2m(V_0-E)}}\\
\Aboxed{T&=e^{-\tfrac{4a}{\hbar}\sqrt{2m(V_0-E)}}}
\end{align}$$


---
#### Problem 2.2
Show how the exact answer
$$\begin{align}
T&=\left(1+\dfrac{V_0^2}{4E(V_0-E)}\sinh^2\left[\dfrac{2a}{\hbar}\sqrt{2m(V_0-E)}\right]\right)^{-1}
\end{align}$$
compares to the WKB result for small tunneling probability.

I graphed the two graphs on Desmos.
 - For potential barriers $V\approx E$, the approximation is pretty poor and the transmission is a good bit larger than the true transmission equation.
 - For potential barriers $V\gg E$, the approximation for transmission is much smaller than the true value, resulting in a much faster decay through the barrier.

---
### Problem 3
In class we found the coupled equations for a time-dependent perturbation $\hat{H}'$:
$$\begin{align}
\dot{c}_a&=-\dfrac{i}{\hbar}H'_{ab}e^{-i\omega_0t}c_b\\
\dot{c}_b&=-\dfrac{i}{\hbar}H'_{ba}e^{i\omega_0t}c_a\\
\end{align}$$
---
#### Problem 3.1
Solve these equations for $c_{a,b}(t)$ exactly for a time-independent perturbation, i.e. for $\hat{H}_{ab}'(t)=V_{ab}$ for the initial conditions $c_a(0)=1$ and $c_b(0)=0$.

**Differential Equation for $c_a(t)$:**
$$\begin{align}
\dot{c}_a(t)&=-\dfrac{i}{\hbar}V_{ab}e^{-i\omega_0t}c_b(t)\\
\ddot{c}_a(t)&=-i\omega_0\left(-\dfrac{i}{\hbar}V_{ab}e^{-i\omega_0t}c_b(t)\right)-\dfrac{i}{\hbar}V_{ab}e^{-i\omega_0t}\dot{c}_b(t)\\
\ddot{c}_a(t)&=-i\omega_0\dot{c}_a(t)-\dfrac{i}{\hbar}V_{ab}e^{-i\omega_0t}\left(-\dfrac{i}{\hbar}V_{ba}e^{i\omega_0t}c_a\right)\\
\ddot{c}_a(t)&=-i\omega_0\dot{c}_a(t)-\dfrac{V_{ab}V_{ba}}{\hbar^2}e^{-i\omega_0t}e^{i\omega_0t}c_a\\
\ddot{c}_a(t)&=-i\omega_0\dot{c}_a(t)-\dfrac{|V_{ab}|^2}{\hbar^2}c_a\\
\end{align}$$
**Solution for $c_a(t)$:**
ANSATZ: Let $c_a(t)=e^{i\omega t}$, then:
$$\begin{align}
\ddot{c}_a(t)&=-i\omega_0\dot{c}_a(t)-\dfrac{|V_{ab}|^2}{\hbar^2}c_a\\
(i\omega)^2e^{i\omega t}&=-i\omega_0(i\omega)e^{i\omega t}-\dfrac{|V_{ab}|^2}{\hbar^2}e^{i\omega t}\\
-\omega^2&=\omega_0\omega-\dfrac{|V_{ab}|^2}{\hbar^2}\\
0&=\omega^2+\omega_0\omega-\dfrac{|V_{ab}|^2}{\hbar^2}\\
\end{align}$$
Therefore, we can find the solutions:
$$\begin{align}
\omega&=\dfrac{-\omega_0\pm\sqrt{\omega_0^2+4|V_{ab}|^2/\hbar^2}}{2}=-\dfrac{\omega_0}{2}\pm\omega_r
\end{align}$$
We can then write $c_a(t)$ as:
$$\begin{align}
c_a(t)&=Ae^{-i\tfrac{\omega_0}{2}t}e^{i\omega_rt}+Be^{-i\tfrac{\omega_0}{2}t}e^{-i\omega_rt}\\
&=e^{-i\tfrac{\omega_0}{2}t}\left(Ae^{i\omega_rt}+Be^{-i\omega_rt}\right)\\
&=e^{-i\tfrac{\omega_0}{2}t}\left(A'\sin(\omega_rt)+B'\cos(\omega_rt)\right)\\
\end{align}$$
Using our initial conditions, we see that:
$$\begin{align}
c_a(t)&=e^{-i\tfrac{\omega_0}{2}t}\left(A'\sin(\omega_rt)+B'\cos(\omega_rt)\right)\\
c_a(0)&=e^{-i\tfrac{\omega_0}{2}t}\left(A'\sin(\omega_r0)+B'\cos(\omega_r0)\right)\\
1&=B'\\
\end{align}$$
Therefore, then:
$$\begin{align}
c_a(t)&=e^{-i\tfrac{\omega_0}{2}t}\left(A'\sin(\omega_rt)+\cos(\omega_rt)\right)\\
\end{align}$$
$$\begin{align}
\dot{c}_a&=-\dfrac{i}{\hbar}H'_{ab}e^{-i\omega_0t}c_b\\
-i\tfrac{\omega_0}{2}c_a(t)+\omega_re^{-i\tfrac{\omega_0}{2}t}\left(A'\cos(\omega_rt)-\sin(\omega_rt)\right)&=-\dfrac{i}{\hbar}H'_{ab}e^{-i\omega_0t}c_b\\
-i\tfrac{\omega_0}{2}+\omega_rA'&=0\\
A'&=i\tfrac{\omega_0}{2\omega_r}
\end{align}$$
$$\begin{align}
c_a(t)&=e^{-i\tfrac{\omega_0}{2}t}\left(\cos(\omega_rt)+i\tfrac{\omega_0}{2\omega_r}\sin(\omega_rt)\right)\\
\end{align}$$
**Solution for $c_b(t)$:**
$$\begin{align}
\dot{c}_a&=-\dfrac{i}{\hbar}H'_{ab}e^{-i\omega_0t}c_b\\
c_b&=i\hbar\dfrac{V_{ba}}{|V_{ab}|^2}e^{i\omega_0t}\dot{c}_a\\
&=i\hbar\dfrac{V_{ba}}{|V_{ab}|^2}e^{i\omega_0t}\left(-i\tfrac{\omega_0}{2}e^{-i\tfrac{\omega_0}{2}t}\left(\cos(\omega_rt)+i\tfrac{\omega_0}{2\omega_r}\sin(\omega_rt)\right)+e^{-i\tfrac{\omega_0}{2}t}\left(-\omega_r\sin(\omega_rt)+i\tfrac{\omega_0}{2}\cos(\omega_rt)\right)\right)\\
&=i\hbar\dfrac{V_{ba}}{|V_{ab}|^2}e^{i\tfrac{\omega_0}{2}t}\left(-i\tfrac{\omega_0}{2}\cos(\omega_rt)+\tfrac{\omega_0^2}{4\omega_r}\sin(\omega_rt)-\omega_r\sin(\omega_rt)+i\tfrac{\omega_0}{2}\cos(\omega_rt)\right)\\
&=-i\dfrac{V_{ba}}{\hbar}\dfrac{1}{|V_{ab}|^2}\left(\tfrac{\hbar^2\omega_0^2}{4\omega_r}+\hbar^2\omega_r\right)e^{i\tfrac{\omega_0}{2}t}\sin(\omega_rt)\\
&=-i\dfrac{V_{ba}}{\hbar\omega_r}\dfrac{1}{|V_{ab}|^2}\left(\tfrac{\hbar^2\omega_0^2}{4}+\hbar^2\omega_r^2\right)e^{i\tfrac{\omega_0}{2}t}\sin(\omega_rt)\\
\Aboxed{c_b&=-i\dfrac{V_{ba}}{\hbar\omega_r}e^{i\tfrac{\omega_0}{2}t}\sin(\omega_rt)}
\end{align}$$
In the end, we can see that:
$$\begin{align}
\Aboxed{c_a(t)&=e^{-i\tfrac{\omega_0}{2}t}\left(\cos(\omega_rt)+i\tfrac{\omega_0}{2\omega_r}\sin(\omega_rt)\right)}\\
\Aboxed{c_b(t)&=-i\dfrac{V_{ba}}{\hbar\omega_r}e^{i\tfrac{\omega_0}{2}t}\sin(\omega_rt)}\\
\omega_r&=\tfrac{\sqrt{\omega_0^2+4|V_{ab}|^2/\hbar^2}}{2}
\end{align}$$

---
#### Problem 3.2
Show that in this case $|c_a(t)|^2+|c_b(t)|^2=1$
$$\begin{align}
\left|c_a(t)\right|^2+\left|c_b(t)\right|^2
&=\left|e^{-i\tfrac{\omega_0}{2}t}\left(\cos(\omega_rt)+i\tfrac{\omega_0}{2\omega_r}\sin(\omega_rt)\right)\right|^2+\left|-i\dfrac{V_{ba}}{\hbar\omega_r}e^{i\tfrac{\omega_0}{2}t}\sin(\omega_rt)\right|^2\\
&=\left|e^{-i\tfrac{\omega_0}{2}t}\right|^2\left|\cos(\omega_rt)+i\tfrac{\omega_0}{2\omega_r}\sin(\omega_rt)\right|^2+\left|-i\dfrac{V_{ba}}{\hbar\omega_r}\right|^2\left|e^{i\tfrac{\omega_0}{2}t}\right|^2\left|\sin(\omega_rt)\right|^2\\
&=1\cdot\left(\cos^2(\omega_rt)+\tfrac{\omega_0^2}{4\omega_r^2}\sin^2(\omega_rt)\right)+\dfrac{|V_{ba}|^2}{(\hbar\omega_r)^2}\cdot1\cdot\sin^2(\omega_rt)\\
&=\cos^2(\omega_rt)+\left(\dfrac{\omega_0^2}{4\omega_r^2}+\dfrac{|V_{ba}|^2}{(\hbar\omega_r)^2}\right)\sin^2(\omega_rt)\\
&=\cos^2(\omega_rt)+\sin^2(\omega_rt)\\
\Aboxed{\left|c_a(t)\right|^2+\left|c_b(t)\right|^2&=1}
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
$$\begin{align}
\dot{c}_a^{(1)}&=-\dfrac{i}{\hbar}\left[H'_{aa}c_a^{(0)}+H'_{ab}e^{-i\omega_0t}c_b^{(0)}\right]\\
\dot{c}_a^{(1)}&\approx-\dfrac{i}{\hbar}\left[H'_{aa}\cdot1+H'_{ab}e^{-i\omega_0t}\cdot0\right]\\
\dot{c}_a^{(1)}&\approx-\dfrac{i}{\hbar}H'_{aa}\\
\Aboxed{c_a^{(1)}&\approx1-\dfrac{i}{\hbar}\int_0^tH'_{aa}(t)\ dt'}
\end{align}$$
$$\begin{align}
\dot{c}_b^{(1)}&=-\dfrac{i}{\hbar}\left[H'_{bb}c_b^{(0)}+H'_{ba}e^{i\omega_0t}c_a^{(0)}\right]\\
\dot{c}_b^{(1)}&\approx-\dfrac{i}{\hbar}\left[H'_{bb}\cdot0+H'_{ba}e^{i\omega_0t}\cdot1\right]\\
\dot{c}_b^{(1)}&\approx-\dfrac{i}{\hbar}H'_{ba}e^{i\omega_0t}\\
\Aboxed{c_b^{(1)}&\approx-\dfrac{i}{\hbar}\int_0^te^{i\omega_0t'}H'_{ba}(t)\ dt}
\end{align}$$
We can then show that:
$$\begin{align}
|c^{(1)}_a(t)|^2+|c^{(1)}_b(t)|^2
&=\left|1-\dfrac{i}{\hbar}\int_0^tH'_{aa}(t)\ dt'\right|^2+\left|-\dfrac{i}{\hbar}\int_0^te^{i\omega_0t'}H'_{ba}(t)\ dt'\right|^2\\
&=1+\left|\dfrac{1}{\hbar}\int_0^tH'_{aa}(t)\ dt'\right|^2+\left|\dfrac{1}{\hbar}\int_0^te^{i\omega_0t'}H'_{ba}(t)\ dt'\right|^2\\
\Aboxed{|c^{(1)}_a(t)|^2+|c^{(1)}_b(t)|^2&=1}
\end{align}$$
For small values of $H'_{aa}$ and $H'_{ba}$, this satisfies the normalization condition.

---
#### Problem 4.2
Defining the variables
$$\begin{align}
d_a&=\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)c_a\\
d_b&=\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)c_b\\
\end{align}$$
show that coupled equations
$$\begin{align}
\dot{d}_a&=-\dfrac{i}{\hbar}e^{+i\phi}\hat{H}_{ab}'e^{-i\omega_0 t}d_b\\
\dot{d}_b&=-\dfrac{i}{\hbar}e^{-i\phi}\hat{H}_{ba}'e^{+i\omega_0 t}d_a\\
\end{align}$$
can be obtained, where
$$\begin{align}
\phi(t)&=\dfrac{1}{\hbar}\int_0^t\left[\hat{H}_{aa}'(\tau)-\hat{H}_{bb}'(\tau)\right]\ d\tau&&\implies&\phi(t)+\dfrac{1}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau&=\dfrac{1}{\hbar}\int_0^t\hat{H}_{aa}'\ d\tau
\end{align}$$
Starting off:
$$\begin{align}
d_a&=\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)c_a\\
\dot{d}_a&=\dfrac{i}{\hbar}\left(\hat{H}_{aa}'(t)-\hat{H}_{aa}'(0)\right)d_a+\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)\dot{c}_a\\
&=\dfrac{i}{\hbar}\left(\hat{H}_{aa}'(t)-\hat{H}_{aa}'(0)\right)d_a-\dfrac{i}{\hbar}\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)\left[H'_{aa}(t)c_a(t)+H'_{ab}(t)e^{-i\omega_0t}c_b(t)\right]\\
&=-\dfrac{i}{\hbar}\hat{H}_{aa}'(0)d_a-\dfrac{i}{\hbar}H'_{ab}(t)e^{-i\omega_0t}\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)c_b(t)\\
&=-\dfrac{i}{\hbar}\left(\hat{H}_{aa}'(0)d_a+H'_{ab}(t)e^{-i\omega_0t}\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)c_b(t)\right)\\
&=-\dfrac{i}{\hbar}\left(\hat{H}_{aa}'(0)d_a+H'_{ab}(t)e^{-i\omega_0t}\exp\left(\phi(t)+\dfrac{1}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)c_b(t)\right)\\
&=-\dfrac{i}{\hbar}\left(\hat{H}_{aa}'(0)d_a+H'_{ab}(t)e^{-i\omega_0t}e^{\phi(t)}\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)c_b(t)\right)\\
\dot{d}_a&=-\dfrac{i}{\hbar}\left(\hat{H}_{aa}'(0)d_a+H'_{ab}(t)e^{-i\omega_0t}e^{i\phi(t)}d_b\right)\\
\Aboxed{\dot{d}_a&=-\dfrac{i}{\hbar}e^{i\phi(t)}H'_{ab}(t)e^{-i\omega_0t}d_b}
\end{align}$$
And:
$$\begin{align}
d_b&=\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)c_b\\
\dot{d}_b&=\dfrac{i}{\hbar}\hat{H}_{bb}'(t)d_b+\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)\dot{c}_b\\
&=\dfrac{i}{\hbar}\hat{H}_{bb}'(t)d_b-\dfrac{i}{\hbar}H'_{bb}c_b\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)-\dfrac{i}{\hbar}H'_{ba}e^{i\omega_0t}c_a\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)\\
&=-\dfrac{i}{\hbar}H'_{ba}e^{i\omega_0t}c_a\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{bb}'(\tau)\ d\tau\right)\\
&=-\dfrac{i}{\hbar}H'_{ba}e^{i\omega_0t}c_a\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau-i\phi(t)\right)\\
&=-\dfrac{i}{\hbar}H'_{ba}e^{-i\phi(t)}e^{i\omega_0t}\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)c_a\\
\Aboxed{\dot{d}_b&=-\dfrac{i}{\hbar}H'_{ba}e^{-i\phi(t)}e^{i\omega_0t}d_a}
\end{align}$$

---
#### Problem 4.3
Use the results of 4.2 above to obtain the results found in 4.1.

Converting our initial conditions ($c_a(t)=1$ and $c_b(t)=0$) over, we get:
$$\begin{align}
d_a(0)&=\exp\left(0\right)\cdot1=1\\
d_b(0)&=\exp\left(0\right)\cdot0=0\\
\end{align}$$
We can take these and plug into their differentials:
$$\begin{align}
\dot{d}_a&=-\dfrac{i}{\hbar}e^{+i\phi}\hat{H}_{ab}'e^{-i\omega_0 t}0\\
\Aboxed{\dot{d}_a&=0}\\
\dot{d}_b&=-\dfrac{i}{\hbar}e^{-i\phi}\hat{H}_{ba}'e^{+i\omega_0 t}1\\
\Aboxed{\dot{d}_b&=-\dfrac{i}{\hbar}e^{-i\phi}\hat{H}_{ba}'e^{+i\omega_0 t}}\\
\end{align}$$
Therefore we can find that:
$$\begin{align}
c_a^{(1)}&=\exp\left(\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau\right)d_a\\
\Aboxed{c_b^{(1)}&\approx1+\dfrac{i}{\hbar}\int_0^t\hat{H}_{aa}'(\tau)\ d\tau}\\
c_b^{(1)}&=\exp\left(-\dfrac{i}{\hbar}\int_0^t\hat{H}_{ba}'(\tau)\ d\tau\right)d_b\\
\Aboxed{c_b^{(1)}&\approx-\dfrac{i}{\hbar}\int_0^t\hat{H}_{ba}'(\tau)\ d\tau}
\end{align}$$
