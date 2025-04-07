**Name:** Stanley Goodwin
**Date:** 3/28/2025

---

### Monte-Carlo Integration (Mean-Value Method)
Given a probability density $\rho(x)$, the expected value of $f(x)$ is:
$$\begin{align}
E\left[f(x)\right]&=\int\rho(x)f(x)\ dx\\
E\left[f(x)\right]&=\lim_{N\rightarrow\infty}\dfrac{1}{N}\sum_{i=1}^Nf(x_i)\\
\end{align}$$
For calculating a generic integral, we can define a random variable:
$$\begin{align}
s&=\dfrac{1}{N}\sum_{i=1}^Nf(x_i)\\
\end{align}$$
Then we can approximate the integral since:
$$\begin{align}
E[s]&=\dfrac{1}{N}\sum_{i=1}^NE[f(x_i)]\\
&=\dfrac{1}{N}NE[f(x)]\\
\Aboxed{E[s]&=E[f(x)]}
\end{align}$$
And the variance:
$$\begin{align}
\sigma^2&=E[s^2]-E[s]^2\\
\Aboxed{\sigma^2&=\dfrac{1}{N}\left(E[f^2]-E[f]^2\right)}
\end{align}$$
### Monte-Carlo Integration (Importance Sampling)
An observation we can see is:
$$\begin{align}
I&=\int g(x)\ dx=\int p(x)\dfrac{g(x)}{p(x)}\ dx=\int p(x)f(x)\ dx
\end{align}$$

### Monte-Carlo Summation (Mean-Value Method)
Same as integration, just discrete.


### Ising Model
A grid of local spin groups with energy:
$$\begin{align}
E_\alpha&=-\sum_{\braket{ij}}\sigma_i\sigma_j-H\sum_i\sigma_i
\end{align}$$
where the $\braket{ij}$ is all pairs that are adjacent in the lattice, $J$ is the spin interaction strength, and $H$ is the applied magnetic field to the system.

If the canonical system is in thermal equilibrium with a heat bath of temperature $T$, then:
$$\begin{align}
p(E_\alpha)&=\dfrac{1}{Z}e^{-E_\alpha/kT} & Z&=\sum_{\alpha=0}^{2^\nu-1}e^{-E_\alpha/kT}
\end{align}$$
We can then calculate the expected values of the statistical properties:
$$\begin{align}
\braket{E}&=\sum_{\alpha=0}^{2^\nu-1}p(E_\alpha)E_\alpha\\
\braket{M}&=\sum_{\alpha=0}^{2^\nu-1}p(E_\alpha)M_\alpha\\
\end{align}$$
### Markov Chain Method
The Markov chain Method enables us to systematically sample $\alpha_n$ with desired probability $p_\alpha$ without having to calculate the normalization $Z=\sum_\alpha p_\alpha$.

Markov Chains have no memory other than the current state.
https://mycourses.rit.edu/d2l/le/content/1132638/viewContent/10816080/View
Continue later.