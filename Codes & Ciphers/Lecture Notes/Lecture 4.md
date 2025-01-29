**Name:** Stanley Goodwin
**Date:** 1/27/2025

---
### Fundamental Theorem of Arithmetic
All positive integers, $n>1$, can be written as a unique product of prime numbers.

### Euclid's Lemma
A number is prime if it divides a number $ab$ implies that it must divide of of the factors.
$$p\in P\iff \left[\ p|ab \implies (p|a)\lor(p|b)\ \right]$$

### Modular Arithmetic
Insert lecture about finite integer fields.

### Greatest Common Divisor
Spent a bit writing in math but this makes way more sense.
$$\begin{align}
\gcd(^*r)&=\max\left\{i\ |\ i\in\mathbb{Z}^+, i\mid \forall ^*r\right\}
\end{align}$$
I used python syntax to compress it a bit more for infinite arguments.

### Division Algorithm
If $a$ and $b$ are integers where $b>0$, then there exists a unique integers $q,r$ such that:
$$a=bq+r$$
Where $q$ is the quotient, and $r$ is the remainder.

### Euclid's Algorithm
If $n\vert a$ and $n\vert b$, then $n\vert a\pm b$, so:
$$\gcd(a,b)=\gcd(b,a+kb)$$
Where $k$ is any integer.


Example:
Let $r_0=a$, $r_1=b$, and $i=1$.
Then, where $q_i$ is an integer and $0\ge r_{i+1}<r_{i}$.
If $r_{i+1}=0$, then $\gcd(a,b)=r_i$.
If $r_{i+1}\neq0$, then $i++$ and $r_{i-1}=q_ir_i+r_{i+1}$.

$\gcd(12345,2025)$
$a=12345$, $b=2025$


$$\begin{align}
i&=1 & 12345&=6\cdot2025+195\\
i&=2 & 2025&=10\cdot195+75\\
i&=3 & 195&=2\cdot75+45\\
i&=4 & 75&=1\cdot45+30\\
i&=5 & 45&=1\cdot30+15\\
i&=6 & 30&=2\cdot15+0\\
\end{align}$$
The number $15$ is the GCD.