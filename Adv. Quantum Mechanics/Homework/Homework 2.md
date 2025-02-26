**Name:** Stanley Goodwin
**Date:** 2/7/2025

---
### Question 1
**Spin ½ particle in a homogeneous magnetic field**
In class, for a spin $1/2$ particle in a uniform magnetic field $B_0\hat{z}$, we found $\chi(t)$ for $\chi(0)=\left[\begin{align}a\\b\end{align}\right]$.
**For Reference**
$$\begin{align}
\chi(t)&=a\chi_+^Ze^{-iE_+t/\hbar}+b\chi_-^Ze^{-iE_-t/\hbar} &
E_\pm&=\mp\dfrac{g_SB_0\hbar}{2}\\
\chi(t)&=a\chi_+^Ze^{iEt/\hbar}+b\chi_-^Ze^{-iEt/\hbar} &
E&=\dfrac{g_SB_0\hbar}{2}\\
\end{align}$$
---
#### Question 1.1
If we measure the spin along the $x$-axis at any time $t$, what is the probability we get $+\tfrac{\hbar}{2}$?
**Post Note:** This solution is incorrect.
$$\begin{align}
p(\chi_+^X|\chi(t))&=\left|\braket{\chi_+^X|\chi(t)}\right|^2\\
&=\left|\dfrac{1}{\sqrt{2}}\begin{bmatrix}1&1\end{bmatrix}\begin{bmatrix}ae^{iEt/\hbar}\\be^{-iEt/\hbar}\end{bmatrix}\right|^2\\
&=\dfrac{1}{2}\left|ae^{iEt/\hbar}+be^{-iEt/\hbar}\right|^2\\
&=\dfrac{1}{2}\left(a^*e^{-iEt/\hbar}+b^*e^{iEt/\hbar}\right)\left(ae^{iEt/\hbar}+be^{-iEt/\hbar}\right)\\
&=\dfrac{1}{2}\left(a^*e^{-iEt/\hbar}+b^*e^{iEt/\hbar}\right)ae^{iEt/\hbar}+\dfrac{1}{2}\left(a^*e^{-iEt/\hbar}+b^*e^{iEt/\hbar}\right)be^{-iEt/\hbar}\\
&=\dfrac{1}{2}\left(|a|^2+|b|^2+b^*ae^{2iEt/\hbar}+a^*be^{-2iEt/\hbar}\right)\\
&=\dfrac{1}{2}+\dfrac{\left(b^*ae^{2iEt/\hbar}\right)+\left(b^*ae^{2iEt/\hbar}\right)^*}{2}\\
&=\dfrac{1}{2}+\dfrac{2\Re\left(b^*ae^{2iEt/\hbar}\right)}{2}\\
&=\dfrac{1}{2}+\Re(ab^*)\cos(2Et/\hbar)\\
&=\dfrac{1}{2}+\Re(ab^*)\cos\left(2\dfrac{g_SB_0\hbar}{2}t/\hbar\right)\\
\Aboxed{p(\chi_+^X|\chi(t))&=\dfrac{1}{2}+\Re(ab^*)\cos\left(g_SB_0t\right)}
\end{align}$$
#### Question 1.2
If we measure the spin along the $y$-axis at any time $t$, what is the probability we get $+\tfrac{\hbar}{2}$?
**Post Note:** This solution is incorrect.
$$\begin{align}
p(\chi_+^Y|\chi(t))&=\left|\braket{\chi_+^Y|\chi(t)}\right|^2\\
&=\left|\dfrac{1}{\sqrt{2}}\begin{bmatrix}1&i\end{bmatrix}\begin{bmatrix}ae^{iEt/\hbar}\\be^{-iEt/\hbar}\end{bmatrix}\right|^2\\
&=\dfrac{1}{2}\left|ae^{iEt/\hbar}+ibe^{-iEt/\hbar}\right|^2\\
&=\dfrac{1}{2}\left(a^*e^{-iEt/\hbar}-ib^*e^{iEt/\hbar}\right)\left(ae^{iEt/\hbar}+ibe^{-iEt/\hbar}\right)\\
&=\dfrac{1}{2}\left(|a|^2+ia^*be^{-2iEt/\hbar}-ib^*ae^{2iEt/\hbar}+|b|^2\right)\\
&=\dfrac{|a|^2+|b|^2}{2}+\dfrac{1}{2}\left(ia^*be^{-2iEt/\hbar}-ib^*ae^{2iEt/\hbar}\right)\\
&=\dfrac{1}{2}+\dfrac{\left(ia^*be^{-2iEt/\hbar}\right)+\left(ia^*be^{-2iEt/\hbar}\right)^*}{2}\\
&=\dfrac{1}{2}+\dfrac{\left(a^*be^{-2iEt/\hbar+\tfrac{\pi}{2}}\right)+\left(a^*be^{-2iEt/\hbar+\tfrac{\pi}{2}}\right)^*}{2}\\
&=\dfrac{1}{2}+\Re(ba^*)\cos(-2Et/\hbar+\tfrac{\pi}{2})\\
&=\dfrac{1}{2}+\Re(ab^*)\sin\left(2\dfrac{g_SB_0\hbar}{2}t/\hbar\right)\\
\Aboxed{p(\chi_+^Y|\chi(t))&=\dfrac{1}{2}+\Re(ab^*)\sin\left(g_SB_0t\right)}
\end{align}$$
---
### Problem 2
Using the individual operators $S_{1\pm}$ and $S_{2\pm}$, show the following.

**Requisite Knowledge**
$$\begin{align}
S_\pm\ket{s,m_s}&=\sqrt{s(s+1)\hbar^2-m_s(m_s\pm1)\hbar^2}\ket{s,m_s\pm1}
\end{align}$$
$$\begin{align}
S_1\cdot S_2
&=S_{x1}S_{x2}+S_{y1}S_{y2}+S_{z1}S_{z2}\\
&=\left(\dfrac{S_{1+}+S_{1-}}{2}\right)\left(\dfrac{S_{2+}+S_{2-}}{2}\right)+\left(\dfrac{S_{1+}-S_{1-}}{2i}\right)\left(\dfrac{S_{2+}-S_{2-}}{2i}\right)+S_{z1}S_{z2}\\\\
&=\dfrac{1}{4}\left(S_{1+}S_{2+}+S_{1+}S_{2-}+S_{1-}S_{2+}+S_{1-}S_{2-}\right)\\
&-\dfrac{1}{4}\left(S_{1+}S_{2+}-S_{1+}S_{2-}-S_{1-}S_{2+}+S_{1-}S_{2-}\right)+S_{z1}S_{z2}\\\\
&=\dfrac{2}{4}\left(S_{1+}S_{2-}+S_{1-}S_{2+}\right)+S_{z1}S_{z2}\\
\Aboxed{S_1\cdot S_2&=\dfrac{1}{2}\left(S_{1+}S_{2-}+S_{1-}S_{2+}\right)+S_{z1}S_{z2}}
\end{align}$$
---
#### Problem 2.1
Prove the following:
$$\begin{align}
[S_1\cdot S_2]\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}&=\dfrac{\hbar^2}{4}\left(2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}-\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\right)
\end{align}$$
We can the find the true value of these operator applications:
$$\begin{align}
S_{1+}S_{2-}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}&=0 & \text{(Falls off the ladder)}
\end{align}$$
$$\begin{align}
S_{1-}S_{2+}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}
&=\left(S_{1-}\ket{+\tfrac{1}{2}}\right)\left(S_{2+}\ket{-\tfrac{1}{2}}\right)\\
&=\sqrt{\tfrac{3}{4}\hbar^2-\tfrac{1}{2}(-\tfrac{1}{2})\hbar^2}\ket{-\tfrac{1}{2}}\sqrt{\tfrac{3}{4}\hbar^2+\tfrac{1}{2}(\tfrac{1}{2})\hbar^2}\ket{+\tfrac{1}{2}}\\
&=\left(\sqrt{\tfrac{3}{4}\hbar^2+\tfrac{1}{4}\hbar^2}\right)^2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\\
\Aboxed{S_{1-}S_{2+}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}&=\hbar^2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}}
\end{align}$$
$$\begin{align}
S_{1z}S_{2z}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}
&=\left(S_{1z}\ket{+\tfrac{1}{2}}\right)\left(S_{2z}\ket{-\tfrac{1}{2}}\right)\\\\
&=\left(\tfrac{1}{2}\hbar\ket{+\tfrac{1}{2}}\right)\left(-\tfrac{1}{2}\hbar\ket{-\tfrac{1}{2}}\right)\\
\Aboxed{S_{1z}S_{2z}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}&=-\tfrac{\hbar^2}{4}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}}
\end{align}$$
Combining the observation from earlier, we can find the following expression:
$$\begin{align}
S_1\cdot S_2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}
&=\left[\dfrac{1}{2}\left(S_{1+}S_{2-}+S_{1-}S_{2+}\right)+S_{z1}S_{z2}\right]\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\\
&=\dfrac{1}{2}S_{1+}S_{2-}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}+\dfrac{1}{2}S_{1-}S_{2+}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\\&\ \ \ \ \ +S_{z1}S_{z2}\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\\
&=0+\dfrac{1}{2}\hbar^2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}-\dfrac{1}{4}\hbar^2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\\
\Aboxed{S_1\cdot S_2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}&=\dfrac{\hbar^2}{4}\left(2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}-\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\right)}
\end{align}$$
---
#### Problem 2.2
Prove the following:
$$\begin{align}
[S_1\cdot S_2]\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}&=\dfrac{\hbar^2}{4}\left(2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}-\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\right)
\end{align}$$
Because I want to reduce on the amount of work required, let's look at an observation.
$$\begin{align}
S_1\cdot S_2&=\dfrac{1}{2}\left(S_{1+}S_{2-}+S_{1-}S_{2+}\right)+S_{z1}S_{z2}
\end{align}$$
If we swap the state from $\ket{\psi_1}\ket{\psi_2}\rightarrow\ket{\psi_2}\ket{\psi_1}$, we can see that $S_1\cdot S_2$ lead to the same values as the previous question, with the difference being that we swap the states.
Therefore, we can conclude that:
$$\begin{align}
\Aboxed{S_1\cdot S_2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}&=\dfrac{\hbar^2}{4}\left(2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}-\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\right)}
\end{align}$$
The simple substitution of $\ket{\psi_1}\ket{\psi_2}\rightarrow\ket{\psi_2}\ket{\psi_1}$ gives the same value only because:
$$\begin{align}
(S_{1+}S_{2-}+S_{1-}S_{2+})\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}&=(S_{1+}S_{2-}+S_{1-}S_{2+})\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\\
\end{align}$$
---
#### Problem 2.3
Prove the following:
$$\begin{align}
(S_1\cdot S_2)\ket{1,0}&=\dfrac{\hbar^2}{4}\ket{1,0}
\end{align}$$
Beginning of proof:
$$\begin{align}
(S_1\cdot S_2)\ket{1,0}
&=(S_1\cdot S_2)\left(\dfrac{\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}+\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}}{\sqrt{2}}\right)\\
&=\dfrac{1}{\sqrt{2}}\left(S_1\cdot S_2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}+S_1\cdot S_2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\right)\\
&=\dfrac{1}{\sqrt{2}}\left(\dfrac{\hbar^2}{4}\left(2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}-\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\right)+\dfrac{\hbar^2}{4}\left(2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}-\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\right)\right)\\
&=\dfrac{1}{\sqrt{2}}\dfrac{\hbar^2}{4}\left(\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}+\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\right)\\
&=\dfrac{\hbar^2}{4}\dfrac{\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}+\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}}{\sqrt{2}}\\
\Aboxed{(S_1\cdot S_2)\ket{1,0}&=\dfrac{\hbar^2}{4}\ket{1,0}}
\end{align}$$
---
#### Problem 2.4
Prove the following:
$$\begin{align}
(S_1\cdot S_2)\ket{0,0}&=-\dfrac{3\hbar^2}{4}\ket{0,0}
\end{align}$$
Beginning of proof:
$$\begin{align}
(S_1\cdot S_2)\ket{0,0}
&=(S_1\cdot S_2)\left(\dfrac{\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}-\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}}{\sqrt{2}}\right)\\
&=\dfrac{1}{\sqrt{2}}\left(S_1\cdot S_2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}-S_1\cdot S_2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\right)\\
&=\dfrac{1}{\sqrt{2}}\left(\dfrac{\hbar^2}{4}\left(2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}-\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\right)-\dfrac{\hbar^2}{4}\left(2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}-\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\right)\right)\\
&=\dfrac{1}{\sqrt{2}}\left(\dfrac{\hbar^2}{4}\left(2\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}-\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\right)+\dfrac{\hbar^2}{4}\left(-2\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}+\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}\right)\right)\\
&=\dfrac{1}{\sqrt{2}}\dfrac{\hbar^2}{4}\left(3\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}-3\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}\right)\\
&=-\dfrac{3\hbar^2}{4}\dfrac{\ket{+\tfrac{1}{2}}\ket{-\tfrac{1}{2}}-\ket{-\tfrac{1}{2}}\ket{+\tfrac{1}{2}}}{\sqrt{2}}\\
\Aboxed{(S_1\cdot S_2)\ket{0,0}&=-\dfrac{3\hbar^2}{4}\ket{0,0}}
\end{align}$$
---
#### Problem 2.5
Prove the following:
$$\begin{align}
S^2\ket{1,0}&=2\hbar^2\ket{1,0}
\end{align}$$
**Requisite Knowledge**
$$\begin{align}
S&=S_1+S_2\\
S\cdot S&=(S_1+S_2)\cdot(S_1+S_2)\\
S^2&=S_1^2+S_1\cdot S_2+S_2\cdot S_1+S_2^2\\
S^2&=S_1^2+2S_1\cdot S_2+S_2^2\\
2S_1\cdot S_2&=S^2-S_1^2-S_2^2\\
\Aboxed{S_1\cdot S_2&=\dfrac{1}{2}\left(S^2-S_1^2-S_2^2\right)}
\end{align}$$
Beginning of proof:
$$\begin{align}
S^2\ket{1,0}
&=\left(S_1^2+2S_1\cdot S_2+S_2^2\right)\ket{1,0}\\
&=S_1^2\ket{1,0}+2S_1\cdot S_2\ket{1,0}+S_2^2\ket{1,0}\\
&=\dfrac{1}{2}\left(\dfrac{1}{2}+1\right)\hbar^2\ket{1,0}+2\cdot\dfrac{1}{4}\hbar^2\ket{1,0}+\dfrac{1}{2}\left(\dfrac{1}{2}+1\right)\hbar^2\ket{1,0}\\
&=\left(\dfrac{3}{4}+2\cdot\dfrac{1}{4}+\dfrac{3}{4}\right)\hbar^2\ket{1,0}\\
\Aboxed{S^2\ket{1,0}&=2\hbar^2\ket{1,0}}
\end{align}$$
---
#### Problem 2.6
Prove the following:
$$\begin{align}
S^2\ket{0,0}&=0\ket{0,0}
\end{align}$$
Beginning of proof:
$$\begin{align}
S^2\ket{0,0}
&=\left(S_1^2+2S_1\cdot S_2+S_2^2\right)\ket{1,0}\\
&=S_1^2\ket{0,0}+2S_1\cdot S_2\ket{0,0}+S_2^2\ket{0,0}\\
&=\dfrac{1}{2}\left(\dfrac{1}{2}+1\right)\hbar^2\ket{0,0}-2\cdot\dfrac{3}{4}\hbar^2\ket{0,0}+\dfrac{1}{2}\left(\dfrac{1}{2}+1\right)\hbar^2\ket{0,0}\\
&=\left(\dfrac{3}{4}-2\cdot\dfrac{3}{4}+\dfrac{3}{4}\right)\hbar^2\ket{0,0}\\
\Aboxed{S^2\ket{0,0}&=0\ket{0,0}}
\end{align}$$
---
### Problem 3
Coupling of more than two angular momenta. Quarks carry spin $1/2$.
#### Problem 3.1
Two quarks bind together to make a meson (e.g. a pion or a kaon). What spins are possible for mesons?

**Microstates**
$$\begin{align}
\ket{\downarrow\downarrow} && \ket{\downarrow\uparrow} && \ket{\uparrow\downarrow} && \ket{\uparrow\uparrow}\\
s=-1 && s=0 && s=0 && s=+1
\end{align}$$
Therefore the only spin states allowed are $\boxed{S\in\left\{-1,0,1\right\}}$.

---
#### Problem 3.2
Three quarks bind together to make a baryon (e.g. a proton or a neutron). What spins are possible for baryons?

**Microstates**
$$\begin{align}
\ket{\downarrow\downarrow\downarrow} && \ket{\downarrow\downarrow\uparrow} && \ket{\downarrow\uparrow\downarrow} && \ket{\downarrow\uparrow\uparrow}\\
s=-\tfrac{3}{2} && s=-\tfrac{1}{2} && s=-\tfrac{1}{2} && s=+\tfrac{1}{2}\\\\
\ket{\uparrow\downarrow\downarrow} && \ket{\uparrow\downarrow\uparrow} && \ket{\uparrow\uparrow\downarrow} && \ket{\uparrow\uparrow\uparrow}\\
s=-\tfrac{1}{2} && s=+\tfrac{1}{2} && s=+\tfrac{1}{2} && s=+\tfrac{3}{2}
\end{align}$$
Therefore the only spin states allowed are $\boxed{S\in\left\{-\tfrac{3}{2},-\tfrac{1}{2},+\tfrac{1}{2},+\tfrac{3}{2}\right\}}$.