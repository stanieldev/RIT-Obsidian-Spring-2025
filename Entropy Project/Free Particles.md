
### Static Free Gaussian
Suppose we have a gaussian wavefunction centered around $x_0$, $p_0=\hbar k_0$:
$$\begin{align}
\psi(x)&=\left(\dfrac{1}{2\pi\sigma_x^2}\right)^{1/4}e^{-\tfrac{(x-x_0)^2}{4\sigma_k^2}}e^{ik_0(x-x_0)}\\
\phi(k)&=\left(\dfrac{1}{2\pi\sigma_k^2}\right)^{1/4}e^{-\tfrac{(k-k_0)^2}{4\sigma_k^2}}e^{-ikx_0}\\
\end{align}$$
Then we can find the associated probability densities:
$$\begin{align}
|\psi(x)|^2&=\dfrac{1}{\sqrt{2\pi\sigma_x^2}}e^{-\tfrac{(x-x_0)^2}{2\sigma_x^2}}\\
|\phi(k)|^2&=\dfrac{1}{\sqrt{2\pi\sigma_k^2}}e^{-\tfrac{(k-k_0)^2}{2\sigma_k^2}}\\
\end{align}$$
We can represent the entropy of each probability density as:
$$\begin{align}
S(\psi)&=-\int\braket{\psi|\psi}\ln\braket{\psi|\psi}
\end{align}$$
For the wavefunction in space:
$$\begin{align}
S[\psi(x)]&=-\int_{-\infty}^\infty\braket{\psi(x)|\psi(x)}\ln\braket{\psi(x)|\psi(x)}\ dx\\
&=-\int_{-\infty}^\infty|\psi(x)|^2\ln\left(\dfrac{1}{\sqrt{2\pi\sigma_x^2}}e^{-\tfrac{(x-x_0)^2}{2\sigma_x^2}}\right)\ dx\\
&=-\ln\left(\dfrac{1}{\sqrt{2\pi\sigma_x^2}}\right)\int_{-\infty}^\infty|\psi(x)|^2\ dx+
\int_{-\infty}^\infty\tfrac{(x-x_0)^2}{2\sigma_x^2}|\psi(x)|^2\ dx\\
\Aboxed{S[\psi(x)]&=\ln\left(\sqrt{2\pi\sigma_x^2}\right)}
\end{align}$$
Similarly, we can find that for the wavefunction in dual of space:
$$\begin{align}
\Aboxed{S[\phi(k)]&=\ln\left(\sqrt{2\pi\sigma_k^2}\right)}
\end{align}$$
We can rearrange for the $\sigma$ terms, leading to:
$$\begin{align}
S[\psi]&=\ln\left(\sqrt{2\pi\sigma^2}\right)\\
e^{S[\psi]}&=\sqrt{2\pi\sigma^2}\\
\Aboxed{\sigma&=\dfrac{e^{S[\psi]}}{\sqrt{2\pi}}}
\end{align}$$
If we choose this for $x$ and $k$, we find the product as:
$$\begin{align}
\sigma_x\sigma_k&=\dfrac{e^{S[\psi(x)]}}{\sqrt{2\pi}}\dfrac{e^{S[\phi(k)]}}{\sqrt{2\pi}}\\
&=\dfrac{e^{S[\psi(x)]}e^{S[\phi(k)]}}{2\pi}\\
\Aboxed{\sigma_x\sigma_k&=\dfrac{e^{S_x+S_k}}{2\pi}}
\end{align}$$
Note: I shortened notation by using $S[\psi(x)]=S_x$ and $S[\phi(k)]=S_k$.

Substituting that $\sigma_p=\hbar\sigma_k$, we can find the typical uncertainty principle:
$$\begin{align}
\Aboxed{\sigma_x\sigma_p&=\dfrac{\hbar}{2\pi}e^{S_x+S_p}}
\end{align}$$
Since the entropy of a system cannot be less than zero, we find our lower bound:
$$\begin{align}
\Aboxed{\sigma_x\sigma_p&\ge\dfrac{\hbar}{2\pi}}
\end{align}$$

### Dynamic Free Gaussian
Suppose we have a gaussian wavefunction again centered around $x_0$, $p_0=\hbar k_0$:
$$\begin{align}
\psi(x,t)&=\left(\dfrac{2\sigma_k^2}{\pi}\right)^{1/4}\dfrac{1}{\sqrt{1+i\tfrac{2\hbar\sigma_k^2}{m}t}}\exp\left(-\tfrac{\left(x-x_0-\tfrac{\hbar k_0}{m}t\right)^2}{4\sigma_x^2\left(1+\left(\tfrac{2\hbar\sigma_k^2}{m}t\right)^2\right)}\right)e^{ik_0\left(x-\tfrac{\hbar k_0}{2m}t\right)}e^{i\Phi(t)}\\
\psi(k,t)&=\left(\dfrac{1}{2\pi\sigma_k^2}\right)^{1/4}e^{-\tfrac{(k-k_0)^2}{4\sigma_k^2}}e^{-ikx_0}e^{-i\tfrac{\hbar k^2}{2m}t}\\
\end{align}$$
Then we can find the associated probability densities:
$$\begin{align}
|\psi(x,t)|^2&=\sqrt{\dfrac{2\sigma_k^2}{\pi}}\dfrac{1}{1+\left(\tfrac{2\hbar\sigma_k^2}{m}t\right)^2}\exp\left(-\tfrac{\left(x-x_0-\tfrac{\hbar k_0}{m}t\right)^2}{2\sigma_x^2\left(1+\left(\tfrac{2\hbar\sigma_k^2}{m}t\right)^2\right)}\right)\\
|\psi(k,t)|^2&=\dfrac{1}{\sqrt{2\pi\sigma_k^2}}e^{-\tfrac{(k-k_0)^2}{2\sigma_k^2}}\\
\end{align}$$




### Relation to Temperature

In thermodynamics, we have the following relationship:
$$\begin{align}
\sigma_p^2&=2mk_B T
\end{align}$$













For a free particle with initial momentum $p_0$:
$$\begin{align}
|\psi(x,t)|^2&=\dfrac{1}{\sigma_x\sqrt{2\pi(1+4t^2)}}\exp\left(-\dfrac{2(x/2\sigma_x-p_0t/\hbar)^2}{1+4t^2}\right)\\
|\psi(x,0)|^2&=\dfrac{1}{\sigma_x\sqrt{2\pi}}e^{-x^2/2\sigma_x^2}\\
\end{align}$$
We can calculate the entropy as:
$$\begin{align}
S_x(t)&=-\int_{-\infty}^\infty\braket{\psi|\psi}\ln\braket{\psi|\psi}\ dx\\
S_x(t)&=\ln\left[\sigma_x\sqrt{2\pi(1+4t^2)}\right]\\
e^{S_x(t)}&=\sigma_x\sqrt{2\pi(1+4t^2)}\\
\Aboxed{\sigma_x&=\dfrac{e^{S_x(t)}}{\sqrt{2\pi(1+4t^2)}}}
\end{align}$$
You can calculate it for the momentum as well (I'd have to verify this later), leading to:
$$\begin{align}
\Aboxed{\sigma_p&=\dfrac{e^{S_p(t)}}{\sqrt{2\pi(1+4t^2)}}}
\end{align}$$
So we can get a relationship of the product of uncertainties:
$$\begin{align}
\sigma_x\sigma_p&=\dfrac{e^{S_x(t)}e^{S_p(t)}}{2\pi(1+4t^2)}\\
\sigma_x\sigma_p&=\dfrac{e^{S_x(t)+S_p(t)}}{2\pi(1+4t^2)}\\
\Aboxed{\sigma_x\sigma_p&=\dfrac{1}{2\pi}\cdot\dfrac{e^{S(t)}}{1+4t^2}}\\
\end{align}$$
At the time $t=0$, we know that this takes the form:
$$\begin{align}
\Aboxed{\sigma_x\sigma_p&=\dfrac{\hbar}{2\pi}}\\
\Aboxed{\sigma_x\sigma_k&=\dfrac{1}{2\pi}}\\
\end{align}$$
