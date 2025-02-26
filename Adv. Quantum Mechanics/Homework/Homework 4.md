**Name:** Stanley Goodwin
**Date:** 2/21/2025

---
### Question 1
#### Question 1.1
For a function $f(\phi)$ that can be expanded in a Taylor series, show that:
$$\begin{align}
f(\phi+\varphi)&=e^{iL_z\varphi/\hbar}f(\phi)
\end{align}$$
where $\varphi$ is an arbitrary angle. This equation shows that $L_z/\hbar$ is the generator of rotations about the $z$ axis. More generally, for spinors, rotation by angle $\varphi$ about the axis $\hat{n}$ is given by the operator:
$$\begin{align}
R_\hat{n}^\varphi&=e^{i(\sigma\cdot\hat{n})\varphi/2}
\end{align}$$
Starting with the Taylor series about the value $\phi$, we get:
$$\begin{align}
f(\phi+\varphi)
&=\sum_{n=0}^\infty\dfrac{1}{n!}\dfrac{d^n}{d\phi^n}f(\phi)\cdot\varphi^n\\
&=\left(\sum_{n=0}^\infty\dfrac{\varphi^n}{n!}\dfrac{d^n}{d\phi^n}\right)f(\phi)\\
&=\left(\sum_{n=0}^\infty\dfrac{\left(\varphi\tfrac{d}{d\phi}\right)^n}{n!}\right)f(\phi)\\
\Aboxed{f(\phi+\varphi)&=e^{\varphi\tfrac{d}{d\phi}}f(\phi)}
\end{align}$$
To go further, we have to look at angular momentum in cylindrical coordinates, I think:
$$\begin{align}
\vec{L}\cdot\hat{z}&=(\vec{r}\times\vec{p})\cdot\hat{z}\\
&=x\left(-i\hbar\dfrac{\partial}{\partial y}\right)-y\left(-i\hbar\dfrac{\partial}{\partial x}\right)\\
&=-i\hbar \left(x\dfrac{\partial}{\partial y}-y\dfrac{\partial}{\partial x}\right)\\
\Aboxed{L_z&=-i\hbar\dfrac{\partial}{\partial\phi}}
\end{align}$$
Rearranging the expression above with our previous answer, we get that:
$$\begin{align}
f(\phi+\varphi)&=e^{\varphi\tfrac{L_z}{-i\hbar}}f(\phi)\\
&=e^{i\varphi\tfrac{L_z}{\hbar}}f(\phi)\\
\Aboxed{f(\phi+\varphi)&=e^{i\varphi L_z/\hbar}f(\phi)}
\end{align}$$
---
#### Question 1.2
Construct the $2\times2$ matrix $R_x^\pi$ representing rotation by $\pi$ about the $x$-axis.
$$\begin{align}
R_x^\varphi&=e^{i(\sigma\cdot\hat{x})\varphi/2}\\
&=e^{i(\sigma_x)\varphi/2}\\
&=\mathbb{I}\cos(\varphi/2)+i\sigma_x\sin(\varphi/2)\\
&=\begin{bmatrix}\cos(\varphi/2)&0\\0&\cos(\varphi/2)\end{bmatrix}+\begin{bmatrix}0&i\sin(\varphi/2)\\i\sin(\varphi/2)&0\end{bmatrix}\\
R_x^\varphi&=\begin{bmatrix}\cos(\varphi/2)&i\sin(\varphi/2)\\i\sin(\varphi/2)&\cos(\varphi/2)\end{bmatrix}\\
R_x^\pi&=\begin{bmatrix}\cos(\pi/2)&i\sin(\pi/2)\\i\sin(\pi/2)&\cos(\pi/2)\end{bmatrix}\\
&=\begin{bmatrix}0&i\\i&0\end{bmatrix}\\
\Aboxed{R_x^\pi&=i\sigma_x}
\end{align}$$
---
#### Question 1.3
Show that $R_x^\pi$ converts $\chi_z^+$ (spin up) to $\chi_z^-$ (spin down). Draw a diagram to support your conclusion.
$$\begin{align}
R_x^\pi\chi_z^+&=\begin{bmatrix}0&i\\i&0\end{bmatrix}\begin{bmatrix}1\\0\end{bmatrix}\\
&=\begin{bmatrix}0\cdot1+i\cdot0\\i\cdot1+0\cdot0\end{bmatrix}\\
&=\begin{bmatrix}0\\i\end{bmatrix}\\
&=i\begin{bmatrix}0\\1\end{bmatrix}\\
\Aboxed{R_x^\pi\chi_z^+&=i\chi_z^-}\\\\
R_x^\pi\chi_z^-&=\begin{bmatrix}0&i\\i&0\end{bmatrix}\begin{bmatrix}0\\1\end{bmatrix}\\
&=\begin{bmatrix}0\cdot0+i\cdot1\\i\cdot0+0\cdot0\end{bmatrix}\\
&=\begin{bmatrix}i\\0\end{bmatrix}\\
&=i\begin{bmatrix}1\\0\end{bmatrix}\\
\Aboxed{R_x^\pi\chi_z^-&=i\chi_z^+}
\end{align}$$
---
#### Question 1.4
Construct the matrix $R_z^{2\pi}$.
$$\begin{align}
R_z^{2\pi}&=e^{i(\sigma\cdot\hat{z})2\pi/2}\\
&=e^{i\pi\sigma_z}\\
&=\mathbb{I}\cos(\pi)+i\sigma_z\sin(\pi)\\
&=-\begin{bmatrix}1&0\\0&1\end{bmatrix}+0i\begin{bmatrix}1&0\\0&-1\end{bmatrix}\\
\Aboxed{R_z^{2\pi}&=-\mathbb{I}}
\end{align}$$
#### Question 1.5
Find the smallest angle $\theta$ such that application of $R_z^\theta$ restores the original state of any spinor.
$$\begin{align}
\left(R_z^{2\pi}\right)^2&=(-\mathbb{I})^2\\
\Aboxed{R_z^{4\pi}&=\mathbb{I}}
\end{align}$$
The smallest angle $\theta$ that returns a state back to itself is $\boxed{\theta=4\pi}$. I knew this not just because of math but because spinors are spin-1/2 objects, and so rotate half as fast as a vector.
### Question 2
Suppose we put a delta-function bump in the center of the one-dimensional infinite square well of width $a$:
$$\begin{align}
\hat{H}'=\alpha\delta\left(x-\dfrac{a}{2}\right)
\end{align}$$
where $\alpha$ is a constant.

For reference:
$$\begin{align}
\psi_n^0&=\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n\pi}{a}x\right)\\
E_n^0&=\dfrac{\hbar^2\pi^2}{2ma^2}n^2
\end{align}$$
---
#### Question 2.1
Find the first-order correction to the energy of the $n$-th level. Explain why the energy is not perturbed for even $n$.
$$\begin{align}
E_n^1&=\int\bra{\psi_n^0}\hat{H}'\ket{\psi_n^0}\ dx\\
&=\int\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n\pi}{a}x\right)\cdot\alpha\delta\left(x-\dfrac{a}{2}\right)\cdot\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n\pi}{a}x\right)\ dx\\
&=\dfrac{2\alpha}{a}\int\delta\left(x-\dfrac{a}{2}\right)\cdot\sin^2\left(\dfrac{n\pi}{a}x\right)\ dx\\
&=\dfrac{2\alpha}{a}\cdot\sin^2\left(\dfrac{n\pi}{a}\dfrac{a}{2}\right)\\
\Aboxed{E_n^1&=\dfrac{2\alpha}{a}\cdot\sin^2\left(\dfrac{n\pi}{2}\right)}
\end{align}$$
For even values of $n$, $\sin^2(n\pi)=0$ for $n=2k$, and so the energy will also be unperturbed.
The physical reason is because the wavefunction, for even $n$, goes to zero at the middle of the well, so adding an energy value there will make no difference since it doesn't add to any other part of the wavefunction.

---
#### Question 2.2
Find the first three nonzero terms in the expansion of the correction to the ground state wavefunction.
$$\begin{align}
\bra{\psi_m}\hat{H}'\ket{\psi_1}&=\int\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{m\pi}{a}x\right)\cdot\alpha\delta\left(x-\dfrac{a}{2}\right)\cdot\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{\pi}{a}x\right)\ dx\\
&=\dfrac{2\alpha}{a}\int\delta\left(x-\dfrac{a}{2}\right)\cdot\sin\left(\dfrac{m\pi}{a}x\right)\sin\left(\dfrac{\pi}{a}x\right)\ dx\\
&=\dfrac{2\alpha}{a}\sin\left(\dfrac{m\pi}{2}\right)\sin\left(\dfrac{\pi}{2}\right)\\
\Aboxed{\bra{\psi_m}\hat{H}'\ket{\psi_1}&=\dfrac{2\alpha}{a}\sin\left(\dfrac{m\pi}{2}\right)}
\end{align}$$
$$\begin{align}
\psi_1^1(x)&=\sum_{m\ne1}\dfrac{\bra{\psi_m}\hat{H}'\ket{\psi_1}}{E_1^0-E_m^0}\ket{\psi_m}\\
&=\dfrac{2\alpha}{a}\sum_{m\ne1}\dfrac{\sin\left(\tfrac{m\pi}{2}\right)}{\tfrac{\hbar^2\pi^2}{2ma^2}-\tfrac{\hbar^2\pi^2}{2ma^2}m^2}\ket{\psi_m}\\
&=\dfrac{4ma\alpha}{\hbar^2\pi^2}\sum_{m=3,5,7,\dots}\dfrac{\sin\left(\tfrac{m\pi}{2}\right)}{1-m^2}\ket{\psi_m}\\
\psi_1^1(x)&\approx\dfrac{4ma\alpha}{\hbar^2\pi^2}\left(-\dfrac{\ket{\psi_3}}{1-3^2}+\dfrac{\ket{\psi_5}}{1-5^2}-\dfrac{\ket{\psi_7}}{1-7^2}\right)\\
\Aboxed{\psi_1^1(x)&\approx
\dfrac{ma\alpha}{2\hbar^2\pi^2}\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{3\pi}{a}x\right)-\dfrac{ma\alpha}{6\hbar^2\pi^2}\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{5\pi}{a}x\right)+\dfrac{ma\alpha}{12\hbar^2\pi^2}\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{7\pi}{a}x\right)-\dots}
\end{align}$$
---
### Question 3
Two identical bosons are placed in a one-dimensional infinite square well of width $a$. They interact weakly with one another via the potential:
$$\begin{align}
V(x_1,x_2)&=-aV_0\delta(x_1-x_2)
\end{align}$$
where $V_0$ is a constant with the dimensions of energy.

---
#### Question 3.1
First, ignoring the interaction between the particles, find the wavefunctions as well as energies for the ground state and the first excited state.

We can write the Hamiltonian of the system as:
$$\begin{align}
\hat{H}^0&=-\dfrac{\hbar^2}{2m}(\vec\nabla^2_1+\vec\nabla^2_2)+V(x_1)+V(x_2)
\end{align}$$
When the particles are within the box ($0<x<a$), $V(x_1)=V(x_2)=0$.
$$\begin{align}
\hat{H}^0\ket\psi&=-\dfrac{\hbar^2}{2m}\left(\dfrac{\partial}{\partial x_1}+\dfrac{\partial}{\partial x_2}\right)\ket\psi\\
\psi_{n_1,n_2}(x_1,x_2)&=\left(\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n_1\pi}{a}x_1\right)\right)\left(\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n_2\pi}{a}x_2\right)\right)\\
\Aboxed{\psi_{n_1,n_2}(x_1,x_2)&=\dfrac{2}{a}\sin\left(\dfrac{n_1\pi}{a}x_1\right)\sin\left(\dfrac{n_2\pi}{a}x_2\right)}\\
\Aboxed{E_{n_1,n_2}&=\dfrac{\hbar^2\pi^2}{2ma^2}\left(n_1^2+n_2^2\right)}
\end{align}$$
For the ground state:
$$\begin{align}
\Aboxed{\psi_{1,1}(x_1,x_2)&=\dfrac{2}{a}\sin\left(\dfrac{\pi}{a}x_1\right)\sin\left(\dfrac{\pi}{a}x_2\right)}\\
\Aboxed{E_{1,1}&=\dfrac{\hbar^2\pi^2}{ma^2}}
\end{align}$$
For the first excited state:
$$\begin{align}
\Aboxed{\psi_{12|21}(x_1,x_2)&=\dfrac{\sqrt{2}}{a}\sin\left(\dfrac{2\pi}{a}x_1\right)\sin\left(\dfrac{\pi}{a}x_2\right)+\dfrac{\sqrt{2}}{a}\sin\left(\dfrac{\pi}{a}x_1\right)\sin\left(\dfrac{2\pi}{a}x_2\right)}\\
\Aboxed{E_{12|21}&=\dfrac{5\hbar^2\pi^2}{2ma^2}}
\end{align}$$
---
#### Question 3.2
Use first-order perturbation theory to estimate the effect of the particle-particle interaction on the energies of the ground state and the first excited state.

Let $\hat{H}'=-aV_0\delta(x_1-x_2)$, then:

**Ground State**
$$\begin{align}
E_1^1&=\int\bra{\psi_{1,1}^0}\hat{H}'\ket{\psi_{1,1}^0}\ dx\\
&=-\iint\dfrac{2}{a}\sin\left(\dfrac{\pi}{a}x_1\right)\sin\left(\dfrac{\pi}{a}x_2\right)\cdot aV_0\delta(x_1-x_2)\cdot\dfrac{2}{a}\sin\left(\dfrac{\pi}{a}x_1\right)\sin\left(\dfrac{\pi}{a}x_2\right)\ dx_1dx_2\\
&=-\dfrac{4aV_0}{a^2}\int_0^a\int_0^a \delta(x_1-x_2)\cdot\sin^2\left(\dfrac{\pi}{a}x_1\right)\sin^2\left(\dfrac{\pi}{a}x_2\right)\ dx_1dx_2\\
&=-\dfrac{4aV_0}{a^2}\int_0^a\int_{-x_2}^{a-x_2} \delta(x)\cdot\sin^2\left(\dfrac{\pi}{a}(x+x_2)\right)\sin^2\left(\dfrac{\pi}{a}x_2\right)\ dx\ dx_2\\
&=-\dfrac{4aV_0}{a^2}\int_0^a \sin^2\left(\dfrac{\pi}{a}x_2\right)\sin^2\left(\dfrac{\pi}{a}x_2\right)\ dx_2\\
&=-\dfrac{4aV_0}{a^2}\int_0^a \sin^4\left(\dfrac{\pi}{a}x_2\right)\ dx_2\\
&=-\dfrac{4aV_0}{a^2}\cdot\dfrac{3a}{8}\\
\Aboxed{E_1^1&=-\dfrac{3}{2}V_0}
\end{align}$$
**First Excited State**
**Post Note:** This solution is incorrect (it's $-2V_0$).
$$\begin{align}
E_1^1&=\int\bra{\psi_{1,1}^0}\hat{H}'\ket{\psi_{1,1}^0}\ dx\\

&=-\iint\dfrac{\sqrt2}{a}\sin\left(\dfrac{2\pi}{a}x_1\right)\sin\left(\dfrac{\pi}{a}x_2\right)\cdot aV_0\delta(x_1-x_2)\cdot\dfrac{\sqrt2}{a}\sin\left(\dfrac{2\pi}{a}x_1\right)\sin\left(\dfrac{\pi}{a}x_2\right)\ dx_1dx_2\\
&\ \ \ \ -\iint\dfrac{\sqrt2}{a}\sin\left(\dfrac{\pi}{a}x_1\right)\sin\left(\dfrac{2\pi}{a}x_2\right)\cdot aV_0\delta(x_1-x_2)\cdot\dfrac{\sqrt2}{a}\sin\left(\dfrac{\pi}{a}x_1\right)\sin\left(\dfrac{2\pi}{a}x_2\right)\ dx_1dx_2\\

&=-\dfrac{2aV_0}{a^2}\int_{0}^{a}\int_{0}^{a}\delta(x_1-x_2)\sin^2\left(\dfrac{2\pi}{a}x_1\right)\sin^2\left(\dfrac{\pi}{a}x_2\right)\ dx_1dx_2\\
&\ \ \ \ -\dfrac{2aV_0}{a^2}\int_{0}^{a}\int_{0}^{a}\delta(x_1-x_2)\sin^2\left(\dfrac{\pi}{a}x_1\right)\sin^2\left(\dfrac{2\pi}{a}x_2\right)\ dx_1dx_2\\

&=-\dfrac{2aV_0}{a^2}\int_{0}^{a}\int_{-x_2}^{a-x_2}\delta(x)\sin^2\left(\dfrac{2\pi}{a}(x_2+x)\right)\sin^2\left(\dfrac{\pi}{a}x_2\right)\ dx\ dx_2\\
&\ \ \ \ -\dfrac{2aV_0}{a^2}\int_{0}^{a}\int_{-x_2}^{a-x_2}\delta(x)\sin^2\left(\dfrac{\pi}{a}(x_2+x)\right)\sin^2\left(\dfrac{2\pi}{a}x_2\right)\ dx\ dx_2\\

&=-\dfrac{2aV_0}{a^2}\int_{0}^{a}\sin^2\left(\dfrac{2\pi}{a}x_2\right)\sin^2\left(\dfrac{\pi}{a}x_2\right)\ dx_2\\
&\ \ \ \ -\dfrac{2aV_0}{a^2}\int_{0}^{a}\sin^2\left(\dfrac{\pi}{a}x_2\right)\sin^2\left(\dfrac{2\pi}{a}x_2\right)\ dx_2\\

&=-\dfrac{4aV_0}{a^2}\int_{0}^{a}\sin^2\left(\dfrac{2\pi}{a}x_2\right)\sin^2\left(\dfrac{\pi}{a}x_2\right)\ dx_2\\

&=-\dfrac{4aV_0}{a^2}\dfrac{a}{4}\\
\Aboxed{E_1^1&=-V_0}
\end{align}$$
---
### Question 4
We perturb an infinite cubical well (side $a$) with a bump:
$$\begin{align}
H'=a^3V_0\delta\left(x-\dfrac{a}{4}\right)\delta\left(y-\dfrac{a}{2}\right)\delta\left(z-\dfrac{3a}{4}\right)
\end{align}$$
Find the resulting first-order energy corrections to the (triply degenerate) first excited states.

**Unperturbed State**
$$\begin{align}
\psi_{n_x,n_y,n_z}(x,y,z)&=\left(\dfrac{2}{a}\right)^\tfrac{3}{2}\sin\left(\dfrac{n_x\pi}{a}x\right)\sin\left(\dfrac{n_y\pi}{a}y\right)\sin\left(\dfrac{n_z\pi}{a}z\right)\\
E_{n_x,n_y,n_z}&=\dfrac{\hbar^2\pi^2}{2ma^2}\left(n_x^2+n_y^2+n_z^2\right)
\end{align}$$
**First-Order Correction of Energy**
So the math doesn't fall off the page, lets calculate $\bra{\psi_{n_x,n_y,n_z}^0}\delta(\vec{x}-\vec{x}_0)\ket{\psi_{n_x,n_y,n_z}^0}$.
$$\begin{align}
\int\bra{\psi_{n_x,n_y,n_z}^0}\delta(\vec{x}-\vec{x}_0)\ket{\psi_{n_x,n_y,n_z}^0}\ d^3\vec{x}
&=\iiint\delta\left(x-\dfrac{a}{4}\right)\delta\left(y-\dfrac{a}{2}\right)\delta\left(z-\dfrac{3a}{4}\right)
\\& \ \ \ \ \left(\dfrac{2}{a}\right)^3\cdot\sin^2\left(\dfrac{n_x\pi}{a}x\right)\sin^2\left(\dfrac{n_y\pi}{a}y\right)\sin^2\left(\dfrac{n_z\pi}{a}z\right)\\
&=\dfrac{8}{a^3}\sin^2\left(\dfrac{n_x\pi}{a}\dfrac{a}{4}\right)\sin^2\left(\dfrac{n_y\pi}{a}\dfrac{a}{2}\right)\sin^2\left(\dfrac{n_z\pi}{a}\dfrac{3a}{4}\right)\\
\Aboxed{\int\bra{\psi_{n_x,n_y,n_z}^0}\delta(\vec{x}-\vec{x}_0)\ket{\psi_{n_x,n_y,n_z}^0}\ d^3\vec{x}
&=\dfrac{8}{a^3}\sin^2\left(\dfrac{n_x\pi}{4}\right)\sin^2\left(\dfrac{n_y\pi}{2}\right)\sin^2\left(\dfrac{3n_z\pi}{4}\right)}
\end{align}$$
So we can then find the energy correction:
$$\begin{align}
E_{n_x,n_y,n_z}^1&=\int\bra{\psi_{n_x,n_y,n_z}^0}\hat{H}'\ket{\psi_{n_x,n_y,n_z}^0}\ d^3\vec{x}\\
&=\int\bra{\psi_{n_x,n_y,n_z}^0}a^3V_0\delta\left(\vec{x}-\vec{x}_0\right)\ket{\psi_{n_x,n_y,n_z}^0}\ d^3\vec{x}\\
&=a^3V_0\int\bra{\psi_{n_x,n_y,n_z}^0}\delta\left(\vec{x}-\vec{x}_0\right)\ket{\psi_{n_x,n_y,n_z}^0}\ d^3\vec{x}\\
&=a^3V_0\dfrac{8}{a^3}\sin^2\left(\dfrac{n_x\pi}{4}\right)\sin^2\left(\dfrac{n_y\pi}{2}\right)\sin^2\left(\dfrac{3n_z\pi}{4}\right)\\
\Aboxed{E_{n_x,n_y,n_z}^1&=8V_0\sin^2\left(\dfrac{n_x\pi}{4}\right)\sin^2\left(\dfrac{n_y\pi}{2}\right)\sin^2\left(\dfrac{3n_z\pi}{4}\right)}
\end{align}$$
We can then evaluate the 3 first excited states:
$$\begin{align}
E_{2,1,1}^1&=8V_0\sin^2\left(\dfrac{2\pi}{4}\right)\sin^2\left(\dfrac{1\pi}{2}\right)\sin^2\left(\dfrac{3\pi}{4}\right)\\
&=8V_0\sin^2\cdot1\cdot1\cdot\dfrac{1}{2}\\
\Aboxed{E_{2,1,1}^1&=4V_0}\\\\
E_{1,2,1}^1&=8V_0\sin^2\left(\dfrac{1\pi}{4}\right)\sin^2\left(\dfrac{2\pi}{2}\right)\sin^2\left(\dfrac{3\pi}{4}\right)\\
&=8V_0\cdot\dfrac{1}{2}\cdot0\cdot\dfrac{1}{2}\\
\Aboxed{E_{1,2,1}^1&=0}\\\\
E_{1,1,2}^1&=8V_0\sin^2\left(\dfrac{1\pi}{4}\right)\sin^2\left(\dfrac{1\pi}{2}\right)\sin^2\left(\dfrac{6\pi}{4}\right)\\
&=8V_0\cdot\dfrac{1}{2}\cdot1\cdot1\\
\Aboxed{E_{1,1,2}^1&=4V_0}
\end{align}$$
Very interesting. With this additional potential, the previously degenerate states split apart into a doubly-degenerate state and an unchanged state (under first order correction).
