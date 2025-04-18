
2D compressible Euler equations (in conservative form)
$$\begin{align}
\dfrac{\partial\rho}{\partial t}+\vec\nabla\cdot(\rho\vec v)&=0\\
\dfrac{\partial(\rho\vec v)}{\partial t}+\vec\nabla\cdot(\rho\vec v\otimes\vec v)+\vec\nabla p&=0\\
\dfrac{\partial E}{\partial t}+\vec\nabla\cdot[(E+p)\vec v]+\vec\nabla\rho&=0\\
\end{align}$$
This ignores energy using a pressure-based model with wave-like model.




2D Euler Equations (Compressible Fluids)
We're solving the equation for a compressible, non-viscous, adiabatic fluid:
$$\begin{align}
\dfrac{\partial U}{\partial t}&=\vec\nabla\cdot\vec{F}(U)
\end{align}$$
Where $U=[\rho,\rho u, \rho v, E]$ are the conserved variables.
To close the system, we need a relation between pressure and energy:
$$\begin{align}
P=(\gamma-1)\left(E-\dfrac{1}{2}\rho(u^2+v^2)\right)
\end{align}$$









Slide: Overview of the problem at hand

We start with a set of primitives, then find conservatives, using equation of state.
