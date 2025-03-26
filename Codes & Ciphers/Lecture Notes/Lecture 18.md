**Name:** Stanley Goodwin
**Date:** 3/24/2025

---
### For Exam
Units 5-8, emphasis on 5 and 8 specifically.

### Pohlig-Hellman Algorithm (Theory)
Let $p$ be a prime such that:
$$p-1=\prod_{i=1}^rp_i^{e_i}$$
and $g$ is a generator of $\mathbb{F}_p^\times$.

Let $h\in\mathbb{F}_p^\times$, we seek to find $m$ ($0\le m<p-2$) such that:
$$h=g^m\mod p$$
Let $m_i\equiv m\mod p_i^{e_i}$ and $g_i=g^{\tfrac{p-1}{p_i^{e_i}}}$, and $h_i=h^{\tfrac{p-1}{p_i^{e_i}}}$.

Claim: $\braket{g_i}$ has order $p_i^{e_i}$.
Suppose $\braket{g_i}$ has order $k$.
This means $g_i$ has order $k$.
$$g_i^k=1$$
And no $0<l<k$ will give:
$$g_i^l=1$$
Magically: $\dfrac{p-1}{p_i^{e_i}}k$ is a multiple of $p-1$, so $p_i^{e_i}|k$.
Therefore: $k=p_i^{e_i}$.


### Introduction to RSA
#### Key Generation
Alice chooses two prime numbers $p$ and $q$ (They should be roughly the same number of digits).
Alice computes $n=pq$.
Alice computes $\phi(n)=(p-1)(q-1)$.
Alice chooses an integer $e$ with $1<e<\phi(n)$ and $\gcd(e,\phi(n))=1$.
 - In practice, people often choose $e=2^{16}+1=65537$.
Alice then computes $d=e^{-1}\mod\phi(n)$. (using Euclidean Algorithm)

Alice's Public Key is $n,e$.
Alice's Private Key is $d$.


Suppose Bob wants to encrypt plaintext $m$ and send it to Alice (Where $m$ is a number modulo $n$).
Bob computes the ciphertext:
$$c=m^e\mod n$$
and sends this to Alice. Alice then computes:
$$\dots$$
#### Why does this work?
We have:
$$\begin{align}
c&\equiv m^e\mod n\\
d&\equiv e^{-1}\mod\phi(n)
\end{align}$$
But then:
$$\begin{align}
c^d&\equiv m^{ed}\mod n\\
ed&\equiv 1\mod\phi(n)
\end{align}$$
And so:
$$\begin{align}
m^{ed}&\equiv m^{1+k\phi(n)}\mod n\\
&\equiv m\cdot m^{k\phi(n)}\mod n\\
&\equiv m\cdot \left(m^{\phi(n)}\right)^k\mod n\\
&\equiv m\cdot \left(1\right)^k\mod n\\
m^{ed}&\equiv m\mod n\\
\end{align}$$

#### Example
Primes $p=113$ and $q=127$, where $n=14351$.
Totient $\phi(n)=112\cdot126=2^53^27^2$.
Take $e=13$, which is relatively prime to $\phi(n)$.

**Alice's Private Key:**
$$\begin{align}
d&\equiv e^{-1}\mod\phi(n)\\
&\equiv 13^{-1}\mod\phi(n)
\end{align}$$
We can find this through the Euclidean Algorithm:
$$\begin{align}
14112&=1085\cdot13+7\\
13&=1\cdot7+6\\
7&=1\cdot6+1
\end{align}$$
Reversing we see that:
$$\begin{align}
7&=14112-1085\cdot13\\
6&=13-1\cdot7\\
1&=7-1\cdot6
\end{align}$$
And so finally $\boxed{d=11941}$.

**Alice's Public Key:** $n=14112, e=13$
**Alice's Private Key:** $\boxed{d=11941}$

Bob wants to encrypt the message $m=5000$. And so:
$$\begin{align}
c&\equiv m^e\mod n\\
&\equiv 5000^{13}\mod 14112\\
\Aboxed{c&\equiv 3488\mod 14112}
\end{align}$$

Alice then wants to decrypt the message $c=3488$. And so:
$$\begin{align}
m&\equiv c^d\mod n\\
&\equiv 3488^{11941}\mod 14351\\
\Aboxed{m&\equiv 5000\mod 14351}
\end{align}$$
#### Why is this secure?
The security of RSA depends on it being hard to find $\phi(n)$ where $n$ is a product of 2 very large prime numbers.

#### Attacking Textbook-RSA
Since Eve knows the public key $(n,e)$, she can brute force all possible plaintext combinations.
 - This is a chosen plaintext attack.
Another problem is that RSA is Malleable.
 - If we change the plaintext predictably, the ciphertext changes predictably.

#### Fixing RSA
Given a chosen plaintext and ciphertext attaches we saw, we have to adjust to fix it.
The fix needed is to adjust the plaintext in some non-deterministic way.
 - You can do random padding to make it less obvious.

#### Optimal Asymmetric Encryption Padding
We're assuming our messages are binary strings. Our original plaintext $m$ is a sequence of $n-k_0-k_1$ bits. We will be padding this out to $n$ bits.

#### Blocking (Chunking), Method 1
Suppose we have the plaintext: "Math is Awesome"
