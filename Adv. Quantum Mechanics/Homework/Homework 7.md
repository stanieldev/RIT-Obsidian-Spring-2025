**Name:** Stanley Goodwin
**Date:** 3/28/2025

---
### Question 1
A hydrogen atom is placed in a time-dependent electric field $\vec{E}(t)=E(t)\hat{z}$.

**Hydrogen Wavefunctions**
$$\begin{align}
\ket{\psi_{1,0,0}}&=\dfrac{1}{\sqrt{\pi}a_0^{3/2}}e^{-r/a_0}\\
\ket{\psi_{2,0,0}}&=\dfrac{1}{4\sqrt{2\pi}a_0^{3/2}}\left[2-\dfrac{r}{a_0}\right]e^{-r/2a_0}\\
\ket{\psi_{2,1,0}}&=\dfrac{1}{4\sqrt{2\pi}a_0^{3/2}}\dfrac{r}{a_0}e^{-r/2a_0}\cos\theta\\
\ket{\psi_{2,1,\pm1}}&=\dfrac{1}{8\sqrt{\pi}a_0^{3/2}}\dfrac{r}{a_0}e^{-r/2a_0}\sin\theta\ e^{\pm i\phi}
\end{align}$$
**Hydrogen Selection Rules**
$$\begin{align}
&& \Delta l&=\pm1 & \Delta m&=0,\pm1\\
\implies
&& \Aboxed{l&=1} & \Aboxed{m&=0}
\end{align}$$
**Hamiltonian Calculation**
$$\begin{align}
H'_{ij}&=\bra{\psi^i}H'\ket{\psi^j}\\
&=\int\bra{\psi_{n_il_im_i}} H'\ket{\psi_{n_jl_jm_j}}\ dV\\
&=\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\bra{\psi_{n_il_im_i}}(-eEz)\ket{\psi_{n_jl_jm_j}}\ r^2\sin\theta\ d\phi\ d\theta\ dr\\
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\bra{\psi_{n_il_im_i}} r\cos\theta\ket{\psi_{n_jl_jm_j}}\ r^2\sin\theta\ d\phi\ d\theta\ dr\\
\Aboxed{H'_{ij}&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\braket{\psi_{n_il_im_i}|\psi_{n_jl_jm_j}}\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr}
\end{align}$$
---
#### Question 1.1
Calculate all four matrix elements $H'_{ij}$ of the perturbation $H'=-eEz$ between the ground state $(n=1)$ and the quadruple degenerate first excited states $(n=2)$.

**Transition Hamiltonian Calculation**
$$\begin{align}
H'_{\psi_\text{final}\rightarrow\psi_\text{initial}}&=\bra{\psi_\text{final}}H'\ket{\psi_\text{initial}}\\
H'_{(2,l,m)\rightarrow(1,0,0)}&=\bra{\psi_{1,0,0}} H'\ket{\psi_{2,l,m}}\\
&=\int\bra{\psi_{1,0,0}} H'\ket{\psi_{2,l,m}}\ dV\\
&=\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\bra{\psi_{1,0,0}}(-eEz)\ket{\psi_{2,l,m}}\ r^2\sin\theta\ d\phi\ d\theta\ dr\\
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\bra{\psi_{1,0,0}}r\cos\theta\ket{\psi_{2,l,m}}\ r^2\sin\theta\ d\phi\ d\theta\ dr\\
\Aboxed{H'_{(2,l,m)\rightarrow(1,0,0)}&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\braket{\psi_{1,0,0}|\psi_{2,l,m}}\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr}
\end{align}$$
**Hamiltonian of** $\ket{210}\rightarrow\ket{100}$
$$\begin{align}
H'_{(2,1,0)\rightarrow(1,0,0)}
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\braket{\psi_{100}|\psi_{210}}\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\left(\dfrac{1}{\sqrt{\pi}a_0^{3/2}}e^{-r/a_0}\right)^\dagger\left(\dfrac{1}{4\sqrt{2\pi}a_0^{3/2}}\dfrac{r}{a_0}e^{-r/2a_0}\cos\theta\right)\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-\dfrac{eE}{4\sqrt{2}\pi}\left(\dfrac{2}{3}\right)^4\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\left(\dfrac{3r}{2a_0}\right)^4e^{-3r/2a_0}\sin\theta\cos^2\theta\ d\phi\ d\theta\ dr\\
&=-\dfrac{4eE}{3^4\sqrt{2}\pi}\cdot\int_0^{\infty}\left(\dfrac{3r}{2a_0}\right)^4e^{-3r/2a_0}\ dr\cdot\int_0^{\pi}\int_0^{2\pi}\sin\theta\cos^2\theta\ d\phi\ d\theta\\
&=-\dfrac{4eE}{3^4\sqrt{2}\pi}\dfrac{2a_0}{3}\cdot\int_0^{\infty}u^4e^{-u}\ du\cdot\dfrac{2}{3}\cdot2\pi\\
&=-\dfrac{32eEa_0}{3^6\sqrt{2}}\cdot24\\
\Aboxed{H'_{(2,1,0)\rightarrow(1,0,0)}&=-\dfrac{256eEa_0}{243\sqrt{2}}}
\end{align}$$
**Hamiltonian of** $\ket{200}\rightarrow\ket{100}$
$$\begin{align}
H'_{(2,0,0)\rightarrow(1,0,0)}
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\braket{\psi_{100}|\psi_{200}}\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\left(\dfrac{1}{\sqrt{\pi}a_0^{3/2}}e^{-r/a_0}\right)^\dagger\left(\dfrac{1}{4\sqrt{2\pi}a_0^{3/2}}\left[2-\dfrac{r}{a_0}\right]e^{-r/2a_0}\right)\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-\dfrac{eE}{4\sqrt{2}\pi}\int_0^{\infty}\left(\dfrac{r}{a_0}\right)^3e^{-3r/2a_0}\left[2-\dfrac{r}{a_0}\right]\ dr\cdot\int_0^{\pi}\int_0^{2\pi}\sin\theta\cos\theta\ d\phi\ d\theta\\
\Aboxed{H'_{(2,0,0)\rightarrow(1,0,0)}&=0}
\end{align}$$
It's 0 because the theta integral leads to a multiplication by 0.

**Hamiltonian of** $\ket{2,1,\pm1}\rightarrow\ket{100}$
$$\begin{align}
H'_{(2,1,\pm1)\rightarrow(1,0,0)}
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\braket{\psi_{100}|\psi_{2,1,\pm1}}\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\left(\dfrac{1}{\sqrt{\pi}a_0^{3/2}}e^{-r/a_0}\right)^\dagger\left(\dfrac{1}{8\sqrt{\pi}a_0^{3/2}}\dfrac{r}{a_0}e^{-r/2a_0}\sin\theta\ e^{\pm i\phi}\right)\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-\dfrac{eE}{8\pi}\int_0^{\infty}\left(\dfrac{r}{a_0}\right)^4e^{-3r/2a_0}\ dr\cdot\int_0^{\pi}\sin^2\theta\cos\theta\ d\theta\cdot\int_0^{2\pi}e^{\pm i\phi} d\phi\\
\Aboxed{H'_{(2,1,\pm1)\rightarrow(1,0,0)}&=0}
\end{align}$$
It's 0 because the phi integral leads to a multiplication by 0.

---
#### Question 1.2
Show that $H'_{ii}=0$ for all five states.

**Inner Products**
$$\begin{align}
\braket{\psi_{1,0,0}|\psi_{1,0,0}}&=\dfrac{1}{\pi a_0^3}e^{-2r/a_0}\\
\braket{\psi_{2,0,0}|\psi_{2,0,0}}&=\dfrac{1}{32\pi a_0^3}\left[2-\dfrac{r}{a_0}\right]^2e^{-r/a_0}\\
\braket{\psi_{2,1,0}|\psi_{2,1,0}}&=\dfrac{1}{32\pi a_0^3}\dfrac{r^2}{a_0^2}e^{-r/a_0}\cos^2\theta\\
\braket{\psi_{2,1,\pm1}|\psi_{2,1,\pm1}}&=\dfrac{1}{64\pi a_0^3}\dfrac{r^2}{a_0^2}e^{-r/a_0}\sin^2\theta
\end{align}$$
**Hamiltonian Matrix Elements**
$$\begin{align}
H'_{(1,0,0)\rightarrow(1,0,0)}&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\braket{\psi_{100}|\psi_{100}}\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-eE\int_0^{\infty}\int_0^{\pi}\int_0^{2\pi}\dfrac{1}{\pi a_0^3}e^{-2r/a_0}\ r^3\sin\theta\cos\theta\ d\phi\ d\theta\ dr\\
&=-\dfrac{eE}{8\pi}\cdot\int_0^{\infty}\left(\dfrac{2r}{a_0}\right)^3e^{-2r/a_0}\ dr\cdot\int_0^{\pi}\int_0^{2\pi}\sin\theta\cos\theta\ d\phi\ d\theta\\
&=-\dfrac{eE}{8\pi}\dfrac{a_0}{2}\cdot\int_0^{\infty}u^3e^{-u}\ du\cdot\int_0^{\pi}\sin\theta\cos\theta\ d\phi\cdot\int_0^{2\pi}d\theta\\
&=-\dfrac{eEa_0}{16\pi}\cdot3!\cdot0\cdot2\pi\\
\Aboxed{H'_{(1,0,0)\rightarrow(1,0,0)}&=0}\\
\end{align}$$
A guess I'll make is that only the theta component actually makes this zero.
$$\begin{align}
H'_{11}&\sim\int_0^{\pi}\braket{\psi_{200}|\psi_{200}}\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\dfrac{1}{32\pi a_0^3}\left[2-\dfrac{r}{a_0}\right]^2e^{-r/a_0}\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\sin\theta\cos\theta\ d\theta\\
\Aboxed{H'_{11}&=0}
\end{align}$$
$$\begin{align}
H'_{22}&\sim\int_0^{\pi}\braket{\psi_{210}|\psi_{210}}\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\dfrac{1}{32\pi a_0^3}\dfrac{r^2}{a_0^2}e^{-r/a_0}\cos^2\theta\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\sin\theta\cos^3\theta\ d\theta\\
\Aboxed{H'_{22}&=0}
\end{align}$$
$$\begin{align}
H'_{33}&\sim\int_0^{\pi}\braket{\psi_{211}|\psi_{211}}\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\dfrac{1}{64\pi a_0^3}\dfrac{r^2}{a_0^2}e^{-r/a_0}\sin^2\theta\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\sin^3\theta\cos\theta\ d\theta\\
\Aboxed{H'_{33}&=0}
\end{align}$$
$$\begin{align}
H'_{44}&\sim\int_0^{\pi}\braket{\psi_{21-1}|\psi_{21-1}}\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\dfrac{1}{64\pi a_0^3}\dfrac{r^2}{a_0^2}e^{-r/a_0}\sin^2\theta\sin\theta\cos\theta\ d\theta\\
&\sim\int_0^{\pi}\sin^3\theta\cos\theta\ d\theta\\
\Aboxed{H'_{44}&=0}
\end{align}$$
---
#### Question 1.3
If the electric field retains its magnitude $E(t)$ but now points in a general direction (not necessarily along the $z$-axis), calculate the lifetime, in seconds, for each of the four excited $n=2$ states.

The new Hamiltonian is:
$$\begin{align}
H'&=-e\vec{E}\cdot\vec{r}\\
&=-e\left(E_xx+E_yy+E_zz\right)\\
&=-e\left(E_xr\sin\theta\cos\phi+E_yr\sin\theta\sin\phi+E_zr\cos\theta\right)
\end{align}$$
From selection rules, we know all but $\ket{200}\rightarrow\ket{100}$ is possible.
These allowed states take the form $\psi=\ket{2,1,m}$.

I'm not really sure how to do this, so I'll just attempt an idea.
$$\begin{align}
A^m_{2\rightarrow1}&=\dfrac{\omega^3e^2}{3\pi\epsilon_0\hbar c^3}\left|\bra{\psi_{1,0,0}}\vec{r}\ket{\psi_{2,1,m}}\right|^2\\
\end{align}$$
The associated frequency with it is:
$$\begin{align}
\omega&=\dfrac{E_2-E_1}{\hbar}\\
&=\dfrac{10.2\text{ eV}}{6.572\cdot10^{-16}\text{ eV}\cdot s}\\
\Aboxed{\omega&=1.552\cdot10^{16}\text{ Hz}}
\end{align}$$
I couldn't be bothered to calculate the matrix elements, so I looked them up.
$$\begin{align}
\left|\bra{\psi_{1,0,0}}\vec{r}\ket{\psi_{2,1,0}}\right|^2&=\dfrac{9}{4}a_0^2\\
\left|\bra{\psi_{1,0,0}}\vec{r}\ket{\psi_{2,1,\pm1}}\right|^2&=\dfrac{9}{4}a_0^2\\
\end{align}$$
The approximation for $A_{2\rightarrow1}$ is then the following:
$$\begin{align}
A_{2\rightarrow1}&=\dfrac{\omega^3e^2}{3\pi\epsilon_0\hbar c^3}\left|\bra{\psi_{1,0,0}}\vec{r}\ket{\psi_{2,1,m}}\right|^2\\
\Aboxed{A_{2\rightarrow1}&\approx 4.7\cdot 10^8\text{ Hz}}
\end{align}$$
I could do it with the electric field, but it's too much arithmetic.

---
### Question 2
**Angular Momentum with Position**
$$\begin{align}
\Aboxed{[L_i,x_j]&=i\hbar\epsilon_{ijk}x_k}\\\\
[L_x,z]&=-i\hbar y\\
[L_y,z]&=+i\hbar x\\
[L_z,z]&=0\\
\end{align}$$
**Angular Momentum Squared with Position**
$$\begin{align}
[L_i^2,x_j]&=L_i[L_i,x_j]+[L_i,x_j]L_i\\
&=i\hbar\epsilon_{ijk}\left(L_ix_k+x_kL_i\right)\\
\Aboxed{[L_i^2,x_j]&=i\hbar\epsilon_{ijk}\left(-i\hbar\epsilon_{ijk}x_j+2x_kL_i\right)}\\\\
[L_x^2,z]&=-i\hbar\left(i\hbar z+2yL_x\right)\\
[L_y^2,z]&=+i\hbar\left(-i\hbar z+2xL_y\right)\\
[L_z^2,z]&=0\\
\end{align}$$
---
#### Question 2.1
Show that $[L^2, z]= 2i\hbar(xL_y - yL_x - i\hbar z)$.

**Identities I derived**
$$\begin{align}
[L_i^2,x_j]&=i\hbar\epsilon_{ijk}\left(-i\hbar\epsilon_{ijk}x_j+2x_kL_i\right)\\\\
[L_x^2,z]&=-i\hbar\left(i\hbar z+2yL_x\right)\\
[L_y^2,z]&=+i\hbar\left(-i\hbar z+2xL_y\right)\\
[L_z^2,z]&=0\\
\end{align}$$
**Proof**
$$\begin{align}
[L^2, z]&=[L_x^2, z]+[L_y^2, z]+[L_z^2, z]\\
&=-i\hbar\left(i\hbar z+2yL_x\right)+i\hbar\left(-i\hbar z+2xL_y\right)+0\\
&=i\hbar\left(-i\hbar z-2yL_x\right)+i\hbar\left(-i\hbar z+2xL_y\right)\\
&=i\hbar\left(-i\hbar z+2xL_y-i\hbar z-2yL_x\right)\\
\Aboxed{[L^2, z]&=2i\hbar\left(xL_y-yL_x-i\hbar z\right)}
\end{align}$$
---
#### Question 2.2
Use the result $[L^2, z]= 2i\hbar(xL_y - yL_x - i\hbar z)$ and $\vec{r}\cdot\vec{L}=\vec{r}\cdot(\vec{r}\times\vec{p})=0$ to prove the relation:
$$[L^2, [L^2, z]]= 2\hbar^2(zL^2+L^2z)$$
**Thing that makes proof faster later**
$$\begin{align}
[L^2,x_j]&=[L_x^2,x_j]+[L_y^2,x_j]+[L_z^2,x_j]\\
&=i\hbar\epsilon_{xjk}\left(-i\hbar\epsilon_{xjk}x_j+2x_kL_x\right)+i\hbar\epsilon_{yjk}\left(-i\hbar\epsilon_{yjk}x_j+2x_kL_y\right)\\
&+i\hbar\epsilon_{zjk}\left(-i\hbar\epsilon_{zjk}x_j+2x_kL_z\right)\\
\Aboxed{[L^2,x_j]&=\hbar^2\left(\epsilon_{xjk}^2+\epsilon_{yjk}^2+\epsilon_{zjk}^2\right) x_j+2i\hbar\left(\epsilon_{xjk}x_kL_x+\epsilon_{yjk}x_kL_y+\epsilon_{zjk}x_kL_z\right)}\\
[L^2,x]&=2i\hbar \left(yL_z-zL_y\right)\\
[L^2,y]&=2i\hbar \left(zL_x-xL_z\right)\\
[L^2,z]&=2i\hbar(xL_y - yL_x - i\hbar z)\\
\end{align}$$
**Proof**
$$\begin{align}
[L^2,[L^2,z]]&=[L^2,[L^2,z]]\\
&=2i\hbar\left([L^2,xL_y]-[L^2,yL_x]-[L^2,i\hbar z]\right)\\
&=2i\hbar\left([L^2,x]L_y+x[L^2,L_y]-[L^2,y]L_x-y[L^2,L_x]\right)+2\hbar^2[L^2,z]\\
&=2i\hbar\left([L^2,x]L_y-[L^2,y]L_x\right)+2\hbar^2[L^2,z]\\
&=-4\hbar^2\left(\left(yL_z-zL_y\right)L_y-\left(zL_x-xL_z\right)L_x\right)+2\hbar^2[L^2,z]\\
&=-4\hbar^2\left(yL_zL_y-zL_y^2-zL_x^2+xL_zL_x\right)+2\hbar^2[L^2,z]\\
&=4\hbar^2\left(zL^2-yL_zL_y-xL_zL_x\right)-4\hbar^2z^2L_z^2+2\hbar^2[L^2,z]\\
\end{align}$$
There's more arithmetic to be done, and not sure how to proceed.

---
#### Question 2.3
Now prove the relation used in class:
$$[L^2, [L^2, \vec{r}]]= 2\hbar^2(\vec{r}L^2+L^2\vec{r})$$
where $\vec{r}$ is the vector displacement operator.

**Knowns**
$$\begin{align}
\Aboxed{[L^2,\vec{r}]&=2\hbar^2\vec{r}-2i\hbar\left(\vec{r}\times\vec{L}\right)}\\
[L^2,\vec{r}\times\vec{L}]&=\vec{r}\times[L^2,\vec{L}]+[L^2,\vec{r}]\times\vec{L}\\
&=[L^2,\vec{r}]\times\vec{L}\\
&=2\hbar^2\vec{r}\times\vec{L}-2i\hbar\left(\vec{r}\times\vec{L}\right)\times\vec{L}\\
\Aboxed{[L^2,\vec{r}\times\vec{L}]&=2\hbar^2\vec{r}\times\vec{L}}\\
\end{align}$$
**Proof**
$$\begin{align}
\left[L^2,[L^2,\vec{r}]\right]
&=\left[L^2,2\hbar^2\vec{r}-2i\hbar\left(\vec{r}\times\vec{L}\right)\right]\\
&=-2i\hbar\left[L^2,\vec{r}\times\vec{L}\right]+2\hbar^2\left[L^2,\vec{r}\right]\\
&=-4i\hbar^3(\vec{r}\times\vec{L})+4\hbar^4\vec{r}+4i\hbar^3\left(\vec{r}\times\vec{L}\right)\\
&=4\hbar^4\vec{r}\\
\end{align}$$
I give up. Too much arithmetic work.

---
### Question 3
An atom is placed in an electric field $\vec{E}(\vec{r},t)=\vec{E}_0\cos(\vec{k}\cdot\vec{r}-\omega t)$.
#### Question 3.1
Show that if the extent of the atom is small in comparison to the wavelength of light, $\vec{E}(\vec{r},t)=\vec{E}_0\cos(\omega t)$ as used in class. Show that if we keep the first order correction, $\vec{E}(\vec{r},t)=\vec{E}_0\left[\cos(\omega t)+(\vec{k}\cdot\vec{r})\sin(\omega t)\right]$. The first term gives allowed (in this case electric dipole) transitions, as discussed in class. The second gives forbidden (in this case electric quadrupole) transitions.

We have a plane wave:
$$\begin{align}
\vec{E}(\vec{r},t)&=\vec{E}_0\cos(\vec{k}\cdot\vec{r}-\omega t)
\end{align}$$
When the atom is small compared the wavelength:
$$\begin{align}
\lambda&\gg 2r_\text{atom}\\
\dfrac{2\pi}{\lambda}&\ll \dfrac{2\pi}{2r_\text{atom}}\\
\Aboxed{k\cdot r_\text{atom}&\ll \pi}
\end{align}$$
We can then expand the cosine about the point whose inside is $\omega t$:
$$\begin{align}
\cos(\omega t+\Delta)&=\cos(\omega t)-\Delta\sin(\omega t)-\dfrac{\Delta^2}{2}\cos(\omega t)+\dots\\
\end{align}$$
In our case $\Delta=k\cdot r_\text{atom}$ which is very small, and so:
$$\begin{align}
\cos(\omega t-\vec{k}\cdot\vec{r})&=\cos(\omega t)+(\vec{k}\cdot\vec{r})\sin(\omega t)-\dfrac{(\vec{k}\cdot\vec{r})^2}{2}\cos(\omega t)+\dots\\
\end{align}$$
Truncating at our 0th order, we get:
$$\begin{align}
\Aboxed{\vec{E}(\vec{r},t)&=\vec{E}_0\cos(\omega t)}
\end{align}$$
If we truncate at the first order, we get:
$$\begin{align}
\Aboxed{\vec{E}(\vec{r},t)&=\vec{E}_0\left[\cos(\omega t)+(\vec{k}\cdot\vec{r})\sin(\omega t)\right]}
\end{align}$$
---
#### Question 3.2
Show that the spontaneous emission rate for the forbidden transition $\ket{b}\rightarrow\ket{a}$ without averaging over polarization is given by:
$$R_{b\rightarrow a}=\dfrac{q^2\omega^5}{\pi\epsilon_0\hbar c^5}\left|\bra{a}(\hat{n}\cdot\vec{r})(\hat{k}\cdot\vec{r})\ket{b}\right|^2$$
where $\hat{n}$ is the direction of the electric field and $\hat{k}$ the unit vector along the wave vector.

#### Question 3.3
If the states of the atom can be approximated using a one-dimensional harmonic oscillator, find the selection rule for the electric quadrupole transition $\ket{n}\rightarrow\ket{n'}$.

#### Question 3.4
Show that the spontaneous emission transition rate for the situation in 3.3 is given by:
$$R=\dfrac{q^2\omega^5}{\pi\epsilon_0\hbar c^5}(\hat{k}_x\hat{n}_x)^2\cdot\left(\dfrac{\hbar}{m\omega}\right)^2n(n-1)$$
