**Name:** Stanley Goodwin
**Date:** 2/5/2025

---
## Affine Ciphers
### Guiding Idea
We can describe a generalized shift cipher as:
$$x\rightarrow x+k\mod 26$$
Where $k$ is the key (shift amount).
Affine Ciphers are a generalization of this.
### Definition
An affine function can be written as:
$$x\rightarrow\alpha x+\beta\mod 26$$
Where $\alpha,\beta\in\mathbb{Z}$ and $\gcd(\alpha,26)=1$.
The keys of the cipher are $\alpha$ and $\beta$.
### Decryption (Example)
Let's take the example of $\alpha=3$ and $\beta=2$, then:
$$y\equiv 3x+2\mod 26$$
Inverting the function for $x$ as the plaintext, then:
$$y-2\equiv 3x\mod 26$$
To solve $x$, we need a multiplicative inverse of $3$ in $\mathbb{Z}/26\mathbb{Z}$


### Decryption (General)
Let's take the example of $\alpha=3$ and $\beta=2$, then:
$$y\equiv\alpha x+\beta\mod 26\implies y-\beta\equiv\alpha x\mod 26$$
To solve $x$, we need a multiplicative inverse of $\alpha$ in $\mathbb{Z}/26\mathbb{Z}$.
What is $\alpha^{-1}$ in $\mathbb{Z}/26\mathbb{Z}$? It is the solution of:
$$\alpha k\equiv 1\mod26$$
We can then use that to find the inverse function:
$$\begin{align}
y-\beta\equiv\alpha x\mod 26\\
k(y-\beta)\equiv k\alpha x\mod 26\\
k(y-\beta)\equiv x\mod 26\\
\end{align}$$
Therefore, the final solution comes to be:
$$\begin{align}
\alpha^{-1}(y-\beta)\equiv x\mod 26\\
\end{align}$$
### Keys
The requirement for $\alpha$ is that it must satisfy $\gcd(\alpha,26)=1$, and so:
$$|\alpha|=\phi(26)=12$$
For Beta, it can take $26$ different values, and so the total permutation count comes to:
$$|\alpha|\cdot|\beta|=12\cdot26=312$$
### Attacks
We can brute force exhaustion attack affine ciphers since there are only $312$ combinations.
### Attack Example
We're given the following string: $\text{th}\rightarrow\text{YQ}$.
This allows us to write it as:
$$\begin{align}
19\alpha+\beta\equiv24\mod 26\\
7\alpha+\beta\equiv16\mod 26\\
\end{align}$$
We can find that $\alpha=5$ and $\beta=7$.
### Attack Exercise
Given the string `XA LSUFS OL QLSP N PLSF WFSQFJO ZAXLA`, find the key and plaintext.
alpha=19, beta=13, output='IN ORDER TO FORM A MORE PERFECT UNION'
I solved this through brute force.

## Matrix Review
An inverse matrix $\exists A^{-1}\iff\gcd(\det A, n)=1$ for modulus $n$.
