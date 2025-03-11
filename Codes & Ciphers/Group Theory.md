### Group
Let $G$ be a non-empty set with a binary operation $\star$ on $G$.
1. **Closure:** $G\star G\rightarrow G$.
2. **Identity:** $\exists e\ |\ e\star a = a \land a\star e = a\ \forall a\in G$
3. **Inverse:** $\forall x\in G \ \exists x^{-1} \ |\ x^{-1}\star x = e$
4. **Associative:** $a\star(b\star c)=(a\star b)\star c$
The "order" of a group, $|G|$, is the cardinality of the elements.
They are typically written as a pair of a Set and Binary Operation, like $(\mathbb{R},+)$.

### Homomorphisms
A group homomorphism is a function that relates two groups.
Given a map of group $(G,*)$ to group $(H,\star)$, then $\phi:G\rightarrow H$.

### Isomorphism
A homomorphic function that has an inverse mapping.
In other words, a bijective homomorphism.

### Subgroup
Suppose we have a group $G$, then a subgroup of $G$ is a subset of $G$ which is also a group.
$$\begin{align}
H&\le G & \text{Subgroup Notation}
\end{align}$$
It must follow the same properties of a group, just that it's a subgroup of $G$.

### Cayley Tables
| $\times$ | $1$  | $-1$ | $i$  | $-i$ |
| -------- | ---- | ---- | ---- | ---- |
| $1$      | $1$  | $-1$ | $i$  | $-i$ |
| $-1$     | $-1$ | $1$  | $-i$ | $i$  |
| $i$      | $i$  | $-i$ | $-1$ | $1$  |
| $-i$     | $-i$ | $i$  | $1$  | $-1$ |
Interesting points of note:
 - All rows and columns contain exactly 1 of each element (like Sudoku).
 - Table is symmetric$\iff$group is Commutative (Abelian).
 - Table is anti-symmetric$\iff$group is Anti-commutative.

### Lagrange's Theorem
If $H \le G$, for a finite group $G$, then $|H|$ divides $|G|$.
Statement: $H\le G \implies |H|\text{ divides }|G|$.
This doesn't make existence, just that *if* they exist, they will be that size.

#### Proof (Incomplete)
Statement: $H\le G \implies |H|\text{ divides }|G|$.
Group $G$ is a finite group with $|G|=n$.
**Case 1:** $\{e\}\le G \implies 1\text{ divides }n$
**Case 2:** $G\le G \implies n\text{ divides }n$
**Case 3:** $H\le G \land H\ne\{e\}$
 - Let $g_1\in G$ where $g_1\notin H$.
 - $g_1 H=\left\{g_1\cdot h,\ \forall h\in H\right\}$  (Left Coset)
 - $H\cap g_1 H=\emptyset$

### Normal Subgroup & Quotient Group
If we use $H$ to partition $G$, then if the cosets together make $G$, we say that $H$ is a *normal subgroup*.
If $G=\mathbb{Z}$ and $H=n\mathbb{Z}$, then they form cosets of the form $a+n\mathbb{Z}$, where $a\in\mathbb{Z}$ and $a\in[0,n)$.

The group of these cosets is called a Quotient Group.
If $G=\mathbb{Z}$ and $H=n\mathbb{Z}$, then the quotient group is $\mathbb{Z}/n\mathbb{Z}$, 
since the cosets are of the form $a+n\mathbb{Z}$, where $a\in\mathbb{Z}$ and $a\in[0,n)$.

For understanding, call them "Partition Group" because that makes wayyy more sense.

