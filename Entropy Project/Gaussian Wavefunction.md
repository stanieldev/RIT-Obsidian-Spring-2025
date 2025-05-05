Let the gaussian wavefunction $\psi(x)$ exist, as well as its momentum dual $\phi(p)$:
$$\begin{align}
\psi(x)&=\dfrac{1}{(2\pi\sigma_x^2)^{1/4}}\exp\left(-\dfrac{(x-x_0)^2}{4\sigma_x^2}+ik_0x\right)\\
\phi(p)&=\dfrac{1}{(2\pi\sigma_p^2)^{1/4}}\exp\left(-\dfrac{(p-p_0)^2}{4\sigma_p^2}-i\dfrac{x_0p}{\hbar}\right)
\end{align}$$
And so we can write it as probability density $\rho(x)$ and $\rho(p)$ such that:
$$\begin{align}
|\psi(x)|^2&=\dfrac{1}{\sqrt{2\pi\sigma_x^2}}\exp\left(-\dfrac{(x-x_0)^2}{2\sigma_x^2}\right)\\
|\phi(p)|^2&=\dfrac{1}{\sqrt{2\pi\sigma_p^2}}\exp\left(-\dfrac{(p-p_0)^2}{2\sigma_p^2}\right)
\end{align}$$
### Entropy of parameter $z$
$$\begin{align}
\rho(z)&=\dfrac{1}{\sqrt{2\pi\sigma_z^2}}\exp\left(-\dfrac{(z-z_0)^2}{2\sigma_z^2}\right)\\
\ln\rho(z)&=\ln\left(\dfrac{1}{\sqrt{2\pi\sigma_z^2}}\right)+\ln\exp\left(-\dfrac{(z-z_0)^2}{2\sigma_z^2}\right)\\
&=-\dfrac{1}{2}\ln\left(2\pi\sigma_z^2\right)-\dfrac{(z-z_0)^2}{2\sigma_z^2}\\
\end{align}$$
$$\begin{align}
S[\rho(z)]&=-\int_{-\infty}^\infty\rho(z)\ln\rho(z)\ dz\\\\
&=\dfrac{\ln\left(2\pi\sigma_z^2\right)}{2\sqrt{2\pi\sigma_z^2}}\int_{-\infty}^\infty\exp\left(-\dfrac{(z-z_0)^2}{2\sigma_z^2}\right)\ dz\\
&\ \ \ \ \ \dfrac{1}{\sqrt{2\pi\sigma_z^2}}\int_{-\infty}^\infty\dfrac{(z-z_0)^2}{2\sigma_z^2}\exp\left(-\dfrac{(z-z_0)^2}{2\sigma_z^2}\right)\ dz\\\\
&=\dfrac{\ln\left(2\pi\sigma_z^2\right)}{2\sqrt{2\pi\sigma_z^2}}\sqrt{2\sigma^2_z}\int_{-\infty}^\infty\exp\left(-u^2\right)\ dz\\
&\ \ \ \ \ \dfrac{1}{\sqrt{2\pi\sigma_z^2}}\sqrt{2\sigma^2_z}\int_{-\infty}^\infty u^2\exp\left(-u^2\right)\ dz\\\\
&=\dfrac{\ln\left(2\pi\sigma_z^2\right)}{2\sqrt{2\pi\sigma_z^2}}\sqrt{2\sigma^2_z}\sqrt{\pi}+\dfrac{1}{\sqrt{2\pi\sigma_z^2}}\sqrt{2\sigma^2_z}\dfrac{\sqrt{\pi}}{2}\\\\
&=\dfrac{\ln\left(2\pi\sigma_z^2\right)}{2}+\dfrac{1}{2}\\
S[\rho(z)]&=\dfrac{1}{2}\left(\ln\left(2\pi\sigma_z^2\right)+1\right)\\
\end{align}$$
### Entropy of Wavefunction System
$$\begin{align}
S[\rho(x)]&=\ln\left(\sqrt{2\pi\sigma_x^2}\right)+\dfrac{1}{2}\\
e^{S[\rho(x)]}&=\sqrt{2\pi\sigma_x^2}\sqrt{e}\\
S[\rho(p)]&=\ln\left(\sqrt{2\pi\sigma_p^2}\right)+\dfrac{1}{2}\\
e^{S[\rho(p)]}&=\sqrt{2\pi\sigma_p^2}\sqrt{e}\\
\end{align}$$
Combining the two, we see:
$$\begin{align}
e^{S[\rho(x)]}e^{S[\rho(p)]}&=\sqrt{2\pi\sigma_p^2}\sqrt{e}\cdot\sqrt{2\pi\sigma_x^2}\sqrt{e}\\
2\pi e\sigma_x\sigma_p&=e^{S[\rho(x)]+S[\rho(p)]}\\
\Aboxed{\sigma_x\sigma_p&=\dfrac{e^{S[\rho(x)]+S[\rho(p)]}}{2\pi e}}
\end{align}$$
In terms of wavenumber (spatial frequency), we can rewrite it as:
$$\begin{align}
\Aboxed{\sigma_x\sigma_k&=\dfrac{e^{S[\rho(x)]+S[\rho(p)]}}{e}}
\end{align}$$



