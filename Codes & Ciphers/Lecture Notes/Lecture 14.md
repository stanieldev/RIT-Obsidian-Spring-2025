**Name:** Stanley Goodwin
**Date:** 3/3/2025

---
### Rings
A ring $R$ is a non-empty set with 2 binary operations.
1. $(R,+)$ is associative and commutative group (Abelian).
2. $(R,\times)$ is associative group.
3. Distributive laws between $+$ and $\times$ follow normal algebra.

#### Examples
Let $R$ be the ring $(\mathbb{Z},+,\times)$.
1. $(\mathbb{Z},+)$ is associative and commutative group (Abelian).
2. $(\mathbb{Z},\times)$ is associative group.
3. Distributive laws work on $\mathbb{Z}$.
4. Since multiplication here is commutative, this is a commutative ring.
Let $R$ be the ring $(\mathbb{Z}/n\mathbb{Z},+,\times)$. This is a *Commutative Ring.*
Let $R$ be the ring $(M_n(\mathbb{R}),+,\times)$. This is a *Ring* since matrices are not commutative under product.

### Fields
A field is a set $F$ with 2 binary operations, $+$ and $\times$.
1. $(F,+,\times)$ is a commutative ring.
2. $(F^\text{x},\times)$ forms an abelian group. 

### Examples
1. Real numbers $(\mathbb{R},+,\times)$, are a field.
2. Rational numbers $(\mathbb{Q},+,\times)$, are a field.
3. Complex numbers $(\mathbb{C},+,\times)$, are a field.
4. Complex numbers $(\mathbb{Z},+,\times)$, are a **not** field.
5. The object $(\mathbb{Z}/p\mathbb{Z},+,\times)$, where $p\in\mathbb{P}$, *is* a field!
	1. Since all elements are relatively prime to $p$, all elements have a multiplicative inverse.
	2. We express these as $\mathbb{F}_p$, defined as $\mathbb{F}_p:(\mathbb{Z}/p\mathbb{Z},+,\times)$.
	3. This is also a finite field.

### Example
Define a field with 4 elements.
Let $F=\{0,1,\omega,\omega^2\}$ with the following rules:
1. $0+x=x$, $\forall x\in F$.
2. $x+x=0$, $\forall x\in F$.
3. $1\times x=x$, $\forall x\in F$.
4. $\omega^2=\omega+1$
5. Addition and multiplication are associative, addition is commutative.
6. Distributive law holds for addition and multiplication.
$$\begin{array}{c|cccc}
+&0&1&\omega&\omega^2\\
0&0&1&\omega&\omega^2\\
1&1&0&\omega^2&\omega\\
\omega&\omega&\omega^2&0&1\\
\omega^2&\omega^2&\omega&1&0\\
\end{array}$$
$$\begin{array}{c|ccc}
\times&1&\omega&\omega^2\\
1&1&\omega&\omega^2\\
\omega&\omega&\omega^2&1\\
\omega^2&\omega^2&1&\omega\\
\end{array}$$
Both operations form an Abelian group, therefore it's a *Field*.
This specific field is called $\text{GF}_4$, the Galois field on $4$ elements.
Generally, $\text{GF}(p^n)$ exists for all exponents of primes, called the Galois Field on $p^n$ elements.



The characteristic of a field $F$ is the least positive integer $n$ such that $nx=0$, $\forall x\in F$.
If no such integer $n$ exists, then the characteristic of $F$ is defined to be 0.
 - $\mathbb{R},\mathbb{Q},\mathbb{C}$ all have characteristic $0$.
 - $\mathbb{Z}/p\mathbb{Z}$ always has a characteristic $p$.
 - $\text{GF}_4$ has characteristic $2$.
 - $\text{GF}(p^n)$ has characteristic $p$.



### Euler's Theorem
Let $a$ and $n$ be integers such that $n>0$ and $\gcd(a,n)=1$, then:
$$a^{\phi(n)}\equiv 1\mod n$$
### Fermat's Little Theorem
Let $p$ be any prime and suppose $p\nmid a$, then:
$$a^{p-1}\equiv 1\mod p$$

Fun little proof. Assume $n^{p-1}\equiv 1\mod p$ holds. Let $a$ be an integer. Then:
$$\begin{align}
(n+ap)^{p-1}&\equiv 1\mod p\\
\sum_{k=0}^{p-1}\left(\begin{array}{c}p-1\\k\end{array}\right)(ap)^kn^{p-1-k}&\equiv 1\mod p\\
\left(\begin{array}{c}p-1\\0\end{array}\right)(ap)^0n^{p-1}+\sum_{k=1}^{p-1}\left(\begin{array}{c}p-1\\k\end{array}\right)(ap)^kn^{p-1-k}&\equiv 1\mod p\\
1\cdot1\cdot n^{p-1}+ap\sum_{k=1}^{p-1}\left(\begin{array}{c}p-1\\k\end{array}\right)(ap)^{k-1}n^{p-1-k}&\equiv 1\mod p\\
n^{p-1}&\equiv 1\mod p\\
\end{align}$$
So we only need to test $n\in[0,p)$ who are integers, instead of all integers.