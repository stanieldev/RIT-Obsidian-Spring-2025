**Name:** Stanley Goodwin
**Date:** 3/19/2025

---

## Computing Discrete Logs
### Shank's Baby-Step Giant-Step Algorithm
Let $G$ be a cyclic group of size $n$ with generator $g$.
Given $h\in G$, the following computes an $m$ such that $h=g^m$ in $O\left(n^{1/2+\epsilon}\right)$:
1. Compute and store the baby-step values:
   $1,g,g^2,\dots,g^{\lfloor\sqrt{n}\rfloor-1}$
2. Compute the giant-step values:
   $hg^{-i\lfloor\sqrt{n}\rfloor}$, for $i=0,1,2,\dots$
   For each $i$, check whether the result is on the baby-step list, then terminate.
3. Once you find a match, you have found an $i$ and $j$ such that:
   $hg^{-i\lfloor\sqrt{n}\rfloor}=g^j \implies h=g^{i\lfloor\sqrt{n}\rfloor+j}$
#### Example
Let $p=257$, $g=3$, and $h=75$. Find $m$ such that:
$$\begin{align}
3^m\equiv75\mod 257
\end{align}$$
The value $n=\phi(257)=256$, and so $\lfloor\sqrt{n}\rfloor=16$. Baby steps are as follows:
$$\begin{align}
&B=\left\{1,3,3^2,\dots,3^{14},3^{15}\right\}\mod 243\\
&B=\left\{1,3,9,27,81,243,215,131,136,151,196,74,222,152,199,83\right\}
\end{align}$$
For the giant steps, we find that:
$$\begin{align}
&\left\{75\cdot3^{-16i}\ \vert\ i\in1,2,\dots15\right\}\\
\end{align}$$
And for reference:
$$\begin{align}
257&=3\cdot85 + 2\\
3&=1\cdot2+1\\
1&=86\cdot3-257\\
3^{-1}&\equiv86\mod 257
\end{align}$$
So we get the following list:
$$\begin{align}
75\cdot3^0=75\cdot3^0&=75\notin B\\
75\cdot3^{-16}=75\cdot86^{16}&=87\notin B\\
75\cdot3^{-32}=75\cdot86^{32}&=214\notin B\\
75\cdot3^{-48}=75\cdot86^{48}&=166\notin B\\
75\cdot3^{-64}=75\cdot86^{64}&=172\notin B\\
75\cdot3^{-80}=75\cdot86^{80}&=107\notin B\\
75\cdot3^{-96}=75\cdot86^{96}&=83\in B\\
\end{align}$$
Therefore, we can see that:
$$\begin{align}
&&75\cdot3^{-96}&=3^{15}\\
\implies&& \Aboxed{75&=3^{111}}\\
&&\Aboxed{m&=111}
\end{align}$$
### Pohlig-Hellman Algorithm
There are some situations where computing the discrete logs is easier.
E.g. when $p-1$ factors into a product of only small primes.

Let $p$ be a prime such that:
$$p-1=\prod_{i}^rp_i^{e_i}$$
and suppose $g$ is a generator of $\mathbb{F}_p^\times$.
1. For each $i=1,2,\dots,r$, compute $g_i=g^{(p-1)/p_i^{e_i}}$.
   This element has order $p_i^{e_i}$ in $\mathbb{F}_p^\times$.
2. For each $i=1,2,\dots,r$, compute $h_i=h^{(p-1)/p_i^{e_i}}$.
   By construction, we know $h_i\in\langle g_i\rangle$.
3. Since the $p_i$'s are small, it should be easy to solve the DLP in $\langle g_i\rangle$.
   I.e. find $m_i\in\left\{0,1,\dots,p_i^{e_i}-1\right\}$ such that $g_i^{m_i}=h_i$.
4. The Chinese Remainder Theorem guarantees a solution to the system of equations:
   $m\equiv m_i\mod p_i^{e_i}$, and this solution $m$ will be the discrete log of $h$ in $\mathbb{F}_p^\times$ with gen $g$.
#### Example
Let $p=61$, and primitive root $g=2$.
Then $p-1=60=2^2\cdot3\cdot5$, and suppose $h=53$.
$$\begin{align}
2^m\equiv53\mod61
\end{align}$$
Calculate the g's:
$$\begin{align}
g_1&=2^{60/4}=2^{15}\equiv11\mod 61 & |g_1|=4\\
g_2&=2^{60/3}=2^{20}\equiv47\mod 61 & |g_2|=3\\
g_3&=2^{60/5}=2^{12}\equiv\ \ 9\mod 61 & |g_3|=5\\
\end{align}$$
Calculate the h's:
$$\begin{align}
h_1&=53^{60/4}=53^{15}\equiv11\mod 61\\
h_2&=53^{60/3}=53^{20}\equiv\ \ 1\mod 61\\
h_3&=53^{60/5}=53^{12}\equiv58\mod 61\\
\end{align}$$
Then we get the system of equations:
$$\begin{align}
h_1=g_1^{m_1}\implies11\equiv11^1\mod61\\
h_2=g_2^{m_2}\implies\ \ 1\equiv47^0\mod61\\
h_3=g_3^{m_3}\implies58\equiv9^3\mod61\\
\end{align}$$
Leading into:
$$\begin{align}
m\equiv1\mod 4\\
m\equiv0\mod 3\\
m\equiv3\mod 5\\
\end{align}$$
We can then find a solution of this system:
$$\begin{align}
e_1&\equiv1\mod 4 & e_1&\equiv0\mod 3 & e_1&\equiv0\mod 5\\
e_2&\equiv0\mod 4 & e_2&\equiv1\mod 3 & e_2&\equiv0\mod 5\\
e_3&\equiv0\mod 4 & e_3&\equiv0\mod 3 & e_3&\equiv1\mod 5\\
\end{align}$$
With the solution $\boxed{m=33}$. And so the discrete log of $53$ in $\mathbb{F}_{61}^\times$ is $m=33$.