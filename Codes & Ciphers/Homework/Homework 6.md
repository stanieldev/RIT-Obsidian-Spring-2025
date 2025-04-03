**Name:** Stanley Goodwin
**Date:** 4/1/2025

**Forward**
In sections that allow code, I didn't write any blocks of code, but I used a lot of the following:
```python
k = pow(base, exponent, modulus)
d = math.gcd(a,b)
n, m = scipy.gcdex(a,b)  # For finding 1 = na + mb
```

---
### Problem 1
Alice and Bob decide to use the Diffie-Hellman Key Exchange with $p = 211$ and $g = 7$,
which is a primitive root in $\mathbb{F}_{211}^\times$.
Alice chooses $a = 11$ and Bob chooses $b = 25$.

**Powers of 7**
$$\begin{align}
7&\equiv7&\mod 211\\
7^2&\equiv49&\mod 211\\
7^3&\equiv132&\mod 211\\
7^4&\equiv80&\mod 211\\
7^8&\equiv70&\mod 211\\
7^{16}&\equiv47&\mod 211\\
\end{align}$$
#### Problem 1.A
What is Alice’s public key?
$$\begin{align}
K_A&\equiv g^A&&\mod p\\
&\equiv 7^{11}&&\mod 211\\
&\equiv 7^{8}\cdot7^3&&\mod 211\\
&\equiv 70\cdot132&&\mod 211\\
&\equiv 70\cdot132&&\mod 211\\
\Aboxed{K_A&\equiv 167}&&\mod 211
\end{align}$$
#### Problem 1.B
What is Bob’s public key?
$$\begin{align}
K_B&\equiv g^B&&\mod p\\
&\equiv 7^{25}&&\mod 211\\
&\equiv 7^{16}\cdot7^8\cdot 7&&\mod 211\\
&\equiv 47\cdot70\cdot 7&&\mod 211\\
\Aboxed{K_B&\equiv 31}&&\mod 211\\
\end{align}$$
#### Problem 1.C
What is the shared key produced by the Diffie-Hellman Key Exchange? (Demonstrate how both Alice and Bob compute this.)

**Alice's Perspective**
$$\begin{align}
K&\equiv (K_B)^A&&\mod p\\
&\equiv (31)^{11}&&\mod 211\\
&\equiv (31^2)^{5}\cdot31&&\mod 211\\
&\equiv (117)^{5}\cdot31&&\mod 211\\
&\equiv (117^2)^{2}\cdot31\cdot117&&\mod 211\\
&\equiv (185)^{2}\cdot40&&\mod 211\\
&\equiv (185)^{2}\cdot40&&\mod 211\\
&\equiv 43\cdot40&&\mod 211\\
\Aboxed{K&\equiv 32}&&\mod 211
\end{align}$$
**Bob's Perspective**
$$\begin{align}
K&\equiv (K_A)^B&&\mod p\\
&\equiv (167)^{25}&&\mod 211\\
&\equiv (167^2)^{12}\cdot167&&\mod 211\\
&\equiv (37)^{12}\cdot167&&\mod 211\\
&\equiv (37^2)^{6}\cdot167&&\mod 211\\
&\equiv (103)^{6}\cdot167&&\mod 211\\
&\equiv (103^2)^{3}\cdot167&&\mod 211\\
&\equiv (59)^{3}\cdot167&&\mod 211\\
&\equiv (59)^{2}\cdot167\cdot59&&\mod 211\\
&\equiv 105\cdot147&&\mod 211\\
\Aboxed{K&\equiv 32}&&\mod 211
\end{align}$$
---
### Problem 2
#### Problem 2.A
Bob wishes to send Alice the plaintext message $m = 62$ encrypted with Elgamal encryption.
*Alice's Public Key*: $(h=49,g=5,p=73)$.
If he picks his random $b = 33$, what is the ciphertext he sends?

**Powers of 49**
$$\begin{align}
49&\equiv49&&\mod 73\\
49^2&\equiv65&&\mod 73\\
49^4&\equiv64&&\mod 73\\
49^8&\equiv8&&\mod 73\\
49^{16}&\equiv64&&\mod 73\\
49^{32}&\equiv8&&\mod 73\\
\end{align}$$
**Shared Secret with Alice**
$$\begin{align}
s&\equiv h^b&&\mod p\\
&\equiv 49^{33}&&\mod 73\\
&\equiv 49^{32}\cdot49&&\mod 73\\
&\equiv 8\cdot49&&\mod 73\\
\Aboxed{s&\equiv 27}&&\mod 73\\
\end{align}$$
**Bob's Encryption**
$$\begin{align}
c_1&\equiv g^b&&\mod p\\
&\equiv 5^{33}&&\mod 73\\
&\equiv (5^3)^{11}&&\mod 73\\
&\equiv (52)^{11}&&\mod 73\\
&\equiv (52^2)^{5}\cdot 52&&\mod 73\\
&\equiv 3^{5}\cdot 52&&\mod 73\\
&\equiv 243\cdot 52&&\mod 73\\
\Aboxed{c_1&\equiv 7}&&\mod 73\\
\end{align}$$
$$\begin{align}
c_2&\equiv ms&&\mod p\\
&\equiv 62\cdot27&&\mod 73\\
\Aboxed{c_2&\equiv 68}&&\mod 73\\
\end{align}$$
Bob sends Alice $(7,68)$ as his encrypted message ciphertext.

#### Problem 2.B
Alice’s sister Anna has also been receiving messages encrypted with Elgamal encryption. 
*Public Key*: $(h=?,g=3,p=79)$
Her secret key is $a = 44$. She receives the ciphertext: $(74, 50)$. 
Decrypt the message and find the plaintext she was sent.

**Alice's Computation of $s$**
$$\begin{align}
74&\equiv74 & 74^2&\equiv25 & 74^4&\equiv72\\
74^8&\equiv49 & 74^{16}&\equiv31 & 74^{32}&\equiv13 & 
\end{align}$$
$$\begin{align}
s&\equiv c_1^a&&\mod p\\
&\equiv 74^{44}&&\mod 79\\
&\equiv 74^{32}\cdot74^{8}\cdot74^{4}&&\mod 79\\
&\equiv 13\cdot49\cdot72&&\mod 79\\
&\equiv 13\cdot49\cdot72&&\mod 79\\
\Aboxed{s&\equiv 44}&&\mod 79\\
\end{align}$$
**Alice's Computation of $m$
$$\begin{align}
35&=79-44\\
9&=44-35\\
8&=35-3\cdot9\\
1&=9-8\\
&=9-(35-3\cdot9)\\
&=-35+4\cdot9\\
&=-35+4\cdot(44-35)\\
&=4\cdot44-5\cdot35\\
&=4\cdot44-5\cdot(79-44)\\
\Aboxed{1&=9\cdot44-5\cdot79}\\
\Aboxed{s^{-1}&=9}
\end{align}$$
$$\begin{align}
m&\equiv s^{-1}c_2&&\mod p\\
&\equiv 9\cdot50&&\mod 79\\
&\equiv 9\cdot50&&\mod 79\\
\Aboxed{m&\equiv 55}&&\mod 79
\end{align}$$
---

### Problem 3
Let $p = 97$ and $g = 5$ (which is a primitive root in $\mathbb{F}_{97}^\times$).
$$\begin{align}
5^m\equiv h\mod 97
\end{align}$$
where we want to find $m$.

**Notes:**
Inverse in $\mathbb{Z}_{97}$: $5^{-1}\equiv 39\mod 97$, for later.
The square root: $\lfloor\sqrt{p}\rfloor=9$.

#### Problem 3.A
Compute the “baby step” values for the Shank’s Baby-Step Giant-Step algorithm.
$$\begin{align}
5^0&\equiv\ \ 1&&\mod 97 & 5^5&\equiv21&&\mod 97\\
5^1&\equiv\ \ 5&&\mod 97 & 5^6&\equiv\ \ 8&&\mod 97\\
5^2&\equiv25&&\mod 97 & 5^7&\equiv40&&\mod 97\\
5^3&\equiv28&&\mod 97 & 5^8&\equiv\ \ 6&&\mod 97\\
5^4&\equiv43&&\mod 97 & 5^9&\equiv30&&\mod 97\\
\end{align}$$
#### Problem 3.B
For the following three values of $h:\{ 8, 13, 41\}$, perform the “giant steps” part of the Shank’s Baby-Step Giant-Step algorithm to compute the discrete logs (i.e., for each $h$, find $m$ such that $h\equiv g^m\mod p$).

| $h$  | $i=0$ | $i=1$ | $i=2$ | $i=3$ | $i=4$ | $i=5$ | $i=6$ | $i=7$ | $i=8$ | $i=9$ |
| ---- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| $8$  | 8     | ...   | ...   | ...   | ...   | ...   | ...   | ...   | ...   | ...   |
| $13$ | 13    | 36    | 40    | ...   | ...   | ...   | ...   | ...   | ...   | ...   |
| $41$ | 41    | 24    | 59    | 44    | 92    | 16    | 7     | 94    | 29    | 43    |
For the second column, record the value of $i$ where the “giant step” value $hg^{-i\lfloor\sqrt{p}\rfloor}$ matched with a value in your “baby step” list.

| $h$  | $j$ |
| ---- | --- |
| $8$  | 6   |
| $13$ | 7   |
| $41$ | 4   |
For the third column, record the value of $j$ that matched in the “baby step” list. I.e., the matched value in the baby step list is $g^j$ , what was $j$? 

| $h$  | $i$ value for match | $j$ value for match |                                 | $m$ (discrete log) |
| ---- | ------------------- | ------------------- | ------------------------------- | ------------------ |
| $8$  | $0$                 | $6$                 | $8\equiv5^{0\cdot9+6} \mod 97$  | 6                  |
| $13$ | $2$                 | $7$                 | $13\equiv5^{2\cdot9+7} \mod 97$ | $25$               |
| $41$ | $9$                 | $4$                 | $41\equiv5^{9\cdot9+4} \mod 97$ | $85$               |
|      |                     |                     |                                 |                    |
For the fourth column, record the final value of m (the discrete log) found for that particular $h$. So, $h \equiv gm \mod p$. 

---
### Problem 4
Let $p = 239$ be a prime number. Let $g=7$ be a primitive root in $\mathbb{F}_{239}^\times$.
Note that $238=2\cdot7\cdot17$.

Use the Pohlig-Hellman algorithm to find $m$ such that:
$$7^m ≡ 102\mod 239$$
In the first step of the algorithm, verify that each $g_i$ you compute has order $p_i^{e_i}$ by computing the cyclic subgroup generated by $g_i$ in $\mathbb{F}_{239}^\times$, and verifying it has $p_i^{e_i}$ elements. (Doing this computation also makes the 3rd step of the algorithm quite easy.)

Calculation of $g_i$:
$$\begin{align}
g_1&=7^{238/2}\ =7^{119}\equiv238\mod 239 & |g_1|&=2\\
g_2&=7^{238/7}\ =7^{34}\ \equiv24\ \ \mod 239 & |g_2|&=7\\
g_3&=7^{238/17}=7^{14}\ \equiv211\mod 239 & |g_3|&=17\\
\end{align}$$
We can verify these values by:
$$\begin{align}
\braket{238}&=\left\{1,238\right\}\\
\braket{24}&=\left\{1, 24, 98, 201, 44, 100, 10\right\}\\
\braket{211}&=\left\{1, 211, 67, 36, 187, 22, 101, 40, 75, 51, 6, 71, 163, 216, 166, 132, 128\right\}\\
\end{align}$$
Calculate the $h_i$:
$$\begin{align}
h_1&=102^{238/2}\ =102^{119}\equiv1\ \ \ \mod 239\\
h_2&=102^{238/7}\ =102^{34}\ \equiv201\mod 239\\
h_3&=102^{238/17}=102^{14}\ \equiv22\ \mod 239\\
\end{align}$$
We can then relate the two to find the powers required:
$$\begin{align}
h_1&=g_1^{m_1} &\implies&& 1&\equiv238^0&\mod239\\
h_2&=g_2^{m_2} &\implies&& 201&\equiv24^3&\mod239\\
h_3&=g_3^{m_3} &\implies&& 22&\equiv211^5&\mod239\\
\end{align}$$
Then we get the system of equations:
$$\begin{align}
m&\equiv0&&\mod 2&\\
m&\equiv3&&\mod 7&\\
m&\equiv5&&\mod 17&\\
\end{align}$$
With the solution $\boxed{m=192}$. 
And so the discrete log of $102$ in $\mathbb{F}_{239}^\times$ is $m=192$.

I did originally do this by hand, but I kept getting the wrong answer.
I'll work on that in the future, but I'm currently busy so I'll stop here.

---
### Problem 5
Suppose Alice is using “textbook RSA” with $p = 907$, $q = 1013$, and $n = pq$.
She chooses her encryption key to be $e = 79$.

#### Problem 5.A
What is Alice’s decryption key?

**Precomputation**
$$\begin{align}
n&=pq\\
\Aboxed{n&=918,791}\\\\
\phi(n)&=(p-1)(q-1)\\
\Aboxed{\phi(n)&=916,872}
\end{align}$$
**Note:** $\gcd(e,\phi(n))=1$ is satisfied.

**Key by Euclidean Algorithm**
$$\begin{align}
ee^{-1}&\equiv 1\mod\phi(n)\\
79e^{-1}&\equiv 1\mod916,872\\
\end{align}$$
I made a program to work it backwards, finding:
$$\begin{align}
e^{-1}&\equiv464239\mod\phi(n)\\
\end{align}$$
Which means that Alice's decryption key is:
$$\begin{align}
\Aboxed{d&\equiv464239}
\end{align}$$

#### Problem 5.B
Bob wants to send Alice the plaintext message $m = 2025$. What is his ciphertext?
$$\begin{align}
c&\equiv m^e\mod n\\
&\equiv 2025^{79}\mod 918,791\\
\Aboxed{c&\equiv 870166\mod 918791}
\end{align}$$

#### Problem 5.C
Bob sends another message to Alice and his ciphertext is $c = 9999$. What was his plaintext message?

$$\begin{align}
p&\equiv c^d\mod n\\
&\equiv 9999^{464239}\mod 918,791\\
\Aboxed{p&\equiv 305957\mod 918791}
\end{align}$$
---
### Problem 6
Alice and Bob decide to use “textbook RSA” with the same modulus $n$. They pick different encryption exponents $e$ and $f$ , which are relatively prime to each other (i.e., $\gcd(e, f ) = 1$). 

Charlie wants to send the same message $m$ to both Alice and Bob. If Eve intercepts both of Charlie’s ciphertexts (and has a hunch they may be encrypted versions of the same plaintext), describe how she can recover the plaintext message $m$. (Assume Eve is also privy to the public information: $n$, $e$, $f$.)

It took me a while, but I was able to figure out a way.
Suppose we have both cipher texts. They were encrypted as the following:
$$\begin{align}
c_1&\equiv m^e\mod n\\
c_2&\equiv m^f\mod n\\
\end{align}$$
Lets suppose we raise each equation to arbitrary powers $a$ and $b$:
$$\begin{align}
c_1^a&\equiv m^{ae}\mod n\\
c_2^b&\equiv m^{bf}\mod n\\
\end{align}$$
If we then multiply each equation, we can see:
$$\begin{align}
c_1^ac_2^b&\equiv m^{ae}m^{bf} &&\mod n\\
c_1^ac_2^b&\equiv m^{ae+bf} &&\mod n\\
\end{align}$$
To find the message, we want the exponent of the message to be 1, and so:
$$\begin{align}
ae+bf&=1
\end{align}$$
We can do this through the Extended Euclidean Algorithm since we know $e$ and $f$.
From there, we find an $a,b$ such that the message is just:
$$\begin{align}
\Aboxed{m&\equiv c_1^ac_2^b &&\mod n}, & ae+bf&=1
\end{align}$$
#### Example of it

**Alice and Bob**
Let $p=76225262877999082276492141315273$ and $q=78134857121513787867555302745199$.
Let $n=pq=5955850024022287163310766406188661589446008441609011943446124327$.
Let $\phi(n)=5955850024022287163310766406188507229326008928738867896002063856$.

Let $e=7718688763562123$ and $f=8241425680726211$, where $\gcd(e, f) = 1$.
Using the `pow(b,e,m)` in python, we find that:

**Charlie's Encryption**
The message is $m=299792458$ (speed of light). Then:
$$\begin{align}
c_1&\equiv m^e&&\mod n\\
&\equiv 299792458^{7718688763562123}&&\mod n\\
c_2&\equiv m^f&&\mod n\\
&\equiv 299792458^{8241425680726211}&&\mod n\\
\end{align}$$
$$\begin{align}
c_1&\equiv 4475895022291312632440939650338056154699252933152971149219821698\\
c_2&\equiv 4000508785359862204181260309474680061676721588490006920546672452
\end{align}$$

**Eve Breaking The Message**
Using the EEA, we can find the following relationship:
$$\begin{align}
1&=x\cdot e+y\cdot f\\
x&=+2577135015179432\\
y&=-2413672567644285
\end{align}$$
So if I now raise the following encrypted messages:
$$\begin{align}
c_1^x&\equiv2234484954126993144018350445284467584547079461124316665000142550\\
c_2^y&\equiv2057442101314816864705888662650609002515919969858211846120943020\\
\end{align}$$
The product, modulo $n$, then is:
$$m=299792458$$
Heck yeah! Took me a while but it worked!

---
### Problem 7
Alice wants to send Ritchie the plaintext message "Hello RIT!" using textbook RSA.
She decides to use blocking with ASCII encoding (what we called Blocking Method 2 in class).
#### Problem 7.A
Prepare this message for RSA encryption by blocking each pair of two characters into 4 hexadecimal digits using ASCII encoding. (Your answer to this part should be 5 decimal numbers that encode the plaintext message (including capitalization, spaces, and punctuation.)

The message is: `4865 6C6C 6F20 5249 5421`.
In decimal, this reads: `18533 27756 28448 21065 21537`.

#### Problem 7.B
Take $n = 34393$ and $e = 11$ and perform the RSA encryption on the message (using the decimal numbers you calculated in part (a)). You can give your answer as 5 decimal numbers or you could convert them to hexadecimal and give your answer as a string of 20 hex digits.
$$\begin{align}
c_1&\equiv 18533^{11}\equiv \ \ 4694 &&\mod n\\
c_2&\equiv 27756^{11}\equiv 12457 &&\mod n\\
c_3&\equiv 28448^{11}\equiv 11295 &&\mod n\\
c_4&\equiv 21065^{11}\equiv \ \ 6171 &&\mod n\\
c_5&\equiv 21537^{11}\equiv \ \ 3573 &&\mod n\\
\end{align}$$
Or in Hexadecimal (in blocks of 5), we get: `0x1256 0x30a9 0x2c1f 0x181b 0xdf5`



