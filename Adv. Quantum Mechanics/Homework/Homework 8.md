**Name:** Stanley Goodwin
**Date:** 4/11/2025

---
### Question 1
We learnt in Intro to Quantum that the delta well $V(x)=-\alpha\delta(x)$ has a single bound state.
$$\begin{align}
\psi(x)&=\sqrt{\dfrac{m\alpha}{\hbar^2}}\exp\left(-\dfrac{m\alpha}{\hbar^2}|x|\right) & E&=-\dfrac{m\alpha^2}{2\hbar^2}
\end{align}$$
---
#### Question 1.1
Find by explicit calculation the geometric phase when $\alpha$ is slowly changed from $\alpha_1$ to $\alpha_2$.
$$\begin{align}
\gamma&=i\int_{\alpha_1}^{\alpha_2}\braket{\psi(x)|\partial_\alpha\psi(x)}\ d\alpha
\end{align}$$
We can calculate the inner expression as:
$$\begin{align}
\braket{\psi(x)|\partial_\alpha\psi(x)}
&=\int_{-\infty}^{\infty}\psi^*(x)\cdot\partial_\alpha\psi(x)\ dx\\
&=\int_{-\infty}^{\infty}\sqrt{\dfrac{m\alpha}{\hbar^2}}\exp\left(-\dfrac{m\alpha}{\hbar^2}|x|\right)\cdot\dfrac{\partial}{\partial\alpha}\left(\sqrt{\dfrac{m\alpha}{\hbar^2}}\exp\left(-\dfrac{m\alpha}{\hbar^2}|x|\right)\right)\ dx\\
&=2\sqrt{\dfrac{m\alpha}{\hbar^2}}\int_{0}^{\infty}\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)\cdot\dfrac{\partial}{\partial\alpha}\left(\sqrt{\dfrac{m\alpha}{\hbar^2}}\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)\right)\ dx\\
&=2\sqrt{\dfrac{m\alpha}{\hbar^2}}\int_{0}^{\infty}\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)\cdot\left(\dfrac{1}{2}\sqrt{\dfrac{m}{\hbar^2\alpha}}\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)-\dfrac{m}{\hbar^2}x\sqrt{\dfrac{m\alpha}{\hbar^2}}\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)\right)\ dx\\
&=2\dfrac{m\alpha}{\hbar^2}\int_{0}^{\infty}\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)\cdot\left(\dfrac{1}{2\alpha}\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)-\dfrac{m}{\hbar^2}x\exp\left(-\dfrac{m\alpha}{\hbar^2}x\right)\right)\ dx\\
&=\dfrac{m}{\hbar^2}\int_{0}^{\infty}e^{-2\tfrac{m\alpha}{\hbar^2}x}\ dx-\dfrac{m}{\hbar^2}\int_{0}^{\infty}\left(2\dfrac{m\alpha}{\hbar^2}x\right)e^{-2\tfrac{m\alpha}{\hbar^2}x}\ dx\\
\end{align}$$
Let $u=2\tfrac{m\alpha}{\hbar^2}x$, so $\tfrac{\hbar^2}{2m\alpha}du=dx$:
$$\begin{align}
\braket{\psi(x)|\partial_\alpha\psi(x)}
&=\dfrac{m}{\hbar^2}\dfrac{\hbar^2}{2m\alpha}\left(\int_{0}^{\infty}e^{-u}\ du-\int_{0}^{\infty}ue^{-u}\ du\right)\\
&=\dfrac{m}{\hbar^2}\dfrac{\hbar^2}{2m\alpha}\left(1-1\right)\\
\Aboxed{\braket{\psi(x)|\partial_\alpha\psi(x)}&=0}
\end{align}$$
Plugging it back in, we get that:
$$\begin{align}
\Aboxed{\gamma&=0}
\end{align}$$
This is to be expected, because there is only 1 parameters that changes with time, and we know that those lead to no Berry phase.

---
#### Question 1.2
If the increase occurs at a constant rate $\dfrac{d\alpha}{dt}=c$, what is the dynamical phase change for this process?

If we let $t_1=0$, then we can find that the final time is:
$$\begin{align}
c=\dfrac{\alpha_2-\alpha_1}{t_2}\implies t_2=\dfrac{\alpha_2-\alpha_1}{c}
\end{align}$$
We can also find the energy by using the slope to find $\alpha$ at any point $t$:
$$\begin{align}
\alpha(t)&=ct+\alpha_1 & 0<t<t_2\\
E(t)&=-\dfrac{m}{2\hbar^2}(ct+\alpha_1)^2\\
\end{align}$$
We can then find the dynamical phase as:
$$\begin{align}
\theta&=-\dfrac{1}{\hbar}\int_{t_1}^{t_2}E(t)\ dt\\
&=\dfrac{m}{2\hbar^3}\int_{0}^{t_2}(ct+\alpha_1)^2\ dt\\
\end{align}$$
Let $u=ct+\alpha_1$, and $\tfrac{1}{c}du=dt$, then:
$$\begin{align}
\theta&=\dfrac{m}{2\hbar^3c}\int_{\alpha_1}^{ct_2+\alpha_1}u^2\ du\\
&=\dfrac{m}{2\hbar^3c}\left(\dfrac{1}{3}u^3\right|_{\alpha_1}^{ct_2+\alpha_1}\\
&=\dfrac{m}{6\hbar^3c}\left((ct_2+\alpha_1)^3-\alpha_1^3\right)\\
&=\dfrac{m}{6\hbar^3c}\left((\alpha_2-\alpha_1+\alpha_1)^3-\alpha_1^3\right)\\
\Aboxed{\theta&=\dfrac{m}{6\hbar^3c}\left(\alpha_2^3-\alpha_1^3\right)}
\end{align}$$
---
### Question 2
In class we found the Berry phase for a spin-$1/2$ particle in a magnetic field whose direction changes with time to be $\gamma_+^B(T)=-\tfrac{\Omega}{2}$ where $\Omega$ is the solid angle subtended by the closed path of the magnetic field vector. Work out the analogous Berry phase for a spin-$1$ particle using the following steps.

---
#### Question 2.1
Write the Hamiltonian and use spin-$1$ angular momentum matrices to write the Hamiltonian in matrix form.
$$\begin{align}
\hat{H}&=-\vec\mu_S\cdot\vec{B}\\
&=-\dfrac{q}{m}\vec{S}\cdot\vec{B}\\
\end{align}$$
We need the values of the spin operators for all 3 cartesian directions:
$$\begin{align}
\bra{1,m_s'}S\ket{1,m_s}&=\hbar\sqrt{1\cdot(1+1)-m\cdot(m-1)}\braket{1,m_s'|1,m_s-1}\\
S_{m_s'm_s}&=\hbar\sqrt{2-m\cdot(m-1)}\cdot\delta_{m_s',m_s-1}\\
S&=\sqrt{2}\hbar\begin{bmatrix}0&1&0\\0&0&1\\0&0&0\end{bmatrix}\\
S^\dagger&=\sqrt{2}\hbar\begin{bmatrix}0&0&0\\1&0&0\\0&1&0\end{bmatrix}\\
\end{align}$$
With these, we can find that:
$$\begin{align}
S_x&=\dfrac{S^\dagger+S}{2}\\
&=\dfrac{\sqrt{2}}{2}\hbar\begin{bmatrix}0&1&0\\0&0&1\\0&0&0\end{bmatrix}+\dfrac{\sqrt{2}}{2}\hbar\begin{bmatrix}0&0&0\\1&0&0\\0&1&0\end{bmatrix}\\
S_x&=\dfrac{\sqrt{2}}{2}\hbar\begin{bmatrix}0&1&0\\1&0&1\\0&1&0\end{bmatrix}\\
\end{align}$$
$$\begin{align}
S_y&=\dfrac{S^\dagger-S}{2i}\\
&=\dfrac{\sqrt{2}}{2i}\hbar\begin{bmatrix}0&1&0\\0&0&1\\0&0&0\end{bmatrix}-\dfrac{\sqrt{2}}{2i}\hbar\begin{bmatrix}0&0&0\\1&0&0\\0&1&0\end{bmatrix}\\
S_y&=\dfrac{\sqrt{2}}{2}\hbar\begin{bmatrix}0&-i&0\\i&0&-i\\0&i&0\end{bmatrix}\\
\end{align}$$
$$\begin{align}
\bra{1,m_s'}S_z\ket{1,m_s}&=\bra{1,m_s'}m_s\hbar \ket{1,m_s}\\
&=m_s\hbar\delta_{m_s',m_s}\\
S_z&=\hbar\begin{bmatrix}1&0&0\\0&0&0\\0&0&-1\end{bmatrix}
\end{align}$$
We can then express the Hamiltonian as:
$$\begin{align}
\hat{H}
&=-\dfrac{q}{m}\vec{S}\cdot\vec{B}\\
&=-\dfrac{q}{m}\left(S_xB_x+S_yB_y+S_zB_z\right)\\
&=-\dfrac{qB_0}{m}\left(S_x\sin\theta\cos\phi+S_y\sin\theta\sin\phi+S_z\cos\theta\right)\\
&=-\dfrac{qB_0\hbar}{m}\dfrac{\sqrt{2}}{2}\begin{bmatrix}\sqrt{2}\cos\theta&\sin\theta\cos\phi-i\sin\theta\sin\phi&0\\\sin\theta\cos\phi+i\sin\theta\sin\phi&0&\sin\theta\cos\phi-i\sin\theta\sin\phi\\0&\sin\theta\cos\phi+i\sin\theta\sin\phi&-\sqrt{2}\cos\theta\end{bmatrix}\\
\hat{H}&=-\dfrac{qB_0\hbar}{m}\begin{bmatrix}\cos\theta&\tfrac{1}{\sqrt{2}}e^{-i\phi}\sin\theta&0\\\tfrac{1}{\sqrt{2}}e^{i\phi}\sin\theta&0&\tfrac{1}{\sqrt{2}}e^{-i\phi}\sin\theta\\0&\tfrac{1}{\sqrt{2}}e^{i\phi}\sin\theta&-\cos\theta\end{bmatrix}\\
\end{align}$$
---
#### Question 2.2
Find the spin-up eigenvector $\chi_+$.

To find the spin-up state eigenvector, we'll need to find the vector associated with the minimal energy (spin aligned with the field).

If we find the eigenvectors of the Hamiltonian, we can pick the one that satisfies it:
$$\begin{align}
\hat{H}&=-\dfrac{qB_0\hbar}{m}\begin{bmatrix}\cos\theta&\tfrac{1}{\sqrt{2}}e^{-i\phi}\sin\theta&0\\\tfrac{1}{\sqrt{2}}e^{i\phi}\sin\theta&0&\tfrac{1}{\sqrt{2}}e^{-i\phi}\sin\theta\\0&\tfrac{1}{\sqrt{2}}e^{i\phi}\sin\theta&-\cos\theta\end{bmatrix}\\
\end{align}$$
I did this originally but the math kept being really annoying, so the spinor is as follows:
$$\begin{align}
\chi_+(\theta,\phi)&=\begin{bmatrix}
	\tfrac{1}{2}(1+\cos\theta)e^{-i\phi}\\
	\tfrac{1}{\sqrt{2}}\sin\theta\\
	\tfrac{1}{2}(1-\cos\theta)e^{i\phi}\\
\end{bmatrix}=\begin{bmatrix}
	\cos^2(\tfrac{\theta}{2})e^{-i\phi}\\
	\sqrt{2}\sin(\tfrac{\theta}{2})\cos(\tfrac{\theta}{2})\\
	\sin^2(\tfrac{\theta}{2})e^{i\phi}\\
\end{bmatrix}
\end{align}$$
This came about from a LOT of Desmos arithmetic.

---
#### Question 2.3
Find $\vec\nabla\chi_+$.
$$\begin{align}
\vec\nabla\chi_+(\theta,\phi)&=\dfrac{1}{r}\hat\theta\dfrac{\partial}{\partial\theta}\chi_+(\theta,\phi)+\dfrac{1}{r\sin\theta}\hat\phi\dfrac{\partial}{\partial\phi}\chi_+(\theta,\phi)
\end{align}$$
Let's calculate the $\hat\theta$ component first:
$$\begin{align}
\dfrac{\partial}{\partial\theta}\chi_+
&=\dfrac{\partial}{\partial\theta}
\begin{bmatrix}
	\cos^2(\tfrac{\theta}{2})e^{-i\phi}\\
	\tfrac{1}{\sqrt{2}}\sin(\theta)\\
	\sin^2(\tfrac{\theta}{2})e^{i\phi}\\
\end{bmatrix}\\
&=\begin{bmatrix}
	-\cos(\tfrac{\theta}{2})\sin(\tfrac{\theta}{2})e^{-i\phi}\\
	\tfrac{1}{\sqrt{2}}\cos(\theta)\\
	\sin(\tfrac{\theta}{2})\cos(\tfrac{\theta}{2})e^{i\phi}\\
\end{bmatrix}\\
\dfrac{\partial}{\partial\theta}\chi_+
&=\begin{bmatrix}
	-\tfrac{1}{2}\sin(\theta)e^{-i\phi}\\
	\tfrac{1}{\sqrt{2}}\cos(\theta)\\
	\tfrac{1}{2}\sin(\theta)e^{i\phi}\\
\end{bmatrix}\\
\end{align}$$
Then the $\hat\phi$ part:
$$\begin{align}
\dfrac{\partial}{\partial\phi}\chi_+
&=\dfrac{\partial}{\partial\phi}
\begin{bmatrix}
	\cos^2(\tfrac{\theta}{2})e^{-i\phi}\\
	\tfrac{1}{\sqrt{2}}\sin(\theta)\\
	\sin^2(\tfrac{\theta}{2})e^{i\phi}\\
\end{bmatrix}\\
\dfrac{\partial}{\partial\phi}\chi_+&=
\begin{bmatrix}
	-i\cos^2(\tfrac{\theta}{2})e^{-i\phi}\\
	0\\
	i\sin^2(\tfrac{\theta}{2})e^{i\phi}\\
\end{bmatrix}\\
\end{align}$$
Putting it together:
$$\begin{align}
\vec\nabla\chi_+(\theta,\phi)
&=\dfrac{1}{r}\hat\theta\dfrac{\partial}{\partial\theta}\chi_+(\theta,\phi)+\dfrac{1}{r\sin\theta}\hat\phi\dfrac{\partial}{\partial\phi}\chi_+(\theta,\phi)\\
&=\dfrac{1}{r}\hat\theta\begin{bmatrix}
	-\tfrac{1}{2}\sin(\theta)e^{-i\phi}\\
	\tfrac{1}{\sqrt{2}}\cos(\theta)\\
	\tfrac{1}{2}\sin(\theta)e^{i\phi}\\
\end{bmatrix}+\dfrac{1}{r\sin\theta}\hat\phi\begin{bmatrix}
	-i\cos^2(\tfrac{\theta}{2})e^{-i\phi}\\
	0\\
	i\sin^2(\tfrac{\theta}{2})e^{i\phi}\\
\end{bmatrix}
\end{align}$$
---
#### Question 2.4
Find $\braket{\chi_+|\vec\nabla\chi_+}$.
$$\begin{align}
\braket{\chi_+|\vec\nabla\chi_+}
&=\dfrac{1}{r}\hat\theta\begin{bmatrix}
	\cos^2(\tfrac{\theta}{2})e^{i\phi}&
	\tfrac{1}{\sqrt{2}}\sin\theta&
	\sin^2(\tfrac{\theta}{2})e^{-i\phi}
\end{bmatrix}\begin{bmatrix}
	-\tfrac{1}{2}\sin(\theta)e^{-i\phi}\\
	\tfrac{1}{\sqrt{2}}\cos(\theta)\\
	\tfrac{1}{2}\sin(\theta)e^{i\phi}\\
\end{bmatrix}\\&+\dfrac{1}{r\sin\theta}\hat\phi\begin{bmatrix}
	\cos^2(\tfrac{\theta}{2})e^{i\phi}&
	\tfrac{1}{\sqrt{2}}\sin\theta&
	\sin^2(\tfrac{\theta}{2})e^{-i\phi}
\end{bmatrix}\begin{bmatrix}
	-i\cos^2(\tfrac{\theta}{2})e^{-i\phi}\\
	0\\
	i\sin^2(\tfrac{\theta}{2})e^{i\phi}\\
\end{bmatrix}\\\\

&=\dfrac{1}{r}\hat\theta\left(-\tfrac{1}{2}\sin(\theta)e^{-i\phi}\cos^2(\tfrac{\theta}{2})e^{i\phi}+\tfrac{1}{\sqrt{2}}\cos(\theta)\tfrac{1}{\sqrt{2}}\sin\theta+\tfrac{1}{2}\sin(\theta)e^{i\phi}\sin^2(\tfrac{\theta}{2})e^{-i\phi}\right)\\
&+\dfrac{1}{r\sin\theta}\hat\phi\left(-i\cos^2(\tfrac{\theta}{2})e^{-i\phi}\cos^2(\tfrac{\theta}{2})e^{i\phi}+i\sin^2(\tfrac{\theta}{2})e^{i\phi}\sin^2(\tfrac{\theta}{2})e^{-i\phi}\right)\\\\

&=\dfrac{1}{2r}\hat\theta\left(\cos\theta\sin\theta+\sin\theta\left[\sin^2(\tfrac{\theta}{2})-\cos^2(\tfrac{\theta}{2})\right]\right)\\
&+\dfrac{i}{r\sin\theta}\hat\phi\left(\sin^4(\tfrac{\theta}{2})-\cos^4(\tfrac{\theta}{2})\right)\\\\

&=\dfrac{1}{2r}\hat\theta\left(0\right)-\dfrac{i}{r\sin\theta}\hat\phi\cos\theta\\

\Aboxed{\braket{\chi_+|\vec\nabla\chi_+}&=-i\cot\theta\ \hat\phi}
\end{align}$$
---
#### Question 2.5
Find $\vec\nabla\times\braket{\chi_+|\vec\nabla\chi_+}$.
$$\begin{align}
\vec\nabla\times\braket{\chi_+|\vec\nabla\chi_+}&=
\dfrac{1}{r\sin\theta}\dfrac{\partial}{\partial\theta}\left(\braket{\chi_+|\vec\nabla\chi_+}\sin\theta\right)\hat{r}\\
&=
\dfrac{1}{r\sin\theta}\dfrac{\partial}{\partial\theta}\left(-i\cos\theta\right)\hat{r}\\
&=
\dfrac{i}{r\sin\theta}\left(\sin\theta\right)\\
\Aboxed{\vec\nabla\times\braket{\chi_+|\vec\nabla\chi_+}&=i\hat{r}}
\end{align}$$

#### Question 2.6
Find $\gamma_+^B(T)$.
$$\begin{align}
\gamma^B_+(T)&=-\oint\Im\left(\braket{\chi_+|\vec\nabla\chi_+}\right)\cdot d\vec{s}\\
&=-\iint_S\Im\left(\vec\nabla\times\braket{\chi_+|\vec\nabla\chi_+}\right)\cdot d\vec{A}\\
&=-\iint_S \Im\left(i\hat{r}\right)\cdot d\vec{A}\\
&=-\iint_S\hat{r}\cdot \hat{r}dA\\
&=-\iint_SdA\\
\Aboxed{\gamma^B_+(T)&=-\Omega}
\end{align}$$
Very interesting. The Berry phase seems to be directly proportional to the spin of the particle!

---
