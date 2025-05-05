**Name:** Stanley Goodwin
**Date:** 3/30/2025

---
### Question 1
A simple quantum pendulum of length $L$ and mass $m$ swings in a vertical plane under the influence of gravity. Its potential energy is given by:
$$\begin{align}
V(\theta)&=mgL\left[1-\cos\theta\right]
\end{align}$$
where $g$ is the acceleration due to gravity.

---
#### Question 1.1
In the small angle approximation (lowest nontrivial order in $\theta$), find the quantized energy levels of the system.

**Hamiltonian**
$$\begin{align}
\hat{H}&=\dfrac{1}{2}I\omega^2+mgL\left[1-\cos\theta\right]\\
&=\dfrac{1}{2}I\left(\dfrac{p_\dot{\theta}}{I}\right)^2+mgL\left[1-1+\dfrac{1}{2}\theta^2+O(\theta^4)\right]\\
&=\dfrac{p_\dot{\theta}^2}{2I}+mgL\left[1-1+\dfrac{1}{2}\theta^2-\dfrac{1}{24}\theta^4+O(\theta^6)\right]\\
\Aboxed{\hat{H}_0&=\dfrac{p_\dot{\theta}^2}{2mL^2}+\dfrac{1}{2}mgL\theta^2}
\end{align}$$
This looks very much like a QHO system, with $\theta$ and $p_\dot{\theta}$ being Fourier conjugates.
Comparing between this system and the typical QHO:
$$\begin{align}
\hat{H}_0(\theta,p_\dot{\theta})&=\dfrac{p_\dot{\theta}^2}{2mL^2}+\dfrac{1}{2}\dfrac{mg}{L}(L\theta)^2\\
\hat{H}_0(x,p)&=\dfrac{p^2}{2m}+\dfrac{1}{2} m\omega^2x^2\\
\end{align}$$
We can then find the following relationship from the potential part:
$$\begin{align}
m\omega^2&=\dfrac{mg}{L}\\
\Aboxed{\omega^2&=g/L}
\end{align}$$
And so the energy states of this system (for small angle approximation) are:
$$\begin{align}
E_n&=\left(n+\dfrac{1}{2}\right)\hbar\omega& \implies&&\Aboxed{E_n&=\left(n+\dfrac{1}{2}\right)\hbar\sqrt{\dfrac{g}{L}}}
\end{align}$$

---
#### Question 1.2
Considering the next higher order term in the angle, use perturbation theory to evaluate the first order correction to the ground state energy.

**Hamiltonian**
$$\begin{align}
\Aboxed{\hat{H}_1=-\dfrac{1}{24}mgL\theta^4}
\end{align}$$
where $\hat{H}\approx\hat{H}_0+\hat{H}_1$. Using the following for the ground state:
$$\begin{align}
\psi_0(x)&=\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}e^{-m\omega x^2/2\hbar}\\
\psi_0(L\theta)&=\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}e^{-m\omega L^2\theta^2/2\hbar}\\
\Aboxed{\psi_0(\theta)&=\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}e^{-I\omega\theta^2/2\hbar}}
\end{align}$$
we can then find the next energy as:
$$\begin{align}
E^1_0&=\bra{\psi_0^0}\hat{H}_1\ket{\psi_0^0}\\
&=
\int\left(\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}e^{-I\omega\theta^2/2\hbar}\right)\left(-\dfrac{1}{24}mgL\theta^4\right)\left(\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}e^{-I\omega\theta^2/2\hbar}\right)\ Ld\theta\\
&=
-\dfrac{1}{24}mgL^2\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/2}\int_{-\infty}^\infty\theta^4e^{-(I\omega/\hbar)\theta^2}\ d\theta\\
&=
-\dfrac{1}{24}mgL^2\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/2}\left(\dfrac{\hbar}{I\omega}\right)^2\int_{-\infty}^\infty\left(\sqrt{\dfrac{I\omega}{\hbar}}\theta\right)^4e^{-(I\omega/\hbar)\theta^2}\ d\theta\\
&=
-\dfrac{1}{24}mgL^2\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/2}\left(\dfrac{\hbar}{I\omega}\right)^2\sqrt{\dfrac{\hbar}{I\omega}}\int_{-\infty}^\infty u^4e^{-u^2}\ d\theta\\
&=
-\dfrac{1}{24}mgL^2\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/2}\left(\dfrac{\hbar}{mL^2\omega}\right)^2\sqrt{\dfrac{\hbar}{mL^2\omega}}\cdot\dfrac{3}{4}\sqrt{\pi}\\
&=-\dfrac{1}{32}mgL\dfrac{\hbar^2}{m^2L^4\omega^2}\\
&=-\dfrac{1}{32}\dfrac{g\hbar^2}{mL^3\omega^2}\\
\Aboxed{E^1_0&=-\dfrac{1}{32}\dfrac{\hbar^2}{mL^2}}
\end{align}$$
In total, we can find that:
$$\begin{align}
E_0&\approx\dfrac{1}{2}\hbar\sqrt{\dfrac{g}{L}}-\dfrac{1}{32}\dfrac{\hbar^2}{mL^2}
\end{align}$$
I'm not 100% sure about the answer, but I'm relatively confident.

---
### Question 2
For the matrix $H=H_0+H_1$, where:
$$\begin{align}
H_0&=\left[\begin{array}{ccc}2&0&0\\0&2&0\\0&0&4\end{array}\right] & 
H_1&=\left[\begin{array}{ccc}0&1&0\\1&0&1\\0&1&0\end{array}\right]
\end{align}$$
use perturbation theory to determine the eigenvalues of $H$ to the highest order tackled in class. Then compare your answers to that yielded by a numerical diagonalization of $H$.

**0th Order Terms of Hamiltonian**
The eigenvalues/vectors of $\hat{H}_0$ are:
$$\begin{align}
E_1^0&=2, & E_2^0&=2, & E_3^0&=4\\
\ket{1}^0&=\begin{bmatrix}1\\0\\0\end{bmatrix}, & \ket{2}^0&=\begin{bmatrix}0\\1\\0\end{bmatrix}, & \ket{3}^0&=\begin{bmatrix}0\\0\\1\end{bmatrix}\\
\end{align}$$
Since the matrix is already diagonal.

**1st Order Terms of Hamiltonian**
$$\begin{align}
E_1^1&=\bra{1}^0H_1\ket{1}^0=\begin{bmatrix}1&0&0\end{bmatrix}\left[\begin{array}{ccc}0&1&0\\1&0&1\\0&1&0\end{array}\right]\begin{bmatrix}1\\0\\0\end{bmatrix}=0\\
E_2^1&=\bra{2}^0H_1\ket{2}^0=\begin{bmatrix}0&1&0\end{bmatrix}\left[\begin{array}{ccc}0&1&0\\1&0&1\\0&1&0\end{array}\right]\begin{bmatrix}0\\1\\0\end{bmatrix}=0\\
E_3^1&=\bra{3}^0H_1\ket{3}^0=\begin{bmatrix}0&0&1\end{bmatrix}\left[\begin{array}{ccc}0&1&0\\1&0&1\\0&1&0\end{array}\right]\begin{bmatrix}0\\0\\1\end{bmatrix}=0\\
\end{align}$$
All of them are 0 since the matrix $H_1$ has 0s along the diagonal, so we'll need to use the 2nd Order Terms.

**0th Order Degeneracy Terms**
Something of note is that $\ket{1}^0$ and $\ket{2}^0$ have the same energy, so degenerate perturbation would be needed. I write $\tilde{H}_1$ to be the the part of the matrix with only  $\ket{1}^0$ and $\ket{2}^0$.
$$\begin{align}
\tilde{H}_1&=\left[\begin{array}{ccc}0&1\\1&0\end{array}\right]\\
\end{align}$$
If we diagonalize this, we find that:
$$\begin{align}
\tilde{E}_a^1&=3, & \tilde{E}_b^1&=1\\
\ket{a}^1&=\dfrac{1}{\sqrt2}\begin{bmatrix}1\\1\end{bmatrix}, & \ket{b}^1&=\dfrac{1}{\sqrt2}\begin{bmatrix}1\\-1\end{bmatrix}
\end{align}$$

**2nd Order Terms of Hamiltonian**
$$\begin{align}
E_n^2&=\sum\dfrac{\left|\bra{m}^0H_1\ket{n}^0\right|^2}{E_n^0-E_m^0}
\end{align}$$
Which leads to the following:
$$\begin{align}
E_a^2&=\sum_{m\neq a}\dfrac{\left|\bra{m}^0\tilde{H}_1\ket{a}\right|^2}{E_a^0-E_m^0}\\
&=\dfrac{\left|1/\sqrt{2}\right|^2}{3-4}\\
\Aboxed{E_a^2&=-\dfrac{1}{2}}\\
E_b^2&=\sum_{m\neq a}\dfrac{\left|\bra{m}^0\tilde{H}_1\ket{b}\right|^2}{E_b^0-E_m^0}\\
&=\dfrac{\left|1/\sqrt{2}\right|^2}{1-4}\\
\Aboxed{E_a^2&=-\dfrac{1}{6}}\\
E_3^2&=\sum_{m\neq a}\dfrac{\left|\bra{m}^0\tilde{H}_1\ket{3}\right|^2}{E_3^0-E_m^0}\\
&=\dfrac{\left|1/\sqrt{2}\right|^2}{4-2}+\dfrac{\left|1/\sqrt{2}\right|^2}{4-2}\\
\Aboxed{E_3^2&=+\dfrac{1}{2}}\\
\end{align}$$
**Final Contributions**
$$\begin{align}
E_1&\approx E_a^0+E_a^1\\
&=3-\dfrac{1}{2}\\
\Aboxed{E_1&\approx2.5}\\\\
E_2&\approx E_b^0+E_b^1\\
&=1-\dfrac{1}{6}\\
\Aboxed{E_2&\approx5/6=0.833\dots}\\\\
E_1&\approx E_3^0+E_3^1\\
&=4+\dfrac{1}{2}\\
\Aboxed{E_3&\approx4.5}
\end{align}$$
**Explicit Answer**
We start with the Hamiltonian:
$$\begin{align}
H&=\left[\begin{array}{ccc}2&1&0\\1&2&1\\0&1&4\end{array}\right]
\end{align}$$
We can find the eigenvalues by:
$$\begin{align}
\det(H-\lambda\mathbb{I})&=\left|\begin{array}{ccc}2-\lambda&1&0\\1&2-\lambda&1\\0&1&4-\lambda\end{array}\right|\\
\end{align}$$
The solutions of which are (using Wolfram Alpha):
$$\begin{align}
\lambda_1&\approx4.481\\
\lambda_2&\approx2.689\\
\lambda_3&\approx0.830\\
\end{align}$$
These are very similar to what I calculated, so I'm satisfied.

---
### Question 3
Consider a hydrogen atom in its ground state, which, beyond time $t=0$, is subject to a spatially uniform but time-dependent electric field $E_0e^{-t/\tau}$. Treating the electric field as a perturbation, calculate to first order the probability of finding the atom in the state $n=2,l=1,m=0$. 

**The Hamiltonian**
$$\begin{align}
\hat{H}_1(t)&=\vec\mu\cdot\vec{E}\\
&=-q(x\hat{x}+y\hat{y}+z\hat{z})\cdot E_0e^{-t/\tau}\hat{z}\\
&=-eE_0ze^{-t/\tau}\\
\Aboxed{\hat{H}_1(t)&=-eE_0\cos\theta\ re^{-t/\tau}}
\end{align}$$
**Transition Coefficient**
$$\begin{align}
\omega_T&=\dfrac{|E_2-E_1|}{\hbar}=10.2\text{ eV}\\
\bra{\psi_{2,1,0}}r\cos\theta\ket{\psi_{1,0,0}}&=\dfrac{1}{\sqrt{2}}\dfrac{3a_0}{2}\\
\bra{\psi_{2,1,0}}\hat{H}_1(\tau)\ket{\psi_{1,0,0}}&=-\dfrac{3a_0eE_0}{2\sqrt{2}}e^{-t/\tau}
\end{align}$$
These were found for hydrogen states, where the derivation is *very long*.
$$\begin{align}
c_{2,1,0}(t)&=-\dfrac{i}{\hbar}\int_0^te^{i\omega_T\lambda}\bra{\psi_{2,1,0}}\hat{H}_1(\lambda)\ket{\psi_{1,0,0}}\ d\lambda\\
&=i\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\int_0^te^{i\omega_T\lambda}e^{-\lambda/\tau}\ d\lambda\\
&=i\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\int_0^te^{(i\omega_T-1/\tau)\lambda}\ d\lambda\\
&=i\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\left.\dfrac{e^{(i\omega_T-1/\tau)\lambda}}{(i\omega_T-1/\tau)}\right|_0^t\\
\Aboxed{c_{2,1,0}(t)&=i\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\cdot\dfrac{e^{(i\omega_T-1/\tau)t}-1}{(i\omega_T-1/\tau)}}
\end{align}$$
**Transition Probability**
$$\begin{align}
p(t)&=c^*_{2,1,0}(t)c_{2,1,0}(t)\\
&=\left(-i\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\cdot\dfrac{e^{(-i\omega_T-1/\tau)t}-1}{(i\omega_T-1/\tau)^*}\right)\left(i\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\cdot\dfrac{e^{(i\omega_T-1/\tau)t}-1}{(i\omega_T-1/\tau)}\right)\\
&=\left(\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\right)^2\left(-i^2\cdot\dfrac{(e^{(-i\omega_T-1/\tau)t}-1)(e^{(i\omega_T-1/\tau)t}-1)}{(i\omega_T-1/\tau)^*(i\omega_T-1/\tau)}\right)\\
&=\left(\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\right)^2\left(\dfrac{(e^{(-i\omega_T-1/\tau)t}-1)(e^{(i\omega_T-1/\tau)t}-1)}{(i\omega_T+1/\tau)(-i\omega_T+1/\tau)}\right)\\
&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\right)^2\left((e^{(-i\omega_T-1/\tau)t}-1)(e^{(i\omega_T-1/\tau)t}-1)\right)\\
&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\right)^2\left(e^{(-i\omega_T-1/\tau)t}e^{(i\omega_T-1/\tau)t}-e^{(i\omega_T-1/\tau)t}-e^{(-i\omega_T-1/\tau)t}+1\right)\\
&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{3a_0eE_0}{2\sqrt{2}\hbar}\right)^2\left(e^{(-2/\tau)t}-2e^{(-1/\tau)t}\left[\dfrac{e^{i(\omega_Tt)}+e^{-i(\omega_Tt)}}{2}\right]+1\right)\\
\Aboxed{p(t)&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)\left(e^{-2t/\tau}-2e^{-t/\tau}\cos(\omega_T t)+1\right)}
\end{align}$$
What form does the probability take for late times $t\gg\tau$?
$$\begin{align}
\lim_{t\rightarrow\infty\tau}p(t)&=\lim_{t\rightarrow\infty\tau}\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)\left(e^{(-2/\tau)t}-2e^{(-1/\tau)t}\cos(\omega_T t)+1\right)\\
&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)\lim_{t\rightarrow\infty\tau}\left(e^{(-2/\tau)t}-2e^{(-1/\tau)t}\cos(\omega_T t)+1\right)\\
&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)\left(0-2\cdot0\cos(\omega_T t)+1\right)\\
\Aboxed{p(t\gg \tau)&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)}
\end{align}$$
Very interesting! I didn't think it would decay into a constant value that's unlikely.
Though this is probably right, I want to do a little more arithmetic.
$$\begin{align}
p(t\gg\tau)&=\dfrac{1}{\omega_T^2+1/\tau^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)\\
&=\dfrac{1}{|E_2-E_1|^2/\hbar^2+1/\tau^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)\\
&=\dfrac{\hbar^2\tau^2}{|E_2-E_1|^2\tau^2+\hbar^2}\left(\dfrac{9a_0^2e^2E_0^2}{8\hbar^2}\right)\\
\Aboxed{p(t\gg\tau)&=\dfrac{9}{8}\dfrac{\tau^2}{|E_2-E_1|^2\tau^2+\hbar^2}\left(a_0^2e^2E_0^2\right)}
\end{align}$$

---
### Question 4
A particle of mass $m$ moves in the three-dimensional attractive central potential:
$$\begin{align}
V(r)&=-\dfrac{g^2}{r^{3/2}}
\end{align}$$
where $g$ is a constant. Using the normalized function:
$$\begin{align}
\psi(r)&=\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}
\end{align}$$
as the trial function, estimate an upper bound to the energy of the ground state.

We can write the Hamiltonian:
$$\begin{align}
\hat{H}&=-\dfrac{\hbar^2}{2m}\vec\nabla^2-\dfrac{g^2}{r^{3/2}}
\end{align}$$
**Spherical Laplacian**
$$\begin{align}
\vec\nabla^2\ket{\psi}&=\dfrac{1}{r^2}\dfrac{\partial}{\partial r}\left(r^2\dfrac{\partial}{\partial r}\right)\ket{\psi}\\
&=\sqrt{\dfrac{k^3}{8\pi}}\cdot\dfrac{1}{r^2}\dfrac{\partial}{\partial r}\left(r^2\dfrac{\partial}{\partial r}e^{-kr/2}\right)\\
&=-\dfrac{k}{2}\sqrt{\dfrac{k^3}{8\pi}}\cdot\dfrac{1}{r^2}\dfrac{\partial}{\partial r}\left(r^2e^{-kr/2}\right)\\
&=-\dfrac{k}{2}\sqrt{\dfrac{k^3}{8\pi}}\cdot\dfrac{1}{r^2}\left(-\dfrac{k}{2}r^2e^{-kr/2}+2re^{-kr/2}\right)\\
\vec\nabla^2\ket{\psi}&=\dfrac{1}{r^2}\sqrt{\dfrac{k^3}{8\pi}}\left(\dfrac{k^2}{4}r^2e^{-kr/2}-kre^{-kr/2}\right)\\
\end{align}$$
**Expected Value of Kinetic Energy**
$$\begin{align}
\bra{\psi}\hat{T}\ket{\psi}
&=\int\left(\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}\right)\left(-\dfrac{\hbar^2}{2m}\vec\nabla^2\right)\left(\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}\right)\ dV\\
&=-\dfrac{\hbar^2}{2m}\int\left(\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}\right)\left(\vec\nabla^2\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}\right)\ dV\\
&=-\dfrac{\hbar^2}{2m}\int_0^\infty\left(\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}\right)\left(\dfrac{1}{r^2}\sqrt{\dfrac{k^3}{8\pi}}\left(\dfrac{k^2}{4}r^2e^{-kr/2}-kre^{-kr/2}\right)\right)\ 4\pi r^2 dr\\
&=-\dfrac{4\pi\hbar^2}{2m}\dfrac{k^3}{8\pi}\int_0^\infty\left(e^{-kr/2}\right)\left(\dfrac{k^2}{4}r^2e^{-kr/2}-kre^{-kr/2}\right)\ dr\\
&=-\dfrac{\hbar^2k^3}{16m}\int_0^\infty(kr)^2e^{-(kr)}\ dr+\dfrac{\hbar^2k^3}{4m}\int_0^\infty (kr)e^{-(kr)}\ dr\\
&=-\dfrac{\hbar^2k^3}{16mk}\int_0^\infty u^2e^{-u}\ dr+\dfrac{\hbar^2k^3}{4mk}\int_0^\infty ue^{-u}\ dr\\
&=-\dfrac{\hbar^2k^2}{16m}\cdot2+\dfrac{\hbar^2k^2}{4m}\cdot1\\
\Aboxed{\braket{\hat{T}}&=\dfrac{\hbar^2k^2}{8m}}
\end{align}$$
**Expected Value of Potential Energy**
$$\begin{align}
\bra{\psi}\hat{V}\ket{\psi}
&=\int\left(\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}\right)\left(-\dfrac{g^2}{r^{3/2}}\right)\left(\sqrt{\dfrac{k^3}{8\pi}}e^{-kr/2}\right)\ dV\\
&=-g^2\dfrac{k^3}{8\pi}\int_0^\infty\dfrac{1}{r^{3/2}}e^{-kr}\ 4\pi r^2\ dr\\
&=-\dfrac{g^2 k^3}{2\sqrt{k}}\int_0^\infty\sqrt{kr}e^{-(kr)}\ dr\\
&=-\dfrac{g^2 k^2}{2\sqrt{k}}\int_0^\infty\sqrt{u}e^{-u}\ dr\\
&=-\dfrac{g^2 k^2}{2\sqrt{k}}\cdot\dfrac{\sqrt{\pi}}{2}\\
\Aboxed{\bra{\psi}\hat{V}\ket{\psi}&=-\dfrac{g^2 k^2}{4}\sqrt{\dfrac{\pi}{k}}}
\end{align}$$
**Minimizing Total Energy**
$$\begin{align}
\dfrac{d}{dk}\braket{\hat{H}}
&=\dfrac{d}{dk}\braket{\hat{T}}+\dfrac{d}{dk}\braket{\hat{V}}\\
&=\dfrac{d}{dk}\left(\dfrac{\hbar^2k^2}{8m}\right)+\dfrac{d}{dk}\left(-\dfrac{\sqrt{\pi}}{4}g^2 k^{3/2}\right)\\
&=\dfrac{\hbar^2}{8m}\dfrac{d}{dk}\left(k^2\right)-\dfrac{\sqrt{\pi}}{4}g^2\dfrac{d}{dk}\left( k^{3/2}\right)\\
0&=\dfrac{\hbar^2}{4m}k+-\dfrac{\sqrt{\pi}}{4}g^2\cdot\dfrac{3}{2}k^{1/2}\\
\dfrac{\hbar^2}{4m}k&=\dfrac{3\sqrt{\pi}}{8}g^2k^{1/2}\\
\sqrt{k}&=\dfrac{4m}{\hbar^2}\dfrac{3\sqrt{\pi}}{8}g^2\\
k_\text{min}&=\left(\dfrac{m}{\hbar^2}\dfrac{3\sqrt{\pi}}{2}g^2\right)^2\\
\Aboxed{k_\text{min}&=\dfrac{9\pi}{4}\dfrac{m^2g^4}{\hbar^4}}
\end{align}$$
**Ground State (Upper Bound)**
$$\begin{align}
E_0&\le\braket{\hat{H}}=\braket{\hat{T}}+\braket{\hat{V}}\\
&=\dfrac{\hbar^2}{8m}k_\text{min}^2-\dfrac{\sqrt{\pi}}{4}g^2 k^{3/2}_\text{min}\\
&=\dfrac{\hbar^2}{8m}\left(\dfrac{9\pi}{4}\dfrac{m^2g^4}{\hbar^4}\right)^2-\dfrac{\sqrt{\pi}}{4}g^2\left(\dfrac{9\pi}{4}\dfrac{m^2g^4}{\hbar^4}\right)^{3/2}\\
&=\dfrac{\hbar^2}{8m}\dfrac{81\pi^2}{16}\dfrac{m^4g^8}{\hbar^8}-\dfrac{\sqrt{\pi}}{4}g^2\dfrac{9\pi}{4}\dfrac{m^2g^4}{\hbar^4}\dfrac{m}{\hbar^2}\dfrac{3\sqrt{\pi}}{2}g^2\\
&=\dfrac{81\pi^2}{128}\dfrac{m^3g^8}{\hbar^6}-\dfrac{27\pi^2}{32}\dfrac{m^3g^8}{\hbar^6}\\
&=\dfrac{27\pi^2}{32}\left(\dfrac{3}{4}-1\right)\dfrac{m^3g^8}{\hbar^6}\\
&=-\dfrac{27\pi^2}{128}\dfrac{m^3g^8}{\hbar^6}\\
\Aboxed{E_0&=\dfrac{27\pi^2}{128}\dfrac{m^3g^8}{\hbar^6}}
\end{align}$$
I removed the sign since we look at it from the out and call binding energy positive.
The previous line has the true energy of the state since it's a bound state.