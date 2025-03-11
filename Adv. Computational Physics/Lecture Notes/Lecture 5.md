**Name:** Stanley Goodwin
**Date:** 2/14/2025

---
### Schrodinger Equation (TISE)
The time independent version takes the form of:
$$\begin{align}
-\dfrac{\hbar^2}{2m}\dfrac{\partial^2}{\partial x^2}\psi(x)+V(x)\psi(x)&=E\psi(x)
\end{align}$$
We can write it in the following form:
$$\begin{align}
\dfrac{\partial^2\psi(x)}{\partial x^2}&=-\dfrac{2m(E-V(x))}{\hbar^2}\psi(x)
\end{align}$$
A required boundary condition for convergence is that $\lim_{x\rightarrow\pm\infty}\psi(x)=0$.

### Nondimensionalization
We can write most differential equation systems in terms of basic units that allow for better computation by removing super large and super small numbers.
$$\begin{align}
\alpha^{-1}&=137.035999177\dots & \text{Fine Structure Constant}\\
a_0&=\dfrac{\hbar}{m_ec\alpha} & \text{Bohr Radius}\\
E_h&=\dfrac{\hbar^2}{m_ea_0^2} & \text{Hartree Energy}
\end{align}$$
Through this, we can substitute these values as factors of the parameters of the Schrodinger equation in order to make the system unitless.

Our Schrodinger Equation turns into the following:
$$\begin{align}
-\dfrac{1}{2}\dfrac{\partial^2}{\partial \chi^2}\psi(\chi)+\mathcal{V}(\chi)\psi(\chi)&=\mathcal{E}\psi(\chi)
\end{align}$$
Where $x=a_0\chi$, $E=E_h\mathcal{E}$, $V(x)=E_h\mathcal{V}(\chi)$, and $\psi(x)=a_0\psi(\chi)$.
A required boundary condition for convergence is that $\lim_{x\rightarrow\pm\infty}\psi(\chi)=0$.

### Reformulation into First-Order Equations
$$\begin{align}
\dfrac{\partial\psi(\chi)}{\partial \chi}&=\phi(\chi)\\
\dfrac{\partial\phi(\chi)}{\partial \chi}&=2[V(\chi)-E]\psi(\chi)
\end{align}$$
### Final Observations
 - Use RK4 to calculate eigenfunctions.
 - Use root solvers to calculate eigenvalues.
 - Use numerical integration to normalize wavefunctions.
