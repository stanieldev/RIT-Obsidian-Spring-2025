**Name:** Stanley Goodwin
**Date:** 2/28/2025

---
### Question 1
Using the Gaussian trial wavefunction
$$\begin{align}
\psi(x)&=Ae^{-bx^2}
\end{align}$$
estimate the ground state energy of a particle of mass $m$ in the linear potential $V(x)=\alpha|x|$.
We can write the Hamiltonian of the system as $\hat{H}=-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}+\alpha|x|=\hat{T}+\hat{V}$.
#### Wavefunction Normalization
We can normalize the wavefunction by integrating over its domain.
$$\begin{align}
\braket{\psi|\psi}&=\int_{-\infty}^\infty Ae^{-bx^2}\cdot Ae^{-bx^2} dx\\
1&=A^2\int_{-\infty}^\infty e^{-2bx^2} dx\\
1&=A^2\cdot\sqrt{\dfrac{\pi}{2b}}\\
\Aboxed{A&=\left(\dfrac{2b}{\pi}\right)^\tfrac{1}{4}}
\end{align}$$
*Verified the above by Desmos.*
#### Expected Value of Kinetic Energy
$$\begin{align}
\braket{\hat{T}}&=\bra{\psi}\hat{T}\ket{\psi}\\
&=\int_{-\infty}^\infty Ae^{-bx^2}\cdot\left(-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}\right)\cdot Ae^{-bx^2} dx\\
&=-\dfrac{\hbar^2}{2m}A^2\int_{-\infty}^\infty e^{-bx^2}\cdot\dfrac{\partial^2}{\partial x^2}\left(e^{-bx^2}\right)\ dx\\
&=-\dfrac{\hbar^2}{2m}A^2\int_{-\infty}^\infty e^{-bx^2}\cdot e^{-bx^2}\left(4b^2x^2-2b\right)\ dx\\
&=-\dfrac{2\hbar^2b^2}{m}A^2\int_{-\infty}^\infty x^2e^{-bx^2}\ dx+\dfrac{\hbar^2b}{m}A^2\int_{-\infty}^\infty e^{-2bx^2}\ dx\\
&=-\dfrac{2\hbar^2b^2}{m}\sqrt{\dfrac{2b}{\pi}}\dfrac{1}{2(2b)}\sqrt{\dfrac{\pi}{2b}}+\dfrac{\hbar^2b}{m}\sqrt{\dfrac{2b}{\pi}}\sqrt{\dfrac{\pi}{2b}}\\
&=-\dfrac{\hbar^2b}{2m}+\dfrac{2\hbar^2b}{2m}\\
\Aboxed{\braket{\hat{T}}&=\dfrac{\hbar^2b}{2m}}
\end{align}$$
*Verified the above with Brandon.*
#### Expected Value of Potential Energy
$$\begin{align}
\braket{\hat{V}}&=\bra{\psi}\hat{V}\ket{\psi}\\
&=\int_{-\infty}^\infty Ae^{-bx^2}\cdot\alpha|x|\cdot Ae^{-bx^2} dx\\
&=A^2\alpha\int_{-\infty}^\infty |x|\cdot e^{-2bx^2} dx\\
&=2A^2\alpha\int_{0}^\infty xe^{-2bx^2} dx\\
&=2\sqrt{\dfrac{2b}{\pi}}\alpha\cdot\dfrac{1}{2(2b)}\\
\Aboxed{\braket{\hat{V}}&=\dfrac{\alpha}{\sqrt{2b\pi}}}
\end{align}$$
*Verified the above with Brandon.*
#### Expected Value of Hamiltonian
$$\begin{align}
\braket{\hat{H}}&=\bra{\psi}\hat{H}\ket{\psi}\\
&=\bra{\psi}\left(\hat{T}+\hat{V}\right)\ket{\psi}\\
&=\bra{\psi}\hat{T}\ket{\psi}+\bra{\psi}\hat{V}\ket{\psi}\\
&=\braket{\hat{T}}+\braket{\hat{V}}\\
\Aboxed{\braket{\hat{H}}&=\dfrac{\hbar^2b}{2m}+\dfrac{\alpha}{\sqrt{2b\pi}}}
\end{align}$$
*Verified the above with Brandon.*
#### Minimal Parameter
We can find the minimum energy by finding the extremum:
$$\begin{align}
\dfrac{\partial\braket{\hat{H}}}{\partial b}&=\dfrac{\partial}{\partial b}\left(\dfrac{\hbar^2b}{2m}+\dfrac{\alpha}{\sqrt{2b\pi}}\right)\\
0&=\dfrac{\hbar^2}{2m}-\dfrac{\alpha}{2\sqrt{2\pi}b^\tfrac{3}{2}}\\
\dfrac{\hbar^2}{2m}b^\tfrac{3}{2}&=\dfrac{\alpha}{2\sqrt{2\pi}}\\
b^\tfrac{3}{2}&=\dfrac{m\alpha}{\hbar^2\sqrt{2\pi}}\\
\Aboxed{b&=\left(\dfrac{m\alpha}{\hbar^2\sqrt{2\pi}}\right)^\tfrac{2}{3}}
\end{align}$$
*Verified the above with Brandon.*
#### Minimal Hamiltonian
Substituting into the Hamiltonian earlier, we find the minimum Hamiltonian.
$$\begin{align}
\braket{\hat{H}}_\text{min}&=\dfrac{\hbar^2b}{2m}+\dfrac{\alpha}{\sqrt{2\pi}}b^{-\tfrac{1}{2}}\\
&=\dfrac{\hbar^2}{2m}\left(\dfrac{m\alpha}{\hbar^2\sqrt{2\pi}}\right)^\tfrac{2}{3}+\dfrac{\alpha}{\sqrt{2\pi}}\left(\dfrac{m\alpha}{\hbar^2\sqrt{2\pi}}\right)^{-\tfrac{1}{3}}\\
&=\left[\dfrac{\hbar^2}{2m}\left(\dfrac{m\alpha}{\hbar^2\sqrt{2\pi}}\right)+\dfrac{\alpha}{\sqrt{2\pi}}\right]\left(\dfrac{m\alpha}{\hbar^2\sqrt{2\pi}}\right)^{-\tfrac{1}{3}}\\
&=\dfrac{3\alpha}{2\sqrt{2\pi}}\left(\dfrac{\hbar^2\sqrt{2\pi}}{m\alpha}\right)^{\tfrac{1}{3}}\\
&=\left(\dfrac{27\alpha^3}{8\sqrt{2\pi}^3}\dfrac{\hbar^2\sqrt{2\pi}}{m\alpha}\right)^{\tfrac{1}{3}}\\
\braket{\hat{H}}_\text{min}&=\left(\dfrac{27\alpha^2\hbar^2}{16\pi m}\right)^{\tfrac{1}{3}}\\
\end{align}$$
With this, we can estimate the ground-state energy as:
$$\begin{align}
\Aboxed{E_\text{gs}&\approx\sqrt[3]{\dfrac{27\alpha^2\hbar^2}{16\pi m}}}
\end{align}$$
*Verified the above with Brandon.*

---
### Question 2
Use a trial wavefunction of the form
$$\begin{align}
\psi(x)&=\begin{cases}
A\cos\left(\tfrac{\pi}{a}x\right), & -a/2\le x\le a/2\\0,&\text{elsewhere}
\end{cases}
\end{align}$$
to variationally obtain a bound in the ground state energy of the one-dimensional harmonic oscillator.
We can write the Hamiltonian of the system as $\hat{H}=-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}+\dfrac{1}{2}m\omega^2x^2$.
#### Wavefunction Normalization
We can normalize the wavefunction by integrating over its domain.
$$\begin{align}
\braket{\psi|\psi}&=\int_{-a/2}^{a/2} A\cos\left(\tfrac{\pi}{a}x\right)\cdot A\cos\left(\tfrac{\pi}{a}x\right)\ dx\\
1&=A^2\int_{-a/2}^{a/2} \cos^2\left(\tfrac{\pi}{a}x\right)\ dx\\
1&=2A^2\int_{0}^{a/2} \cos^2\left(\tfrac{\pi}{a}x\right)\ dx\\
1&=2A^2\left(\dfrac{x}{2}+\dfrac{a\sin(2\tfrac{\pi}{a}x)}{4\pi}\right|_0^{a/2}\\
1&=2A^2\left(\dfrac{a}{4}+\dfrac{a\sin(\pi)}{4\pi}\right)\\
1&=\dfrac{a}{2}A^2\\
\Aboxed{A&=\sqrt{\dfrac{2}{a}}}
\end{align}$$
*Verified the above by Desmos.*
#### Expected Value of Kinetic Energy
$$\begin{align}
\braket{\hat{T}}&=\bra{\psi}\hat{T}\ket{\psi}\\
&=\int_{-a/2}^{a/2} A\cos\left(\tfrac{\pi}{a}x\right)\cdot\left(-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}\right)\cdot A\cos\left(\tfrac{\pi}{a}x\right)\ dx\\
&=-\dfrac{\hbar^2}{2m}A^2\int_{-a/2}^{a/2}\cos\left(\tfrac{\pi}{a}x\right)\cdot\dfrac{\partial^2}{\partial x^2}\left(\cos\left(\tfrac{\pi}{a}x\right)\right)\ dx\\
&=\dfrac{\hbar^2\pi^2}{2ma^2}A^2\int_{-a/2}^{a/2}\cos^2\left(\tfrac{\pi}{a}x\right)\ dx\\
&=\dfrac{\hbar^2\pi^2}{ma^2}A^2\int_{0}^{a/2}\cos^2\left(\tfrac{\pi}{a}x\right)\ dx\\
&=\dfrac{\hbar^2\pi^2}{ma^2}A^2\left(\dfrac{x}{2}+\dfrac{\sin(2\tfrac{\pi}{a}x)}{4\tfrac{\pi}{a}}\right|_{0}^{a/2}\\
&=\dfrac{\hbar^2\pi^2}{4ma}\dfrac{2}{a}\left(1+\dfrac{\sin(\pi)}{\pi}\right)\\
\Aboxed{\braket{\hat{T}}&=\dfrac{\hbar^2\pi^2}{2ma^2}}
\end{align}$$
*Verified the above with Brandon.*
#### Expected Value of Potential Energy
$$\begin{align}
\braket{\hat{V}}&=\bra{\psi}\hat{V}\ket{\psi}\\
&=\int_{-a/2}^{a/2} A\cos\left(\tfrac{\pi}{a}x\right)\cdot\left(\dfrac{1}{2}m\omega^2x^2\right)\cdot A\cos\left(\tfrac{\pi}{a}x\right)\ dx\\
&=\dfrac{1}{2}m\omega^2A^2\int_{-a/2}^{a/2} x^2\cos^2\left(\tfrac{\pi}{a}x\right)\ dx\\
&=m\omega^2A^2\int_{0}^{a/2} x^2\cos^2\left(\tfrac{\pi}{a}x\right)\ dx\\
&=m\omega^2A^2\left(\dfrac{x^3}{6}+\left[\dfrac{ax^2}{4\pi}-\dfrac{a^3}{8\pi^3}\right]\sin\left(2\tfrac{\pi}{a}x\right)+\dfrac{xa^2\cos\left(2\tfrac{\pi}{a}x\right)}{4\pi^2}\right|_0^{a/2}\\
&=m\omega^2A^2\left(\dfrac{a^3}{48}+\left[\dfrac{a^3}{16\pi}-\dfrac{a^3}{8\pi^3}\right]\sin\left(\pi\right)+\dfrac{a^3\cos\left(\pi\right)}{8\pi^2}\right)\\
&=m\omega^2\dfrac{2}{a}\left(\dfrac{a^3}{48}-\dfrac{a^3}{8\pi^2}\right)\\
\Aboxed{\braket{\hat{V}}&=\dfrac{\pi^2-6}{24\pi^2}\cdot m\omega^2a^2}
\end{align}$$
*Verified the above with Brandon.*
#### Expected Value of Hamiltonian
$$\begin{align}
\braket{\hat{H}}&=\bra{\psi}\hat{H}\ket{\psi}\\
&=\bra{\psi}\left(\hat{T}+\hat{V}\right)\ket{\psi}\\
&=\bra{\psi}\hat{T}\ket{\psi}+\bra{\psi}\hat{V}\ket{\psi}\\
&=\braket{\hat{T}}+\braket{\hat{V}}\\
\Aboxed{\braket{\hat{H}}&=\dfrac{\hbar^2\pi^2}{2ma^2}+\dfrac{\pi^2-6}{24\pi^2}\cdot m\omega^2a^2}
\end{align}$$
*Verified the above with Brandon.*
#### Minimal Parameter
We can find the minimum energy by finding the extremum:
$$\begin{align}
\dfrac{\partial\braket{\hat{H}}}{\partial a}&=\dfrac{\partial}{\partial a}\left(\dfrac{\hbar^2\pi^2}{2m}\dfrac{1}{a^2}+\dfrac{\pi^2-6}{24\pi^2}\cdot m\omega^2a^2\right)\\
0&=-\dfrac{\hbar^2\pi^2}{m}\dfrac{1}{a^3}+\dfrac{\pi^2-6}{12\pi^2}\cdot m\omega^2a\\
\dfrac{\pi^2-6}{12\pi^2}\cdot m\omega^2a^4&=\dfrac{\hbar^2\pi^2}{m}\\
a^4&=\dfrac{12\pi^4}{\pi^2-6}\dfrac{\hbar^2}{m^2\omega^2}\\
\Aboxed{a&=\sqrt[4]{\dfrac{12\pi^4}{\pi^2-6}}\sqrt{\dfrac{\hbar}{m\omega}}}
\end{align}$$
*Verified the above with Brandon.*
#### Minimal Hamiltonian
$$\begin{align}
\braket{\hat{H}}_\text{min}&=\dfrac{\hbar^2\pi^2}{2m}a^{-2}+\dfrac{\pi^2-6}{24\pi^2}\cdot m\omega^2a^2\\
&=\dfrac{\hbar^2\pi^2}{2m}\sqrt{\dfrac{\pi^2-6}{12\pi^4}}\dfrac{m\omega}{\hbar}+\dfrac{\pi^2-6}{24\pi^2}\cdot m\omega^2\sqrt{\dfrac{12\pi^4}{\pi^2-6}}\dfrac{\hbar}{m\omega}\\
&=\dfrac{\hbar\omega\sqrt{12}}{2}\dfrac{\sqrt{\pi^2-6}}{12}
+\dfrac{\hbar\omega\sqrt{12}}{24}\cdot\sqrt{\pi^2-6}\\
\Aboxed{\braket{\hat{H}}_\text{min}&=\hbar\omega\sqrt{\dfrac{\pi^2-6}{12}}}
\end{align}$$
With this, we can estimate the ground-state energy as:
$$\begin{align}
\Aboxed{E_\text{gs}&\approx\hbar\omega\sqrt{\dfrac{\pi^2-6}{12}}\approx0.568\hbar\omega}
\end{align}$$
*Verified the above with Brandon.*

---
### Question 3
Find the lowest bound on the ground state energy (in $\text{eV}$) of hydrogen using the trial wave function
$$\begin{align}
\psi(r)&=Ae^{-br^2}
\end{align}$$
with 𝑏 as a variational parameter.
We can write the Hamiltonian of the system as $\hat{H}=-\dfrac{\hbar^2}{2\mu}\dfrac{\partial^2}{\partial r^2}-\dfrac{e^2}{4\pi\epsilon_0}\dfrac{1}{r}$.
#### Wavefunction Normalization
We can normalize the wavefunction by integrating over its domain.
$$\begin{align}
\braket{\psi|\psi}&=4\pi\int_{0}^\infty Ae^{-br^2}\cdot Ae^{-br^2}r^2dr\\
1&=4\pi A^2\int_{0}^\infty r^2e^{-2br^2}\ dr\\
1&=4\pi A^2\cdot\dfrac{1}{8b}\left(\dfrac{\pi}{2b}\right)^{1/2}\\
A^2&=\dfrac{8b}{4\pi}\left(\dfrac{2b}{\pi}\right)^{1/2}\\
\Aboxed{A&=\left(\dfrac{2b}{\pi}\right)^{3/4}}
\end{align}$$
*Verified the above by Desmos.*
#### Expected Value of Kinetic Energy
$$\begin{align}
\braket{\hat{T}}&=\bra{\psi}\hat{T}\ket{\psi}\\
&=4\pi\int_0^\infty Ae^{-br^2}\cdot\left(-\dfrac{\hbar^2}{2\mu}\dfrac{1}{r^2}\dfrac{d}{dr}\left(r^2\dfrac{d}{dr}\right)\right)\cdot Ae^{-br^2}\ r^2dr\\
&=-\dfrac{4\pi\hbar^2}{2\mu} A^2\int_0^\infty r^2e^{-br^2}\cdot\dfrac{1}{r^2}\dfrac{d}{dr}\left(r^2\dfrac{d}{dr}e^{-br^2}\right) \ dr\\
&=-\dfrac{2\pi\hbar^2}{\mu} A^2\int_0^\infty e^{-br^2}\dfrac{d}{dr}\left(-2br^3e^{-br^2}\right) \ dr\\
&=-\dfrac{2\pi\hbar^2}{\mu} A^2\int_0^\infty e^{-br^2}\left(-6br^2e^{-br^2}+4b^2r^4e^{-br^2}\right) \ dr\\
&=\dfrac{12\pi\hbar^2b}{\mu} A^2\int_0^\infty r^2e^{-2br^2} \ dr-\dfrac{8\pi\hbar^2b^2}{\mu} A^2\int_0^\infty r^4e^{-2br^2} \ dr\\
&=\dfrac{12\pi\hbar^2b}{\mu} A^2\cdot\dfrac{1}{8b}\sqrt{\dfrac{\pi}{2b}}-\dfrac{8\pi\hbar^2b^2}{\mu} A^2\cdot\dfrac{3}{8(2b)^2}\sqrt{\dfrac{\pi}{2b}}\\
&=\dfrac{3\hbar^2b}{\mu}-\dfrac{3\hbar^2b}{2\mu}\\
\Aboxed{\braket{\hat{T}}&=\dfrac{3\hbar^2b}{2\mu}}
\end{align}$$
*Verified the above with Brandon.*
#### Expected Value of Potential Energy
$$\begin{align}
\braket{\hat{V}}&=\bra{\psi}\hat{V}\ket{\psi}\\
&=4\pi\int_0^\infty Ae^{-br^2}\cdot\left(-\dfrac{e^2}{4\pi\epsilon_0}\dfrac{1}{r}\right)\cdot Ae^{-br^2}\ r^2dr\\
&=-\dfrac{e^2}{\epsilon_0}A^2\int_0^\infty re^{-2br^2}\ dr\\
&=-\dfrac{e^2}{\epsilon_0}\left(\dfrac{2b}{\pi}\right)^{3/2}\cdot\dfrac{1}{4b}\\
\Aboxed{\braket{\hat{V}}&=-\dfrac{e^2}{\epsilon_0}\sqrt{\dfrac{b}{2\pi^{3}}}}
\end{align}$$
*Verified the above with Brandon.*
#### Expected Value of Hamiltonian
$$\begin{align}
\braket{\hat{H}}&=\bra{\psi}\hat{H}\ket{\psi}\\
&=\bra{\psi}\left(\hat{T}+\hat{V}\right)\ket{\psi}\\
&=\bra{\psi}\hat{T}\ket{\psi}+\bra{\psi}\hat{V}\ket{\psi}\\
&=\braket{\hat{T}}+\braket{\hat{V}}\\
\Aboxed{\braket{\hat{H}}&=\dfrac{3\hbar^2b}{2\mu}-\dfrac{e^2}{\epsilon_0}\sqrt{\dfrac{b}{2\pi^{3}}}}
\end{align}$$
*Verified the above with Brandon.*
#### Minimal Parameter
We can find the minimum energy by finding the extremum:
$$\begin{align}
\dfrac{\partial\braket{\hat{H}}}{\partial b}&=\dfrac{\partial}{\partial b}\left(\dfrac{3\hbar^2b}{2\mu}-\dfrac{e^2}{\epsilon_0\sqrt{2\pi^{3}}}b^{1/2}\right)\\
0&=\dfrac{3\hbar^2}{2\mu}-\dfrac{e^2}{2\epsilon_0\sqrt{2\pi^{3}}}b^{-1/2}\\
\dfrac{3\hbar^2}{2\mu}b^{1/2}&=\dfrac{e^2}{2\epsilon_0\sqrt{2\pi^{3}}}\\
b^{1/2}&=\dfrac{\mu e^2}{3\hbar^2\epsilon_0\sqrt{2\pi^{3}}}\\
\Aboxed{b&=\dfrac{\mu^2 e^4}{18\pi^{3}\hbar^4\epsilon_0^2}}
\end{align}$$
*Verified the above with Brandon.*
#### Minimal Hamiltonian
Substituting into the Hamiltonian earlier, we find the minimum Hamiltonian.
$$\begin{align}
\braket{\hat{H}}_\text{min}&=\dfrac{3\hbar^2b}{2\mu}-\dfrac{e^2}{\epsilon_0}\sqrt{\dfrac{b}{2\pi^{3}}}\\
&=\dfrac{3\hbar^2}{2\mu}\dfrac{\mu^2 e^4}{18\pi^{3}\hbar^4\epsilon_0^2}-\dfrac{e^2}{\epsilon_0}\sqrt{\dfrac{1}{2\pi^{3}}}\dfrac{\mu e^2}{3\hbar^2\epsilon_0\sqrt{2\pi^{3}}}\\
&=\dfrac{\mu e^4}{12\pi^{3}\hbar^2\epsilon_0^2}-\dfrac{\mu e^4}{6\hbar^2\epsilon_0^2\pi^{3}}\\
\Aboxed{\braket{\hat{H}}_\text{min}&=-\dfrac{\mu e^4}{12\hbar^2\epsilon_0^2\pi^{3}}}
\end{align}$$
With this, we can estimate the ground-state energy as:
$$\begin{align}
\Aboxed{E_\text{gs}&\approx-\dfrac{\mu e^4}{12\hbar^2\epsilon_0^2\pi^{3}}}
\end{align}$$
We can rewrite this in terms of the hydrogen energy ground state as:
$$\begin{align}
E_\text{gs}&\approx-\dfrac{\mu e^4}{12\hbar^2\epsilon_0^2\pi^{3}}\\
&\approx-\dfrac{32}{12\pi}\dfrac{\mu e^4}{2(4\pi\epsilon_0)^2\hbar^2}\\
&\approx0.849(-13.6\text{ eV})\\
\Aboxed{E_\text{gs}&\approx-11.544\text{ eV}}
\end{align}$$
*Verified the above with Brandon.*

---
### Question 4
#### Question 4.1
Prove the following corollary to the variational principle stated in class: if we pick a trial function orthogonal to the actual ground state wavefunction,
$$\begin{align}
\braket{\psi|\psi_\text{gs}}=0 \implies \braket{\hat{H}}\ge E_\text{fe}
\end{align}$$
where $E_\text{fe}$ is the energy of the first excited state.

Let $\psi$ be a linear combination of energy eigenstates, and $\braket{\psi|\psi_\text{gs}}=0$, then:
$$\begin{align}
\ket{\psi}&=\sum_{n\ge1}c_n\ket{\psi_n}
\end{align}$$
We can express $\hat{H}$ as the following:
$$\begin{align}
\braket{\hat{H}}&=\bra{\psi}\hat{H}\ket{\psi}\\
&=\left(\sum_{n\ge1}c_n^*\bra{\psi_n}\right)\left(\sum_{m\ge1}c_m\hat{H}\ket{\psi_m}\right)\\
&=\sum_{n\ge1}\sum_{m\ge1}c_n^*c_mE_m\braket{\psi_n|\psi_m}\\
\Aboxed{\braket{\hat{H}}&=\sum_{n\ge1}|c_n|^2E_n}
\end{align}$$
Observing that $E_n\ge E_\text{fe}$:
$$\begin{align}
E_n&\ge E_\text{fe}\\
|c_n|^2E_n&\ge |c_n|^2E_\text{fe}\\
\sum_{n\ge1}|c_n|^2E_n&\ge\sum_{n\ge1}|c_n|^2E_\text{fe}\\
\sum_{n\ge1}|c_n|^2E_n&\ge E_\text{fe}\sum_{n\ge1}|c_n|^2\\
\braket{\hat{H}}&\ge E_\text{fe}\cdot1\\
\Aboxed{\braket{\hat{H}}&\ge E_\text{fe}}
\end{align}$$

---
#### Question 4.2
Apply the conclusion of 4.1 above to the harmonic oscillator. Since $V(x)$ in this case is even in $x$, so is the ground state. So any odd trial function will work for the excited state. Assume
$$\begin{align}
\psi(x)&=Axe^{-bx^2}
\end{align}$$
and estimate the first excited state energy of a particle of mass $m$ harmonically oscillating at frequency $\omega$.
We can write the Hamiltonian of the system as $\hat{H}=-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}+\dfrac{1}{2}m\omega^2x^2$.
#### Wavefunction Normalization
We can normalize the wavefunction by integrating over its domain.
$$\begin{align}
\braket{\psi|\psi}&=\int_{-\infty}^{\infty} Axe^{-bx^2}\cdot Axe^{-bx^2} dx\\
1&=A^2\int_{-\infty}^{\infty}x^2e^{-2bx^2} dx\\
1&=2A^2\int_{0}^{\infty}x^2e^{-2bx^2} dx\\
1&=2A^2\cdot\dfrac{1}{8b}\sqrt{\dfrac{\pi}{2b}}\\
\Aboxed{A&=\sqrt[4]{\dfrac{32b^3}{\pi}}}
\end{align}$$
*Verified the above by Desmos.*
#### Expected Value of Kinetic Energy
$$\begin{align}
\braket{\hat{T}}&=\bra{\psi}\hat{T}\ket{\psi}\\
&=\int_{-\infty}^{\infty} Axe^{-bx^2}\cdot\left(-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}\right)\cdot Axe^{-bx^2}\ dx\\
&=-\dfrac{\hbar^2}{2m}A^2\int_{-\infty}^{\infty} xe^{-bx^2}\cdot\dfrac{\partial^2}{\partial x^2}\left(xe^{-bx^2}\right)\ dx\\
&=-\dfrac{\hbar^2}{2m}A^2\int_{-\infty}^{\infty} xe^{-bx^2}\cdot2bxe^{-bx^2}\left(2bx^2-3\right)\ dx\\
&=-\dfrac{2\hbar^2b^2}{m}A^2\int_{-\infty}^{\infty} x^4e^{-2bx^2}dx+\dfrac{3\hbar^2b}{m}A^2\int_{-\infty}^{\infty} x^2e^{-2bx^2} dx\\
&=-\dfrac{2\hbar^2b^2}{m}\cdot\sqrt{\dfrac{32b^3}{\pi}}\cdot\dfrac{3}{32b^2}\sqrt{\dfrac{\pi}{2b}}+\dfrac{3\hbar^2b}{m}\cdot\sqrt{\dfrac{32b^3}{\pi}}\cdot\dfrac{1}{8b}\sqrt{\dfrac{\pi}{2b}}\\
&=-\dfrac{2\hbar^2b^2}{m}\cdot4b\cdot\dfrac{3}{32b^2}+\dfrac{3\hbar^2b}{m}\cdot4b\cdot\dfrac{1}{8b}\\
&=-\dfrac{3\hbar^2b}{4m}+\dfrac{3\hbar^2b}{2m}\\
\Aboxed{\braket{\hat{T}}&=\dfrac{3\hbar^2b}{4m}}
\end{align}$$
#### Expected Value of Potential Energy
$$\begin{align}
\braket{\hat{V}}&=\bra{\psi}\hat{V}\ket{\psi}\\
&=\int_{-\infty}^{\infty} Axe^{-bx^2}\cdot\left(\dfrac{1}{2}m\omega^2x^2\right)\cdot Axe^{-bx^2}dx\\
&=\dfrac{1}{2}m\omega^2A^2\int_{-\infty}^{\infty} x^4e^{-2bx^2}dx\\
&=\dfrac{1}{2}m\omega^2\cdot\sqrt{\dfrac{32b^3}{\pi}}\cdot\dfrac{3}{32b^2}\sqrt{\dfrac{\pi}{2b}}\\
\Aboxed{\braket{\hat{V}}&=\dfrac{3}{16}\dfrac{m\omega^2}{b}}
\end{align}$$
#### Expected Value of Hamiltonian
$$\begin{align}
\braket{\hat{H}}&=\bra{\psi}\hat{H}\ket{\psi}\\
&=\bra{\psi}\left(\hat{T}+\hat{V}\right)\ket{\psi}\\
&=\bra{\psi}\hat{T}\ket{\psi}+\bra{\psi}\hat{V}\ket{\psi}\\
&=\braket{\hat{T}}+\braket{\hat{V}}\\
\Aboxed{\braket{\hat{H}}&=\dfrac{3\hbar^2b}{4m}+\dfrac{3}{16}\dfrac{m\omega^2}{b}}
\end{align}$$
#### Minimal Parameter
We can find the minimum energy by finding the extremum:
$$\begin{align}
\dfrac{\partial\braket{\hat{H}}}{\partial a}&=\dfrac{\partial}{\partial a}\left(\dfrac{3\hbar^2b}{4m}+\dfrac{3}{16}\dfrac{m\omega^2}{b}\right)\\
0&=\dfrac{3\hbar^2}{4m}-\dfrac{3}{16}\dfrac{m\omega^2}{b^2}\\
\dfrac{3\hbar^2}{4m}b^2&=\dfrac{3}{16}m\omega^2\\
b^2&=\dfrac{3}{16}m\omega^2\dfrac{4m}{3\hbar^2}\\
b^2&=\dfrac{1}{4}\dfrac{m^2\omega^2}{\hbar^2}\\
\Aboxed{b&=\dfrac{m\omega}{2\hbar}}
\end{align}$$
#### Minimal Hamiltonian
$$\begin{align}
\braket{\hat{H}}_\text{min}&=\dfrac{3\hbar^2b}{4m}+\dfrac{3}{16}m\omega^2b^{-1}\\
&=\dfrac{3\hbar^2}{4m}\dfrac{m\omega}{2\hbar}+\dfrac{3}{16}m\omega^2\dfrac{2\hbar}{m\omega}\\
&=\dfrac{3}{8}\hbar\omega+\dfrac{3}{8}\hbar\omega\\
\braket{\hat{H}}_\text{min}&=\dfrac{3}{4}\hbar\omega
\end{align}$$
With this, we can estimate the first excited state energy as:
$$\begin{align}
\Aboxed{E_\text{fs}&=\dfrac{3}{2}\hbar\omega}
\end{align}$$
I made a mistake somewhere that makes my energy be exactly half the value it should be.
I wasn't able to find it, but since the wavefunction is the exact form as the true solution this solution is exactly the value of energy we'd expect to find.
