**Name:** Stanley Goodwin
**Date:** 2/10/2025

---
### Hill Cipher
Encrypts blocks of plaintext instead of letter by letter.
This is called a *block cipher*, as opposed to a *stream cipher*.
### Guiding Idea
Suppose a block size of $n$, then we can construct a key that is an $n\times n$ invertible matrix.
Our values will be elements of $\mathbb{Z}/26\mathbb{Z}$. Take our blocks and multiply by this matrix.
### Definition
A Hill function can be written as:
$$Av=w$$
Where $A$ is the key, $v$ is the plaintext, and $w$ is the ciphertext.
### Decryption
Since $A$ is invertible, then:
$$v=A^{-1}w$$
It's very easy to break since inverse matrices are fast.
### Keys
The requirement $A$ is that it must be invertible and must have a determinant who is coprime with $26$.
### Attack
It's a linear set of equations, so it's extremely easy to break.
### Attack Example
plaintext:   `ho wa re yo ut od ay`
ciphertext: `ZW SE NI US PL JV EU`
$$\begin{align}
\begin{bmatrix}a&b\\c&d\end{bmatrix}
\begin{bmatrix}
\text{"h"}&\text{"w"}&\text{"r"}&\text{"y"}&\text{"u"}&\text{"o"}&\text{"a"}\\
\text{"o"}&\text{"a"}&\text{"e"}&\text{"o"}&\text{"t"}&\text{"d"}&\text{"y"}
\end{bmatrix}
&=
\begin{bmatrix}
\text{"Z"}&\text{"S"}&\text{"N"}&\text{"U"}&\text{"P"}&\text{"J"}&\text{"E"}\\
\text{"W"}&\text{"E"}&\text{"I"}&\text{"S"}&\text{"L"}&\text{"V"}&\text{"U"}
\end{bmatrix}
\end{align}$$
We can break this into 2 problems:
$$\begin{align}
\begin{bmatrix}a&b\end{bmatrix}
\begin{bmatrix}
\text{"h"}&\text{"w"}&\text{"r"}&\text{"y"}&\text{"u"}&\text{"o"}&\text{"a"}\\
\text{"o"}&\text{"a"}&\text{"e"}&\text{"o"}&\text{"t"}&\text{"d"}&\text{"y"}
\end{bmatrix}&=
\begin{bmatrix}
\text{"Z"}&\text{"S"}&\text{"N"}&\text{"U"}&\text{"P"}&\text{"J"}&\text{"E"}\\
\end{bmatrix}\\
\begin{bmatrix}c&d\end{bmatrix}
\begin{bmatrix}
\text{"h"}&\text{"w"}&\text{"r"}&\text{"y"}&\text{"u"}&\text{"o"}&\text{"a"}\\
\text{"o"}&\text{"a"}&\text{"e"}&\text{"o"}&\text{"t"}&\text{"d"}&\text{"y"}
\end{bmatrix}
&=
\begin{bmatrix}
\text{"W"}&\text{"E"}&\text{"I"}&\text{"S"}&\text{"L"}&\text{"V"}&\text{"U"}
\end{bmatrix}
\end{align}$$
Note: All of this is under modulus 26 arithmetic.
$$\begin{align}
\begin{bmatrix}a&b\end{bmatrix}
\begin{bmatrix}
7&22&17&24&20&14&0\\
14&0&4&14&19&3&24
\end{bmatrix}&=
\begin{bmatrix}
25&18&\text{"N"}&\text{"U"}&\text{"P"}&\text{"J"}&4\\
\end{bmatrix}\\
\begin{bmatrix}c&d\end{bmatrix}
\begin{bmatrix}
7&22&17&24&20&14&0\\
14&0&4&14&19&3&24
\end{bmatrix}&=
\begin{bmatrix}
\text{"W"}&4&8&18&\text{"L"}&21&20
\end{bmatrix}
\end{align}$$
The answer provided is:
$$\begin{align}
\begin{bmatrix}a&b\\c&d\end{bmatrix}&=\begin{bmatrix}15&11\\12&3\end{bmatrix}
\end{align}$$
Yippee!!

