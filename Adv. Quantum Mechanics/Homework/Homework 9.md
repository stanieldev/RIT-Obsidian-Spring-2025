**Name:** Stanley Goodwin
**Date:** 4/18/2025

---
### Question 1
Consider the case of low energy scattering $(l = 0)$ from a spherical delta-function shell:
$$\begin{align}
V(r)&=\alpha\delta(r-a)
\end{align}$$
where $\alpha$ and $a$ are constants.

---
#### Question 1.1
Find the scattering amplitude $f(\theta)$.

**Radial Schrodinger Equation ($l=0$)**
$$\begin{align}
-\dfrac{\hbar^2}{2m}\dfrac{d^2}{dr^2}u(r)+V(r)u(r)&=\dfrac{\hbar^2k^2}{2m}u(r)\\
\left[\dfrac{d^2}{dr^2}+k^2-\dfrac{2m\alpha}{\hbar^2}\delta(r-a)\right]u(r)&=0\\
\end{align}$$
Where $k=\dfrac{\sqrt{2mE}}{\hbar}$.

In the domain where $r\neq a$:
$$\begin{align}
&&\dfrac{d^2}{dr^2}u(r)&=-k^2u(r), & k&=\dfrac{\sqrt{2mE}}{\hbar}\\
\implies&& \Aboxed{u(r<a)&=Ae^{ikr}+Be^{-ikr}}\\\\
&&\dfrac{d^2}{dr^2}u(r)&=-k^2u(r), & k&=\dfrac{\sqrt{2mE}}{\hbar}\\
\implies&& \Aboxed{u(r>a)&=A'e^{ikr}+B'e^{-ikr}}
\end{align}$$
Since $R(r)=\dfrac{u(r)}{r}$, only the sine term will not blow up at $r=0$, and so:
$$\begin{align}
\Aboxed{u(r<a)&=A\sin(kr)}\\
\Aboxed{u(r>a)&=A'\sin(kr+\delta)}
\end{align}$$
Since the system must be continuous at the point $r=a$:
$$\begin{align}
&&\lim_{r\rightarrow a^-}u(r)&=\lim_{r\rightarrow a^+}u(r)\\
\implies&& A\sin(ka)&=A'\sin(ka+\delta)\\
\implies&& \Aboxed{A&=A'\dfrac{\sin(ka+\delta)}{\sin(ka)}}
\end{align}$$
The derivative is discontinuous at $r=a$:
$$\begin{align}
&&\lim_{r\rightarrow a^+}u'(r)-\lim_{r\rightarrow a^-}u'(r)&=\dfrac{2m\alpha}{\hbar^2}\lim_{r\rightarrow a}u(r)\\
\implies&&kA'\cos(ka+\delta)-kA\cos(ka)&=\dfrac{2m\alpha}{\hbar^2}A\sin(ka)\\
\implies&&A'\cos(ka+\delta)-A\cos(ka)&=\dfrac{2m\alpha}{k\hbar^2}A\sin(ka)\\
\implies&&\Aboxed{\dfrac{2m\alpha}{k\hbar^2}\sin(ka)+\cos(ka)&=\dfrac{A'}{A}\cos(ka+\delta)}
\end{align}$$
Combining the two above, we find that:
$$\begin{align}
\dfrac{A'}{A}&=\dfrac{\sin(ka)}{\sin(ka+\delta)}\\
\dfrac{2m\alpha}{k\hbar^2}\sin(ka)+\cos(ka)&=\dfrac{A'}{A}\cos(ka+\delta)\\
\dfrac{2m\alpha}{k\hbar^2}\sin(ka)+\cos(ka)&=\dfrac{\sin(ka)}{\sin(ka+\delta)}\cos(ka+\delta)\\
\dfrac{2m\alpha}{k\hbar^2}+\cot(ka)&=\cot(ka+\delta)\\
\end{align}$$
In the limiting case that $ka\ll 1$, $\cot(x+\delta x)\approx\dfrac{1}{x+\delta x}$:
$$\begin{align}
\dfrac{2m\alpha}{k\hbar^2}+\cot(ka)&=\cot(ka+\delta)\\
\dfrac{2m\alpha a}{k\hbar^2 a}+\dfrac{1}{ka}&\approx\dfrac{1}{ka+\delta}\\
\dfrac{\beta+1}{ka}&\approx\dfrac{1}{ka+\delta}\\
ka+\delta&\approx\dfrac{ka}{\beta+1}\\
\dfrac{\beta+1}{ka}&\approx\dfrac{1}{ka+\delta}\\
\delta&\approx\dfrac{ka}{\beta+1}-ka\\
&\approx ka\dfrac{1-\beta-1}{\beta+1}\\
\Aboxed{\delta&\approx-k\dfrac{\beta a}{\beta+1}},\ \ \beta=\dfrac{2m\alpha a}{\hbar^2}
\end{align}$$
From there we can use the equation we used in class (low energy limit for $l=0$): 
If we assume that $\delta\ll 1$:
$$\begin{align}
f(\theta)&\approx\dfrac{1}{k}e^{i\delta}\sin\delta\\
&\approx\dfrac{1}{k}(1)\delta\\
&\approx-\dfrac{1}{k}k\dfrac{\beta a}{\beta+1}\\
\Aboxed{f(\theta)&\approx-\dfrac{\beta a}{\beta+1}}
\end{align}$$
---
#### Question 1.2
Find the differential cross-section $D(\theta)$.
$$\begin{align}
D(\theta)&=|f(\theta)|^2\\
&=\left|-\dfrac{\beta a}{\beta+1}\right|^2\\
\Aboxed{D(\theta)&=\left(\dfrac{\beta a}{\beta+1}\right)^2}
\end{align}$$
---
#### Question 1.3
Find the total cross-section $\sigma$.
Express your answers in terms of the dimensionless quantity $\beta=\tfrac{2ma\alpha}{\hbar^2}$.
$$\begin{align}
\sigma&=\int D(\theta)\ d\Omega\\
&=\int\left(\dfrac{\beta a}{\beta+1}\right)^2\ d\Omega\\
&=\left(\dfrac{\beta a}{\beta+1}\right)^2\int d\Omega\\
\Aboxed{\sigma&=4\pi\left(\dfrac{\beta a}{\beta+1}\right)^2}
\end{align}$$
---
### Question 2
A particle of mass $m$ and energy $E$ is incident from the left on the potential:
$$\begin{align}
V(x)&=\begin{cases}
0,&x<-a\\
-V_0,&-a\le x\le 0\\
\infty,& x>0
\end{cases}
\end{align}$$
---
#### Question 2.1
If the incoming wave is $Ae^{ikx}$ (with $k=\tfrac{\sqrt{2mE}}{\hbar}$), find the reflected wave.

**Region 1** ($x<-a, V=0$):
$$\begin{align}
-\dfrac{\hbar^2}{2m}\dfrac{\partial^2\psi_1}{\partial x^2}&=E\psi_1 &\implies&& \psi_1&=Ae^{ikx}+Be^{-ikx},& k&=\dfrac{\sqrt{2mE}}{\hbar}\\
\end{align}$$
**Region 2** ($-a<x<0, V=-V_0$):
$$\begin{align}
-\dfrac{\hbar^2}{2m}\dfrac{\partial^2\psi_2}{\partial x^2}-V_0\psi_2&=E\psi_2 &\implies&& \psi_2&=Ce^{ik'x}+De^{-ik'x}& k'&=\dfrac{\sqrt{2m(E+V_0)}}{\hbar}\\
\end{align}$$
**Region 3** ($x>0, V=\infty$):
$$\begin{align}
\psi_3(x)=0
\end{align}$$
**Wavefunction Continuity at** $x=0$:
$$\begin{align}
&&\lim_{x\rightarrow 0^-}\psi_2(x)&=\lim_{x\rightarrow 0^+}\psi_3(x)\\
&&Ce^{0}+De^{0}&=0\\
\implies&& \Aboxed{D&=-C}\\
\implies&& \Aboxed{\psi_2(r)&=C\sin(k'x)}
\end{align}$$
**Wavefunction Continuity at** $x=-a$:
$$\begin{align}
&&\lim_{x\rightarrow -a^-}\psi_1(x)&=\lim_{x\rightarrow -a^+}\psi_2(x)\\
&&Ae^{ika}+Be^{-ika}&=C\sin(k'a)\\
&&\Aboxed{C&=\dfrac{Ae^{ika}+Be^{-ika}}{\sin(k'a)}}
\end{align}$$
**Derivative Continuity at** $x=-a$:
$$\begin{align}
&&\lim_{x\rightarrow -a^-}\psi_1'(x)&=\lim_{x\rightarrow -a^+}\psi_2'(x)\\
&&ikAe^{ika}-ikBe^{-ika}&=Ck'\cos(k'a)\\
&&\Aboxed{C&=\dfrac{ik}{k'}\dfrac{Ae^{ika}-Be^{-ika}}{\cos(k'a)}}
\end{align}$$
Combining the two above:
$$\begin{align}
\dfrac{Ae^{-ika}+Be^{ika}}{\sin(k'a)}&=\dfrac{ik}{k'}\dfrac{Ae^{-ika}-Be^{ika}}{\cos(k'a)}\\
k'e^{-ika}\left(Ae^{-ika}+Be^{ika}\right)&=ike^{-ika}\left(Ae^{-ika}-Be^{ika}\right)\dfrac{\sin(k'a)}{\cos(k'a)}\\
k'Ae^{-2ika}+k'B&=ikAe^{-2ika}\tan(k'a)-ikB\tan(k'a)\\
k'B+ikB\tan(k'a)&=ikAe^{-2ika}\tan(k'a)-k'Ae^{-2ika}\\
B\left[k'+ik\tan(k'a)\right]\cot(k'a)&=A\left[ik\tan(k'a)-k'\right]e^{-2ika}\cot(k'a)\\
B\left[ik+k'\cot(k'a)\right]&=A\left[ik-k'\cot(k'a)\right]e^{-2ika}\\
\Aboxed{B&=A\left(\dfrac{ik-k'\cot(k'a)}{ik+k'\cot(k'a)}\right)e^{-2ika}}
\end{align}$$
And so the reflected wavefunction is:
$$\begin{align}
\Aboxed{\psi_{1R}&=A\left(\dfrac{ik-k'\cot(k'a)}{ik+k'\cot(k'a)}\right)e^{-2ika}e^{-ikx}}
\end{align}$$
---
#### Question 2.2
Show that the reflected wave has the same amplitude as the incident wave.

This is the case if the magnitude squared is equal between both waves:
$$\begin{align}
|\psi_{1R}|^2&=|A|^2\left|\dfrac{ik-k'\cot(k'a)}{ik+k'\cot(k'a)}\right|^2|e^{-2ika}|^2|e^{-ikx}|^2\\
&=|A|^2\dfrac{-ik-k'\cot(k'a)}{-ik+k'\cot(k'a)}\dfrac{ik-k'\cot(k'a)}{ik+k'\cot(k'a)}\\
&=|A|^2\dfrac{k'^2\cot^2(k'a)+k^2}{k'^2\cot^2(k'a)+k^2}\\
&=|A|^2\\
\Aboxed{|\psi_{1R}|^2&=|\psi_{1T}|^2}
\end{align}$$
---
#### Question 2.3
Show that for a very deep well $E\ll V_0$, the phase shift $\delta\approx-ka$.

When $E\ll V_0$, then $k\ll k'$:
$$\begin{align}
\psi_{1R}&=A\left(\dfrac{ik-k'\cot(k'a)}{ik+k'\cot(k'a)}\right)e^{-2ika}e^{-ikx}\\
&=A\left(\dfrac{-k'\cot(k'a)}{k'\cot(k'a)}\right)e^{-2ika}e^{-ikx}\\
&=A\left(-1\right)e^{-2ika}e^{-ikx}\\
&=Ae^{i\pi}e^{-2ika}e^{-ikx}\\
\end{align}$$
The $\pi$ isn't always $\pi$, since it depends on $\cot(k'a)$, so the net effect is $0$ overall.
This also applies for the position-dependent term, since it's not a constant phase shift.

Therefore, the shift only comes from the $e^{-2ika}$ term. Since we assume that the reflection phase shift happens in 2 parts (entering and exiting), we say that:
$$\begin{align}
e^{2i\delta}&=e^{-2ika} \implies \boxed{\delta=-ka}
\end{align}$$
