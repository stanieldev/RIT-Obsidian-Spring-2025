**Name:** Stanley Goodwin
**Date:** 3/17/2025

---

Symmetric Encryption: Same key for encryption and decryption.
Asymmetric Encryption: Different key for encryption and decryption.

### Diffie-Hellman Key Exchange
Public Info: Prime $p$, and primitive root $g$.
$$\begin{align}
\text{Alice}: && g^a\mod p\\
\text{Bob}: && g^b\mod p
\end{align}$$
These generate the public keys for Alice and Bob.
The shared value comes from raising it to the other power.
$$\begin{align}
\text{Alice}: && (g^b\mod p)^a\\
\text{Bob}: && (g^a\mod p)^b
\end{align}$$


### ElGamal Key Generation
Alice chooses a prime $p$, primitive root $g$, and a key $a$ between $0$ and $p-2$.
$$\begin{align}
h&=g^a\mod p&\implies&& \text{Public Key: }(h,g,p)
\end{align}$$
Bob picks a random number $b$ between $0$ and $p-2$.
$$\begin{align}
s&=h^b\mod p
\end{align}$$
This is a shared secret with Alice.

Bob encrypts his message as:
$$\begin{align}
c_1&=g^b\mod p\\
c_2&=ms\mod p
\end{align}$$

Alice receives the ciphertext $(c_1,c_2)$.

Alice computes
$$\begin{align}
c_1^a&=(g^b)^a\\
&=g^{ba}\\
&=(g^a)^b\\
&=h^b\\
c_1^a&=s\mod p
\end{align}$$
Then Alice computes:
$$\begin{align}
m=s^{-1}c_2\mod p
\end{align}$$


### Example
Let $p=59$, $g=2$, and $a=16$.
$$\begin{align}
(h=46,g=2,p=59)
\end{align}$$
Bob has message $m=50$, and key $b=4$.
$$\begin{align}
s&=h^b\mod p\\
s&=5\\
c_1&=16\mod 59\\
c_2&=250\mod 59
\end{align}$$
So he sends along $(c_1=16,c_2=14)$.

Alice computes
$$\begin{align}
c_1^a&=(g^b)^a\\
&=g^{ba}\\
&=(g^a)^b\\
&=h^b\\
c_1^a&=s\mod p
\end{align}$$
Then Alice computes:
$$\begin{align}
m=s^{-1}c_2\mod p
\end{align}$$
