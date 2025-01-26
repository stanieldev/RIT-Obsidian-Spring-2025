**Name:** Stanley Goodwin
**Date:** 1/22/2025

---
### Review of Proof Techniques
Direct Proof ($A^T\implies B^T$)
Indirect Proof ($B^F\implies A^F$)
Proof by Induction ($\text{Case}\implies\text{Case}+1$)
 - Weak: Only $\text{Case} - 1\implies\text{Case}$
 - Strong: $\text{Cases}<\text{Case}\implies\text{Case}$

## Number Theory: Primes & Factorization

### Cardinality of Primes
**Theorem:** The cardinality of the set of prime numbers is $\aleph_0$.
**Proof:** 
Suppose $P=\{p_1,p_2,p_3,\dots,p_n\}$ where $p_1=2<p_2<p_3<\dots<p_n$.
Let $M=p_1p_2p_3\dots p_n + 1$.

Case I: $M$ is prime.
a) $M$ is prime$\implies$ $M>p_n$
b) $M\notin P$
$\therefore P$ is not the set of all primes (contradiction)

Case II: $M$ is not prime.
a) $M$ must be composite$\implies$$\exists i \ |\ p_i|M$.
b) $M\mod p_i = 1 \ \ \forall i\in\{1,2,3,\dots,n\}$
c) $M$ is divisible by a prime not in $P$.
$\therefore P$ is not the set of all primes (contradiction)

Conclusion:
$\therefore |P|=\aleph_0$

### Fundamental Theorem of Arithmetic (Pt 1)
**Theorem:** All positive integers greater than 1 can be written as a product of prime numbers.

**Proof:**
Suppose all positive integers strictly less than $n$ can be written as a product of primes.

Base case:
Element $n=2$ is prime, which is its factorization.

Case I: $n$ is prime.
a) Primes, by definition, are just their own product.

Case II: $n$ is not prime.
Suppose $m$ is a factor of n.
a) $1<m<n$
b) $n=rm$, where $r\in\mathbb{Z}$
c) By strong induction, both $r$ and $m$ can be written as a product of primes.
$\therefore n$ is also a product of primes.

### Fundamental Theorem of Arithmetic (Pt 2)
**Theorem:** All positive integers greater than 1 can be written as a **unique** product of prime numbers.

**Proof:**
Suppose the factorization is not unique.
Let $n$ be the smallest integer with two different factorizations.
$n=p_1p_2p_3\dots p_r=q_1q_2q_3\dots q_s$.
If some $p_i=q_j$, then $\dfrac{n}{p_i}=\dfrac{n}{q_j}$ also has 2 factorizations.
We assumed $n$ was the smallest integer, so we can assume all $p_i$ and $q_j$ are different.
Assume without loss of generality, $p_1<q_1$.
Consider $m=(q_1-p_1)q_2q_3\dots q_s$.
Since $q_1-p_1<q_1$, then $m<n$, so $m$ must have a unique prime factorization.
$$\begin{align}
m&=q_1q_2q_3\dots q_s - p_1q_2q_3\dots q_s\\
&=n-p_1q_2q_3\dots q_s\\
&=p_1p_2p_3\dots p_r-p_1q_2q_3\dots q_s\\
&=p_1(p_2p_3\dots p_r-q_2q_3\dots q_s)\\
&=p_1\left(\dfrac{n}{p_i}-\dfrac{n}{q_j}\right)\\
\end{align}$$
Since $p_1<q_1$, $\dfrac{1}{p_1}>\dfrac{1}{q_1}\implies\dfrac{n}{p_1}-\dfrac{n}{q_1}>0$.
Also we know that $\dfrac{n}{p_1}-\dfrac{n}{q_1}\in\mathbb{Z}$, so $p_1|m$.
But since $m$ has a unique prime factorization, and $p_1$ is a prime that divides $m$, $p_1$ bust occur in the unique factorization of $m$.

Blah blah blah anyways it's unique. I can prove this with set theory.

### Euclid's Lemma
**Theorem:** An integer $p\ge2$ is prime$\iff$whenever $a$ and $b$ are integers such that $p|ab$, then $p|a$ or $p|b$.
**Logical Statement:** $p\in P\iff \left(p|ab\implies (p|a \lor p|b)\right)$

**Proof:** $p\in P\implies \left(p|ab\implies (p|a \lor p|b)\right)$
Suppose $p\ge2$ is prime, and $a,b\in\mathbb{Z}^+$ such that $p|ab$.
Using the FTA:
Then $a=p_1^{e_1}p_2^{e_2}p_3^{e_3}\dots p_r^{e_r}$ and $b=q_1^{f_1}q_2^{f_2}q_3^{f_3}\dots q_s^{f_s}$.
Not writing all that but it's obvious to see that one of the factors must be $p$.

**Proof:** $p\in P\impliedby \left(p|ab\implies (p|a \lor p|b)\right)$
Can't be bothered.