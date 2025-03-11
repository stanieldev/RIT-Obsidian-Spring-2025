$$\begin{align}
p(\chi_\pm^r|\chi)&=\left|\braket{\chi_\pm^r|\chi}\right|^2
\end{align}$$
---
### Pauli Matrices
Assuming that the basis formed by the span of $\ket{\uparrow}$ and $\ket{\downarrow}$:
$$\begin{align}
\begin{bmatrix}0&1\\1&0\end{bmatrix}&=\sigma_x &
\begin{bmatrix}0&-i\\i&0\end{bmatrix}&=\sigma_y &
\begin{bmatrix}1&0\\0&-1\end{bmatrix}&=\sigma_z &  &&
\begin{bmatrix}1&0\\0&1\end{bmatrix}&=\mathbb{I}\\
[\sigma_x,\sigma_y]&=2i\sigma_z &
[\sigma_y,\sigma_z]&=2i\sigma_x &
[\sigma_z,\sigma_x]&=2i\sigma_y & | &&
[\sigma_a,\sigma_b]&=2i\epsilon_{abc}\sigma_c\\
\{\sigma_x,\sigma_y\}&=0 &
\{\sigma_y,\sigma_z\}&=0 &
\{\sigma_z,\sigma_x\}&=0 & | &&
\{\sigma_a,\sigma_b\}&=2\delta_{ab}\sigma_a^2\\
\end{align}$$
---
### Spin Operators
Assuming that the basis formed by the span of $\ket{\uparrow}$ and $\ket{\downarrow}$:
$$\begin{align}
S_x&=\dfrac{\hbar}{2}\sigma_x & 
S_y&=\dfrac{\hbar}{2}\sigma_y & 
S_z&=\dfrac{\hbar}{2}\sigma_z & | &&
S_a&=\dfrac{\hbar}{2}\sigma_a\\
[S_x,S_y]&=i\hbar S_z &
[S_y,S_z]&=i\hbar S_x &
[S_z,S_x]&=i\hbar S_y & | &&
[S_a,S_b]&=i\hbar\epsilon_{abc}S_c\\
\end{align}$$
$$\begin{align}
S^2\ket{s,m_s}&=s(s+1)\hbar^2\ket{s,m_s}\\
S_z\ket{s,m_s}&=m_s\hbar\ket{s,m_s}\\
S_\pm\ket{s,m_s}&=\sqrt{s(s+1)\hbar^2-m_s(m_s\pm1)\hbar^2}\ket{s,m_s\pm1}
\end{align}$$
---
### State Representations
Assuming that the basis formed by the span of $\ket{\uparrow}$ and $\ket{\downarrow}$:
$$\begin{align}
S_x&=\dfrac{\hbar}{2}\sigma_x & 
S_y&=\dfrac{\hbar}{2}\sigma_y & 
S_z&=\dfrac{\hbar}{2}\sigma_z & | &&
S_r&=\dfrac{\hbar}{2}\begin{bmatrix}\cos\theta&e^{-i\phi}\sin\theta\\e^{i\phi}\sin\theta&-\cos\theta\end{bmatrix}\\
\chi_+^X&=\dfrac{1}{\sqrt2}\begin{bmatrix}1\\1\end{bmatrix}_Z & 
\chi_+^Y&=\dfrac{1}{\sqrt{2}}\begin{bmatrix}1\\i\end{bmatrix}_Z & 
\chi_+^Z&=\begin{bmatrix}1\\0\end{bmatrix}_Z & | &&
\chi_+^r&=\begin{bmatrix}\cos(\theta/2)\\e^{i\phi}\sin(\theta/2)\end{bmatrix}_Z\\
\chi_-^X&=\dfrac{1}{\sqrt2}\begin{bmatrix}1\\-1\end{bmatrix}_Z & 
\chi_-^Y&=\dfrac{1}{\sqrt{2}}\begin{bmatrix}1\\ -i\end{bmatrix}_Z & 
\chi_-^Z&=\begin{bmatrix}0\\1\end{bmatrix}_Z & | &&
\chi_-^r&=\begin{bmatrix}e^{-i\phi}\sin(\theta/2)\\-\cos(\theta/2)\end{bmatrix}_Z\\
\end{align}$$
---
### Magnetic Fields
$$\begin{align}
\vec{\mu}_L&=g_L\vec{L} & g_L&=-\dfrac{e}{2m}\\
\vec{\mu}_S&=g_S\vec{S} & g_S&=-\dfrac{e}{m}
\end{align}$$
$$\begin{align}
\chi(t)&=\cos(\tfrac{\alpha}{2})\chi_+^Ze^{-iE_+t/\hbar}+\sin(\tfrac{\alpha}{2})\chi_-^Ze^{-iE_-t/\hbar} &
E_\pm&=\mp\dfrac{g_SB_0\hbar}{2}\\
\end{align}$$
---
### Hydrogen Atom
$$\begin{align}
-\dfrac{\hbar^2}{2M}\nabla_R^2\psi_R\left(\vec{R}\right)&=E_R\psi_R\left(\vec{R}\right) & M&=m_1+m_2\\
-\dfrac{\hbar^2}{2\mu}\nabla_r^2\psi_r\left(\vec{r}\right)+V\left(\vec{r}\right)\psi_r\left(\vec{r}\right)&=E_r\psi_r\left(\vec{r}\right) & \dfrac{1}{\mu}&=\dfrac{1}{m_1}+\dfrac{1}{m_2}\\
\end{align}$$
---
### Statistical Properties
$$\begin{align}
\left\langle(\Delta x)^2\right\rangle_\pm&=\left\langle x^2\right\rangle_a+\left\langle x^2\right\rangle_b-2\left\langle x\right\rangle_a\left\langle x\right\rangle_b\mp2\left|\left\langle x\right\rangle_{ab}\right|^2\\
\left\langle x\right\rangle_{ab}&=\begin{cases}0, & \text{Distinguishable}\\1, & \text{Indistinguishable}\end{cases}
\end{align}$$
---
### Variational Principle
$$\begin{align}
E_\text{gs}\le\bra{\psi}\hat{H}\ket{\psi}
\end{align}$$

### Perturbation Theory (NDTIPT)
$$\begin{align}
E^1_n&=\bra{\psi_n^0}\hat{H}^1\ket{\psi_n^0}\\
\psi_n^1&=\sum_{m\ne n}\dfrac{\bra{\psi_m^0}\hat{H}'\ket{\psi_n^0}}{E^0_n-E^0_m}\psi_m^0
\end{align}$$
### Perturbation Theory (DTIPT)
$$\begin{align}
W^n_{ij}&=\bra{\psi_i^n}\hat{H}^{n+1}\ket{\psi_j^n}\\
W^n\ket{\psi^n}&=E^{n+1}\ket{\psi^n}
\end{align}$$
### Perturbation Theory (DTDPT)
$$\begin{align}
\psi(t)&=c_a(t)\psi_ae^{-iE_at/\hbar}+c_b(t)\psi_be^{-iE_bt/\hbar}\\
\dot{c}^{n+1}_i(t)&=-\dfrac{i}{\hbar}\left(c^{n}_i\hat{H}^1_{ii}+c^{n}_j\hat{H}^1_{ij}e^{-i(E_j-E_i)t/\hbar}\right)
\end{align}$$
### WKB Approximation
$$\begin{align}
p(x)&=\sqrt{2m(E-V(x))}\\
\phi(x)&=\dfrac{1}{\hbar}\int^x_a p(x')\ dx'\\
\psi(x)&=\dfrac{c}{\sqrt{p(x)}}e^{\pm i\phi(x)}
\end{align}$$

Rabi Problem and Beyond (Lecture 17+)