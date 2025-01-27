### Spin Operators
$$\begin{align}
S_x&=\dfrac{\hbar}{2}\sigma_x & 
S_y&=\dfrac{\hbar}{2}\sigma_y & 
S_z&=\dfrac{\hbar}{2}\sigma_z & | &&
S_a&=\dfrac{\hbar}{2}\sigma_a\\
[S_x,S_y]&=i\hbar S_z &
[S_y,S_z]&=i\hbar S_x &
[S_z,S_x]&=i\hbar S_y & | &&
[S_a,S_b]&=c\hbar\epsilon_{abc}S_c\\
\end{align}$$
$$\begin{align}
S^2\ket{s,m_s}&=s(s+1)\hbar^2\ket{s,m_s}\\
S_z\ket{s,m_s}&=m_s\hbar\ket{s,m_s}\\
S_\pm\ket{s,m_s}&=\sqrt{s(s+1)\hbar^2-m_s(m_s\pm1)\hbar^2}\ket{s,m_s\pm1}
\end{align}$$
### Pauli Matrices
Assuming that the basis formed by the span of $\ket{\uparrow}$ and $\ket{\downarrow}$:
$$\begin{align}
\begin{bmatrix}0&1\\1&0\end{bmatrix}&=\sigma_x &
\begin{bmatrix}0&-i\\i&0\end{bmatrix}&=\sigma_y &
\begin{bmatrix}1&0\\0&-1\end{bmatrix}&=\sigma_z &  &&
\begin{bmatrix}1&0\\0&1\end{bmatrix}&=\mathbb{I}\\
[\sigma_x,\sigma_y]&=2i\sigma_z &
[\sigma_y,\sigma_z]&=2i\sigma_x &
[\sigma_z,\sigma_x]&=2i\sigma_y & | &&
[\sigma_a,\sigma_b]&=2\epsilon_{abc}\sigma_c\\
\{\sigma_x,\sigma_y\}&=2i\sigma_z &
\{\sigma_y,\sigma_z\}&=2i\sigma_x &
\{\sigma_z,\sigma_x\}&=2i\sigma_y & | &&
\{\sigma_a,\sigma_b\}&=2\delta_{ab}\sigma_a\\
\end{align}$$
