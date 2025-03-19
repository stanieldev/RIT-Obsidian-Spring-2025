**Name:** Stanley Goodwin
**Date:** 2/19/2025

---
## Algebraic Structures
### Group (Abstract Algebra)
Define a binary operation $\star$ on a set $G$ is a binary operation such that:
$$G\star G\rightarrow G$$
**Definition**
A group $(G,\star)$ is a set $G$ with a binary operation $\star$ that satisfy:
 - **Associativity:**  $(a\star b)\star c=a\star(b\star c)$ for all $a,b,c\in G$.
 - **Identity:**           $e\in G$ where $e\star a=a$ and $a\star e=a$ for all $a\in G$.
 - **Inverses:**          $\forall a\in G$, $\exists a^{-1}$ such that $a\star a^{-1}=a^{-1}\star a=e$.

**Proposition:** The identity element of a group is unique.
Let $e$ and $e'$ be different identities of group $G$.
$$\begin{align}
e\star e'&=e & e\star e'&=e'
\end{align}$$
Therefore $e=e'$, so contradiction. Therefore there's a unique identity.

**Proposition:** The inverse element of a group's elements are unique.
Let $a'$ and $a''$ be different inverses of element $a\in G$.
$$\begin{align}
(a'\star a)\star a''&=e\star a''=a''\\
a'\star (a\star a'')&=a'\star e=a'\\
\end{align}$$
Therefore $a'=a''$, so contradiction. Therefore there's a unique identity.

An element $a$ is a unit in $\mathbb{Z}/m\mathbb{Z}$ iff $a$ has a multiplicative inverse.
