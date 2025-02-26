**Name:** Stanley Goodwin
**Date:** 1/31/2025

---
### Question 1
Suppose a spin-$1/2$ particle is in the state:
$$\chi=\dfrac{1}{\sqrt{6}}\begin{bmatrix}1+i\\2\end{bmatrix}_Z$$
#### Question 1.1
Calculate the corresponding probability of getting $\hbar/2$ and $-\hbar/2$ if you measure $S_z$.
To find the probabilities, we can use $p(s|\chi)=\left|\braket{s|\chi}\right|^2$:
$$\begin{align}
p(\chi_+^Z|\chi)&=\left|\braket{\chi_+^Z|\chi}\right|^2\\
&=\left|\begin{bmatrix}1&0\end{bmatrix}\dfrac{1}{\sqrt{6}}\begin{bmatrix}1+i\\2\end{bmatrix}\right|^2\\
&=\dfrac{1}{6}\left|1+i\right|^2\\
\Aboxed{p(\chi_+^Z|\chi)&=\dfrac{1}{3}\sim 0.333 \text{ for } s=+\dfrac{\hbar}{2}}
\end{align}$$
$$\begin{align}
p(\chi_-^Z|\chi)&=\left|\braket{\chi_-^Z|\chi}\right|^2\\
&=\left|\begin{bmatrix}0&1\end{bmatrix}\dfrac{1}{\sqrt{6}}\begin{bmatrix}1+i\\2\end{bmatrix}\right|^2\\
&=\dfrac{1}{6}\left|2\right|^2\\
\Aboxed{p(\chi_-^Z|\chi)&=\dfrac{2}{3}\sim 0.667 \text{ for } s=-\dfrac{\hbar}{2}}
\end{align}$$
#### Question 1.2
Calculate the corresponding probability of getting $\hbar/2$ and $-\hbar/2$ if you measure $S_x$.
$$\begin{align}
p(\chi_+^X|\chi)&=\left|\braket{\chi_+^X|\chi}\right|^2\\
&=\left|\dfrac{1}{\sqrt{2}}\begin{bmatrix}1&1\end{bmatrix}\dfrac{1}{\sqrt{6}}\begin{bmatrix}1+i\\2\end{bmatrix}\right|^2\\
&=\dfrac{1}{12}\left|3+i\right|^2\\
\Aboxed{p(\chi_+^X|\chi)&=\dfrac{5}{6}\sim 0.833 \text{ for } s=+\dfrac{\hbar}{2}}
\end{align}$$
$$\begin{align}
p(\chi_-^X|\chi)&=\left|\braket{\chi_-^X|\chi}\right|^2\\
&=\left|\dfrac{1}{\sqrt{2}}\begin{bmatrix}1&-1\end{bmatrix}\dfrac{1}{\sqrt{6}}\begin{bmatrix}1+i\\2\end{bmatrix}\right|^2\\
&=\dfrac{1}{12}\left|-1+i\right|^2\\
\Aboxed{p(\chi_-^X|\chi)&=\dfrac{1}{6}\sim 0.167 \text{ for } s=-\dfrac{\hbar}{2}}
\end{align}$$
### Question 2
In class, we found the matrix form of the spin component $S_r$ along any direction $\hat r$ and also its eigenvalues. Find the normalized eigenspinors of $S_r$.

Given the matrix representation of $S_r=\dfrac{\hbar}{2}\begin{bmatrix}\cos\theta&e^{-i\phi}\sin\theta\\e^{i\phi}\sin\theta&-\cos\theta\end{bmatrix}$, as well as $\lambda=\pm\dfrac{\hbar}{2}$.
Suppose $\lambda=\hbar/2$, then:
$$\begin{align}
0&=\left(S_r-\dfrac{\hbar}{2}\mathbb{I}\right)\vec\lambda\\
&=\dfrac{\hbar}{2}\begin{bmatrix}\cos\theta-1&e^{-i\phi}\sin\theta\\e^{i\phi}\sin\theta&-\cos\theta-1\end{bmatrix}\begin{bmatrix}a\\b\end{bmatrix}\\
&=\begin{bmatrix}a(\cos\theta-1)+be^{-i\phi}\sin\theta\\ae^{i\phi}\sin\theta-b(\cos\theta+1)\end{bmatrix}\\
\end{align}$$
For the following, I'm switching to cases in parallel:
$$\begin{align}
-2a\left(\dfrac{1-\cos\theta}{2}\right)+be^{-i\phi}\sin\theta&=0 &
ae^{i\phi}\sin\theta-2b\left(\dfrac{1+\cos\theta}{2}\right)&=0 \\
-2a\sin(\theta/2)^2+be^{-i\phi}\sin\theta&=0 &
ae^{i\phi}\sin\theta-2b\cos(\theta/2)^2&=0 \\
be^{-i\phi}\sin\theta&=2a\sin(\theta/2)^2 &
2b\cos(\theta/2)^2&=ae^{i\phi}\sin\theta \\
\end{align}$$
Suppose $a=\cos(\theta/2)$, as mentioned in lecture, we get that:
$$\begin{align}
be^{-i\phi}\sin\theta&=2a\sin(\theta/2)^2 &
2b\cos(\theta/2)^2&=ae^{i\phi}\sin\theta \\
be^{-i\phi}\sin\theta&=2\cos(\theta/2)\sin^2(\theta/2) &
2b\cos^2(\theta/2)&=\cos(\theta/2)e^{i\phi}\sin\theta \\
be^{-i\phi}\sin\theta&=[2\cos(\theta/2)\sin(\theta/2)]\sin(\theta/2) &
2b\cos(\theta/2)&=e^{i\phi}\cdot2\sin(\theta/2)\cos(\theta/2) \\
be^{-i\phi}&=\sin(\theta/2) &
b&=e^{i\phi}\sin(\theta/2)
\end{align}$$
Therefore, for we can see that:
$$\begin{align}
\Aboxed{\lambda=+\hbar/2 \implies \chi_+^r&=\begin{bmatrix}\cos(\theta/2)\\e^{i\phi}\sin(\theta/2)\end{bmatrix}}
\end{align}$$
Repeating the above for the other eigenvalue swaps the trigonometry substitutions and introduces a negative, which results in the following being true:
$$\begin{align}
\Aboxed{\lambda=-\hbar/2 \implies \chi_-^r&=\begin{bmatrix}e^{-i\phi}\sin(\theta/2)\\-\cos(\theta/2)\end{bmatrix}}
\end{align}$$
### Question 3
Consider the spin operator $S_y$ for a spin $1/2$ particle.
$$\begin{align}
S_y&=\dfrac{\hbar}{2}\begin{bmatrix}0&-i\\i&0\end{bmatrix}\\
\end{align}$$
#### Question 3.1
Using its matrix form, find its eigenvalues.
$$\begin{align}
0&=\det(S_y-\lambda\mathbb{I})\\
&=\left|\begin{array}{}-\lambda&-i\tfrac{\hbar}{2}\\i\tfrac{\hbar}{2}&-\lambda\end{array}\right|\\
&=(-\lambda)^2-(i\tfrac{\hbar}{2})(-i\tfrac{\hbar}{2})\\
0&=\lambda^2-\tfrac{\hbar^2}{4}\\
\Aboxed{\lambda&=\pm\dfrac{\hbar}{2}}
\end{align}$$
#### Question 3.2
Find its eigenspinors.
$$\begin{align}
0&=(S_r-\lambda\mathbb{I})\vec\lambda\\
&=\dfrac{\hbar}{2}\left[\begin{array}{}\mp1&-i\\i&\mp1\end{array}\right]\begin{bmatrix}a\\b\end{bmatrix}\\
0&=\begin{bmatrix}\mp a-bi\\ai\mp b\end{bmatrix}\\
\end{align}$$
The constraint is $ai=\pm b\implies b=\pm ai$. We must also normalize, and so:
$$\begin{align}
\chi_\pm^Y&=c\begin{bmatrix}a\\\pm ai\end{bmatrix}\\
&=\dfrac{1}{\sqrt{a^2+(ai)^*(ai)}}\begin{bmatrix}a\\\pm ai\end{bmatrix}\\
&=\dfrac{1}{a\sqrt{2}}\begin{bmatrix}a\\\pm ai\end{bmatrix}\\
\Aboxed{\chi_\pm^Y&=\dfrac{1}{\sqrt{2}}\begin{bmatrix}1\\\pm i\end{bmatrix}}
\end{align}$$
Therefore, we can say that the eigenspinors of $S_y$ are:
$$\begin{align}
\Aboxed{\lambda=+\hbar/2 \implies \chi_+^Y&=\dfrac{1}{\sqrt{2}}\begin{bmatrix}1\\ i\end{bmatrix}}\\
\Aboxed{\lambda=-\hbar/2 \implies \chi_-^Y&=\dfrac{1}{\sqrt{2}}\begin{bmatrix}1\\ -i\end{bmatrix}}
\end{align}$$
#### Question 3.3
If you measured $S_y$ on a particle in the state $\chi=a\chi_+^z+b\chi_-^z$ what values might you get and with what probability of each?

**Post Note:** This solution is incorrect.
$$\begin{align}
p(\chi_+^Y|\chi)&=\left|\braket{\chi_+^Y|\chi}\right|^2\\
&=\left|\dfrac{1}{\sqrt{2}}\begin{bmatrix}1&i\end{bmatrix}\dfrac{1}{\sqrt{|a|^2+|b|^2}}\begin{bmatrix}a\\b\end{bmatrix}\right|^2\\
&=\dfrac{1}{2(|a|^2+|b|^2)}\left|a+bi\right|^2\\
\Aboxed{p(\chi_+^Y|\chi)&=\dfrac{1}{2}\sim 0.500 \text{ for } s=+\dfrac{\hbar}{2}}
\end{align}$$
$$\begin{align}
p(\chi_-^Y|\chi)&=\left|\braket{\chi_-^Y|\chi}\right|^2\\
&=\left|\dfrac{1}{\sqrt{2}}\begin{bmatrix}1&-i\end{bmatrix}\dfrac{1}{\sqrt{|a|^2+|b|^2}}\begin{bmatrix}a\\b\end{bmatrix}\right|^2\\
&=\dfrac{1}{2(|a|^2+|b|^2)}\left|a-bi\right|^2\\
\Aboxed{p(\chi_-^Y|\chi)&=\dfrac{1}{2}\sim 0.500 \text{ for } s=-\dfrac{\hbar}{2}}
\end{align}$$
### Question 4
Consider a particle of spin $1$. Follow the procedure used in class for spin $1/2$.
#### Question 4.1
Write down a matrix representation for the basis states.
$$\begin{align}
\ket{1,1}&=\begin{bmatrix}1\\0\\0\end{bmatrix}\\
\ket{1,0}&=\begin{bmatrix}0\\1\\0\end{bmatrix}\\
\ket{1,-1}&=\begin{bmatrix}0\\0\\1\end{bmatrix}
\end{align}$$
#### Question 4.2
In the representation of 4.1, write a matrix for $S_z$.
$$\begin{align}
S_z&=\begin{bmatrix}
\bra{1,1}S_z\ket{1,1}&\bra{1,1}S_z\ket{1,0}&\bra{1,1}S_z\ket{1,-1}\\
\bra{1,0}S_z\ket{1,1}&\bra{1,0}S_z\ket{1,0}&\bra{1,0}S_z\ket{1,-1}\\
\bra{1,-1}S_z\ket{1,1}&\bra{1,-1}S_z\ket{1,0}&\bra{1,-1}S_z\ket{1,-1}
\end{bmatrix}\\
S_z&=\hbar\begin{bmatrix}
1&0&0\\
0&0&0\\
0&0&-1\end{bmatrix}\\
\end{align}$$
#### Question 4.3
Derive matrix representations for $S_\pm$.
$$\begin{align}
S_+&=\begin{bmatrix}
\bra{1,1}S_+\ket{1,1}&\bra{1,1}S_+\ket{1,0}&\bra{1,1}S_+\ket{1,-1}\\
\bra{1,0}S_+\ket{1,1}&\bra{1,0}S_+\ket{1,0}&\bra{1,0}S_+\ket{1,-1}\\
\bra{1,-1}S_+\ket{1,1}&\bra{1,-1}S_+\ket{1,0}&\bra{1,-1}S_+\ket{1,-1}
\end{bmatrix}\\
S_+&=\begin{bmatrix}
0&\bra{1,1}S_+\ket{1,0}&0\\
0&0&\bra{1,0}S_+\ket{1,-1}\\
0&0&0
\end{bmatrix}\\
S_+&=\hbar\sqrt{2}\begin{bmatrix}0&1&0\\0&0&1\\0&0&0\end{bmatrix}\\
\end{align}$$
$$\begin{align}
S_-&=S_+^\dagger\\
S_-&=\hbar\sqrt{2}\begin{bmatrix}
0&0&0\\
1&0&0\\
0&1&0
\end{bmatrix}\\
\end{align}$$

#### Question 4.4
Construct matrix representations of the operators $S_x$ and $S_y$.
$$\begin{align}
S_x&=\dfrac{1}{2}\left(S_++S_-\right)\\
&=\dfrac{1}{2}\left(\hbar\sqrt{2}\begin{bmatrix}0&1&0\\0&0&1\\0&0&0\end{bmatrix}+\hbar\sqrt{2}\begin{bmatrix}0&0&0\\1&0&0\\0&1&0\end{bmatrix}\right)\\
S_x&=\dfrac{\sqrt{2}}{2}\hbar\begin{bmatrix}0&1&0\\1&0&1\\0&1&0\end{bmatrix}\\
\end{align}$$
$$\begin{align}
S_y&=\dfrac{1}{2i}\left(S_+-S_-\right)\\
&=\dfrac{1}{2i}\left(\hbar\sqrt{2}\begin{bmatrix}0&1&0\\0&0&1\\0&0&0\end{bmatrix}-\hbar\sqrt{2}\begin{bmatrix}0&0&0\\1&0&0\\0&1&0\end{bmatrix}\right)\\
&=\dfrac{\sqrt{2}}{2i}\hbar\begin{bmatrix}0&1&0\\-1&0&1\\0&-1&0\end{bmatrix}\\
S_y&=\dfrac{\sqrt{2}}{2}\hbar\begin{bmatrix}0&-i&0\\i&0&-i\\0&i&0\end{bmatrix}\\
\end{align}$$
