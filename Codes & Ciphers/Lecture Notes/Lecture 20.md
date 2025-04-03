**Name:** Stanley Goodwin
**Date:** 3/31/2025

---

### Digital Signatures
Assume both Alice and Bob have RSA public keys established.

|                   | Alice | Bob   |
| ----------------- | ----- | ----- |
| Encoding Function | $e_A$ | $e_B$ |
| Decoding Function | $d_A$ | $d_B$ |
The following transaction then shows:
$$\begin{align}
d_B(e_A(d_A(e_B(m))))=m
\end{align}$$

### Security of RSA
The security of RSA is factoring the modulus $n$.
If Eve can factor $n=p\cdot q$, she can compute the decryption.


### Euler's Criterion
Let $p$ be an odd prime, and $a$ be relatively prime to $p$. Then:
$$\begin{align}
a^{\tfrac{p-1}{2}}&\equiv\begin{cases}+1\mod p & \exists x | a\equiv x^2\mod p\\-1\mod p & \not\exists x | a\equiv x^2\mod p\end{cases}
\end{align}$$
**Proof of Equation**
$$\begin{align}
a^{p-1}&\equiv 1\mod p\\
a^{p-1}-1&\equiv0\mod p\\
\left(a^{\tfrac{p-1}{2}}+1\right)\left(a^{\tfrac{p-1}{2}}-1\right)&\equiv0\mod p\\
\end{align}$$
The integers mod $p$ ($\mathbb{Z}_p$) form a field which implies that one of these factors is $0\mod p$.
If $a\equiv x^2\mod p$, then:
$$\begin{align}
a^{\tfrac{p-1}{2}}&\equiv (x^2)^{\tfrac{p-1}{2}}\mod p\\
&\equiv x^{p-1}\mod p\\
\Aboxed{a^{\tfrac{p-1}{2}}&\equiv 1\mod p}
\end{align}$$
When it's not, we get the second condition instead.


### Rabin Cryptosystem
#### Key Generation
Choose two large primes $p$ and $q$ such that:
$$\begin{align}
p\equiv3\mod4\\
q\equiv3\mod4
\end{align}$$
Compute $n=pq$. Then Public Key is $n$ and Private Key is $(p,q)$.
#### Encryption
Suppose the plaintext $m$ is an integer less than $n$. Bob computes:
$$\begin{align}
c\equiv m^2\mod n
\end{align}$$
This is the ciphertext.
#### Decryption
Compute:
$$\begin{align}
m_p\equiv c^{(p+1)/4}\mod p\\
m_q\equiv c^{(q+1)/4}\mod q\\
\end{align}$$
Use the Extended Euclidean Algorithm to find $y_p$ and $y_1$ such that:
$$\begin{align}
y_pp+y_qq=1
\end{align}$$
Then compute:
$$\begin{align}
r\equiv(y_ppm_q+y_qqm_p)\mod n\\
s\equiv(y_ppm_q-y_qqm_p)\mod n\\
\end{align}$$
The values $\pm r, \pm s$ are your 4 square roots of $c$ mod $n$.
One of them is the original plaintext message $m$.

#### Example
Let $p=11$ and $q=23$, then $n=253$.

Bob wants to encrypt the message $m=158$, and so:
$$\begin{align}
c\equiv158^2\equiv170\mod 253
\end{align}$$
So the ciphertext is $170$.

Alice then computes:
$$\begin{align}
m_p\equiv 170^{(11+1)/4}\equiv 4\mod 11\\
m_q\equiv 170^{(23+1)/4}\equiv 3\mod 23\\
\end{align}$$

Use the Extended Euclidean Algorithm to find $y_p$ and $y_1$ such that:
$$\begin{align}
y_pp+y_qq=1
\end{align}$$
Then compute:
$$\begin{align}
r\equiv(y_ppm_q+y_qqm_p)\mod n\\
s\equiv(y_ppm_q-y_qqm_p)\mod n\\
\end{align}$$
The values $\pm r, \pm s$ are your 4 square roots of $c$ mod $n$.
One of them is the original plaintext message $m$.


#### Security
**Theorem:** Breaking the Rabin system is as difficult as factoring the Rabin modulus.
It's hard to break it, so this encryption is relatively secure for large primes.
