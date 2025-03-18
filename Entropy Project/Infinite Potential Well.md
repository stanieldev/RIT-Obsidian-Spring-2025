### Infinite Potential Well (1D)
Suppose the probability density and energy in infinite potential well exist.
Assume a width $a=1$ with no loss of generality:
$$\begin{align}
\rho(x)&=\dfrac{2}{1-\text{sinc}(2n\pi)}\sin^2\left(n\pi x\right)\\
E&=\dfrac{\hbar^2\pi^2}{2m}n^2
\end{align}$$
Keep in mind, $n$ currently has no restrictions.
$$\begin{align}
S(\rho)/k_S&=-\int\rho\ln\rho\\
&=-\int_0^1\left(\dfrac{2}{1-\text{sinc}(2n\pi)}\sin^2\left(n\pi x\right)\right)\ln\left(\dfrac{2}{1-\text{sinc}(2n\pi)}\sin^2\left(n\pi x\right)\right)\ dx\\
&=-\int_0^1\left(\dfrac{2}{1-\text{sinc}(2n\pi)}\sin^2\left(n\pi x\right)\right)\ln\left(\dfrac{2}{1-\text{sinc}(2n\pi)}\sin^2\left(n\pi x\right)\right)\ dx\\
S(\rho)/k_S&=\ln\left(\dfrac{1-\text{sinc}(2n\pi)}{2}\right)-\dfrac{2}{1-\text{sinc}(2n\pi)}\dfrac{1}{n\pi}\int_0^{n\pi}\sin^2\left(u\right)\ln\left(\sin^2u\right)\ du\\
\end{align}$$
