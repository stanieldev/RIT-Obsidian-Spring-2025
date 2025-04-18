**Name:** Stanley Goodwin
**Date:** 4/17/2025

---
### Problem 1
#### Problem 1.A
Let $x^3 + ax^2 + bx + c$ be a cubic polynomial with roots $r_1, r_2, r_3$.
Show that $r_1 + r_2 + r_3 = -a$:
$$\begin{align}
p(x)&=(x-r_1)(x-r_2)(x-r_3)\\
&=(x^2-r_1x-r_2x+r_1r_2)(x-r_3)\\
&=x^3-r_1x^2-r_2x^2+r_1r_2x-r_3x^2+r_1r_3x+r_2r_3x-r_1r_2r_3\\
x^3+ax^2+bx+c&=x^3-(r_1+r_2+r_3)x^2+(r_1r_2+r_1r_3+r_2r_3)x-r_1r_2r_3\\
\end{align}$$
So we can see the following relationships:
$$\begin{align}
\Aboxed{r_1+r_2+r_3&=-a}\\
r_1r_2+r_1r_3+r_2r_3&=b\\
r_1r_2r_3&=-c\\
\end{align}$$
---
#### Problem 1.B
Write $x = x_1 - a/3$. Show that:
$$x^3+ax^2+bx+c=x_1^3+b'x_1+c'$$
where $b'=b-\tfrac{1}{3}a^2$ and $c'=c-\tfrac{1}{3}ab+\tfrac{2}{27}a^3$.
$$\begin{align}
x^3+ax^2+bx+c&=\left(x_1-\dfrac{a}{3}\right)^3+a\left(x_1-\dfrac{a}{3}\right)^2+b\left(x_1-\dfrac{a}{3}\right)+c\\\\
&=x_1^3-3x_1^2\left(\dfrac{a}{3}\right)+3x_1\left(\dfrac{a}{3}\right)^2-\left(\dfrac{a}{3}\right)^3\\
&+ax_1^2-2ax_1\left(\dfrac{a}{3}\right)+a\left(\dfrac{a}{3}\right)^2\\
&+bx_1-b\left(\dfrac{a}{3}\right)+c\\\\
&=x_1^3+\left[-3\left(\dfrac{a}{3}\right)+a\right]x_1^2+\left[3\left(\dfrac{a}{3}\right)^2-2a\left(\dfrac{a}{3}\right)+b\right]x_1+\\
&+\left[-\left(\dfrac{a}{3}\right)^3+a\left(\dfrac{a}{3}\right)^2-b\left(\dfrac{a}{3}\right)+c\right]\\\\
&=x_1^3+\left[b-\dfrac{a^2}{3}\right]x_1+\left[\dfrac{2}{27}a^3-\dfrac{1}{3}ab+c\right]\\
\Aboxed{x^3+ax^2+bx+c&=x_1^3+b'x_1+c'}
\end{align}$$
---
### Problem 2
Let $E$ be the elliptic curve $y^2 = x^3 + 7$ over the field $\mathbb{F}_{29}$.
Let $P=(0,6)$ and $Q=(3,11)$.
#### Problem 2.A
Show that $E(\mathbb{F}_{29})$ is a valid elliptic curve.
$$\begin{align}
\Delta&=-16(4a^3+27b^2)&\mod29\\
&=-16\left(4(0)^3+27(7)^2\right)&\mod29\\
&=-21168&\mod29\\
&=-27&\mod29\\
\Aboxed{\Delta&=2}&\mod29
\end{align}$$
Since the discriminant is not $0$, this is a valid elliptic curve.

---
#### Problem 2.B
Show that $P$ and $Q$ are points on the elliptic curve $E(\mathbb{F}_{29})$.
$$\begin{align}
P:y^2&\equiv x^3+7&&\mod29\\
6^2&\equiv0^3+7&&\mod29\\
36&\equiv7&&\mod29\\
\Aboxed{7&\equiv7}&&\mod29\\\\
Q:y^2&\equiv x^3+7&&\mod29\\
11^2&\equiv3^3+7&&\mod29\\
121&\equiv34&&\mod29\\
\Aboxed{5&\equiv5}&&\mod29
\end{align}$$
#### Problem 2.C
Find the point $P+Q$ on $E(\mathbb{F}_{29})$.
First we find the line passing through $P$ and $Q$:
$$\begin{align}
y&=\dfrac{11-6}{3-0}(x-0)+6 & \mod29\\
y&=\dfrac{5}{3}x+6 & \mod29\\
y&=5\cdot3^{-1}x+6 & \mod29\\
y&=5\cdot10x+6 & \mod29\\
y&=21x+6 & \mod29\\
\end{align}$$
We can then set it equal to the elliptic curve to find its intersection points.
We can also use the make-it-easier equation of:
$$\begin{align}
0+3+x&=21^2 & \mod29\\
0+3+x&=6 & \mod29\\
\Aboxed{x&=3} & \mod29
\end{align}$$
So we can find the corresponding y-value as:
$$\begin{align}
y&=-(21x+6) & \mod29\\
&=-69 & \mod29\\
\Aboxed{y&=18} & \mod29\\
\end{align}$$
And therefore $\boxed{P+Q=(3,18)}$.

---
#### Problem 2.D
Find the point $2Q$ on $E(\mathbb{F}_{29})$.

We can find the slope of the line as:
$$\begin{align}
\dfrac{dy}{dx}&=\dfrac{3x^2}{2y} & \mod29\\
&=3x^2\cdot15\cdot y^{-1} & \mod29\\
\dfrac{dy}{dx}&=16x^2\cdot y^{-1} & \mod29\\
\end{align}$$
At the point $Q=(3,11)$:
$$\begin{align}
\left.\dfrac{dy}{dx}\right|_{(3,11)}&=16(3)^2\cdot 11^{-1} & \mod29\\
&=16(3)^2\cdot 8 & \mod29\\
&=1152 & \mod29\\
m&=21 & \mod29
\end{align}$$
And so we can create a line tangent to the curve:
$$\begin{align}
y&=m(x-3)+18&\mod 29\\
&=21x-45&\mod 29\\
y&=21x+13&\mod 29\\
\end{align}$$
We can just use the slope here, so the line wasn't really needed.
$$\begin{align}
3+3+x&=21^2 & \mod29\\
3+3+x&=6 & \mod29\\
\Aboxed{x&=0} & \mod29
\end{align}$$
So we can find the corresponding y-value as:
$$\begin{align}
y&=-(21(x-3)+11) & \mod29\\
&=-(-63+11) & \mod29\\
&=52 & \mod29\\
\Aboxed{y&=23} & \mod29
\end{align}$$
And therefore $\boxed{Q+Q=(0,23)}$.

---
### Problem 3
Alice and Bob decide to do an Elliptic Curve Diffie Hellman Key Exchange. They take the elliptic curve $E$ to be $y^2 = x^3 + x + 3$ over the field $\mathbb{F}_p$ where $p=8779$, and they agree to use the base point $P=(1,1579)$. Alice chooses $a=75$ as her secret and Bob chooses $b=1909$ as his secret.
```python
def point_add(P, Q, a, p):  
    if P is None: return Q  
    if Q is None: return P  
    x1, y1 = P  
    x2, y2 = Q  
    if x1 == x2 and y1 != y2:  
        return None  # Point at infinity  
    if P == Q: m = (3 * x1 * x1 + a) * pow(2 * y1, -1, p) % p  
    else:      m = (y2 - y1) * pow(x2 - x1, -1, p) % p  
    x3 = (m * m - x1 - x2) % p  
    y3 = (m * (x1 - x3) - y1) % p  
    return (x3, y3)  
  
def scalar_mult(k, P, a, p):  
    result = None  
    addend = P  
    while k:  
        if k & 1:  
            result = point_add(result, addend, a, p)  
        addend = point_add(addend, addend, a, p)  
        k >>= 1  
    return result
```
Found this code on the internet, but I made sure it was correct since you can never trust strangers on the internet for cryptography functions.

#### Problem 3.A
What is Alice's public key?
$$\begin{align}
P&=(1,1579) &\implies&& \Aboxed{75P&=(2191, 7572)}
\end{align}$$
#### Problem 3.B
What is Bob's public key?
$$\begin{align}
P&=(1,1579) &\implies&& \Aboxed{1909P&=(8166, 5387)}
\end{align}$$
#### Problem 3.C
What is the shared key produced by the Elliptic Curve Diffie-Hellman Key Exchange?
(Demonstrate how both Alice and Bob compute this.)

**Alice**
$$\begin{align}
S&=(8166, 5387)&\implies&& \Aboxed{75S&=(8089, 6538)}
\end{align}$$
**Bob**
$$\begin{align}
S&=(2191, 7572)&\implies&& \Aboxed{1909S&=(8089, 6538)}
\end{align}$$
**Expected**
$$\begin{align}
P&=(1,1579)&\implies&& \Aboxed{(75\cdot1909)S&=(8089, 6538)}
\end{align}$$

---
### Problem 4
Bob wants to send Alice a message encrypted with Elliptic Curve Elgamal encryption. They are using the same elliptic curve and base point as Problem 4. I.e., $E$ is the curve $y^2 = x^3 + x + 3$ over the field $\mathbb{F}_p$ where $p = 8779$, and the base point is $P = (1, 1579)$.  This time you don’t know Alice’s secret key (and she isn’t using the same one as in Problem 4). But she provides her public key which is the point $(8089, 6538)$.

---
#### Problem 4.A
Bob would like to encrypt a message that encodes to the decimal number $200$. He’s worried this might not be the x-coordinate of a point on this elliptic curve. Is it? (Justify your answer.)
$$\begin{align}
y^2&=x^3+x+3 & \mod8779\\
&=200^3+200+3 & \mod8779\\
&=8000203 & \mod8779\\
y^2&=2534 & \mod8779
\end{align}$$
```python
for i in range(8779):
    val = (i ** 2) % 8779
    if val == 2534:
        print(i)
        break
else:
    print("no value found")
```
There was no value found, so there is no number in this system that squares to $2534$.
Therefore, he cannot encrypt $200$ directly, but there probably is some way to encode it otherwise that I'm not aware of yet.

---
#### Problem 4.B
Find a number close to $200$ that is the $x$-coordinate of a point on the elliptic curve and encrypt the point with that $x$ value. In either case, your answer should be the ciphertext that Bob sends to Alice (along with the point you used to do the encryption).

Similar to the code above, I found that $x=201\implies y^2=230$ works.
A modified version of it again found that the 2 square roots and their associated points are:
$$\begin{align}
M&=(478,5073) & M&=(8301,3712)
\end{align}$$
So we can use either for them to encode our value of $200$ (close enough).

Givens: $P=(1,1579)$, $K_a=(8089,6538)$, and $M=(201,478)$.
Suppose $k=256$ (random):
$$\begin{align}
C_1&=kP\\
&=256\cdot(1,1579)\\
\Aboxed{C_1&=(99, 3662)}\\\\
C_2&=M+kK_a\\
&=(201,478)+256\cdot(8089,6538)\\
&=(201,478)+(1406, 470)\\
\Aboxed{C_2&=(4893, 8558)}
\end{align}$$
So Bob sends along $\boxed{(C_1,C_2)=(\ (99, 3662),(4893, 8558)\ )}$.
