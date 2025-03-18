## Conceptual Idea
If I have a wavefunction $\psi$, where $\int_{-\infty}^\infty|\psi|^2\ dx$.
The the smallest discernible interval of space be $\Delta x$.
1. The smallest Spatial Entropy is $\psi(x)=\begin{cases}\tfrac{1}{\sqrt{\Delta x}}e^{-i\phi(x)},&|x-x_0|<\Delta x/2\\0,&\text{elsewhere}\end{cases}$
2. The largest Spatial Entropy is a uniform distribution over the interval of space.

Let's assume that $\Delta x\rightarrow 0$, then:
1. The smallest Spatial Entropy takes the form of a particle in Classical Mechanics.
   $\psi(x)=\sqrt{\delta(x-x_0)}e^{-i\phi(x)}$.
2. The largest Spatial Entropy takes the form of a uniform distribution over space.
   $\psi(x)=\dfrac{1}{\sqrt{a}}e^{-i\phi(x)}$, where $a$ is the interval where the particle exists.

---
### Gaussian Wavefunction
Let's go with the discrete case and then take the limit for the continuum.
Suppose we have a particle with a wavefunction:
$$\begin{align}
\psi(x)&=\dfrac{1}{\sigma\sqrt{2\pi}}e^{-\dfrac{(x-x_0)^2}{2\sigma^2}}&\rightarrow&&|\psi(x)|^2&=\dfrac{1}{2\pi\sigma^2}e^{-\dfrac{(x-x_0)^2}{\sigma^2}}
\end{align}$$
We can then find the entropy as:
$$\begin{align}
S(\psi)/k&=-\int\braket{\psi|\psi}\ln\braket{\psi|\psi}\\
&=-\int_{-\infty}^\infty\dfrac{1}{2\pi\sigma^2}e^{-\dfrac{(x-x_0)^2}{\sigma^2}}\ln\left(\dfrac{1}{2\pi\sigma^2}e^{-\dfrac{(x-x_0)^2}{\sigma^2}}\right)\ dx\\
&=-\ln\left(\dfrac{1}{2\pi\sigma^2}\right)\int_{-\infty}^\infty\dfrac{1}{2\pi\sigma^2}e^{-\dfrac{(x-x_0)^2}{\sigma^2}}\ dx-\int_{-\infty}^\infty\dfrac{1}{2\pi\sigma^2}e^{-\dfrac{(x-x_0)^2}{\sigma^2}}\ln\left(e^{-\dfrac{(x-x_0)^2}{\sigma^2}}\right)\ dx\\
&=\ln\left(2\pi\sigma^2\right)\int_{-\infty}^\infty\dfrac{1}{2\pi\sigma^2}e^{-\dfrac{(x-x_0)^2}{\sigma^2}}\ dx+\dfrac{1}{
\sigma^2
}\int_{-\infty}^\infty\dfrac{1}{2\pi\sigma^2}(x-x_0)^2e^{-\dfrac{(x-x_0)^2}{\sigma^2}}\ dx\\
&=\ln\left(2\pi\sigma^2\right)\cdot1+\dfrac{1}{\sigma^2}\cdot\sigma^2\\
\Aboxed{S(\psi)/k&=\ln\left(2\pi\sigma^2\right)+1}
\end{align}$$
If we find where $S(\psi)=0$, we find that $\sigma=\dfrac{1}{\sqrt{2\pi e}}\implies \sigma^2=\dfrac{1}{2\pi}\dfrac{1}{e}$.
We can safely ignore entropies less than 0, since that means we'd gain information from measuring the wavefunction, which seems nonsense.

This is for a classical entropy, not including quantum mechanics. The $e$ appears as the natural basis for the continuum in classical mechanics. To find the true value, we have to use the uncertainty principle to find the minimal standard deviation.

---
### Infinite Potential Well (1D)
Take the wavefunction and energy in infinite potential well of width $a$:
$$\begin{align}
\psi(x)&=\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n\pi}{a}x\right)\rightarrow\\
|\psi(x)|^2&=\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)
\end{align}$$
From there, we can write the entropy of the system as:
$$\begin{align}
S(\psi)/k&=-\int\braket{\psi|\psi}\ln\braket{\psi|\psi}\\
&=\int_{0}^a\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)\ln\left(\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)\right)\ dx\\
&=-\dfrac{2}{a}\ln\left(\dfrac{2}{a}\right)\int_{0}^a\sin^2\left(\dfrac{n\pi}{a}x\right)\ dx-\dfrac{2}{a}\int_{0}^a\sin^2\left(\dfrac{n\pi}{a}x\right)\ln\left(\sin^2\left(\dfrac{n\pi}{a}x\right)\right)\ dx\\
&=-\ln\left(\dfrac{2}{a}\right)-\int_{0}^a\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)\ln\left(\sin^2\left(\dfrac{n\pi}{a}x\right)\right)\ dx\\
&=\ln\left(\dfrac{a}{2}\right)-\dfrac{2}{n\pi}\int_{0}^{n\pi}\sin^2x\ln\left(\sin^2x\right)\ dx\\
\Aboxed{S(\psi)/k&=\ln\left(\dfrac{a}{2}\right)+0.38629436112}
\end{align}$$
We can find when $S(\psi)=0$ to find the box with minimal entropy:
$$\begin{align}
\Aboxed{a_\text{min}&=2\exp\left(\dfrac{2}{n\pi}\int_{0}^{n\pi}\sin^2x\ln\left(\sin^2x\right)\ dx\right)}
\end{align}$$


### Infinite Potential Well (ND)
Take the wavefunction and energy in infinite potential well of width $a_k$:
$$\begin{align}
\psi(x)&=\prod_{k=1}^N\sqrt{\dfrac{2}{a_k}}\sin\left(\dfrac{n_k\pi}{a_k}x_k\right)\rightarrow\\
|\psi(x)|^2&=\prod_{k=1}^N|\psi_i(x_i)|^2=\prod_{k=1}^N\rho_i(x_i)
\end{align}$$
From there, we can write the entropy of the system as (this is incorrect):
$$\begin{align}
S(\psi)/k_S&=-\int\braket{\psi|\psi}\ln\braket{\psi|\psi}\\
&=-\int\prod_{k=1}^N\rho_k(x_k)\ln\left[\prod_{m=1}^N\rho_m(x_m)\right]\ dx_k\\
&=-\prod_{k=1}^N\int_{0}^{a_k}\rho_k(x_k)\cdot\sum_{m=1}^N\ln\left[\rho_m(x_m)\right]\ dx_k\\
&=-\prod_{k=1}^N\left(\int_{0}^{a_k}\rho_k(x_k)\cdot\ln\left[\rho_k(x_k)\right]\ dx_k+\int_{0}^{a_k}\rho_k(x_k)\cdot\sum_{m\ne k}^N\ln\left[\rho_m(x_m)\right]\ dx_k\right)\\
&=-\prod_{k=1}^N\left(\int_{0}^{a_k}\rho_k(x_k)\cdot\ln\left[\rho_k(x_k)\right]\ dx_k+\left[\sum_{m\ne k}^N\ln\rho_m(x_m)\right]\int_{0}^{a_k}\rho_k(x_k)\ dx_k\right)\\
&=-\prod_{k=1}^N\left(C+\left[\sum_{m\ne k}^N\ln\rho_m(x_m)\right]\right)\\
&=-\prod_{k=1}^N\left(C+\left[\sum_{m=1}^N\ln\rho_m(x_m)\right]-\ln\rho_k(x_k)\right)\\
&=-\prod_{k=1}^N\left(C+\ln\left[\prod_{m=1}^N\rho_m(x_m)\right]-\ln\rho_k(x_k)\right)\\
&=-\prod_{k=1}^N\left(C+\ln\left[\prod_{m=1}^N\rho_m(x_m)\right]-\ln\rho_k(x_k)\right)\\
\end{align}$$


### Conjecture
Quantization occurs in states when $S(\psi)$ is a (global/local) minimum:
$$\begin{align}
S(\rho)&=-k_S\int\rho\ln\rho\\
\dfrac{dS}{dn}&=-k_S\dfrac{d}{d n}\int\rho\ln\rho\\
&=-k_S\int\dfrac{\partial}{\partial n}\left(\rho\ln\rho\right)\\
&=-k_S\int\left(\dfrac{\partial\rho}{\partial n}\ln\rho+\rho\dfrac{\partial}{\partial n}\ln\rho\right)\\
&=-k_S\int\left(\dfrac{\partial\rho}{\partial n}\ln\rho+\rho\dfrac{1}{\rho}\dfrac{\partial\rho}{\partial n}\right)\\
\dfrac{dS}{dn}&=-k_S\int\left(\ln\rho+1\right)\dfrac{\partial\rho}{\partial n}\\
\Aboxed{0&=-k_S\int\left(\ln\rho+1\right)\dfrac{\partial\rho}{\partial n}}
\end{align}$$


Example (Infinite Potential Well):
$$\begin{align}
\rho(x)&=\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)
\end{align}$$
$$\begin{align}
0&=\int_0^a\left[\ln\rho(x)+1\right]\dfrac{\partial\rho(x)}{\partial n}dx\\
&=\int_0^a\left[\ln\left(\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)\right)+1\right]\cdot\dfrac{4\pi n}{a^2}\sin\left(\dfrac{n\pi}{a}x\right)\cos\left(\dfrac{n\pi}{a}x\right)dx\\
&=\dfrac{4\pi n}{a^2}\int_0^a\left[\ln\left(\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)\right)+1\right]\sin\left(\dfrac{n\pi}{a}x\right)\cos\left(\dfrac{n\pi}{a}x\right)dx\\
&=\dfrac{4\pi n}{a^2}\int_0^a\sin\left(\dfrac{n\pi}{a}x\right)\cos\left(\dfrac{n\pi}{a}x\right)\ln\left(\dfrac{2}{a}\sin^2\left(\dfrac{n\pi}{a}x\right)\right)\ dx+\dfrac{4\pi n}{a^2}\int_0^a\sin\left(\dfrac{n\pi}{a}x\right)\cos\left(\dfrac{n\pi}{a}x\right)\ dx\\
\end{align}$$
Let $u=\sin\left(\dfrac{n\pi}{a}x\right)$, and $\dfrac{a}{n\pi}du=\cos\left(\dfrac{n\pi}{a}x\right)dx$:
$$\begin{align}
0&=\dfrac{4\pi n}{a^2}\int_0^{\sin(n\pi)}u\ln\left(\dfrac{2}{a}u^2\right)\dfrac{a}{n\pi}\ du+\dfrac{4\pi n}{a^2}\int_0^{\sin(n\pi)}u\dfrac{a}{n\pi}\ du\\
&=\dfrac{4}{a}\int_0^{\sin(n\pi)}u\ln\left(\dfrac{2}{a}u^2\right)\ du+\dfrac{4}{a}\int_0^{\sin(n\pi)}u\ du\\
&=\dfrac{4}{a}\ln\left(\dfrac{2}{a}\right)\int_0^{\sin(n\pi)}u\ du+\dfrac{4}{a}\int_0^{\sin(n\pi)}u\ln\left(u^2\right)\ du+\dfrac{4}{a}\int_0^{\sin(n\pi)}u\ du\\
&=\dfrac{4}{a}\ln\left(\dfrac{2}{a}\right)\left.\dfrac{u^2}{2}\right|_0^{\sin(n\pi)}+\dfrac{4}{a}\left.\dfrac{u^2}{2}\left(\ln u^2-1\right)\right|_0^{\sin(n\pi)}+\dfrac{4}{a}\left.\dfrac{u^2}{2}\right|_0^{\sin(n\pi)}\\
&=\dfrac{4}{a}\left(\ln\left(\dfrac{2}{a}\right)+1\right)\dfrac{}{2}+\dfrac{4}{a}\left.\dfrac{u^2}{2}\left(\ln u^2-1\right)\right|_0^{\sin(n\pi)}\\
\end{align}$$










Interesting idea I'm currently working on:


Using the definition of Entropy from probabilities, we can write it as:
$$\begin{align}
S(\psi)/k&=\int\braket{\psi|\psi}\ln\braket{\psi|\psi}\\
\end{align}$$
For the case of the particle in an infinite potential well, it surprisingly is the same value for every state parametrized by $n$ (principle quantum number). It doesn't matter what mass or box size until $a<2$, then it started making nonsense.


When I plug in the QHO solution, the difference in entropy between states is unchanging upon changing mass and angular frequency.



### Infinite Potential Well (1D)
Take the wavefunction and energy in infinite potential well:
$$\begin{align}
\psi(x)&=\sqrt{\dfrac{2}{a}}\sin\left(\dfrac{n\pi}{a}x\right)\\ E_n&=\dfrac{\hbar^2\pi^2}{2ma^2}n^2
\end{align}$$
Using the definition of Entropy from probabilities:
$$\begin{align}
S(\psi)/k&=\int\braket{\psi|\psi}\ln\braket{\psi|\psi}\\
\end{align}$$
We can then express the "entropy" of the state as:

Where $C$ is the negative of that integral, and it is constant. Since we want entropy to be positive, that forces the condition:
$$\begin{align}
\ln\left(\dfrac{2}{a}\right)-0.38629436112&>0\\
\ln\left(\dfrac{2}{a}\right)&>0.38629436112\\
\dfrac{2}{a}&>e^{0.38629436112}\\
2e^{-0.38629436112}&>a\\
1.35914091423&>a
\end{align}$$
Or more simply: $a<1.35914091423$.




