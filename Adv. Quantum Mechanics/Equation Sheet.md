$$\begin{align}
p(\chi_\pm^r|\chi)&=\left|\braket{\chi_\pm^r|\chi}\right|^2
\end{align}$$
---
### Spin Operators
The typical operators for spin has the following operations:
$$\begin{align}
S\ket{s,m_s}&=\sqrt{s(s+1)\hbar^2-m_s(m_s-1)\hbar^2}\ket{s,m_s-1}\\
S^\dagger\ket{s,m_s}&=\sqrt{s(s+1)\hbar^2-m_s(m_s+1)\hbar^2}\ket{s,m_s+1}\\
S^2\ket{s,m_s}&=s(s+1)\hbar^2\ket{s,m_s}\\\\
S_x\ket{s,m_s}&=\dfrac{1}{2}(S^\dagger+S)\\
S_y\ket{s,m_s}&=\dfrac{1}{2i}(S^\dagger-S)\\
S_z\ket{s,m_s}&=m_s\hbar\ket{s,m_s}
\end{align}$$
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
### State Representations
Assuming that the basis formed by the span of $\ket{\uparrow}$ and $\ket{\downarrow}$:
$$\begin{align}
S_x&=\dfrac{\hbar}{2}\sigma_x & 
S_y&=\dfrac{\hbar}{2}\sigma_y & 
S_z&=\dfrac{\hbar}{2}\sigma_z & | &&
S_r&=\dfrac{\hbar}{2}\begin{bmatrix}\cos\theta&e^{-i\phi}\sin\theta\\e^{i\phi}\sin\theta&-\cos\theta\end{bmatrix}\\
\ket{\chi_+^X}&=\dfrac{1}{\sqrt2}\begin{bmatrix}1\\1\end{bmatrix}_Z & 
\ket{\chi_+^Y}&=\dfrac{1}{\sqrt{2}}\begin{bmatrix}1\\i\end{bmatrix}_Z & 
\ket{\chi_+^Z}&=\begin{bmatrix}1\\0\end{bmatrix}_Z & | &&
\ket{\chi_+^r}&=\begin{bmatrix}\cos(\theta/2)\\e^{i\phi}\sin(\theta/2)\end{bmatrix}_Z\\
\ket{\chi_-^X}&=\dfrac{1}{\sqrt2}\begin{bmatrix}1\\-1\end{bmatrix}_Z & 
\ket{\chi_-^Y}&=\dfrac{1}{\sqrt{2}}\begin{bmatrix}1\\ -i\end{bmatrix}_Z & 
\ket{\chi_-^Z}&=\begin{bmatrix}0\\1\end{bmatrix}_Z & | &&
\ket{\chi_-^r}&=\begin{bmatrix}e^{-i\phi}\sin(\theta/2)\\-\cos(\theta/2)\end{bmatrix}_Z\\
\end{align}$$
---
### Uncertainty
$$\begin{align}
\sigma_a^2\sigma_b^2&\ge\left|\dfrac{\braket{[A,B]}}{2i}\right|^2
\end{align}$$
---
### Magnetic Fields
Magnetic moments and Gyromagnetic constants:
$$\begin{align}
\vec{\mu}_L&=g_L\vec{L} & g_L&=-\dfrac{e}{2m}\\
\vec{\mu}_S&=g_S\vec{S} & g_S&=-\dfrac{e}{m}
\end{align}$$
Electrons in a magnetic field $\vec{B}(z)=B_0\hat{z}$ along the $z$-axis:
$$\begin{align}
\hat{H}&=-\vec\mu_S\cdot\vec{B} & E_\pm&=\mp\dfrac{\hbar}{2}g_SB_0\\
\end{align}$$
$$\begin{align}
\ket{\chi(t)}&=\cos(\tfrac{\alpha}{2})e^{-iE_+t/\hbar}\ket{\chi_+^Z}+\sin(\tfrac{\alpha}{2})e^{-iE_-t/\hbar}\ket{\chi_-^Z}\\
\omega_L&=g_sB_0\text{ (Larmor Frequency)}\\
\braket{S_x}&=+\dfrac{\hbar}{2}\sin(\alpha)\cos(\omega_Lt)\\
\braket{S_y}&=-\dfrac{\hbar}{2}\sin(\alpha)\sin(\omega_Lt)\\
\braket{S_z}&=+\dfrac{\hbar}{2}\cos(\alpha)\\
\end{align}$$
Electrons in a magnetic field $\vec{B}(z)=(B_0+\alpha z)\hat{z}$ along the $z$-axis for $T$ seconds:
$$\begin{align}
\hat{H}&=-\vec\mu_S\cdot\vec{B} & E_\pm&=\mp\dfrac{\hbar}{2}g_S(B_0+\alpha z)\\
\end{align}$$
$$\begin{align}
\ket{\chi(t)}&=\cos(\tfrac{\alpha}{2})e^{-iE_+t/\hbar}\ket{\chi_+^Z}+\sin(\tfrac{\alpha}{2})e^{-iE_-t/\hbar}\ket{\chi_-^Z} & 0\le t\le T\\
&=A(T)e^{ikz}\ket{\chi_+^Z}+B(T)e^{-ikz}\ket{\chi_-^Z}\\
p&=\hbar k=\dfrac{\hbar}{2}\alpha g_S T
\end{align}$$
---
### Hydrogen Atom
$$\begin{align}
-\dfrac{\hbar^2}{2M}\nabla_R^2\psi_R\left(\vec{R}\right)&=E_R\psi_R\left(\vec{R}\right) & M&=m_1+m_2\\
-\dfrac{\hbar^2}{2\mu}\nabla_r^2\psi_r\left(\vec{r}\right)+V\left(\vec{r}\right)\psi_r\left(\vec{r}\right)&=E_r\psi_r\left(\vec{r}\right) & \dfrac{1}{\mu}&=\dfrac{1}{m_1}+\dfrac{1}{m_2}\\
\end{align}$$
---
### Statistical Properties
The $\pm$ refers to the wavefunction being symmetric (bosons) or antisymmetric (fermions).
$$\begin{align}
\left\langle(\Delta x)^2\right\rangle_\pm&=\left\langle x^2\right\rangle_a+\left\langle x^2\right\rangle_b-2\left\langle x\right\rangle_a\left\langle x\right\rangle_b\mp2\left|\left\langle x\right\rangle_{ab}\right|^2\\
\left\langle x\right\rangle_{ab}&=\begin{cases}0, & \text{Distinguishable}\\1, & \text{Indistinguishable}\end{cases}
\end{align}$$
---
### Perturbation Theory (Time-Independent, Non-Degenerate)
For systems of non-degenerate energy $\hat{H}'$ and unchanging in time:
$$\begin{align}
E^1_n&=\bra{\psi_n^0}\hat{H}^1\ket{\psi_n^0}\\
\psi_n^1&=\sum_{m\ne n}\dfrac{\bra{\psi_m^0}\hat{H}^1\ket{\psi_n^0}}{E^0_n-E^0_m}\psi_m^0
\end{align}$$
Energy corrections are usually good, but wavefunction corrections are poor.

---
### Perturbation Theory (Time-Independent, Degenerate)
$$\begin{align}
W^n_{ij}&=\bra{\psi_i^n}\hat{H}^{n+1}\ket{\psi_j^n}\\
W^n\ket{\psi^n}&=E^{n+1}\ket{\psi^n}
\end{align}$$
---
### Perturbation Theory (Time-Dependent, Non-Degenerate)
$$\begin{align}
\psi(t)&=c_a(t)e^{-iE_at/\hbar}\psi_a+c_b(t)e^{-iE_bt/\hbar}\psi_b\\
\dot{c}^{n+1}_i(t)&=-\dfrac{i}{\hbar}\left(c^{n}_i\hat{H}^1_{ii}+c^{n}_j\hat{H}^1_{ij}e^{-i(E_j-E_i)t/\hbar}\right)\\
\omega_0&=\dfrac{E_b-E_a}{\hbar}
\end{align}$$
---
### Variational Principle
$$\begin{align}
E_\text{gs}\le\bra{\psi}\hat{H}\ket{\psi}=\braket{\hat{H}}
\end{align}$$
---
### WKB Approximation
Classical Accepted Region $E>V(x)$:
$$\begin{align}
p(x)&=\sqrt{2m(E-V(x))}\\
\phi(x)&=\dfrac{1}{\hbar}\int^x_a p(x')\ dx'=n\pi\hbar\\
\psi(x)&=\dfrac{A}{\sqrt{p(x)}}e^{\pm i\phi(x)}\\
\end{align}$$
Classical Forbidden Region $E<V(x)$:
$$\begin{align}
p(x)&=\sqrt{2m(E-V(x))}\\
\phi(x)&=\dfrac{1}{\hbar}\int^x_a |p(x')|\ dx'\\
\psi(x)&=\dfrac{A}{\sqrt{p(x)}}e^{\pm\phi(x)}
\end{align}$$
---
### The Rabi Problem
If we choose the Hamiltonian $\hat{H}_{ba}=\tfrac{V_{ba}}{2}e^{-i\omega t}$.
$$\begin{align}
\omega_r&=\dfrac{1}{2}\sqrt{(\omega-\omega_0)^2+\dfrac{|V_{ab}|^2}{\hbar^2}}
\end{align}$$
Using initial conditions $c_a(0)=1$ and $c_b(0)=0$, we get:
$$\begin{align}
c_a(t)&=e^{i(\omega-\omega_0)t/2}\left[\cos(\omega_rt)+i\left(\dfrac{\omega_0-\omega}{2\omega_r}\right)\sin(\omega_rt)\right]\\
c_b(t)&=-\left(\dfrac{iV_{ba}}{2\hbar\omega_r}\right)e^{-i(\omega-\omega_0)t/2}\sin(\omega_rt)\\
\end{align}$$
And the transition state (where $|V_{ba}|^2\ll\hbar^2(\omega-\omega_0)^2$) comes as the following:
$$\begin{align}
P_{a\rightarrow b}(t)\approx\dfrac{|V_{ba}|^2}{\hbar^2}\dfrac{\sin^2\left(\tfrac{\omega-\omega_0}{2}t\right)}{(\omega-\omega_0)^2}
\end{align}$$
---
### Absorption and Emission
For a two-level atom in electromagnetic field $\vec{E}=E_0\cos(\omega t)\hat{z}$:
$$\begin{align}
H'_{ba}&=-\vec{p}\cdot\vec{E}=-q\braket{\psi_b|z|\psi_a}E_0\cos(\omega t)
\end{align}$$
For initial conditions $c_a(0)=1$ and $c_b(0)=0$, we get:
$$\begin{align}
P_{a}(t)&=\dfrac{(-pE_0)^2}{\hbar^2}\dfrac{\sin^2\left(\tfrac{\omega-\omega_0}{2}t\right)}{(\omega-\omega_0)^2}
\end{align}$$
We can then find the transition rate for stimulated emission:
$$\begin{align}
R_{b\rightarrow a}&=\dfrac{\pi p^2}{3\epsilon_0\hbar^2}\rho(\omega_0)
\end{align}$$
In statistical mechanics, we know that:
$$\begin{align}
\rho(\omega_0)&=\dfrac{A}{e^{\hbar\omega_0/kT}B_{ab}-B_{ba}}
\end{align}$$
Combining, we get (A is the spontaneous emission rate):
$$\begin{align}
A&=\dfrac{\omega_0^3p^2}{3\pi\epsilon_0\hbar c^3}
\end{align}$$
---
### Selection Rules


---
### Adiabatic Approximation
Change thing slow enough that the system adapts as it goes.
$$\begin{align}
\hat{H}\psi_n&=E_n\psi_n &\implies&& \psi_n(t)&=\psi_n(0)e^{-iE_nt/\hbar} && \text{(Time-Independent)}\\
\hat{H}(t)\psi_n(t)&=i\hbar\dfrac{\partial}{\partial t}\psi_n(t) &\implies&& \psi(t)&=\sum_{n}c_n(t)\psi_n(t)e^{i\theta_n(t)} && \text{(Time-Dependent)}\\
\end{align}$$
Where $\theta_n(t)$ is the phase factor to when $E_n$ varies with time.
$$\begin{align}
\theta_n(t)&=-\dfrac{1}{\hbar}\int_0^tE_n(t')\ dt'
\end{align}$$
The final wavefunction can be found as the following ($\gamma$ is geometric phase):
$$\begin{align}
\psi(t)&=e^{i\gamma_n(t)}e^{i\theta_n(t)}\psi_n(t)\\
\gamma_n(t)&=i\int_0^t\left\langle\psi_n(t')|\dfrac{\partial}{\partial t}\psi_n(t')\right\rangle\ dt
\end{align}$$
---
### Berry Phase
If the $\gamma_n(t)$ phase returns back to its original position at time $T$, we find:
$$\begin{align}
\gamma_n(T)&=i\oint\left\langle\psi_n|\vec\nabla_R\psi_n\right\rangle\ dR
\end{align}$$
Where $R$ is a parameter of $\psi_n$ that (potentially) changes over time.
The Berry phase vanishes if only 1 parameter is time-dependent.

---
### Aharonov-Bohm Effect
Given the electromagnetic potentials $\phi$ and $\vec{A}$.
The general Hamiltonian that handles these are:
$$\begin{align}
\hat{H}&=\dfrac{1}{2m}\left(\dfrac{\hbar}{i}\vec{\nabla}-q\vec{A}\right)^2+q\phi
\end{align}$$
For the case of a solenoid and electron beams going around the 2 sides:
$$\begin{align}
E_n&=\dfrac{\hbar^2}{2mr^2}\left(n-\dfrac{q\Phi}{2\pi\hbar}\right)^2
\end{align}$$
where $r$ is the radius from the center of the solenoid that's larger than the solenoid radius.
These changes lead to a phase difference in the 2 beams.
$$\begin{align}
\Delta g&=g_+-g_-=\dfrac{q\Phi}{\hbar}
\end{align}$$
This is equal to the Berry phase of the system $\gamma_n(T)=\dfrac{q\Phi}{\hbar}$.

---
### Rutherford Scattering

---
### Born Approximation

---











**Angular Momentum with Position**
$$\begin{align}
\Aboxed{[L_i,x_j]&=-i\hbar\epsilon_{ijk}x_k}\\
\{L_i,x_j\}&=2L_ix_j-[L_i,x_j]\\
\Aboxed{\{L_i,x_j\}&=2L_ix_j+i\hbar\epsilon_{ijk}x_k}
\end{align}$$

**Angular Momentum Squared with Position**
$$\begin{align}
[L_i^2,x_j]&=L_i[L_i,x_j]+[L_i,x_j]L_i\\
&=-i\hbar\epsilon_{ijk}\left(L_ix_k+x_kL_i\right)\\
&=-i\hbar\epsilon_{ijk}\left\{L_i,x_k\right\}\\
&=-i\hbar\epsilon_{ijk}\left(2L_ix_j+i\hbar\epsilon_{ijk}x_k\right)\\
\Aboxed{[L_i^2,x_j]&=-2i\hbar\epsilon_{ijk}L_ix_j+\hbar^2\epsilon_{ijk}^2x_k}\\\\
[L_x^2,z]&=+2i\hbar L_xz+\hbar^2y\\
[L_y^2,z]&=-2i\hbar L_yz+\hbar^2x\\
[L_z^2,z]&=0\\
\end{align}$$


