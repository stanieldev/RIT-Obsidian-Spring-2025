**Name:** Stanley Goodwin
**Date:** 2/28/2025

---
### PDEs with Time Dependence
#### Initial Value Problems
Example: The Heat Equation
$$\dfrac{\partial\phi}{\partial t}=\kappa\vec\nabla^2\phi$$
 - Evolution of temperature $\phi=T(t,x,y,z)$ (heat flow).
 - Evolution of particle density $\phi=\rho(t,x,y,z)$ (concentration flow).
#### Forward-Time Centered-Space Method
For the heat equation, we can show:
$$\begin{align}
\phi(t+\Delta t,x)\approx\phi(t,x)+\Delta t\cdot\kappa\dfrac{\phi(t,x+\Delta x)-2\phi(t,x)+\phi(t,x-\Delta x)}{(\Delta x)^2}
\end{align}$$
#### Stability of FTCS Method (Heat Equation)
In practice, we need sufficiently small changes, where we can find:
$$\begin{align}
\Delta t\ll\dfrac{(\Delta x)^2}{2\kappa}
\end{align}$$
#### Stability of FTCS Method (Wave Equation)
Given the structure of the wave equation:
$$\begin{align}
\dfrac{\partial^2\psi}{\partial t^2}&=v^2\dfrac{\partial^2\psi}{\partial x^2}
\end{align}$$
We can convert it into a system of first-order equations as:
$$\begin{align}
\dfrac{\partial\psi}{\partial t}&=\phi(t,x)\\
\dfrac{\partial\phi}{\partial t}&=v^2\dfrac{\partial^2\psi}{\partial x^2}\\
\end{align}$$
We can then use FTCS method to write:
$$\begin{align}
\psi(t+\Delta t,x)&=\psi(t,x)+\psi(t,x)\Delta t\\
\phi(t+\Delta t,x)&=\phi(t,x)+\Delta t\dfrac{v^2}{(\Delta x)^2}\left(\phi(t,x+\Delta x)-2\phi(t,x)+\phi(t,x-\Delta x)\right)
\end{align}$$
The von Neumann analysis shows that this approximation is unstable.

#### Implicit Method (Heat Equation)
If we find the steps for a negative time step:
$$\begin{align}
\phi(t+\Delta,x)-\Delta t\cdot\kappa\dfrac{\phi(t+\Delta,x+\Delta x)-2\phi(t+\Delta,x)+\phi(t+\Delta,x-\Delta x)}{(\Delta x)^2}\approx\phi(t,x)
\end{align}$$
This is sometimes more stable, since they solve a system of equations.

#### Crank-Nicolson Method
For the heat equation:
$$\begin{align}
\phi(t+\Delta t,x)\approx\phi(t,x)+\Delta t\cdot\kappa\dfrac{\phi(t,x+\Delta x)-2\phi(t,x)+\phi(t,x-\Delta x)}{(\Delta x)^2}
\end{align}$$
Leads to (through the method, an average):
$$\begin{align}
\phi(t+\Delta t,x)&\approx\phi(t,x)+\dfrac{\Delta t}{2}\cdot\kappa\dfrac{\phi(t,x+\Delta x)-2\phi(t,x)+\phi(t,x-\Delta x)}{(\Delta x)^2}\\
& \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ +
\dfrac{\Delta t}{2}\cdot\kappa\dfrac{\phi(t+\Delta t,x+\Delta x)-2\phi(t+\Delta t,x)+\phi(t+\Delta t,x-\Delta x)}{(\Delta x)^2}\\
\end{align}$$
