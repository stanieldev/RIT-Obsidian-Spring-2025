**Name:** Stanley Goodwin
**Date:** 2/16/2025

---
### Problem 1
Show that, for the Pauli matrices $\sigma_i$ along any direction $\hat{n}$,
$$\begin{align}
e^{i(\sigma\cdot\hat{n})\theta}&=\mathbb{I}\cos\theta+i(\sigma\cdot\hat{n})\sin\theta
\end{align}$$
Let's take the exponential and turn it into a Taylor series:
$$\begin{align}
e^{i(\sigma\cdot\hat{n})\theta}
&=\sum_{k=0}^\infty\dfrac{[i(\sigma\cdot\hat{n})\theta]^k}{k!}\\
&=\sum_{k=0,2,4,\dots}\dfrac{[i(\sigma\cdot\hat{n})\theta]^k}{k!}+\sum_{k=1,3,5,\dots}\dfrac{[i(\sigma\cdot\hat{n})\theta]^k}{k!}\\
&=\sum_{k=0}^\infty\dfrac{[i(\sigma\cdot\hat{n})\theta]^{2k}}{(2k)!}+\sum_{k=0}^\infty\dfrac{[i(\sigma\cdot\hat{n})\theta]^{2k+1}}{(2k+1)!}\\
&=\sum_{k=0}^\infty\dfrac{i^{2k}(\sigma\cdot\hat{n})^{2k}\theta^{2k}}{(2k)!}+i(\sigma\cdot\hat{n})\sum_{k=0}^\infty\dfrac{i^{2k}(\sigma\cdot\hat{n})^{2k}\theta^{2k+1}}{(2k+1)!}\\
&=\sum_{k=0}^\infty\dfrac{(-1)^{k}(\mathbb{I})^{k}\theta^{2k}}{(2k)!}+i(\sigma\cdot\hat{n})\sum_{k=0}^\infty\dfrac{(-1)^{k}(\mathbb{I})^{k}\theta^{2k+1}}{(2k+1)!}\\
&=\mathbb{I}\sum_{k=0}^\infty\dfrac{(-1)^{k}}{(2k)!}\theta^{2k}+i(\sigma\cdot\hat{n})\mathbb{I}\sum_{k=0}^\infty\dfrac{(-1)^{k}}{(2k+1)!}\theta^{2k+1}\\
\Aboxed{e^{i(\sigma\cdot\hat{n})\theta}&=\mathbb{I}\cos\theta+i(\sigma\cdot\hat{n})\sin\theta}
\end{align}$$
The simplification come from what $(\sigma\cdot\hat{n})^2$ becomes, which I will show as the following.
Let $a,b,c$ be the components of $\hat{n}$ such that $a^2+b^2+c^2=1$ (to maintain unit length).
$$\begin{align}
(\sigma\cdot\hat{n})^2
&=\left(\begin{bmatrix}\sigma_x\\\sigma_y\\\sigma_z\end{bmatrix}\cdot\begin{bmatrix}a\\b\\c\end{bmatrix}\right)^2\\
&=\left(a\sigma_x+b\sigma_y+c\sigma_z\right)^2\\
&=(a\sigma_x)^2+(b\sigma_y)^2+(c\sigma_z)^2\\
&\ + (ab\sigma_x\sigma_y)+ (ba\sigma_y\sigma_x)\\
&\ + (bc\sigma_y\sigma_z)+ (cb\sigma_z\sigma_y)\\
&\ + (ca\sigma_z\sigma_x)+ (ac\sigma_x\sigma_z)\\
&=a^2+b^2+c^2+ab\left\{\sigma_x,\sigma_y\right\}+bc\left\{\sigma_y,\sigma_z\right\}+ca\left\{\sigma_z,\sigma_x\right\}\\
&=a^2+b^2+c^2+0+0+0\\
\Aboxed{(\sigma\cdot\hat{n})^2&=1}
\end{align}$$
---
### Problem 2
For the general normalized spinor $\chi=\begin{bmatrix}a\\b\end{bmatrix}$, calculate the following quantities.

For the sake of the problem, I'll be using $a=\cos(\tfrac{\theta}{2})$ and $b=\sin(\tfrac{\theta}{2})$, as well as assuming there is no phase between the states since that led to messier answers when I didn't assume that and I don't think we ever went over the phase offset stuff.

I had previously done it with the following form:
$a=\cos(\tfrac{\theta}{2})e^{i\alpha}$ and $b=\sin(\tfrac{\theta}{2})e^{i\beta}$.

---
#### Problem 2.1
$$\begin{align}
\langle S_x\rangle
&=\bra{\chi}S_x\ket{\chi}\\
&=\dfrac{\hbar}{2}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}0&1\\1&0\end{bmatrix}\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar}{2}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}\sin(\tfrac{\theta}{2})\\\cos(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar}{2}\left[\cos(\tfrac{\theta}{2})\sin(\tfrac{\theta}{2})+\sin(\tfrac{\theta}{2})\cos(\tfrac{\theta}{2})\right]\\
&=\dfrac{\hbar}{2}\left[2\sin(\tfrac{\theta}{2})\cos(\tfrac{\theta}{2})\right]\\
&=\dfrac{\hbar}{2}\sin(2\cdot\tfrac{\theta}{2})\\
\Aboxed{\langle S_x\rangle&=\dfrac{\hbar}{2}\sin(\theta)}
\end{align}$$
---
#### Problem 2.2
$$\begin{align}
\langle S_y\rangle
&=\bra{\chi}S_y\ket{\chi}\\
&=\dfrac{i\hbar}{2}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}0&-1\\1&0\end{bmatrix}\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{i\hbar}{2}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}-\sin(\tfrac{\theta}{2})\\\cos(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{i\hbar}{2}\left[-\cos(\tfrac{\theta}{2})\sin(\tfrac{\theta}{2})+\sin(\tfrac{\theta}{2})\cos(\tfrac{\theta}{2})\right]\\
&=\dfrac{i\hbar}{2}\cdot0\\
\Aboxed{\langle S_y\rangle&=0}
\end{align}$$
---
#### Problem 2.3
$$\begin{align}
\langle S_z\rangle
&=\bra{\chi}S_z\ket{\chi}\\
&=\dfrac{\hbar}{2}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}1&0\\0&-1\end{bmatrix}\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar}{2}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}\cos(\tfrac{\theta}{2})\\-\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar}{2}\left[\cos^2(\tfrac{\theta}{2})-\sin^2(\tfrac{\theta}{2})\right]\\
&=\dfrac{\hbar}{2}\cos(2\cdot\tfrac{\theta}{2})\\
\Aboxed{\langle S_z\rangle&=\dfrac{\hbar}{2}\cos(\theta)}
\end{align}$$
---
#### Problem 2.4
$$\begin{align}
\langle S_x^2\rangle
&=\bra{\chi}S_x^2\ket{\chi}\\
&=\dfrac{\hbar^2}{4}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}0&1\\1&0\end{bmatrix}^2\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar^2}{4}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\mathbb{I}\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar^2}{4}\left(\cos^2(\tfrac{\theta}{2})+\sin^2(\tfrac{\theta}{2})\right)\\
\Aboxed{\langle S_x^2\rangle&=\dfrac{\hbar^2}{4}}
\end{align}$$
---
#### Problem 2.5
$$\begin{align}
\langle S_y^2\rangle
&=\bra{\chi}S_y^2\ket{\chi}\\
&=\dfrac{\hbar^2}{4}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}0&-i\\i&0\end{bmatrix}^2\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar^2}{4}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\mathbb{I}\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar^2}{4}\left(\cos^2(\tfrac{\theta}{2})+\sin^2(\tfrac{\theta}{2})\right)\\
\Aboxed{\langle S_y^2\rangle&=\dfrac{\hbar^2}{4}}
\end{align}$$
---
#### Problem 2.6
$$\begin{align}
\langle S_z^2\rangle
&=\bra{\chi}S_z^2\ket{\chi}\\
&=\dfrac{\hbar^2}{4}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\begin{bmatrix}1&0\\0&-1\end{bmatrix}^2\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar^2}{4}\begin{bmatrix}\cos(\tfrac{\theta}{2})&\sin(\tfrac{\theta}{2})\end{bmatrix}\mathbb{I}\begin{bmatrix}\cos(\tfrac{\theta}{2})\\\sin(\tfrac{\theta}{2})\end{bmatrix}\\
&=\dfrac{\hbar^2}{4}\left(\cos^2(\tfrac{\theta}{2})+\sin^2(\tfrac{\theta}{2})\right)\\
\Aboxed{\langle S_z^2\rangle&=\dfrac{\hbar^2}{4}}
\end{align}$$
---
#### Problem 2.7
$$\begin{align}
\langle S_x^2\rangle+\langle S_y^2\rangle+\langle S_z^2\rangle&=\dfrac{\hbar^2}{4}+\dfrac{\hbar^2}{4}+\dfrac{\hbar^2}{4}\\
&=3\cdot\dfrac{\hbar^2}{4}\\
\Aboxed{\langle S_x^2\rangle+\langle S_y^2\rangle+\langle S_z^2\rangle&=\dfrac{3}{4}\hbar^2}
\end{align}$$
---
### Problem 3
Two electrons with spin angular momenta $S_1$ and $S_2$ interact via the Hamiltonian:
$$\begin{align}
\hat{H}&=A\left(S_1\cdot S_2-3S_{1z}S_{2z}\right)
\end{align}$$
where $A$ is a constant. In the coupled basis $\ket{S,M}$ where $S=S_1+S_2$, find the eigenvalue $B$ such that:
$$\begin{align}
\hat{H}\ket{S,M}=B\ket{S,M}
\end{align}$$
Your final expression for 𝐵 should only be in terms of $A$, $S$, $M$ and $\hbar$.

**Precomputation Relations**
$$\begin{align}
S^2&=(S_1+S_2)^2\\
S^2&=S_1^2+S_1\cdot S_2+S_2\cdot S_1+S_2^2\\
S^2&=S_1^2+2S_1\cdot S_2+S_2^2\\
\Aboxed{S_1\cdot S_2&=\dfrac{1}{2}\left(S^2-S_1^2-S_2^2\right)}\\\\
S_1\cdot S_2&=\dfrac{1}{2}\left(S(S+1)\hbar^2-\dfrac{1}{2}\dfrac{3}{2}\hbar^2-\dfrac{1}{2}\dfrac{3}{2}\hbar^2\right)\\
\Aboxed{S_1\cdot S_2&=\dfrac{1}{2}\left(S(S+1)\hbar^2-\dfrac{3}{2}\hbar^2\right)}
\end{align}$$
$$\begin{align}
S_z^2&=(S_{z1}+S_{z2})^2\\
S_z^2&=S_{z1}^2+S_{z1}\cdot S_{z2}+S_{z2}\cdot S_{z1}+S_{z1}^2+S_{z2}^2\\
S_z^2&=S_{z1}^2+2S_{z1}S_{z2}+S_{z2}+S_{z2}^2\\
\Aboxed{S_{z1}S_{z2}&=\dfrac{1}{2}\left(S_z^2-S_{z1}^2-S_{z2}^2\right)}\\\\
S_{z1}S_{z2}&=\dfrac{1}{2}\left(M^2\hbar^2-(\tfrac{1}{2}\hbar)^2-(\tfrac{1}{2}\hbar)^2\right)\\
\Aboxed{S_{z1}S_{z2}&=\dfrac{1}{2}\left(M^2\hbar^2-\dfrac{1}{2}\hbar^2\right)}
\end{align}$$
**Solving the problem**
$$\begin{align}
\hat{H}\ket{S,M}
&=A\left(S_1\cdot S_2-3S_{1z}S_{2z}\right)\ket{S,M}\\
&=A\left(\dfrac{1}{2}\left(S(S+1)\hbar^2-\dfrac{3}{2}\hbar^2\right)-3\dfrac{1}{2}\left(M^2\hbar^2-\dfrac{1}{2}\hbar^2\right)\right)\ket{S,M}\\
&=A\left(\dfrac{1}{2}S(S+1)\hbar^2-\dfrac{3}{4}\hbar^2-\dfrac{3}{2}M^2\hbar^2+\dfrac{3}{4}\hbar^2\right)\ket{S,M}\\
&=A\left(\dfrac{1}{2}S(S+1)\hbar^2-\dfrac{3}{2}M^2\hbar^2\right)\ket{S,M}\\
\Aboxed{\hat{H}\ket{S,M}&=\dfrac{A\hbar^2}{2}\left(S(S+1)-3M^2\right)\ket{S,M}}
\end{align}$$
Therefore, our eigenvalues of energy are:
$$\begin{align}
\Aboxed{B&=\dfrac{A\hbar^2}{2}\left(S(S+1)-3M^2\right)}
\end{align}$$
---
### Problem 4
An electron is initially spin up along $\hat{z}$. At time $t = 0$, a magnetic field  $B(t) = B_0[\cos(\omega t)\hat{x} + \sin(\omega t)\hat{y}]$ is turned on.
#### Problem 4.1
Using the spinor $\chi(t)=\begin{bmatrix}a(t)\\b(t)\end{bmatrix}$, write the TDSE in matrix form and derive it from the coupled equations:
$$\begin{align}
\dot{a}&=-i\omega_0e^{-i\omega t}b\\
\dot{b}&=-i\omega_0e^{i\omega t}a\\
\end{align}$$
where $\omega_0=\tfrac{eB_0}{2m}$, with $e$ and $m$ are the charge and mass of the electron.

**Hamiltonian**
$$\begin{align}
\hat{H}&=-\vec{\mu}_S\cdot\vec{B}\\
&=-\left(-\dfrac{e}{m}\right)\vec{S}\cdot\vec{B}\\
&=\dfrac{e}{m}\left(\dfrac{\hbar}{2}\sigma_x\cdot B_0\cos(\omega t)+\dfrac{\hbar}{2}\sigma_y\cdot B_0\sin(\omega t)\right)\\
&=\dfrac{\hbar eB_0}{2m}\left(\begin{bmatrix}0&1\\1&0\end{bmatrix}\cos(\omega t)+\begin{bmatrix}0&-i\\i&0\end{bmatrix}\sin(\omega t)\right)\\
&=\hbar\dfrac{eB_0}{2m}\begin{bmatrix}0&\cos(\omega t)-i\sin(\omega t)\\\cos(\omega t)+i\sin(\omega t)&0\end{bmatrix}\\
&=\hbar\omega_0\begin{bmatrix}0&\cos(-\omega t)+i\sin(-\omega t)\\\cos(\omega t)+i\sin(\omega t)&0\end{bmatrix}\\
\hat{H}&=\hbar\omega_0\begin{bmatrix}0&e^{-i\omega t}\\e^{i\omega t}&0\end{bmatrix}
\end{align}$$
**TDSE**
$$\begin{align}
i\hbar\dfrac{d}{dt}\chi(t)
&=\hat{H}\chi(t)\\
i\hbar\dfrac{d}{dt}\begin{bmatrix}a\\b\end{bmatrix}
&=\hat{H}\begin{bmatrix}a\\b\end{bmatrix}\\
i\hbar\dfrac{d}{dt}\begin{bmatrix}a\\b\end{bmatrix}
&=\hbar\omega_0\begin{bmatrix}0&e^{-i\omega t}\\e^{i\omega t}&0\end{bmatrix}\begin{bmatrix}a\\b\end{bmatrix}\\
-i^2\dfrac{d}{dt}\begin{bmatrix}a\\b\end{bmatrix}
&=-i\omega_0\begin{bmatrix}0&e^{-i\omega t}\\e^{i\omega t}&0\end{bmatrix}\begin{bmatrix}a\\b\end{bmatrix}\\
\dfrac{d}{dt}\begin{bmatrix}a\\b\end{bmatrix}&=
-i\omega_0\begin{bmatrix}be^{-i\omega t}\\ae^{i\omega t}\end{bmatrix}\\
\end{align}$$
Splitting the vector into 2 differential equations, we get:
$$\begin{align}
\Aboxed{\dfrac{d}{dt}a(t)&=-i\omega_0e^{-i\omega t}b(t)}\\
\Aboxed{\dfrac{d}{dt}b(t)&=-i\omega_0e^{i\omega t}a(t)}
\end{align}$$
I kept getting a positive solution of this until I remembered that electron charges are $-e$ and not $e$ so I was able to quickly change the rest of the work. Should be fixed.

---
#### Problem 4.2
Using the trial solutions
$$\begin{align}
a(t)&=e^{-\tfrac{i\omega t}{2}+i\Omega t}A\\
b(t)&=e^{\tfrac{i\omega t}{2}+i\Omega t}B
\end{align}$$
where $A$ and $B$ are constants, show that:
$$\begin{align}
\dfrac{B}{A}&=\dfrac{\Omega-\omega/2}{-\omega_0}\\
\Omega&=\Omega_\pm=\pm\sqrt{\left(\dfrac{\omega}{2}\right)^2+\omega_0^2}
\end{align}$$
**Equation 1 Proof**
$$\begin{align}
b(t)&=\dfrac{ie^{i\omega t}}{\omega_0}\dot{a}(t)\\
\dfrac{b(t)}{a(t)}&=\dfrac{e^{\tfrac{i\omega t}{2}+i\Omega t}}{e^{-\tfrac{i\omega t}{2}+i\Omega t}}\dfrac{B}{A}=e^{i\omega t}\dfrac{B}{A}\\\\
e^{i\omega t}\dfrac{B}{A}&=\dfrac{ie^{i\omega t}}{\omega_0}\dfrac{\dot{a}(t)}{a(t)}\\
\dfrac{B}{A}&=\dfrac{i}{\omega_0}\dfrac{\dot{a}(t)}{a(t)}\\
\dfrac{B}{A}&=\dfrac{i}{\omega_0}\left(-\dfrac{i\omega }{2}+i\Omega \right)\dfrac{e^{-\tfrac{i\omega t}{2}+i\Omega t}A}{e^{-\tfrac{i\omega t}{2}+i\Omega t}A}\\
\dfrac{B}{A}&=\dfrac{1}{2\omega_0}\left(-2\Omega+\omega\right)\\
\dfrac{B}{A}&=\dfrac{-2\Omega+\omega}{2\omega_0}\\
\Aboxed{\dfrac{B}{A}&=\dfrac{\Omega-\omega/2}{-\omega_0}}
\end{align}$$
**Equation 2 Proof**
$$\begin{align}
a(t)&=e^{-\tfrac{i\omega t}{2}+i\Omega t}A&\implies&&
\dot{a}(t)&=\left(-\tfrac{i\omega}{2}+i\Omega\right)a(t)\\
b(t)&=e^{\tfrac{i\omega t}{2}+i\Omega t}B&\implies&& 
\dot{b}(t)&=\left(\tfrac{i\omega}{2}+i\Omega\right)b(t)
\end{align}$$
$$\begin{align}
\dot{a}(t)&=-i\omega_0e^{-i\omega t}b(t)\implies\left(-\tfrac{i\omega}{2}+i\Omega\right)a(t)=-i\omega_0e^{-i\omega t}b(t)\\
\dot{b}(t)&=-i\omega_0e^{i\omega t}a(t)\implies \left(\tfrac{i\omega}{2}+i\Omega\right)b(t)=-i\omega_0e^{i\omega t}a(t)\\
\end{align}$$
With these, we have 2 equations:
$$\begin{align}
\left(-\tfrac{i\omega}{2}+i\Omega\right)a(t)+i\omega_0e^{-i\omega t}b(t)&=0\\
i\omega_0e^{i\omega t}a(t)+\left(\tfrac{i\omega}{2}+i\Omega\right)b(t)&=0\\\\
\left(-\tfrac{\omega}{2}+\Omega\right)a(t)+\omega_0e^{-i\omega t}b(t)&=0\\
\omega_0e^{i\omega t}a(t)+\left(\tfrac{\omega}{2}+\Omega\right)b(t)&=0\\
\end{align}$$
We can write this as a system of equations where it maps to the zero vector:
$$\begin{align}
\left[\begin{array}{cc|c}-\tfrac{\omega}{2}+\Omega&\omega_0e^{-i\omega t}&0\\\omega_0e^{i\omega t}&\tfrac{\omega}{2}+\Omega&0\end{array}\right]\\
\end{align}$$
This occurs when the determinant of a system is 0, and so:
$$\begin{align}
(-\tfrac{\omega}{2}+\Omega)(\tfrac{\omega}{2}+\Omega)-(\omega_0e^{-i\omega t})(\omega_0e^{i\omega t})&=0\\
\Omega^2-\dfrac{\omega^2}{4}-\omega_0^2(e^{-i\omega t}e^{i\omega t})&=0\\
\Omega^2-\dfrac{\omega^2}{4}-\omega_0^2&=0\\
\Omega^2=\dfrac{\omega^2}{4}-\omega_0^2&\\
\Aboxed{\Omega_\pm=\pm\sqrt{\left(\dfrac{\omega}{2}\right)^2-\omega_0^2}&}
\end{align}$$
---
#### Problem 4.3
Using the given initial condition, find the solution for $\chi(t)$ and thus the probability $p_\downarrow(t)$ of finding the spin down along $\hat{z}$.

**Initial Condition**
$$\begin{align}
a(t)&=e^{-\tfrac{i\omega t}{2}+i\Omega t}A\\
b(t)&=e^{\tfrac{i\omega t}{2}+i\Omega t}B
\end{align}$$
$$\begin{align}
\chi(0)=\begin{bmatrix}1\\0\end{bmatrix}\implies\Aboxed{\begin{bmatrix}A\\B\end{bmatrix}=\begin{bmatrix}1\\0\end{bmatrix}}
\end{align}$$
**State Vector**
$$\begin{align}
\chi(t)&=\begin{bmatrix}e^{-\tfrac{i\omega t}{2}+i\Omega t}A\\e^{\tfrac{i\omega t}{2}+i\Omega t}B\end{bmatrix}\\
\chi(t)&=\begin{bmatrix}e^{-\tfrac{i\omega t}{2}+i\Omega t}\\0\end{bmatrix}\\
\end{align}$$
**Probability of Down State**
$$\boxed{p_\downarrow(t)=0}$$
This system doesn't change the orientation of the z-component of the spin.
Therefore, the probability of finding it in a down state, given that it starts in the up state, is 0.