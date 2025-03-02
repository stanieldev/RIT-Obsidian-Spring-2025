**Name:** Stanley Goodwin
**Date:** 2/26/2025

---
### Order of a Group
If $G$ is a finite group, then $|G|=\text{\# of elements}$ in the set.
### Order of an Element
Let $a\in G$, where $G$ is a group, and $a$ is an element of $G$.
The order of $a$ is the smallest positive integer $n$ such that $|a|=n\implies a^n=e$.
If there is no value of $n$ to do so, then the order of $a$ is infinite.

### Examples
What is the order of $1$ in $(\mathbb{Z},+)$?
 - $1$ has infinite order, since $1+1+1+1+\dots$ never equals $0$.
What are the orders of the elements in $(\mathbb{Z}_4,+)$?
 - $0$ gets to $0$ with 1 iteration $\implies |0|=1$
 - $1$ gets to $0$ with 4 iterations$\implies |1|=4$
 - $2$ gets to $0$ with 2 iterations$\implies |2|=2$
 - $3$ gets to $0$ with 4 iterations$\implies |3|=4$
What are the orders of the elements in $((\mathbb{Z}/9\mathbb{Z})^\text{x},\times)$?
 - $1$ gets to $1$ with 1 iteration  $\implies |1|=1$
 - $2$ gets to $1$ with 6 iterations $\implies |2|=6$
 - $4$ gets to $1$ with  iterations $\implies |4|=$
 - $5$ gets to $1$ with  iterations $\implies |5|=$
 - $7$ gets to $1$ with  iterations $\implies |7|=$
 - $8$ gets to $1$ with  iterations $\implies |8|=$

### Connection of the Orders
If $G$ is a cyclic group, and if $a$ is a generator, then $|a|=|G|$.

### Proposition
Let $G$ be a cyclic group of order $n$ and $a$ is a generator, then:
$$a^k=e\iff n|k$$

### Theorem
Let $G$ be a cyclic group of order $n$ and suppose $a\in G$ is a generator of $G$.
If $b=a^k$, then $|b|=n/\gcd(k,n)$.
