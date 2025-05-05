**Name:** Stanley Goodwin
**Date:** 4/25/2025

---
### Question 1
Verify, by directly plugging in, that the Green's Function:
$$\begin{align}
G(r)&=-\dfrac{e^{ikr}}{4\pi r}
\end{align}$$
satisfies the equation:
$$\begin{align}
\left(\vec\nabla^2+k^2\right)G(r)&=\delta^3(r) & \vec\nabla^2\left(\dfrac{1}{r}\right)&=-4\pi\delta^3(r)
\end{align}$$
Hint: Use the provided gradient for solving the system.
$$\begin{align}
-4\pi \vec\nabla^2G(r)&=\vec\nabla^2\left(\dfrac{e^{ikr}}{r}\right)\\
&=\dfrac{1}{r}\vec\nabla^2\left(e^{ikr}\right)+2\vec\nabla\left(e^{ikr}\right)\vec\nabla\left(\dfrac{1}{r}\right)+e^{ikr}\vec\nabla^2\left(\dfrac{1}{r}\right)\\
&=\dfrac{1}{r}\dfrac{1}{r^2}\dfrac{\partial}{\partial r}\left(r^2\dfrac{\partial}{\partial r}\left(e^{ikr}\right)\right)+2\cdot\dfrac{\partial}{\partial r}\left(e^{ikr}\right)\cdot\dfrac{\partial}{\partial r}\left(\dfrac{1}{r}\right)-4\pi e^{ik(r=0)}\delta^3(r)\\
&=\dfrac{ik}{r^3}\dfrac{\partial}{\partial r}\left(r^2e^{ikr}\right)+2\cdot ike^{ikr}\cdot\left(-\dfrac{1}{r^2}\right)-4\pi\delta^3(r)\\
&=\dfrac{ik}{r^3}\left(2re^{ikr}+ikr^2e^{ikr}\right)-2 ik\cdot\dfrac{e^{ikr}}{r^2}-4\pi\delta^3(r)\\
&=2ik\dfrac{re^{ikr}}{r^3}-k^2\dfrac{r^2e^{ikr}}{r^3}-2 ik\cdot\dfrac{e^{ikr}}{r^2}-4\pi\delta^3(r)\\
&=-k^2\dfrac{e^{ikr}}{r}+2ik\dfrac{e^{ikr}}{r^2}-2 ik\cdot\dfrac{e^{ikr}}{r^2}-4\pi\delta^3(r)\\
-4\pi \vec\nabla^2G(r)&=-k^2\dfrac{e^{ikr}}{r}-4\pi\delta^3(r)\\
\vec\nabla^2G(r)&=k^2\dfrac{e^{ikr}}{4\pi r}+\delta^3(r)\\
\Aboxed{\vec\nabla^2G(r)&=-k^2G(r)+\delta^3(r)}
\end{align}$$
From there, we can plug this into the differential equation:
$$\begin{align}
\left(\vec\nabla^2+k^2\right)G(r)&=\vec\nabla^2G(r)+k^2G(r)\\
&=\left(-k^2G(r)+\delta^3(r)\right)+k^2G(r)\\
&=-k^2G(r)+k^2G(r)+\delta^3(r)\\
\Aboxed{\left(\vec\nabla^2+k^2\right)G(r)&=\delta^3(r)}
\end{align}$$
---
### Question 2
#### Question 2.1
Find the scattering amplitude, in the Born approximation, for soft sphere scattering at arbitrary energy.
$$\begin{align}
f(k_f,k_i)&=-\dfrac{m}{2\pi\hbar^2}\int V(r)\ e^{i(\vec{k}_f-\vec{k}_i)\cdot\vec{r}}\ d\tau\\
&=-\dfrac{m}{2\pi\hbar^2}\int_0^{2\pi}\int_0^\pi\int_0^\infty V(r)\ e^{i(\Delta k\cdot r)\cos\theta}\ r^2\sin\theta\ dr\ d\theta\ d\phi\\
&=-\dfrac{2\pi m}{2\pi\hbar^2}\int_0^\infty r^2V(r)\int_0^\pi e^{i(\Delta k\cdot r)\cos\theta}\sin\theta\ d\theta\ dr\\
&=-\dfrac{m}{\hbar^2}\int_0^\infty rV(r)\cdot2\dfrac{\sin(\Delta k\cdot r)}{\Delta k\cdot r}\ dr\\
&=-\dfrac{2m}{\hbar^2(\Delta k)}\int_0^\infty rV(r)\sin(\Delta k\cdot r)\ dr\\
&=-\dfrac{2m}{\hbar^2(\Delta k)}\int_0^a V_0r\sin(\Delta k\cdot r)\ dr+0\\
&=-\dfrac{2mV_0}{\hbar^2(\Delta k)^2}\int_0^a (\Delta k\cdot r)\sin(\Delta k\cdot r)\ dr\\
&=-\dfrac{2mV_0}{\hbar^2(\Delta k)^2}\int_0^{\Delta k\cdot a} x\sin(x)\ \dfrac{dx}{\Delta k}\\
&=-\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\int_0^{\Delta k\cdot a} x\sin(x)\ dx\\
&=-\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[\sin(x)-x\cos(x)\right|_0^{\Delta k\cdot a}\\
&=\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[x\cos(x)-\sin(x)\right|_0^{\Delta k\cdot a}\\
&=\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[(\Delta k\cdot a)\cos(\Delta k\cdot a)-\sin(\Delta k\cdot a)-0\cos(0)+\sin(0)\right]\\
\Aboxed{f(\Delta k)&=\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[(\Delta k\cdot a)\cos(\Delta k\cdot a)-\sin(\Delta k\cdot a)\right]}
\end{align}$$
---
#### Question 2.2
Show that your answer reduces to that derived in class in the low energy limit.

The low-energy limit is when $\Delta k\rightarrow 0$, and so:
$$\begin{align}
\sin(\Delta k\cdot a)&=(\Delta k\cdot a)-\dfrac{(\Delta k\cdot a)^3}{3!}+\dots\\
\cos(\Delta k\cdot a)&=1-\dfrac{(\Delta k\cdot a)^2}{2!}+\dots\\
\end{align}$$
Plugging these approximations in from 2.1, we get:
$$\begin{align}
f(\Delta k)&=\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[(\Delta k\cdot a)\cos(\Delta k\cdot a)-\sin(\Delta k\cdot a)\right]\\
&=\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[(\Delta k\cdot a)-(\Delta k\cdot a)\dfrac{(\Delta k\cdot a)^2}{2!}-(\Delta k\cdot a)+\dfrac{(\Delta k\cdot a)^3}{3!}\right]\\
&=\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[-\dfrac{(\Delta k\cdot a)^3}{2}+\dfrac{(\Delta k\cdot a)^3}{6}\right]\\
&=\dfrac{2mV_0}{\hbar^2(\Delta k)^3}\left[-\dfrac{(\Delta k\cdot a)^3}{3}\right]\\
&=-\dfrac{2mV_0}{3\hbar^2(\Delta k)^3}(\Delta k\cdot a)^3\\
\Aboxed{f(\Delta k\approx0)&=-\dfrac{2mV_0}{3\hbar^2}a^3}
\end{align}$$
---
### Question 3
For the potential $V(r)=\alpha\delta(r-a)$.
#### Question 3.1
Find $f(\theta),D(\theta)$ and $\sigma$ for low energy in the Born approximation.
$$\begin{align}
f(\Delta k)&=-\dfrac{m}{2\pi\hbar^2}\int V(r)\ e^{i(\Delta\vec{k}\cdot\vec{r})}\ d\tau\\
&=-\dfrac{m}{2\pi\hbar^2}\int_0^{2\pi}\int_0^{\pi}\int_0^\infty V(r)\ e^{i(\Delta k\cdot r)\cos\theta}\ r^2\sin\theta\ dr\ d\theta\ d\phi\\
&=-\dfrac{m}{\hbar^2}\int_0^\infty r^2V(r)\int_0^{\pi}e^{i(\Delta k\cdot r)\cos\theta}\sin\theta\ d\theta\ dr\\
&=-\dfrac{m}{\hbar^2}\int_0^\infty r^2V(r)\int_0^{\pi}e^{i(\Delta k\cdot r)\cos\theta}\sin\theta\ d\theta\ dr\\
&=-\dfrac{m}{\hbar^2}\int_0^\infty r^2V(r)\cdot2\dfrac{\sin(\Delta k\cdot r)}{\Delta k\cdot r}\ dr\\
&=-\dfrac{2m}{\hbar^2(\Delta k)}\int_0^\infty rV(r)\sin(\Delta k\cdot r)\ dr\\
&=-\dfrac{2m}{\hbar^2(\Delta k)}\int_0^\infty r\alpha\delta(r-a)\sin(\Delta k\cdot r)\ dr\\
&=-\dfrac{2m\alpha}{\hbar^2(\Delta k)}\int_0^\infty r\sin(\Delta k\cdot r)\delta(r-a)\ dr\\
&=-\dfrac{2m\alpha}{\hbar^2(\Delta k)}a\sin(\Delta k\cdot a)\\
\Aboxed{f(\Delta k)&=-\dfrac{2m\alpha a^2}{\hbar^2}\dfrac{\sin(\Delta k\cdot a)}{\Delta k\cdot a}}
\end{align}$$
The low-energy limit means $\Delta k\rightarrow 0$ and $\lim_{x\rightarrow 0}\dfrac{\sin x}{x}=1$, and so:
$$\begin{align}
\Aboxed{f(\Delta k)&=-\dfrac{2m\alpha a^2}{\hbar^2}}
\end{align}$$
The differential cross-section is:
$$\begin{align}
D(\theta)&=|f(\Delta k)|^2\\
&=\left|-\dfrac{2m\alpha a^2}{\hbar^2}\right|^2\\
&=\left(\dfrac{2m\alpha a^2}{\hbar^2}\right)^2\\
\Aboxed{D(\theta)&=\dfrac{4m^2\alpha^2 a^4}{\hbar^4}}
\end{align}$$
And the total cross section is:
$$\begin{align}
\sigma&=\int D(\theta)\ d\Omega\\
&=\int \dfrac{4m^2\alpha^2 a^4}{\hbar^4}\ d\Omega\\
&=\dfrac{4m^2\alpha^2 a^4}{\hbar^4}\int d\Omega\\
&=\dfrac{4m^2\alpha^2 a^4}{\hbar^4}\cdot4\pi\\
\Aboxed{\sigma&=\dfrac{16\pi m^2\alpha^2 a^4}{\hbar^4}}
\end{align}$$
---
#### Question 3.2
Find $f(\theta)$ for arbitrary energies in the Born approximation.

From the previous section, we can start with the equation for $f(\theta)$:
$$\begin{align}
f(\Delta k)&=-\dfrac{2m\alpha a^2}{\hbar^2}\dfrac{\sin(\Delta k\cdot a)}{\Delta k\cdot a}
\end{align}$$
We can use an equation in class to relate $\theta$ to $\Delta k$:
When $k_f\approx k_i\approx k$, we can find that:
$$\begin{align}
(\Delta k)^2&=k_f\cdot k_f-2k_f\cdot k_i\cos\theta+k_f\cdot k_i\\
&=2k^2-2k^2\cos\theta\\
&=2k^2\left(1-\cos\theta\right)\\
&=2k^2\cdot2\sin^2\left(\dfrac{\theta}{2}\right)\\
(\Delta k)^2&=4k^2\sin^2\left(\dfrac{\theta}{2}\right)\\
\Aboxed{\Delta k&=2k\sin\left(\dfrac{\theta}{2}\right)}
\end{align}$$
And so we can write the scattering amplitude from previous:
$$\begin{align}
f(\Delta k)&=-\dfrac{2m\alpha a^2}{\hbar^2}\dfrac{\sin\left(\Delta k\cdot a\right)}{\Delta k\cdot a}\\
&=-\dfrac{2m\alpha a^2}{\hbar^2}\dfrac{\sin\left(2k\sin\left(\tfrac{\theta}{2}\right)\cdot a\right)}{2k\sin\left(\tfrac{\theta}{2}\right)\cdot a}\\
\Aboxed{f(\theta)&=-\dfrac{2m\alpha a}{\hbar^2}\dfrac{\sin\left(2ka\sin\left(\tfrac{\theta}{2}\right)\right)}{2k\sin\left(\tfrac{\theta}{2}\right)}}
\end{align}$$
---
#### Question 3.3
Discuss how your results compare to your answer to the first problem in the previous homework.

From the previous homework, we found:
$$\begin{align}
\text{Homework 9} &&
f(\theta)&\approx-\dfrac{\beta a}{\beta+1} &
D(\theta)&=\left(\dfrac{\beta a}{\beta+1}\right)^2 &
\sigma&=4\pi\left(\dfrac{\beta a}{\beta+1}\right)^2\\
\text{Homework 10} &&
f(\theta)&\approx-\dfrac{2m\alpha a^2}{\hbar^2} & 
D(\theta)&\approx\left(\dfrac{2m\alpha a^2}{\hbar^2}\right)^2 &
\sigma&\approx4\pi\left(\dfrac{2m\alpha a^2}{\hbar^2}\right)^2\\
\end{align}$$
When we use our value of $\beta=\tfrac{2ma\alpha}{\hbar^2}$, we see that:
$$\begin{align}
\text{Homework 9} &&
f(\theta)&\approx-\dfrac{\beta a}{\beta+1} &
D(\theta)&\approx\left(\dfrac{\beta a}{\beta+1}\right)^2 &
\sigma&=4\pi\left(\dfrac{\beta a}{\beta+1}\right)^2\\
\text{Homework 10} &&
f(\theta)&\approx-\beta a & 
D(\theta)&\approx\left(\beta a\right)^2 &
\sigma&=4\pi\left(\beta a\right)^2\\
\end{align}$$
Between the two cases, the previous homework had an extra factor of $\dfrac{1}{\beta+1}$.
In the limit that $\beta\rightarrow 0$, this returns our case in Homework 10.

This means either:
$$\begin{align}
\lim_{a\rightarrow0}\dfrac{2ma\alpha}{\hbar^2}&&\text{or}&&\lim_{\alpha\rightarrow0}\dfrac{2ma\alpha}{\hbar^2}
\end{align}$$
As in, these two approximations are equal when either the radius of the shell approaches $0$, or when the energy of the potential approaches $0$. Either way results identically.

Weak potential or closer shell results in the Born Approximation equaling our analytic solution.

---
### Question 4
In the class we solved the quantum harmonic oscillator in the Heisenberg picture. Using the solutions, find the following commutators.

We can write the Hamiltonian as:
$$\begin{align}
\hat{H}&=\dfrac{\hat{p}^2}{2m}+\dfrac{1}{2}m\omega^2\hat{x}^2
\end{align}$$
And so we can write the operators as:
$$\begin{align}
\hat{x}(t)&=e^{i\hat{H}t/\hbar}\hat{x}(0)e^{-i\hat{H}t/\hbar}\\
\hat{p}(t)&=e^{i\hat{H}t/\hbar}\hat{p}(0)e^{-i\hat{H}t/\hbar}\\
\end{align}$$
We solved these relations in class, and so:
$$\begin{align}
\hat{x}(t)&=\hat{x}(0)\cos(\omega t)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t)\\
\hat{p}(t)&=\hat{p}(0)\cos(\omega t)-m\omega\hat{x}(0)\sin(\omega t)\\
\end{align}$$
---
#### Question 4.1
Commutator $[\hat{x}(t_1),\hat{x}(t_2)]$
$$\begin{align}
\hat{x}(t_1)\hat{x}(t_2)
&=\left(\hat{x}(0)\cos(\omega t_1)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\right)\left(\hat{x}(0)\cos(\omega t_2)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_2)\right)\\
&=\hat{x}(0)\cos(\omega t_1)\hat{x}(0)\cos(\omega t_2)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\hat{x}(0)\cos(\omega t_2)\\&+\hat{x}(0)\cos(\omega t_1)\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_2)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_2)\\\\
\hat{x}(t_1)\hat{x}(t_2)
&=\hat{x}^2(0)\cos(\omega t_1)\cos(\omega t_2)+\dfrac{1}{m\omega}\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\cos(\omega t_2)\\
&+\dfrac{1}{m\omega}\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\sin(\omega t_2)+\dfrac{1}{(m\omega)^2}\hat{p}^2(0)\sin(\omega t_1)\sin(\omega t_2)
\end{align}$$
$$\begin{align}
\hat{x}(t_2)\hat{x}(t_1)
&=\left(\hat{x}(0)\cos(\omega t_2)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_2)\right)\left(\hat{x}(0)\cos(\omega t_1)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\right)\\
&=\hat{x}(0)\cos(\omega t_2)\hat{x}(0)\cos(\omega t_1)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_2)\hat{x}(0)\cos(\omega t_1)\\&+\hat{x}(0)\cos(\omega t_2)\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_2)\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\\\\
\hat{x}(t_2)\hat{x}(t_1)
&=\hat{x}^2(0)\cos(\omega t_1)\cos(\omega t_2)+\dfrac{1}{m\omega}\hat{p}(0)\hat{x}(0)\cos(\omega t_1)\sin(\omega t_2)\\
&+\dfrac{1}{m\omega}\hat{x}(0)\hat{p}(0)\sin(\omega t_1)\cos(\omega t_2)+\dfrac{1}{(m\omega)^2}\hat{p}^2(0)\sin(\omega t_1)\sin(\omega t_2)\\\\
\end{align}$$
$$\begin{align}
\hat{x}(t_1)\hat{x}(t_2)-\hat{x}(t_2)\hat{x}(t_1)

&=\hat{x}^2(0)\cos(\omega t_1)\cos(\omega t_2)+\dfrac{1}{m\omega}\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\cos(\omega t_2)\\
&+\dfrac{1}{m\omega}\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\sin(\omega t_2)+\dfrac{1}{(m\omega)^2}\hat{p}^2(0)\sin(\omega t_1)\sin(\omega t_2)\\
&-\hat{x}^2(0)\cos(\omega t_1)\cos(\omega t_2)-\dfrac{1}{m\omega}\hat{p}(0)\hat{x}(0)\cos(\omega t_1)\sin(\omega t_2)\\
&-\dfrac{1}{m\omega}\hat{x}(0)\hat{p}(0)\sin(\omega t_1)\cos(\omega t_2)-\dfrac{1}{(m\omega)^2}\hat{p}^2(0)\sin(\omega t_1)\sin(\omega t_2)\\\\

&=\dfrac{1}{m\omega}\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\cos(\omega t_2)-\dfrac{1}{m\omega}\hat{x}(0)\hat{p}(0)\sin(\omega t_1)\cos(\omega t_2)\\
&+\dfrac{1}{m\omega}\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\sin(\omega t_2)-\dfrac{1}{m\omega}\hat{p}(0)\hat{x}(0)\cos(\omega t_1)\sin(\omega t_2)\\\\

&=-\dfrac{1}{m\omega}\sin(\omega t_1)\cos(\omega t_2)\left[\hat{x}(0)\hat{p}(0)-\hat{p}(0)\hat{x}(0)\right]\\
&\ \ \ \ +\dfrac{1}{m\omega}\cos(\omega t_1)\sin(\omega t_2)\left[\hat{x}(0)\hat{p}(0)-\hat{p}(0)\hat{x}(0)\right]\\\\

&=\dfrac{1}{m\omega}\left[\sin(\omega t_2)\cos(\omega t_1)-\sin(\omega t_1)\cos(\omega t_2)\right]\left[\hat{x}(0),\hat{p}(0)\right]\\\\

&=\dfrac{\sin(\omega (t_2-t_1))}{m\omega}\left[\hat{x}(0),\hat{p}(0)\right]\\\\

\Aboxed{[\hat{x}(t_1),\hat{x}(t_2)]&=i\hbar\dfrac{\sin(\omega (t_2-t_1))}{m\omega}}
\end{align}$$
---
#### Question 4.2
Commutator $[\hat{p}(t_1),\hat{p}(t_2)]$
$$\begin{align}
\hat{p}(t_1)\hat{p}(t_2)&=\left(\hat{p}(0)\cos(\omega t_1)-m\omega\hat{x}(0)\sin(\omega t_1)\right)\left(\hat{p}(0)\cos(\omega t_2)-m\omega\hat{x}(0)\sin(\omega t_2)\right)\\\\
&=\hat{p}(0)\cos(\omega t_1)\hat{p}(0)\cos(\omega t_2)-m\omega\hat{x}(0)\sin(\omega t_1)\hat{p}(0)\cos(\omega t_2)\\&-\hat{p}(0)\cos(\omega t_1)m\omega\hat{x}(0)\sin(\omega t_2)+m\omega\hat{x}(0)\sin(\omega t_1)m\omega\hat{x}(0)\sin(\omega t_2)\\\\
&=\hat{p}(0)\cos(\omega t_1)\hat{p}(0)\cos(\omega t_2)-m\omega\hat{x}(0)\sin(\omega t_1)\hat{p}(0)\cos(\omega t_2)\\&-\hat{p}(0)\cos(\omega t_1)m\omega\hat{x}(0)\sin(\omega t_2)+m\omega\hat{x}(0)\sin(\omega t_1)m\omega\hat{x}(0)\sin(\omega t_2)\\\\
\hat{p}(t_1)\hat{p}(t_2)&=\hat{p}^2(0)\cos(\omega t_1)\cos(\omega t_2)-m\omega\hat{x}(0)\hat{p}(0)\sin(\omega t_1)\cos(\omega t_2)\\&-m\omega\hat{p}(0)\hat{x}(0)\cos(\omega t_1)\sin(\omega t_2)+(m\omega)^2\hat{x}^2(0)\sin(\omega t_1)\sin(\omega t_2)
\end{align}$$
$$\begin{align}
\hat{p}(t_2)\hat{p}(t_1)&=\left(\hat{p}(0)\cos(\omega t_2)-m\omega\hat{x}(0)\sin(\omega t_2)\right)\left(\hat{p}(0)\cos(\omega t_1)-m\omega\hat{x}(0)\sin(\omega t_1)\right)\\\\
&=\hat{p}(0)\cos(\omega t_2)\hat{p}(0)\cos(\omega t_1)-m\omega\hat{x}(0)\sin(\omega t_2)\hat{p}(0)\cos(\omega t_1)\\&-\hat{p}(0)\cos(\omega t_2)m\omega\hat{x}(0)\sin(\omega t_1)+m\omega\hat{x}(0)\sin(\omega t_2)m\omega\hat{x}(0)\sin(\omega t_1)\\\\
&=\hat{p}(0)\cos(\omega t_2)\hat{p}(0)\cos(\omega t_1)-m\omega\hat{x}(0)\sin(\omega t_2)\hat{p}(0)\cos(\omega t_1)\\&-\hat{p}(0)\cos(\omega t_2)m\omega\hat{x}(0)\sin(\omega t_1)+m\omega\hat{x}(0)\sin(\omega t_2)m\omega\hat{x}(0)\sin(\omega t_1)\\\\
\hat{p}(t_2)\hat{p}(t_1)&=\hat{p}^2(0)\cos(\omega t_1)\cos(\omega t_2)-m\omega\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\sin(\omega t_2)\\&-m\omega\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\cos(\omega t_2)+(m\omega)^2\hat{x}^2(0)\sin(\omega t_1)\sin(\omega t_2)
\end{align}$$
$$\begin{align}
\hat{p}(t_1)\hat{p}(t_2)-\hat{p}(t_2)\hat{p}(t_1)
&=\hat{p}^2(0)\cos(\omega t_1)\cos(\omega t_2)-m\omega\hat{x}(0)\hat{p}(0)\sin(\omega t_1)\cos(\omega t_2)\\&-m\omega\hat{p}(0)\hat{x}(0)\cos(\omega t_1)\sin(\omega t_2)+(m\omega)^2\hat{x}^2(0)\sin(\omega t_1)\sin(\omega t_2)\\
&-\hat{p}^2(0)\cos(\omega t_1)\cos(\omega t_2)+m\omega\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\sin(\omega t_2)\\&+m\omega\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\cos(\omega t_2)-(m\omega)^2\hat{x}^2(0)\sin(\omega t_1)\sin(\omega t_2)\\\\
&=-m\omega\hat{x}(0)\hat{p}(0)\sin(\omega t_1)\cos(\omega t_2)+m\omega\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\sin(\omega t_2)\\
&\ \ \ \ -m\omega\hat{p}(0)\hat{x}(0)\cos(\omega t_1)\sin(\omega t_2)+m\omega\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\cos(\omega t_2)\\\\
&=-m\omega\hat{x}(0)\hat{p}(0)\sin(\omega(t_2-t_1))-m\omega\hat{p}(0)\hat{x}(0)\sin(\omega(t_1-t_2))\\\\
&=-m\omega\sin(\omega(t_2-t_1))\left[\hat{x}(0)\hat{p}(0)-\hat{p}(0)\hat{x}(0)\right]\\\\
[\hat{p}(t_1),\hat{p}(t_2)]&=m\omega\sin(\omega(t_1-t_2))\left[\hat{x}(0),\hat{p}(0)\right]\\\\
\Aboxed{[\hat{p}(t_1),\hat{p}(t_2)]&=i\hbar m\omega\sin(\omega(t_1-t_2))}
\end{align}$$
---
#### Question 4.3
Commutator $[\hat{x}(t_1),\hat{p}(t_2)]$
$$\begin{align}
\hat{x}(t_1)\hat{p}(t_2)&=\left(\hat{x}(0)\cos(\omega t_1)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\right)\left(\hat{p}(0)\cos(\omega t_2)-m\omega\hat{x}(0)\sin(\omega t_2)\right)\\

&=\hat{x}(0)\cos(\omega t_1)\hat{p}(0)\cos(\omega t_2)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\hat{p}(0)\cos(\omega t_2)\\
&-\hat{x}(0)\cos(\omega t_1)m\omega\hat{x}(0)\sin(\omega t_2)-\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)m\omega\hat{x}(0)\sin(\omega t_2)\\\\

&=\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\cos(\omega t_2)-\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\sin(\omega t_2)\\
&+\dfrac{1}{m\omega}\hat{p}^2(0)\sin(\omega t_1)\cos(\omega t_2)-m\omega\hat{x}^2(0)\cos(\omega t_1)\sin(\omega t_2)\\\\
\end{align}$$
$$\begin{align}
\hat{p}(t_2)\hat{x}(t_1)
&=\left(\hat{p}(0)\cos(\omega t_2)-m\omega\hat{x}(0)\sin(\omega t_2)\right)\left(\hat{x}(0)\cos(\omega t_1)+\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\right)\\

&=\hat{p}(0)\cos(\omega t_2)\hat{x}(0)\cos(\omega t_1)-m\omega\hat{x}(0)\sin(\omega t_2)\hat{x}(0)\cos(\omega t_1)\\
&+\hat{p}(0)\cos(\omega t_2)\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)-m\omega\hat{x}(0)\sin(\omega t_2)\dfrac{\hat{p}(0)}{m\omega}\sin(\omega t_1)\\\\

&=\hat{p}(0)\hat{x}(0)\cos(\omega t_2)\cos(\omega t_1)-\hat{x}(0)\hat{p}(0)\sin(\omega t_2)\sin(\omega t_1)\\
&+\dfrac{1}{m\omega}\hat{p}^2(0)\cos(\omega t_2)\sin(\omega t_1)-m\omega\hat{x}^2(0)\sin(\omega t_2)\cos(\omega t_1)\\\\
\end{align}$$
$$\begin{align}
\hat{x}(t_1)\hat{p}(t_2)-\hat{p}(t_2)\hat{x}(t_1)

&=\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\cos(\omega t_2)-\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\sin(\omega t_2)\\
&+\dfrac{1}{m\omega}\hat{p}^2(0)\sin(\omega t_1)\cos(\omega t_2)-m\omega\hat{x}^2(0)\cos(\omega t_1)\sin(\omega t_2)\\
&-\hat{p}(0)\hat{x}(0)\cos(\omega t_2)\cos(\omega t_1)+\hat{x}(0)\hat{p}(0)\sin(\omega t_2)\sin(\omega t_1)\\
&-\dfrac{1}{m\omega}\hat{p}^2(0)\cos(\omega t_2)\sin(\omega t_1)+m\omega\hat{x}^2(0)\sin(\omega t_2)\cos(\omega t_1)\\\\

&=\hat{x}(0)\hat{p}(0)\cos(\omega t_1)\cos(\omega t_2)-\hat{p}(0)\hat{x}(0)\sin(\omega t_1)\sin(\omega t_2)\\
&+\hat{x}(0)\hat{p}(0)\sin(\omega t_1)\sin(\omega t_2)-\hat{p}(0)\hat{x}(0)\cos(\omega t_1)\cos(\omega t_2)\\
&+m\omega\hat{x}^2(0)\cos(\omega t_1)\sin(\omega t_2)-m\omega\hat{x}^2(0)\cos(\omega t_1)\sin(\omega t_2)\\
&+\dfrac{1}{m\omega}\hat{p}^2(0)\sin(\omega t_1)\cos(\omega t_2)-\dfrac{1}{m\omega}\hat{p}^2(0)\sin(\omega t_1)\cos(\omega t_2)\\\\

&=\hat{x}(0)\hat{p}(0)[\cos(\omega t_1)\cos(\omega t_2)+\sin(\omega t_1)\sin(\omega t_2)]\\
&-\hat{p}(0)\hat{x}(0)[\cos(\omega t_1)\cos(\omega t_2)+\sin(\omega t_1)\sin(\omega t_2)]\\\\

&=\hat{x}(0)\hat{p}(0)\cos(\omega (t_1-t_2))-\hat{p}(0)\hat{x}(0)\cos(\omega (t_1-t_2))\\\\

&=\cos(\omega (t_1-t_2))[\hat{x}(0),\hat{p}(0)]\\\\

\Aboxed{[\hat{x}(t_1),\hat{p}(t_2)]&=i\hbar\cos(\omega (t_1-t_2))}
\end{align}$$
#### Question 4.4
Discuss if and why your answers make sense for $t_1=t_2$.
$$\begin{align}
[\hat{x}(t_1),\hat{x}(t_2)]&=i\hbar\dfrac{\sin(\omega (t_2-t_1))}{m\omega}\\
[\hat{x}(t_1),\hat{x}(t_1)]&=i\hbar\dfrac{\sin(\omega (t_1-t_1))}{m\omega}\\
&=i\hbar\dfrac{\sin(0\omega)}{m\omega}\\
\Aboxed{[\hat{x}(t_1),\hat{x}(t_1)]&=0}\\
\end{align}$$
$$\begin{align}
[\hat{p}(t_1),\hat{p}(t_2)]&=i\hbar m\omega\sin(\omega(t_1-t_2))\\
[\hat{p}(t_1),\hat{p}(t_1)]&=i\hbar m\omega\sin(\omega(t_1-t_1))\\
&=i\hbar m\omega\sin(0\omega)\\
\Aboxed{[\hat{p}(t_1),\hat{p}(t_1)]&=0}
\end{align}$$
$$\begin{align}
[\hat{x}(t_1),\hat{p}(t_2)]&=i\hbar\cos(\omega (t_1-t_2))\\
[\hat{x}(t_1),\hat{p}(t_1)]&=i\hbar\cos(\omega (t_1-t_1))\\
&=i\hbar\cos(0\omega)\\
\Aboxed{[\hat{p}(t_1),\hat{p}(t_1)]&=i\hbar}
\end{align}$$
If we evaluate position/momentum at the same point in time, it makes sense that the positions/momenta commute with themselves. When the time is equal, you can translate $t\rightarrow0$ (recentering in time) and all the typical commutation relations will hold.
