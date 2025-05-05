**Name:** Stanley Goodwin
**Date:** 4/28/2025

---
### Shor's Algorithm
Consists of two parts:
 - A classical reduction of the factoring to the problem of "order-finding."
 - A quantum algorithm for solving the "order-finding" problem.
#### From Factoring to Order Finding
Suppose $N$ is an odd integer (We'll assume that $N$ isn't a simple power of a prime). 
Because of the Euclidean Algorithm, if there is an $2\le a<N$ where $\gcd(a,N)>1$, then we found a factor of $N$.

Suppose $a$ has order $r$ in the multiplicative of units modulo $N$.
I.e. $r$ is the smallest positive integer such that $a^r\equiv 1\mod N$.

Suppose we found an order $r$ and it's an even number. If so, then we can factor:
$$\begin{align}
(a^r-1)&\equiv (a^{r/2}-1)(a^{r/2}+1)
\end{align}$$
And so we can find that:
$$\begin{align}
(a^{r/2}-1)(a^{r/2}+1)\equiv 0\mod N
\end{align}$$
Then one of the factors, if not 0, is a factor of $N$.
#### Algorithm
Assume $N$ is an odd integer that's not a power of a prime.
We seek a non-trivial factor of $N$ (I.e. not $1$ nor $N$).
1. Pick a random number $1<a<N$.
2. Compute $d=\gcd(a,N)$.
3. If $d\neq 1$, then $d$ is a non-trivial factor of $N$.
4. If $d=1$, then use the quantum algorithm to find the order $r$ of $a$.
5. If $r$ is odd, go back to step 1.
6. Compute $d'=\gcd(N,a^{r/2}+1)$
7. If $d'=1$, then $d'$ is a non-trivial factor of $N$.
8. ...
