
---

Title: Classical Heisenberg Model
([https://en.wikipedia.org/wiki/Classical_Heisenberg_model)](https://en.wikipedia.org/wiki/Classical_Heisenberg_model\)))

Restrictions: 1 Dimension to avoid computational intensive processes.
Investigating the physical influence of different interaction ranges is interesting. 
Find interaction as $J_{ij} = J/r^{\alpha}$, where $r = |\mathbf{x}_i - \mathbf{x}_j|$.  
Use $\vec{S}_i$ for spins.


Use Monte Carlo (adapted for 3D vector spins) to study how the system's behavior changes as you vary the exponent $\alpha$ (using the notation of the wikipedia page).

Calculate quantities like energy $E(T)$ and magnetization $M(T)$ (or the scalar quantity $M^2(T)$) for different $\alpha$, and analyze the impact of interaction range on ordering tendencies at low temperatures, connecting to the known results in the literature.

### The Ising Model
In common literature, the Ising model is used in order to model the a grid of particles with spin in order to find how the system behaves and is modeled.

In typical formulation, the general form is usually:
$$\begin{align}
\hat{H}&=-\sum_{\braket{ij}}J_{ij}s_is_j-\mu\sum_{i}h_is_i\\
\vec{M}&=\sum_{i}s_i\\
\end{align}$$
The restrictions placed on the system are as follows:
 - Interactions are *local*, meaning they only occur by adjacent grid-points.
 - Interaction strength is dependent on the two spins.
 - Spins are binary in an orthogonal basis (typically $z$-axis).
 - Magnetic field is aligned or anti-aligned with the spins.

---
### Extending the Ising Model
I want to make a system that allows for more degrees of freedom in the system.
 - Interactions aren't necessarily local and are dependent on a function of $\vec{r}$.
 - Interaction strengths are proportional to a function of $\vec{r}$.
 - Spins are allowed all directions in 3D.
 - Magnetic fields are allowed to exist in 3D.

To implement 3D vectors for spin and field, we can write them as the following:
$$\begin{align}
\hat{H}&=-\sum_{\braket{ij}}J_{ij}(\vec\sigma_i\cdot\vec\sigma_j)-\mu\sum_{i}\vec{H}_i(\vec{x}_i)\cdot\vec\sigma_i
\end{align}$$
To implement non-locality using $J_{ij}$, we can adjust the equation to:
$$\begin{align}
J_{ij}&=J\cdot k(|x_i-x_j|)\\
\hat{H}&=-J\sum_{\braket{ij}_r}(\vec\sigma_i\cdot\vec\sigma_j)\cdot k(|x_i-x_j|)-\mu\sum_{i}\vec{H}_i(\vec{x}_i)\cdot\vec\sigma_i
\end{align}$$
Where $k_r(|x_i-x_j|)$ is a decreasing function based on the radius of interaction.

**Note:** I will **not** be doing the Heisenberg model for Quantum Spin particles.

---
### Implementation of the Model
The grid is generated with random normalized spin states.













Before coding, anything:

Explain as if I was the first person.
 - How people do this.
 - Markov Chain move?
 - There are differences (Heisenberg Model)






Spin System with arrows physically on the graph.





Exploring extensions to the Ising model is a good direction. But the project plan currently lacks clarity and is too broad. Below is some feedback to resolve some terminology issues (allowing you to connect more precisely to the available literature) and feasible for Phys 377 (considering the time and computational restrictions):

- **Model Identification:** The model you have described with 3D vector (classical) spins ($\vec{\sigma}_i$) interacting via a dot product is referred to as the **_"Classical Heisenberg Model"_**. It is distinct from the Ising model (which has scalar $\pm 1$ spins). Please use this standard name and consider using the notation $\vec{S}_i$ for the classical vectors to avoid confusion. ([https://en.wikipedia.org/wiki/Classical_Heisenberg_model)](https://en.wikipedia.org/wiki/Classical_Heisenberg_model\)).  
      
- **Scope Restriction:** Simulating this model with variable-range interactions in 2D or 3D is computationally intensive. I strongly recommend restricting the study to 1 Dimension (a chain).  
    
- **Focused Goal:** Your idea of investigating the physical influence of different interaction ranges is interesting. A clear and achievable project would be to investigate the effect of the interaction range in 1D.  
        - Implement the interaction as $J_{ij} = J/r^{\alpha}$, where $r = |\mathbf{x}_i - \mathbf{x}_j|$.  
        - Use Monte Carlo (adapted for 3D vector spins) to study how the system's behavior changes as you vary the exponent $\alpha$ (using the notation of the Wikipedia page).
        - Calculate quantities like energy $E(T)$ and magnetization $M(T)$ (or the scalar quantity $M^2(T)$) for different $\alpha$, and analyze the impact of interaction range on ordering tendencies at low temperatures, connecting to the known results in the literature.

I think that focusing on 1D as above would retain your core idea about target model and analysis of non-local interactions, while ensuring the project is manageable on a laptop in the available time.