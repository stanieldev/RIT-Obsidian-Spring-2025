**Name:** Stanley Goodwin
**Date:** 2/21/2025

---
### Relaxation Method Recap
We may want to find values of $x$ that solve the following nonlinear equation (which has no closed-form analytic solution):
$$G(x):=2-x-e^{-x}=0$$
The iteration steps are as follows:
 - Write the following equation as $x=f(x)$ (fixed points)
 - Then implement the following algorithm:
	 - Choose an initial guess $x_0$
	 - Iterate $x_{n+1}=f(x_n)$

It doesn't always converge (multiple solutions as well).
Convergence typically relies on initial guess.
Convergence is typically not fast either.
Let's try to use this method for solving PDEs.

---
### Partial Differential Equations with Relaxation Methods
A function may depend on two, independent variables $x$ and $y$, its partial derivatives.

**Example:** Laplace's Equation
$$\begin{align}
\vec\nabla^2\psi&=\dfrac{\partial^2\psi}{\partial x^2}+\dfrac{\partial^2\psi}{\partial y^2}+\dfrac{\partial^2\psi}{\partial z^2}=0
\end{align}$$
**Example:** Poisson's Equation
$$\begin{align}
\vec\nabla^2\psi&=\dfrac{\partial^2\psi}{\partial x^2}+\dfrac{\partial^2\psi}{\partial y^2}+\dfrac{\partial^2\psi}{\partial z^2}=f(x,y,z)
\end{align}$$
**Example:** Time-Independent Schrodinger Equation
$$\begin{align}
-\dfrac{\hbar^2}{2m}\vec\nabla^2\psi+V(\vec{x})\psi&=E\psi
\end{align}$$
**Example:** Heat Equation
$$\begin{align}
\dfrac{\partial T}{\partial t}&=\kappa\vec\nabla^2T
\end{align}$$
**Example:** Wave Equation
$$\begin{align}
c^2\dfrac{\partial^2\psi}{\partial t^2}-\vec\nabla^2\psi&=0
\end{align}$$
**Example:** Klein-Gordon Equation
$$\begin{align}
c^2\dfrac{\partial^2\psi}{\partial t^2}-\vec\nabla^2\psi&=f(x,y,z)
\end{align}$$
**Example:** Time-Dependent Schrodinger Equation
$$\begin{align}
-\dfrac{\hbar^2}{2m}\vec\nabla^2\psi+V(\vec{x})\psi&=-\hbar\dfrac{\partial\psi}{\partial t}
\end{align}$$
#### Method of Finite Differences
First Derivative, 0th Order (Point):
$$\begin{align}
f'(x)&=\dfrac{f(x+h)-f(x)}{h}+O(h) & \text{Forward Difference}\\
f'(x)&=\dfrac{f(x)-f(x-h)}{h}+O(h) & \text{Backward Difference}\\
\end{align}$$
First Derivative, 1st Order (Linear): 
$$\begin{align}
f'(x)&=\dfrac{f(x+h)-f(x-h)}{2h}+O(h^2) & \text{Central Difference}\\
\end{align}$$
Second Derivative, 0th Order (Point):
$$\begin{align}
f''(x)&=\dfrac{f(x+h)-2f(x)+f(x-h)}{h^2}+O(h^2)
\end{align}$$

**Extension into 2 Dimensions**
You can do the same in every dimension so long as they are orthogonal.

---
#### Boundary Value Problems (Laplace)
Consider a Laplace's Equation with a potential $V$ on the top plate:
$$\begin{align}
\vec\nabla^2\psi&=\dfrac{\partial^2\psi}{\partial x^2}+\dfrac{\partial^2\psi}{\partial y^2}=0
\end{align}$$
We can discretize the space with spacing $\Delta x=\Delta y = a$.
We know the boundary conditions, being $0$ on all walls except on the top plate.
$$\begin{align}
\vec\nabla^2\phi&=\dfrac{\partial^2\phi}{\partial x^2}+\dfrac{\partial^2\phi}{\partial y^2}\\
0&=\dfrac{\phi_{i+1,j}+\phi_{i-1,j}+\phi_{i,j+1}+\phi_{i,j-1}-4\phi_{i,j}}{a^2}
\end{align}$$
We can write it as a function $G$ such that $G(\phi)=0$, and so we can use the relaxation method.
Rearranging, we can get the following:
$$\begin{align}
\phi_{i,j}&=\dfrac{1}{4}\left(\phi_{i+1,j}+\phi_{i-1,j}+\phi_{i,j+1}+\phi_{i,j-1}\right)
\end{align}$$
We can then transform it into a fixed point problem as:
$$\begin{align}
\phi&=F_\text{Jacobi}(\phi)
\end{align}$$
We fix $\phi$ at the boundaries, and so we can find a solution for the problem.
By recursive implementation, we get:
$$\begin{align}
\phi^{n+1}&=F_\text{Jacobi}(\phi^n)\\
\phi^{n+1}&=\dfrac{1}{4}\left(\phi_{i+1,j}^n+\phi_{i-1,j}^n+\phi_{i,j+1}^n+\phi_{i,j-1}^n\right)
\end{align}$$
---
#### Boundary Value Problems (Poisson)
Consider a Poisson's Equation with a potential $V$ on the top plate:
$$\begin{align}
\vec\nabla^2\psi&=\dfrac{\partial^2\psi}{\partial x^2}+\dfrac{\partial^2\psi}{\partial y^2}=-4\pi\rho_{i,j}
\end{align}$$
We can discretize the space with spacing $\Delta x=\Delta y = a$.
We know the boundary conditions, being $0$ on all walls except on the top plate.
$$\begin{align}
\vec\nabla^2\phi&=\dfrac{\partial^2\phi}{\partial x^2}+\dfrac{\partial^2\phi}{\partial y^2}\\
0&=4\pi\rho_{i,j}+\dfrac{\phi_{i+1,j}+\phi_{i-1,j}+\phi_{i,j+1}+\phi_{i,j-1}-4\phi_{i,j}}{a^2}
\end{align}$$
We can write it as a function $G$ such that $G(\phi)=0$, and so we can use the relaxation method.
Rearranging, we can get the following:
$$\begin{align}
\phi_{i,j}&=\dfrac{1}{4}\left(\phi_{i+1,j}+\phi_{i-1,j}+\phi_{i,j+1}+\phi_{i,j-1}\right)+\pi a^2\rho_{i,j}
\end{align}$$
We can then transform it into a fixed point problem as:
$$\begin{align}
\phi&=F_\text{Jacobi}(\phi)
\end{align}$$
We fix $\phi$ at the boundaries, and so we can find a solution for the problem.
By recursive implementation, we get:
$$\begin{align}
\phi^{n+1}&=F_\text{Jacobi}(\phi^n)\\
\phi^{n+1}&=\dfrac{1}{4}\left(\phi_{i+1,j}^n+\phi_{i-1,j}^n+\phi_{i,j+1}^n+\phi_{i,j-1}^n\right)+\pi a^2\rho_{i,j}^{n}
\end{align}$$
---
### Jacobi Method
Same as the above method, where $F$ is the function to find the stationary points of.
#### Overrelaxation Method
We can overrelax to quicker find the convergence:
$$\begin{align}
\phi^{n+1}&=(1+\omega)F_\text{Jacobi}(\phi^n)-\omega\phi^n\\
\end{align}$$
Effectively, we choose to overshoot in order to converge faster in general.
When $\omega=0$, we get the normal Jacobi Method.
When $\omega>0$, we get more aggressive updates (faster), but sometimes becomes unstable.
When $\omega<0$, we get less aggressive updates, but is more likely to be stable.
#### Gauss-Seidel Method
It's a batching strategy, starting with the overrelaxation method:
$$\begin{align}
\phi^{n+1}&=(1+\omega)F_\text{Jacobi}(\phi^n)-\omega\phi^n\\
\end{align}$$
We loop over the points, but use the new values if already generated, since they all converge to equilibrium anyways, and so it will get there much much faster. 
It's also much more stable (generally).
