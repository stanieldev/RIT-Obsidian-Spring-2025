**Name:** Stanley Goodwin
**Date:** 4/7/2025

---
### Birthday Problem
If there are $n$ possible "birthdays" with states equally likely, then it requires roughly:
$$k=\sqrt{2n\ln(2)}$$
"people" to expect a collision (probability > 50% that there are shared values).
#### Proof
Suppose we have $n$ birthdays and $k$ people.
$$\begin{align}
P(\text{All Different})&=1\cdot\left(1-\dfrac{1}{n}\right)\cdot\left(1-\dfrac{1}{n}\right)\dots\left(1-\dfrac{k-1}{n}\right)\\
&\approx1\cdot e^{-1/n}\cdot e^{-2/n}\cdots e^{-(k-1)/n}\\
&\approx\exp\left(-\dfrac{1}{n}\sum_{i=1}^{k-1}i\right)\\
&\approx\exp\left(-\dfrac{1}{n}\dfrac{k(k-1)}{2}\right)\\
P(\text{All Different})&\approx e^{-k^2/2n}
\end{align}$$
Setting the probability to $1/2$, we find that:
$$\begin{align}
e^{-k^2/2n}&\approx\dfrac{1}{2}\\
k^2/2n&\approx\ln2\\
\Aboxed{k&\approx\sqrt{2n\ln2}}
\end{align}$$

## Factoring
If we use the birthday problem, we can say it should require something similar for a congruence class:
$$k=\sqrt{2m\ln(2)}\mod m$$
Note that if we want to find the factors of $n$, we could search for $m$'s such that $\gcd(n,m)>1$.

### Pollard $\rho$ Algorithm
#### Algorithm Implementation
1. Choose a random polynomial $f:\mathbb{Z}/n\mathbb{Z}\rightarrow\mathbb{Z}/n\mathbb{Z}$.
2. Start with initial conditions for $x$ and $y$.
3. Replace $x$ with $f(x)$ and $y$ with $f(f(y))$.
4. Compute $d=\gcd(|x-y|,n)$
5. Evaluate the conditions below:
	1. If $d=1$, jump to Step 3.
	2. If $d=n$, $f(x)$ was a bad choice. Choose another function.
	3. If $d\not\in\{1,n\}$, then you've found a factor of $n$.
#### How it Works
The polynomial $f(x)$ generates a pseudo-random sequence:
$$x_n=f^n(x_0)=(f\circ f\circ\dots\circ f )(x_0)$$
Consider the two sequences $S_n=\{x_k\mod n\}$ and $S_p=\{x_k\mod p\}$ for some $p|n$.
We are calculating $S_n$ directly, but we can't calculate $S_p$ directly.
Both sequences will repeat. Since $p<n$ then $S_p$ will repeat faster than $S_n$.
If we find $x_{k_1}\neq x_{k_2}$ such that $x_{k_1}\equiv x_{k_2}\mod p$, then $|x_{k_1}-x_{k_2}|$ is a multiple of $p$.

In Pollard $\rho$, when we get $\gcd(|x-y|,n)=p>1$, then $p|(|x-y|)$.
The $\gcd$ value might not always be prime, but it will always be a factor of $n$.


## Primality Testing
Recall Fermat's Little Theorem:
$$\begin{align}
\gcd(a,p)&=1 &\implies&& a^{p-1}&\equiv1\mod p
\end{align}$$
Not all solutions for $p$ must be prime, but it's a good start.

### Observation
Let $n$ be an odd positive integer. Suppose we pick $a$ and find that:
$$\begin{align}
a^{n-1}&\equiv1\mod n
\end{align}$$
If it doesn't it gets instantly ruled out. Next, we look at:
$$\begin{align}
a^{(n-1)/2}\equiv\pm 1
\end{align}$$
If it is not equal to $\pm1$, it must be that $n$ is composite from the Euler Criterion.
If $n\equiv 1\mod 4$, as well as above, we look at:
$$\begin{align}
a^{(n-1)/4}\equiv\pm 1
\end{align}$$
If it is not equal to $\pm1$, then $n$ is composite.

### Miller-Rabin Primality Test
#### Algorithm
Let $n$ be an odd positive integer and let $s=\max\{r\in\mathbb{N}:2^r|(n-1)\}$.
So $2^s$ is the largest power of $2$ that divides $n-1$. Set $d=(n-1)/2^s$.

If $n$ is prime and $\gcd(a,n)=1$, then either:
$$\begin{align}
a^d\equiv 1\mod n
\end{align}$$
or there exists an $r$ in the set $\{0,1,\dots,s-1\}$ with:
$$\begin{align}
a^{2^rd}\equiv -1\mod n
\end{align}$$
#### Miller-Rabin Witnesses
1. When a number $a$ allows us to prove the compositeness of an integer $n$, we say $a$ is a **Miller-Rabin witness** to the compositeness of $n$.
2. If $n$ is a Fermat pseudo-prime to base $a$ but $a$ is NOT a Miller-Rabin witness to the compositeness of $n$, we call $a$ a **Miller-Rabin non-witness**.
3. If $a$ is a Miller-Rabin non-witness for $n$, we say $n$ is a strong pseudoprime to base $a$.

### Deterministic Miller-Rabin Primality Test
If we assume the Generalized Riemann Hypothesis is true, then we have a deterministic version.

Start with $a=2$ and try the Miller-Rabin test on all values $a\le\lfloor2\ln(n)^2\rfloor$.
If $n$ is composite, a witness is guaranteed to be produced via these tests.
If no witness is found in that sequence, you can conclude that $n$ is **prime**.

