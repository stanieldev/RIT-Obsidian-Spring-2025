**Name:** Stanley Goodwin
**Date:** 3/21/2025

---
## Random Numbers and Monte-Carlo Integration
### Randomness in Physics
 Random processes are commonly encountered in physics:
  - Measurements of observables in Quantum Mechanics.
  - Particle decays.
  - Decay of unstable isotopes.
  - Brownian motion

Random numbers (Monte-Carlo Simulations) allow us to tackle complex problems.
 - Computational Integrals
 - Randomized Linear Algebra
////

### Randomness in Random Number Generators
Example: Linear Congruential Generator:
$$x'=(ax+c)\mod m$$
Where $a$ is the multiplier, $c$ is the increment, and $m$ is the modulus.
This is a deterministic random value.

### Inverse Transform Method for Sampling from generic $p(E)$
Given the CDF as:
$$F(E)=\int_{E_\text{min}}^Ep(E')\ dE'$$
Then:
$$E=F^{-1}(x)$$
### Exponential Decay Law
We will need conditional probability for Markov Chain Method.
$$\begin{align}
S(t|0)&=2^{-t/\tau} & P(t|0)&=1-2^{-t/\tau}
\end{align}$$
#### Decay of an Isotope
For the decay of the following:
$$\begin{align}
^{208}\text{Tl}\ \rightarrow\ ^{208}\text{Pb} + e^-+\bar\nu_e
\end{align}$$
We write that:
$$\begin{align}
P(t|0)&=1-2^{-t/\tau}
\end{align}$$
### Monte-Carlo Integration
#### Example
Suppose we want to evaluate the following integral:
$$\begin{align}
I&=\int_0^2\sin^2\left(\dfrac{1}{x(2-x)}\right)
\end{align}$$
#### Hit-Or-Miss
We sample a bunch of random points with the probability of the function.
If we know the domain and range, we can approximate the area as the proportion of the points sampled from the domain$\times$range that is under the curve.
#### Mean Value Method
Key observation: Given the probability density $\rho(x)$, the expectation value can be calculated as:
$$\begin{align}
E\left[f(x)\right]&=\int\rho(x)f(x)\ dx & \text{(Continuous)}\\
E\left[f(x)\right]&=\lim_{N\rightarrow\infty}\dfrac{1}{N}\sum
_{n=1}^Nf(x_n) & \text{(Discrete)}\\
\end{align}$$
If we define a random variable:
$$\begin{align}
s&=\dfrac{b-a}{N}\sum
_{n=1}^Nf(x_n)
\end{align}$$
Then the expected value can calculate the integral as an approximation.
The error is found with the standard deviation.
It also has an error that always scales as $1/\sqrt{N}$, independent of dimension.
