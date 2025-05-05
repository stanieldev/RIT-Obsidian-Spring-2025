Given a wavefunction with a vector of parameters $\vec{v}$, we start with:
$$\begin{align}
S(\psi)/k&=-\int\braket{\psi|\psi}\ln\braket{\psi|\psi}
\end{align}$$
We want to find the gradient, and so:
$$\begin{align}
\vec\nabla_vS(\psi)/k&=-\vec\nabla_v\int\rho\ln\rho\\
&=-\int(\vec\nabla_v\rho)\ln\rho-\int\rho(\vec\nabla_v\ln\rho)\\
&=-\int(\vec\nabla_v\rho)\ln\rho-\int\rho\left(\dfrac{1}{\rho}\vec\nabla_v\rho\right)\\
\vec\nabla_vS(\psi)/k&=-\int(\vec\nabla_v\rho)(\ln\rho+1)\\
\end{align}$$
While we're here, lets look at the second gradient:
$$\begin{align}
\vec\nabla_v^2S(\psi)/k&=-\vec\nabla_v\int(\vec\nabla_v\rho)(\ln\rho+1)\\
&=-\int(\vec\nabla_v^2\rho)(\ln\rho+1)-\vec\nabla_v\int(\vec\nabla_v\rho)(\vec\nabla_v\ln\rho)\\
0&=-\int(\vec\nabla_v^2\rho)(\ln\rho+1)-\int\dfrac{1}{\rho}(\vec\nabla_v\rho)^2\\
\end{align}$$
We can then see:
$$\begin{align}
\int(\vec\nabla_v^2\rho)(\ln\rho+1)&=-\int\dfrac{1}{\rho}(\vec\nabla_v\rho)^2\\
\end{align}$$





Suppose "Action" but instead of an $\epsilon$ it's some form of $e^{E/kT}$.
Minimal action at T=0, perhaps?
