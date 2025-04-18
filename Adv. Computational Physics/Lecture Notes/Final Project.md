


### Extension of the Ising Model
In common literature, the Ising model is used in order to model the a grid of particles with spin in order to find how the system behaves and is modeled.

The restrictions placed on are as follows:
 - Interactions are *local*, meaning they only occur by adjacent grid-points.
 - Spins are binary in an orthogonal basis.

I intend to remove these restrictions, and show how we can implement these into the model in order to extend it for further applications:
 - Interactions aren't necessarily local (dependent on $\vec{r}$).
 - Spins are allowed all directions in 3D.

**Note:** I will **not** be doing the Heisenberg model for Quantum Spin particles.

#### Variable Interaction
To extend the interaction range to non-adjacent particles, we must modify the Hamiltonian of the system of variable interaction radius:
$$\begin{align}
\hat{H}&=-J\sum_{\braket{ij}_r}(\vec{s}_i\cdot\vec{s}_j)\cdot k(|\vec{x}_i-\vec{x}_j|)-\sum_{i}\vec{H}\cdot\vec{s}_i
\end{align}$$
where $k(\vec{r})$ is a decreasing function representing the interaction coefficient strength based on distance from the particles.





Before coding, anything:

Explain as if I was the first person.
 - How people do this.
 - Markov Chain move?
 - There are differences (Heisenberg Model)






Spin System with arrows physically on the graph.




