
---
### The Ising Model
In common literature, the Ising model is used in order to model the a grid of particles with spin in order to find how the system behaves and is modeled.

In typical formulation, the general form is usually:
$$\begin{align}
\hat{H}&=-\sum_{\braket{ij}}J_{ij}\sigma_i\sigma_j-\mu\sum_{i}h_i\sigma_i
\end{align}$$
The restrictions placed on the system are as follows:
 - Interactions are *local*, meaning they only occur by adjacent grid-points.
 - Spins are binary in an orthogonal basis (typically $z$-axis).
 - Magnetic field is aligned with the spins.

---
### Extending the Ising Model
I want to make a system that allows for more degrees of freedom in the system.
 - Interactions aren't necessarily local and are dependent on a function of $\vec{r}$.
 - Spins are allowed all directions in 3D.
 - Magnetic fields are allowed to exist in 3D.

To implement non-locality using $J_{ij}$, we can write it in the following way:
$$\begin{align}
J_{ij}&=J\cdot k(|x_i-x_j|)\\
\hat{H}&=-J\sum_{\braket{ij}_r}(\sigma_i\sigma_j)\cdot k(|x_i-x_j|)-\mu\sum_{i}H_i\sigma_i
\end{align}$$
We can also implement spins, positions, and magnetic fields as vectors as well:
$$\begin{align}
\hat{H}&=-J\sum_{\braket{ij}}(\vec\sigma_i\cdot\vec\sigma_j)\cdot k_r(|\vec{x}_i-\vec{x}_j|)-\mu\sum_{i}\vec{H}_i(\vec{x}_i)\cdot\vec\sigma_i
\end{align}$$
Where $k_r(|x_i-x_j|)$ is a decreasing function based on the radius of interaction.

**Note:** I will **not** be doing the Heisenberg model for Quantum Spin particles.











Before coding, anything:

Explain as if I was the first person.
 - How people do this.
 - Markov Chain move?
 - There are differences (Heisenberg Model)






Spin System with arrows physically on the graph.




