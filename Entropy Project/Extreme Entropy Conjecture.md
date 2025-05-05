### Conjecture
Quantization of a parameter $n$ occurs in states when $\dfrac{\partial^2S(\psi)}{\partial n^2}=0$ and $\dfrac{\partial^3S(\psi)}{\partial n^3}>0$.

Suppose we have the following form for entropy:
$$\begin{align}
\Aboxed{S(\rho)&=-k_S\int\rho\ln\rho}\\
\end{align}$$
Taking the derivative of Entropy with respect to $n$, we get:
$$\begin{align}
\dfrac{dS}{dn}&=-k_S\dfrac{d}{d n}\int\rho\ln\rho\\
&=-k_S\int\dfrac{\partial}{\partial n}\left(\rho\ln\rho\right)\\
&=-k_S\int\left(\dfrac{\partial\rho}{\partial n}\ln\rho+\rho\dfrac{\partial}{\partial n}\ln\rho\right)\\
&=-k_S\int\left(\dfrac{\partial\rho}{\partial n}\ln\rho+\rho\dfrac{1}{\rho}\dfrac{\partial\rho}{\partial n}\right)\\
\Aboxed{\dfrac{dS}{dn}&=-k_S\int\left(1+\ln\rho\right)\dfrac{\partial\rho}{\partial n}}
\end{align}$$
The second derivative is found similarly:
$$\begin{align}
\dfrac{d^2S}{dn^2}&=-k_S\dfrac{d}{d n}\int\left(\ln\rho+1\right)\dfrac{\partial\rho}{\partial n}\\
&=-k_S\int\dfrac{\partial}{\partial n}\left(\left(\ln\rho+1\right)\dfrac{\partial\rho}{\partial n}\right)\\
&=-k_S\int\dfrac{\partial}{\partial n}\left(\ln\rho+1\right)\dfrac{\partial\rho}{\partial n}+\left(\ln\rho+1\right)\dfrac{\partial^2\rho}{\partial n^2}\\
\Aboxed{\dfrac{d^2S}{dn^2}&=-k_S\int\left[\dfrac{1}{\rho}\left(\dfrac{\partial\rho}{\partial n}\right)^2+\left(\ln\rho+1\right)\dfrac{\partial^2\rho}{\partial n^2}\right]}
\end{align}$$
Looking at its zeros:
$$\begin{align}
\Aboxed{\int\dfrac{1}{\rho}\left(\dfrac{\partial\rho}{\partial n}\right)^2&=-\int\left(\ln\rho+1\right)\dfrac{\partial^2\rho}{\partial n^2}}
\end{align}$$
There are some things we can note:
$$\begin{align}
\left(\dfrac{\partial\rho}{\partial n}\right)^2&\ge0 & \rho&\ge0 & \ln\rho&\le0
\end{align}$$
This actually makes the situation better, since:
$$\begin{align}
\Aboxed{\int\left(\ln\rho+1\right)\dfrac{\partial^2\rho}{\partial n^2}<0}
\end{align}$$