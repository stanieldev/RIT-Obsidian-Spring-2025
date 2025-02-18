**Name:** Stanley Goodwin
**Date:** 2/14/2025

---
### Problem 1
#### Problem 1.1
Find to two significant digits the percent error in the binding energy of hydrogen introduced by our use of $m$ instead of $\mu$.
$$\begin{align}
E_{m}&=\dfrac{m_e e^4}{8\epsilon_0^2h^2}\\
E_{\mu}&=\dfrac{\mu e^4}{8\epsilon_0^2h^2}\\
E_{m}-E_{\mu}&=\dfrac{ e^4}{8\epsilon_0^2h^2}\left(m_e-\mu\right)\\
\dfrac{E_{m}-E_{\mu}}{E_{\mu}}&=\dfrac{\tfrac{ e^4}{8\epsilon_0^2h^2}\left(m_e-\mu\right)}{\tfrac{e^4}{8\epsilon_0^2h^2}\mu}\\
&=\dfrac{m_e-\mu}{\mu}\\
&=\dfrac{m_e}{\mu}-1\\
&=m_e\dfrac{1}{\mu}-1\\
&=m_e\left(\dfrac{1}{m_e}+\dfrac{1}{m_p}\right)-1\\
&=\left(1+\dfrac{m_e}{m_p}\right)-1\\
\Aboxed{\text{Error}&=\dfrac{m_e}{m_p}}
\end{align}$$
> Substituting the values for each mass from above, we get:
$$\begin{align}
\text{Error}&=\dfrac{0.511\text{ MeV}/c^2}{938.27\text{ MeV}/c^2}\\
&=0.000544619352638\\
\Aboxed{\text{Error}&=0.055\%}
\end{align}$$
> I purposely rounded up on error since it's it's how off a value is. With normal rounding rules, it would be $0.054\%$ but I chose the higher of the 2.

---
#### Problem 1.2
Find the binding energy, in $\text{eV}$, of positronium, in which the proton is replaced by a positron, which has the same mass as an electron.
$$\begin{align}
E&=-\dfrac{\mu e^4}{8\epsilon_0^2h^2}\\
&=-\dfrac{ e^4}{8\epsilon_0^2h^2}\left(\dfrac{1}{m_e}+\dfrac{1}{m_e}\right)^{-1}\\
&=-\dfrac{ e^4}{8\epsilon_0^2h^2}\left(\dfrac{2}{m_e}\right)^{-1}\\
&=-\dfrac{ e^4}{8\epsilon_0^2h^2}\dfrac{m_e}{2}\\
&=-\dfrac{1}{2}\dfrac{m_e e^4}{8\epsilon_0^2h^2}\\
&=-\dfrac{1}{2}\left(13.605\text{ eV}\right)\\
\Aboxed{E&=-6.8025\text{ eV}}
\end{align}$$
---
### Problem 2
$N$ non-interacting bosons, each of mass $m$, are placed in an infinite potential well of width $a$.
Wavefunction and energy of particles in an infinite square potential well:
$$\psi_n(x)=\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n\pi}{a}x\right), \ \ \ E_n=\dfrac{\pi^2\hbar^2}{2ma^2}n^2$$
#### Problem 2.1
What is the $N$-particle ground state energy of the system? Your answer should be in terms of the given and fundamental constants. Assume $N$ is an even number.
$$\begin{align}
E_\text{ground}&=NE_1=\dfrac{N\pi^2\hbar^2}{2ma^2}
\end{align}$$
#### Problem 2.2
What would be the ground state energy of the $N$-particle system if the particles were fermions?

> Each energy level can only be occupied by 2 fermions each since they can have equal and opposite spin states.
$$\begin{align}
E_\text{ground}&=\sum_{1}^NE_n\\
&=2\sum_{1}^{N/2}\dfrac{\pi^2\hbar^2}{2ma^2}n^2\\
&=\dfrac{\pi^2\hbar^2}{ma^2}\sum_{1}^{N/2}n^2\\
&=\dfrac{\pi^2\hbar^2}{ma^2}\dfrac{\tfrac{N}{2}(\tfrac{N}{2}+1)(2\tfrac{N}{2}+1)}{6}\\
\Aboxed{E_\text{ground}&=\dfrac{\pi^2\hbar^2}{24ma^2}N(N+2)(N+1)}
\end{align}$$
---
### Problem 3
Show explicitly, using the product basis for two spin ½ particles, that:
$$\begin{align}
P&=\dfrac{1}{2}(1+\sigma_1\cdot\sigma_2)\\
P\ket{M_1}\ket{M_2}&=\ket{M_2}\ket{M_1}
\end{align}$$
where the $M_i$ is the $z$-component of the spin $S_i$.

**Case 1:**
$$\begin{align}
P\ket{\uparrow\uparrow}
&=\dfrac{1}{2}(1+\sigma_1\cdot\sigma_2)\ket{\uparrow\uparrow}\\
&=\dfrac{1}{2}\ket{\uparrow\uparrow}+\dfrac{1}{2}\left(\sigma_1\cdot\sigma_2\ket{\uparrow\uparrow}\right)\\
&=\dfrac{1}{2}\ket{\uparrow\uparrow}+\dfrac{1}{2}\left(+1\cdot\ket{\uparrow\uparrow}\right)\\
&=\dfrac{1}{2}\ket{\uparrow\uparrow}+\dfrac{1}{2}\cdot\ket{\uparrow\uparrow}\\
P\ket{\uparrow\uparrow}&=\ket{\uparrow\uparrow}\\
\Aboxed{P\ket{\uparrow}\ket{\uparrow}&=\ket{\uparrow}\ket{\uparrow}}
\end{align}$$
**Case 2:**
$$\begin{align}
P\ket{\uparrow\downarrow}
&=\dfrac{1}{2}(1+\sigma_1\cdot\sigma_2)\ket{\uparrow\downarrow}\\
&=\dfrac{1}{2}\ket{\uparrow\downarrow}+\dfrac{1}{2}\left(\sigma_1\cdot\sigma_2\ket{\uparrow\downarrow}\right)\\
&=\dfrac{1}{2}\ket{\uparrow\downarrow}+\dfrac{1}{2}\left(2\ket{\downarrow\uparrow}-\ket{\uparrow\downarrow}\right)\\
P\ket{\uparrow\downarrow}&=\ket{\downarrow\uparrow}\\
\Aboxed{P\ket{\uparrow}\ket{\downarrow}&=\ket{\downarrow}\ket{\uparrow}}
\end{align}$$
**Case 3:**
$$\begin{align}
P\ket{\downarrow\uparrow}
&=\dfrac{1}{2}(1+\sigma_1\cdot\sigma_2)\ket{\downarrow\uparrow}\\
&=\dfrac{1}{2}\ket{\downarrow\uparrow}+\dfrac{1}{2}\left(\sigma_1\cdot\sigma_2\ket{\downarrow\uparrow}\right)\\
&=\dfrac{1}{2}\ket{\downarrow\uparrow}+\dfrac{1}{2}\left(2\ket{\uparrow\downarrow}-\ket{\downarrow\uparrow}\right)\\
P\ket{\downarrow\uparrow}&=\ket{\uparrow\downarrow}\\
\Aboxed{P\ket{\downarrow}\ket{\uparrow}&=\ket{\uparrow}\ket{\downarrow}}
\end{align}$$
**Case 4:**
$$\begin{align}
P\ket{\downarrow\downarrow}
&=\dfrac{1}{2}(1+\sigma_1\cdot\sigma_2)\ket{\downarrow\downarrow}\\
&=\dfrac{1}{2}\ket{\downarrow\downarrow}+\dfrac{1}{2}\left(\sigma_1\cdot\sigma_2\ket{\downarrow\downarrow}\right)\\
&=\dfrac{1}{2}\ket{\downarrow\downarrow}+\dfrac{1}{2}\left(+1\cdot\ket{\downarrow\downarrow}\right)\\
&=\dfrac{1}{2}\ket{\downarrow\downarrow}+\dfrac{1}{2}\cdot\ket{\downarrow\downarrow}\\
P\ket{\downarrow\downarrow}&=\ket{\downarrow\downarrow}\\
\Aboxed{P\ket{\downarrow}\ket{\downarrow}&=\ket{\downarrow}\ket{\downarrow}}
\end{align}$$
> We can see that the expression for $P$ is correct and reproduces the same results we'd expect of the operator. The simplifications I made with being able to evaluate $\sigma_1\cdot\sigma_2$ comes from the previous homework, where I $S_1\cdot S_2$ onto these kinds of states, and they are related algebraically by $\sigma_1\cdot\sigma_2=2(S_1+S_2)$, if we ignore the $\hbar$ pieces.

---
### Problem 4
Suppose you had three particles, one in state $\psi_a(x)$, another in state $\psi_b(x)$, and the third in $\psi_c(x)$. Assuming these states are orthonormal, construct three-particle wavefunctions, if the particles are...
#### Problem 4.1
**Distinguishable**
$$\begin{align}
\ket{\psi(x)}&=\ket{\psi_a(x)}\ket{\psi_b(x)}\ket{\psi_c(x)}\\
\Aboxed{\psi(x)&=\psi_a(x)\psi_b(x)\psi_c(x)}
\end{align}$$
> Since they are distinguishable, they are automatically orthonormal since all the particles are independent of each other.

---
#### Problem 4.2
Identical bosons (can you predict the number of contributing terms before you write down the answer?)

> There will be 6 terms, since there are 3 particles, since $6 = 3!$.
> For the sake of brevity, all vectors shown below will be in $x_1,x_2,x_3$ tuples, and so:
$$\begin{align}
\ket{\psi(x)}&=\dfrac{\ket{abc}+\ket{bca}+\ket{cab}+\ket{bac}+\ket{acb}+\ket{cba}}{\sqrt6}
\end{align}$$
Where $\ket{ijk}=\psi_i(x_1)\psi_j(x_2)\psi_k(x_3)$.

---
#### Problem 4.3
Identical fermions

> This looks almost exactly like the bosons, but if the number of swaps is odd, then it has an extra negative sign.
$$\begin{align}
\ket{\psi(x)}&=\dfrac{\ket{abc}-\ket{bac}-\ket{acb}+\ket{bca}+\ket{cab}-\ket{cba}}{\sqrt6}
\end{align}$$
---
#### Problem 4.4
Show your answer to 4.3 can be written as a determinant. This is known as a Slater determinant.
$$\begin{align}
\ket{\psi(x)}
&=\dfrac{\ket{abc}-\ket{bac}-\ket{acb}+\ket{bca}+\ket{cab}-\ket{cba}}{\sqrt6}\\
&=\dfrac{\ket{abc}-\ket{acb}-(\ket{bac}-\ket{bca})+\ket{cab}-\ket{cba}}{\sqrt6}\\
&=\dfrac{\ket{a}(\ket{bc}-\ket{cb})-\ket{b}(\ket{ac}-\ket{ca})+\ket{c}(\ket{ab}-\ket{ba})}{\sqrt6}\\
&=\dfrac{\ket{a}\left|\begin{array}{cc}\ket{b}&\ket{c}\\\ket{b}&\ket{c}\end{array}\right|-\ket{b}\left|\begin{array}{cc}\ket{a}&\ket{c}\\\ket{a}&\ket{c}\end{array}\right|+\ket{c}\left|\begin{array}{cc}\ket{a}&\ket{b}\\\ket{a}&\ket{b}\end{array}\right|}{\sqrt6}\\
&=\dfrac{1}{\sqrt6}\left|\begin{array}{ccc}\ket{a}&\ket{b}&\ket{c}\\\ket{a}&\ket{b}&\ket{c}\\\ket{a}&\ket{b}&\ket{c}\end{array}\right|\\
\ket{\psi(x)}&=\dfrac{1}{\sqrt6}\left|\begin{array}{ccc}\psi_a(x_1)&\psi_b(x_1)&\psi_c(x_1)\\\psi_a(x_2)&\psi_b(x_2)&\psi_c(x_2)\\\psi_a(x_3)&\psi_b(x_3)&\psi_c(x_3)\end{array}\right|\\
\end{align}$$
 >Looking it up online, this is equal to the Slater determinant, and so hence concludes the proof.

---
#### Problem 4.5
Assuming $a$, $b$ and $c$ refer to electron spin states, show using 4.4 that it is impossible to construct a completely antisymmetric spin wavefunction for three electrons. Explain physically why this is true.

> When swapping rows and columns of the determinant, you introduce a negative sign.
> Swapping columns is swapping electron states without changing position.
> Swapping rows is swapping spatial position of those electrons without changing states.
> Therefore, since the wavefunction must be antisymmetric under spatial swaps, the spin wave function has to be symmetric in order to maintain that the total wavefunction is antisymmetric.

Effectively $(+)\times(-)=(-)$, where $-$ is anti-symmetry and $+$ is symmetry.

---
