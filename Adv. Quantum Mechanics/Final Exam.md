**Name:** Stanley Goodwin
**Date:** 5/04/2025

---
### Question 1
Use the WKB method to calculate the transmission coefficient for the potential barrier:
$$\begin{align}
V(x)=\begin{cases}0,&x<0\\V_0-ax,&x>0\end{cases}
\end{align}$$
**Notes / Assumptions**:
Transmission only occurs when $a> 0$.               Otherwise there would be no tunneling.
The energy of the particle must follow $E<V_0$. Otherwise there would be no tunneling.

From there, we can find the different regions of the wavefunction:
$$\begin{align}
\text{Classical Regions:}&& x<0,\ x>\tfrac{V_0-E}{a}\\
\text{Non-Classical Regions:} && 0<x<\tfrac{V_0-E}{a}\\
\end{align}$$
We want to look at the tunneling behavior in the non-classical region.
$$\begin{align}
E\psi(x)&=-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}\psi(x)+V(x)\psi(x)\\
\dfrac{\partial^2\psi}{\partial x^2}&=-i^2\dfrac{2m[V(x)-E]}{\hbar^2}\psi\\
\dfrac{\partial^2\psi}{\partial x^2}&=-\dfrac{(ip(x))^2}{\hbar^2}\psi\\
\Aboxed{\dfrac{\partial^2\psi}{\partial x^2}&=-\dfrac{p(x)^2}{\hbar^2}\psi, \ \ \ \ p(x)=-i\sqrt{2m[V(x)-E]}}
\end{align}$$
With some arithmetic, we can find a form for the "momentum."
#### Tunneling Region ($0<x<\tfrac{V_0-E}{a}$)
$$\begin{align}
\Aboxed{p(x)=-i\sqrt{2m[V_0-ax-E]}}
\end{align}$$
I actually don't have to solve the wavefunction directly, just finding the contribution in the exponent for $0<x<\dfrac{V_0-E}{a}$.
$$\begin{align}
\int_0^{x_c} |p(x')| dx'&=-i\sqrt{2m}\int_0^\tfrac{V_0-E}{a} \sqrt{V_0-ax'-E} dx'\\
&=\sqrt{2ma}\int_0^\tfrac{V_0-E}{a} \sqrt{\dfrac{V_0-E}{a}-x'} dx'\\
&=\sqrt{2ma}\cdot\dfrac{2}{3}\left(\tfrac{V_0-E}{a}\right)^{3/2}\\
\Aboxed{\int_0^{x_c} p(x') dx'&=\dfrac{2\sqrt{2m}}{3a}\left(V_0-E\right)^{3/2}}
\end{align}$$
**For strong barriers:**
$$\begin{align}
T&\approx\exp\left(-2\dfrac{1}{\hbar}\int_0^{x_c} p(x') dx'\right)\\
\Aboxed{T&\approx\exp\left(-\dfrac{4\sqrt{2m}}{3a\hbar}\left(V_0-E\right)^{3/2}\right)}
\end{align}$$
---
### Question 2
Consider a simple harmonic oscillator in its ground state:
$$\begin{align}
\psi_0(x; \omega)&=\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}\exp\left(-\dfrac{m\omega}{2\hbar}x^2\right)
\end{align}$$
The frequency of the oscillator is slowly varied from $\omega=W$ to $\omega=2W$.

---
#### Question 2.1
Find the geometric phase (Berry phase) accumulated by the ground state at the end of this process. Show at least a couple of steps of your work.

For starters, I know that the Berry phase is 0 under parameter transforms who only have 1 time-dependent parameter, and so I just need to prove it.

The definition of Berry Phase (for $\omega$) for the $n=0$ wavefunction given:
$$\begin{align}
\gamma_0&=i\int_W^{2W}\braket{\psi_0|\partial_\omega\psi_0}\ d\omega
\end{align}$$
For the sake of brevity, I will calculate this component-by-component.
$$\begin{align}
\dfrac{\partial}{\partial\omega}\psi_0
&=\dfrac{\partial}{\partial\omega}\left[\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}\exp\left(-\dfrac{m\omega}{2\hbar}x^2\right)\right]\\
&=\left[\dfrac{1}{4}\dfrac{m}{\pi\hbar}\left(\dfrac{m\omega}{\pi\hbar}\right)^{-3/4}\exp\left(-\dfrac{m\omega}{2\hbar}x^2\right)\right]+\left[-\dfrac{m}{2\hbar}x^2\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}\exp\left(-\dfrac{m\omega}{2\hbar}x^2\right)\right]\\
&=\dfrac{1}{4}\dfrac{m}{\pi\hbar}\left(\dfrac{m\omega}{\pi\hbar}\right)^{-1}\left[\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}\exp\left(-\dfrac{m\omega}{2\hbar}x^2\right)\right]-\dfrac{m}{2\hbar}x^2\left[\left(\dfrac{m\omega}{\pi\hbar}\right)^{1/4}\exp\left(-\dfrac{m\omega}{2\hbar}x^2\right)\right]\\
\Aboxed{\dfrac{\partial}{\partial\omega}\psi_0&=\dfrac{1}{4\omega}\psi_0-\dfrac{mx^2}{2\hbar}\psi_0}
\end{align}$$
We can then find the inner product as:
$$\begin{align}
\braket{\psi_0|\partial_\omega\psi_0}
&=\psi_0\left(\dfrac{1}{4\omega}\psi_0-\dfrac{mx^2}{2\hbar}\psi_0\right)\\
&=\dfrac{1}{4\omega}\psi_0^2-\dfrac{mx^2}{2\hbar}\psi_0^2\\
\end{align}$$
The integral of the first part is:
$$\begin{align}
\gamma_0^1&=i\int_W^{2W}\dfrac{1}{4\omega}\psi_0^2\ d\omega\\
&=i\int_W^{2W}\dfrac{1}{4\omega}\sqrt{\dfrac{m\omega}{\pi\hbar}}\exp\left(-\dfrac{mx^2}{\hbar}\omega\right)\ d\omega\\
&=\dfrac{i}{4}\sqrt{\dfrac{m}{\pi\hbar}}\int_W^{2W}\dfrac{1}{\sqrt{\omega}}\exp\left(-\dfrac{mx^2}{\hbar}\omega\right)\ d\omega\\
\end{align}$$
Make the substitution $u=\dfrac{mx^2}{\hbar}\omega \implies d\omega=\dfrac{\hbar}{mx^2}du$:
$$\begin{align}
\gamma_0^1&=\dfrac{i}{4}\sqrt{\dfrac{m}{\pi\hbar}}\int_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}\left(\dfrac{\hbar}{mx^2}u\right)^{-1/2}e^{-u}\ \dfrac{\hbar}{mx^2}du\\
&=\dfrac{i}{4}\sqrt{\dfrac{m}{\pi\hbar}\dfrac{mx^2}{\hbar}}\dfrac{\hbar}{mx^2}\int_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}u^{-1/2}e^{-u}\ du\\
&=\dfrac{i}{4x}\sqrt{\dfrac{1}{\pi}}\int_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}u^{-1/2}e^{-u}\ du\\
&=-\dfrac{i}{4x}\sqrt{\dfrac{1}{\pi}}\cdot\left.\sqrt{\pi}(1-\text{erf}(\sqrt{u}))\right|_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}\\
&=-\dfrac{i}{4x}\left[1-\text{erf}\left(\sqrt{2W\tfrac{mx^2}{\hbar}}\right)-1+\text{erf}\left(\sqrt{W\tfrac{mx^2}{\hbar}}\right)\right]\\
\Aboxed{\gamma_0^1&=-\dfrac{i}{4x}\left[\text{erf}\left(\sqrt{W\tfrac{mx^2}{\hbar}}\right)-\text{erf}\left(\sqrt{2W\tfrac{mx^2}{\hbar}}\right)\right]}
\end{align}$$
The integral of the second part is:
$$\begin{align}
\gamma_0^2&=i\int_W^{2W}-\dfrac{mx^2}{2\hbar}\psi_0^2\ d\omega\\
&=-i\dfrac{mx^2}{2\hbar}\int_W^{2W}\sqrt{\dfrac{m\omega}{\pi\hbar}}\exp\left(-\dfrac{mx^2}{\hbar}\omega\right)\ d\omega\\
&=-i\dfrac{mx^2}{2\hbar}\sqrt{\dfrac{m}{\pi\hbar}}\int_W^{2W}\sqrt{\omega}\exp\left(-\dfrac{mx^2}{\hbar}\omega\right)\ d\omega\\
\end{align}$$
Make the substitution $u=\dfrac{mx^2}{\hbar}\omega \implies d\omega=\dfrac{\hbar}{mx^2}du$:
$$\begin{align}
\gamma_0^2&=-i\dfrac{mx^2}{2\hbar}\sqrt{\dfrac{m}{\pi\hbar}}\int_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}\sqrt{\dfrac{\hbar}{mx^2}u}e^{-u}\ \dfrac{\hbar}{mx^2}du\\
&=-i\dfrac{1}{2 x}\sqrt{\dfrac{1}{\pi}}\int_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}\sqrt{u}e^{-u}\ du\\
&=-i\dfrac{1}{2 x}\sqrt{\dfrac{1}{\pi}}\left[-\dfrac{\sqrt{\pi}}{2}\left(1-\text{erf}\left(\sqrt{x}\right)-\sqrt{x}e^{-x}\right)\right|_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}\\
&=i\dfrac{1}{2 x}\sqrt{\dfrac{1}{\pi}}\left[\dfrac{\sqrt{\pi}}{2}\left(1-\text{erf}\left(\sqrt{x}\right)\right)+\sqrt{x}e^{-x}\right|_{W\tfrac{mx^2}{\hbar}}^{2W\tfrac{mx^2}{\hbar}}\\
\gamma_0^2&=i\dfrac{1}{4 x}\left(\text{erf}\left(\sqrt{W\tfrac{mx^2}{\hbar}}\right)-\text{erf}\left(\sqrt{2W\tfrac{mx^2}{\hbar}}\right)\right)\\
&+i\dfrac{1}{2 x}\sqrt{W\tfrac{mx^2}{\pi\hbar}}\left[\sqrt{2}e^{-2W\tfrac{mx^2}{\hbar}}-e^{-W\tfrac{mx^2}{\hbar}}\right]\\
\end{align}$$
The sum of these two factors will lead to our geometric phase:
$$\begin{align}
\gamma_0&=\gamma_0^1+\gamma_0^2\\
&=-\dfrac{i}{4x}\left[\text{erf}\left(\sqrt{W\tfrac{mx^2}{\hbar}}\right)-\text{erf}\left(\sqrt{2W\tfrac{mx^2}{\hbar}}\right)\right]\\
&+i\dfrac{1}{4 x}\left(\text{erf}\left(\sqrt{W\tfrac{mx^2}{\hbar}}\right)-\text{erf}\left(\sqrt{2W\tfrac{mx^2}{\hbar}}\right)\right)\\
&+i\dfrac{1}{2 x}\sqrt{W\tfrac{mx^2}{\pi\hbar}}\left[\sqrt{2}e^{-2W\tfrac{mx^2}{\hbar}}-e^{-W\tfrac{mx^2}{\hbar}}\right]\\
&=i\dfrac{1}{2 x}\sqrt{W\tfrac{mx^2}{\pi\hbar}}\left[\sqrt{2}e^{-2W\tfrac{mx^2}{\hbar}}-e^{-W\tfrac{mx^2}{\hbar}}\right]\\
\Aboxed{\gamma_0&=i\sqrt{W\tfrac{m}{4\pi\hbar}}\left[\sqrt{2}e^{-2W\tfrac{mx^2}{\hbar}}-e^{-W\tfrac{mx^2}{\hbar}}\right]}
\end{align}$$
**Note:** Had I caught this earlier, this would have made it easier. 
Since Berry phase must be a real number, then we know that:
$$\begin{align}
\dfrac{1}{2 x}\sqrt{W\tfrac{mx^2}{\pi\hbar}}\left[\sqrt{2}e^{-2W\tfrac{mx^2}{\hbar}}-e^{-W\tfrac{mx^2}{\hbar}}\right]\in i\mathbb{R}
\end{align}$$
However, from inspection, none of these parts will ever lead to an imaginary number.
Therefore:
$$\begin{align}
\Aboxed{\gamma_0&=0}
\end{align}$$
---
#### Question 2.2
If the oscillator frequency varies with time as $\omega(t)=Wt+W$, find the dynamical phase accumulated by the state at the end of this process.

Since I am unsure of the bounds of this, I'll assume it relates to the previous question.
$$\begin{align}
W&=Wt_1+W &&\implies& t_1=0\\
2W&=Wt_2+W &&\implies& t_2=0\\
\end{align}$$
The definition of dynamical phase is:
$$\begin{align}
\theta_n(t)&=-\dfrac{1}{\hbar}\int_{t_1}^{t_2}E_n(t)\ dt
\end{align}$$
A) We know the bounds, and B) we know energy is $E_0=\dfrac{1}{2}\hbar\omega$, and so:
$$\begin{align}
\theta_0(t)&=-\dfrac{1}{\hbar}\int_{0}^{1}\dfrac{1}{2}\hbar\omega(t)\ dt\\
&=-\dfrac{1}{2}\dfrac{\hbar W}{\hbar}\int_{0}^{1}t+1\ dt\\
&=-\dfrac{1}{2}W\left[\dfrac{t^2}{2}+t\right|_{0}^{1}\\
&=-\dfrac{1}{2}W\left[\dfrac{1^2}{2}+1-0-0\right]\\
&=-\dfrac{1}{2}W\left[\dfrac{3}{2}\right]\\
\Aboxed{\theta_0(t)&=-\dfrac{3}{4}W}
\end{align}$$
---
### Question 3
Use the Born Approximation to determine the total cross-section for scattering of a particle of mass $m$ from the potential:
$$\begin{align}
V(r)&=V_0e^{-r/r_0}
\end{align}$$
where $V_0$ and $r_0$ are real and positive constants.

Using the equation from Lecture 35 on 4/16/2025 has spherically-symmetric potentials.
$$\begin{align}
f(\theta)&=-\dfrac{2m}{\hbar^2\kappa}\int rV(r)\sin(\kappa r)\ dr\\
\kappa&=2k\sin(\theta/2)=2\dfrac{\sqrt{2mE}}{\hbar}\sin(\theta/2)
\end{align}$$
So for our system:
$$\begin{align}
f(\theta)&=-\dfrac{2mV_0}{\hbar^2\kappa}\int_0^\infty re^{-r/r_0}\sin(\kappa r)\ dr\\
&=-\dfrac{2mV_0r_0^2}{\hbar^2\kappa}\int_0^\infty ue^{-u}\sin(\kappa r_0\cdot u)\ du\\
\end{align}$$
Using Wolfram Alpha, we can evaluate that integral as:
$$\begin{align}
f(\theta)&=-\dfrac{2mV_0r_0^2}{\hbar^2\kappa}\int_0^\infty ue^{-u}\sin(\kappa r_0\cdot u)\ du\\
&=-\dfrac{2mV_0r_0^2}{\hbar^2\kappa}\dfrac{2\kappa r_0}{(1+(\kappa r_0)^2)^2}\\
\Aboxed{f(\theta)&=-\dfrac{4mV_0r_0^3}{\hbar^2}\dfrac{1}{(1+\kappa^2 r_0^2)^2}}
\end{align}$$
The differential cross-section is just the modulus squared, and so:
$$\begin{align}
D(\theta)&=
|f(\theta)|^2\\
&=\left(-\dfrac{4mV_0r_0^3}{\hbar^2}\dfrac{1}{\left(1+\kappa^2r_0^2\right)^2}\right)^2\\
&=\left(\dfrac{4mV_0r_0^3}{\hbar^2}\right)^2\left(\dfrac{1}{\left(1+4k^2r_0^2\sin^2(\theta/2)\right)^2}\right)^2\\
\Aboxed{D(\theta)&=\left(\dfrac{4mV_0r_0^3}{\hbar^2}\right)^2\left(1+4k^2r_0^2\sin^2(\theta/2)\right)^{-4}}
\end{align}$$
The total cross-section is just integrating over the angular components:
$$\begin{align}
\sigma&=\int_{0}^{2\pi}\int_{0}^{\pi}D(\theta)\sin\theta\ d\theta\ d\phi\\
&=2\pi\cdot\left(\dfrac{4mV_0r_0^3}{\hbar^2}\right)^2\int_{0}^{\pi}\dfrac{\sin\theta}{\left(1+4k^2r_0^2\sin^2(\theta/2)\right)^{4}}\ d\theta\\
&=\dfrac{32\pi m^2V_0^2r_0^6}{\hbar^4}\int_{0}^{\pi}\dfrac{\sin\theta}{\left(1+4k^2r_0^2\sin^2(\theta/2)\right)^{4}}\ d\theta\\
&=\dfrac{32\pi m^2V_0^2r_0^6}{\hbar^4}\dfrac{16}{3(4k^2r_0^2)}\left[\dfrac{1}{\left(4k^2r_0^2\cos(\theta)-4k^2r_0^2-2\right)^3}\right|_0^\pi\\
&=\dfrac{128\pi m^2V_0^2r_0^4}{3\hbar^4k^2}\left[\dfrac{1}{\left(4k^2r_0^2\cos(\pi)-4k^2r_0^2-2\right)^3}-\dfrac{1}{\left(4k^2r_0^2\cos(0)-4k^2r_0^2-2\right)^3}\right]\\
&=\dfrac{128\pi m^2V_0^2r_0^4}{3\hbar^4k^2}\left[\dfrac{1}{\left(-8k^2r_0^2-2\right)^3}-\dfrac{1}{\left(-2\right)^3}\right]\\
&=\dfrac{128\pi m^2V_0^2r_0^4}{3\hbar^4k^2}\left[\dfrac{1}{8}-\dfrac{1}{8\left(4k^2r_0^2+1\right)^3}\right]\\
\Aboxed{\sigma&=\dfrac{16\pi m^2V_0^2r_0^4}{3\hbar^4k^2}\left[1-\dfrac{1}{\left(1+4k^2r_0^2\right)^3}\right]}
\end{align}$$
---
### Question 4
In a scattering experiment, the potential is spherically symmetric and the particle is scattered such that only $s$ and $p$ waves need to be considered.
#### Question 4.1
Show that the differential cross section can be written as:
$$\begin{align}
D(\theta)&=A+B\cos(\theta)+C\cos^2(\theta)
\end{align}$$
With partial wave analysis, we found that:
$$\begin{align}
f(\theta)&=\sum_{l=0}^\infty(2l+1)a_lP_l(\cos\theta)\\
a_l&=\dfrac{e^{i\delta_l}}{k}\sin(\delta_l)
\end{align}$$
I couldn't find what $\delta_l$ was, so I'll leave it in this form for now.

We're only looking at the $l=0$ and $l=1$ cases, and so:
$$\begin{align}
f(\theta)&=\dfrac{e^{i\delta_0}}{k}\sin(\delta_0)P_0(\cos\theta)+
3\dfrac{e^{i\delta_1}}{k}\sin(\delta_1)P_1(\cos\theta)\\
&=\left(\dfrac{e^{i\delta_0}}{k}\sin(\delta_0)\right)+
\left(3\dfrac{e^{i\delta_1}}{k}\sin(\delta_1)\right)\cos\theta\\
\Aboxed{f(\theta)&=a+b\cos\theta}
\end{align}$$
Then the differential cross-section is:
$$\begin{align}
D(\theta)&=|a+b\cos\theta|^2\\
&=|a|^2+(a^*b+b^*a)\cos\theta+|b|^2\cos^2\theta\\
\Aboxed{D(\theta)&=|a|^2+[a^*b+(a^*b)^*]\cos\theta+|b|^2\cos^2\theta}
\end{align}$$
Combined together, we see that:
$$\begin{align}
D(\theta)&=A+B\cos(\theta)+C\cos^2(\theta)\\
A&=|a|^2\\
B&=2\ \text{Re}(a^*b)\\
C&=|b|^2
\end{align}$$
---
#### Question 4.2
What are the values of $A$, $B$ and $C$ in terms of phase shifts?
$$\begin{align}
a&=\dfrac{e^{i\delta_0}}{k}\sin(\delta_0)\\
b&=3\dfrac{e^{i\delta_1}}{k}\sin(\delta_1)\\
\end{align}$$
We can then find:
$$\begin{align}
a^*b+ab^*&=3\dfrac{e^{-i\delta_0}}{k}\sin(\delta_0)\dfrac{e^{i\delta_1}}{k}\sin(\delta_1)+3\dfrac{e^{i\delta_0}}{k}\sin(\delta_0)\dfrac{e^{-i\delta_1}}{k}\sin(\delta_1)\\
&=\dfrac{3}{k}\left[e^{-i\delta_0}e^{i\delta_1}+e^{i\delta_0}e^{-i\delta_1}\right]\sin(\delta_0)\sin(\delta_1)\\
&=\dfrac{3\cdot2}{k}\dfrac{e^{-i(\delta_0-\delta_1)}e^{i(\delta_0-\delta_1)}}{2}\sin(\delta_0)\sin(\delta_1)\\
a^*b+ab^*&=\dfrac{6}{k}\sin(\delta_0)\sin(\delta_1)\cos(\delta_0-\delta_1)\\\\
|a|^2&=\left|\dfrac{e^{i\delta_0}}{k}\sin(\delta_0)\right|^2\\
|a|^2&=\dfrac{1}{k^2}\sin^2(\delta_0)\\\\
|b|^2&=\left|3\dfrac{e^{i\delta_1}}{k}\sin(\delta_1)\right|^2\\
|b|^2&=\dfrac{9}{k^2}\sin^2(\delta_1)\\
\end{align}$$
Therefore, we can see that:
$$\begin{align}
D(\theta)&=A+B\cos(\theta)+C\cos^2(\theta)\\
A&=\dfrac{1}{k^2}\sin^2(\delta_0)\\
B&=\dfrac{6}{k}\sin(\delta_0)\sin(\delta_1)\cos(\delta_0-\delta_1)\\
C&=\dfrac{9}{k^2}\sin^2(\delta_1)\\
\end{align}$$
---
#### Question 4.3
What is the value of the total cross section 𝜎 in terms of $A$, $B$ and $C$?
$$\begin{align}
\sigma&=\int_{0}^{2\pi}\int_{0}^{\pi}D(\theta)\sin\theta\ d\theta\ d\phi\\
&=2\pi\int_{0}^{\pi}\left[A+B\cos(\theta)+C\cos^2(\theta)\right]\sin\theta\ d\theta\\
&=2\pi\left[A\int_{0}^{\pi}\sin\theta\ d\theta+B\int_{0}^{\pi}\sin\theta\cos(\theta)\ d\theta+C\int_{0}^{\pi}\cos^2(\theta)\sin\theta\ d\theta\right]\\
&=2\pi\left[A\cdot2+B\cdot0+C\cdot\dfrac{2}{3}\right]\\
&=2\pi\left[2A+\dfrac{2}{3}C\right]\\
\Aboxed{\sigma&=4\pi A+\dfrac{4}{3}\pi C}
\end{align}$$
---
### Question 5
Obtain the "hyperfine" splitting (between the singlet and triplet spin states, which are otherwise degenerate) in the ground state of the hydrogen atom to first order in the perturbation:
$$\begin{align}
H'&=A\delta^3
(\vec{r})\ S_p\cdot S_e\end{align}$$
where $A$ is a real and positive constant, and $S_p$ and $S_e$ are the proton and electron spins.
Assume the atomic state is $\psi=\psi_{100}\chi$ where $\psi_{100}=\tfrac{1}{\sqrt{\pi a_0^3}}e^{-r/a_0}$.

We can calculate the first-order energy shift as:
$$\begin{align}
E^1_0&=\bra{\psi^0}H'\ket{\psi^0}\\
&=\bra{\psi^0_{100}\chi}A\delta^3
(\vec{r})\ S_p\cdot S_e\ket{\psi^0_{100}\chi}\\
&=A\braket{\psi^0_{100}|\psi^0_{100}}\cdot\bra{\chi}\delta^3
(\vec{r})\ (S_p\cdot S_e)\ket{\chi}\\
\end{align}$$
Since the delta makes $r=0$ the evaluation point:
$$\begin{align}
E^1_0&=A\braket{\psi^0_{100}|\psi^0_{100}}\cdot\bra{\chi}\delta^3
(\vec{r})\ (S_p\cdot S_e)\ket{\chi}\\
&=A\braket{\psi^0_{100}(r=0)|\psi^0_{100}(r=0)}\cdot\bra{\chi}(S_p\cdot S_e)\ket{\chi}\\
\Aboxed{E^1_0&=\dfrac{A}{\pi a_0^3}\cdot\bra{\chi}(S_p\cdot S_e)\ket{\chi}}
\end{align}$$
#### Spin Things
Let $S=S_p+S_e$. The following relationships will be used:
$$\begin{align}
S^2&=(S_p+S_e)^2\\
S^2&=S_p^2+S_e^2+2\braket{S_p\cdot S_e}\\
\braket{S_p\cdot S_e}&=\dfrac{1}{2}\left(S^2-S_p^2-S_e^2\right)\\\\

S_p^2&=s(s+1)\hbar^2=\dfrac{1}{2}\left(1+\dfrac{1}{2}\right)\hbar^2=\dfrac{3}{4}\hbar^2\\
S_e^2&=s(s+1)\hbar^2=\dfrac{1}{2}\left(1+\dfrac{1}{2}\right)\hbar^2=\dfrac{3}{4}\hbar^2
\end{align}$$
For the $S=0 \implies S^2=0(0+1)\hbar^2$ state:
$$\begin{align}
\braket{S_p\cdot S_e}&=\dfrac{1}{2}\left(S^2-S_p^2-S_e^2\right)\\
&=\dfrac{1}{2}\left(0-\dfrac{3}{4}\hbar^2-\dfrac{3}{4}\hbar^2\right)\\
\Aboxed{\braket{S_p\cdot S_e}_{S=0}&=-\dfrac{3}{4}\hbar^2}
\end{align}$$
For the $S=1\hbar \implies S^2=1(1+1)\hbar^2$ state:
$$\begin{align}
\braket{S_p\cdot S_e}&=\dfrac{1}{2}\left(S^2-S_p^2-S_e^2\right)\\
&=\dfrac{1}{2}\left(2\hbar^2-\dfrac{3}{4}\hbar^2-\dfrac{3}{4}\hbar^2\right)\\
\Aboxed{\braket{S_p\cdot S_e}_{S=1}&=\dfrac{1}{4}\hbar^2}
\end{align}$$
#### Back to Energies
We found that:
$$\begin{align}
E^1_0&=\dfrac{A}{\pi a_0^3}\cdot\bra{\chi}(S_p\cdot S_e)\ket{\chi}
\end{align}$$
For the $S=0$ (singlet) state:
$$\begin{align}
E^1_\text{singlet}&=\dfrac{A}{\pi a_0^3}\cdot\bra{\chi}(S_p\cdot S_e)\ket{\chi}\\
&=\dfrac{A}{\pi a_0^3}\braket{S_p\cdot S_e}_{S=0}\\
&=-\dfrac{3}{4}\dfrac{A}{\pi a_0^3}\hbar^2\\
\Aboxed{E^1_\text{singlet}&=-\dfrac{3A\hbar^2}{4\pi a_0^3}}
\end{align}$$
For the $S=1$ (triplet) state:
$$\begin{align}
E^1_\text{triplet}&=\dfrac{A}{\pi a_0^3}\cdot\bra{\chi}(S_p\cdot S_e)\ket{\chi}\\
&=\dfrac{A}{\pi a_0^3}\braket{S_p\cdot S_e}_{S=1}\\
&=+\dfrac{1}{4}\dfrac{A}{\pi a_0^3}\hbar^2\\
\Aboxed{E^1_\text{triplet}&=\dfrac{A\hbar^2}{4\pi a_0^3}}
\end{align}$$
For the energy different (hyperfine split):
$$\begin{align}
|\Delta E|&=|E^1_\text{triplet}-E^1_\text{singlet}|\\
&=\left|\dfrac{A\hbar^2}{4\pi a_0^3}--\dfrac{3A\hbar^2}{4\pi a_0^3}\right|\\
&=\dfrac{A\hbar^2}{\pi a_0^3}\left|\dfrac{1}{4}+\dfrac{3}{4}\right|\\
\Aboxed{|\Delta E|&=\dfrac{A\hbar^2}{\pi a_0^3}}
\end{align}$$
