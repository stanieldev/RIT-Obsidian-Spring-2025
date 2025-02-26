**Name:** Stanley Goodwin
**Date:** 2/3/2025

---
### Problem 1
Let $n$ be a composite positive integer. Prove $n$ has a prime divisor $p$ such that $p\le\sqrt{n}$.
$$\begin{align}
n\in\mathbb{Z}^+\backslash\mathbb{P}\implies n=ab, \ a,b\in\mathbb{Z}
\end{align}$$
Lets constrain $b\ge a>1$ for the sake of brevity, making $a$ always the smaller divisor.

**Proof by Contradiction**
Suppose $a>\sqrt{n}$ and $b\ge a$ (from above), then:
$$\begin{align}
&\sqrt{n}<a\implies n<a^2\\
&a\le b\implies a^2\le ab\\
\implies&n<ab
\end{align}$$
We earlier defined $n=ab$, so this is a contradiction $\rightarrow\leftarrow$. Therefore $\boxed{a\le\sqrt{n}}$
To finish, we must take both cases of $a$ being prime and composite.

**Cases of the Minimum Divisor**
**Case 1:** $a$ is prime.
$$a\le\sqrt{n}\implies \boxed{p\le\sqrt{n}}$$
**Case 2:** $a$ is composite.
If $a$ is composite, then all primes must be less than $a$ since the only reduction would be a division by 2, and it cannot be any smaller since we assert that $a$ is not a prime.
$$\begin{align}
p&<a\\
a&\le\sqrt{n}\\
\Aboxed{p&\le\sqrt{n}}
\end{align}$$
Therefore, we can conclude that the proposition must be true that $\boxed{p\le\sqrt{n}}$.
Proof has concluded.

---
### Problem 2
Let $a, b$ be positive integers. Prove that $\gcd(a, b) = \gcd(b, a + kb)$ for any integer $k$.

Let $\gcd(a,b)=d$, then (this took me a while to get the last step):
$$\begin{align}
d\ |\ b \implies& d\ |\ kb\\
d\ |\ a \ \land\ d\ |\ kb \implies& d\ |\ (a+kb)\\
d\ |\ b \ \land\ d\ |\ (a+kb) \implies& d\ |\ \gcd(b,a+kb)
\end{align}$$
Let $\gcd(b, a + kb)=c$, then:
$$\begin{align}
c\ |\ b \implies& c\ |\ kb\\
c\ |\ (a+kb) \ \land\ c\ |\ kb \implies& c\ |\ (a+kb-kb)\\
c\ |\ b \ \land\ c\ |\ a \implies& c\ |\ \gcd(a,b)
\end{align}$$
Using the definitions of $d$ and $c$, we see that:
$$\begin{align}
d\ |\ \gcd(b,a+kb) \implies& \gcd(a,b)\ |\ \gcd(b,a+kb)\\
c\ |\ \gcd(a,b) \implies& \gcd(b,a+kb)\ |\ \gcd(a,b)
\end{align}$$
If two numbers mutually divide each other, they must be the same value, therefore:
$$\boxed{\gcd(a,b) = \gcd(b,a+kb)}$$
Proof is concluded.

---
### Problem 3
#### Problem 3.A
Use the Euclidean Algorithm to compute $d = \gcd(22110, 3267)$, showing all of your work, including the details for every step of the Euclidean Algorithm calculation.
$$\begin{align}
i&=1 & 22110&=k\cdot3267+r\\
&& 3267)22110&=6\cdot3267,2508\\\\
i&=2 & 3267&=k\cdot2508+r\\
&& 2508)3267&=1\cdot2508,759\\\\
i&=3 & 2508&=k\cdot759+r\\
&& 759)2508&=3\cdot759,231\\\\
i&=4 & 759&=k\cdot231+r\\
&& 231)759&=3\cdot231,66\\\\
i&=5 & 231&=k\cdot66+r\\
&& 66)231&=3\cdot66,33\\\\
i&=6 & 66&=k\cdot33+r\\
&& 33)66&=2\cdot33,0\\\\
\end{align}$$
Since the last value was $33$, then $\boxed{\gcd(22110, 3267)=33}$.

---
#### Problem 3.B
Find integers $m$ and $n$ such that $d = 22110m + 3267n$, where $d$ is your result from part (a). Justify your answer by showing all of the work to back-track through the steps of the Euclidean Algorithm to compute $m$ and $n$.
$$\begin{align}
i&=5 & 231&=3\cdot66+33 &&\implies& 33&=231-3\cdot66\\
i&=4 & 759&=3\cdot231+66 &&\implies& 66&=759-3\cdot231\\
i&=3 & 2508&=3\cdot759+231 &&\implies& 231&=2508-3\cdot759\\
i&=2 & 3267&=1\cdot2508+759 &&\implies& 759&=3267-1\cdot2508\\
i&=1 & 22110&=6\cdot3267+2508 &&\implies& 2508&=22110-6\cdot3267\\
\end{align}$$
Working backwards, we get:
$$\begin{align}
33&=231-3\cdot66\\
33&=231-3\cdot(759-3\cdot231)\\
33&=10\cdot231-3\cdot759\\
33&=10\cdot(2508-3\cdot759)-3\cdot759\\
33&=10\cdot2508-33\cdot759\\
33&=10\cdot2508-33\cdot(3267-1\cdot2508)\\
33&=43\cdot2508-33\cdot3267\\
33&=43\cdot(22110-6\cdot3267)-33\cdot3267\\
\Aboxed{33&=43\cdot22110-291\cdot3267{}}
\end{align}$$
Therefore $\boxed{m=43}$ and $\boxed{n=-291}$.

---
### Problem 4
Consider the following system of congruences:
$$\begin{align}
x\equiv19\mod21\\
x\equiv2\mod10\\
x\equiv1\mod13\\
\end{align}$$
#### Problem 4.A
Explain why you can be confident that there exists an integer $x$ that satisfies the above system of congruences.

Using the *Chinese Remainder Theorem*, there exists an $x$ satisfying $x\equiv a_i\mod n_i$ if the moduli are relatively prime to each other.
$$\begin{align}
21&=3\cdot7 & 10&=2\cdot5 & 13&=13
\end{align}$$
They share no prime factors, and so they are all coprime.
Therefore there must be a solution $x$ for the problem given.

---
#### Problem 4.B
Using the method we discussed in class, find an integer $x$ that satisfies the system of congruences. Show ALL of your work to fully justify your solution. (Even if you know a “faster” way to solve this, you must use the method we discussed in class to receive full credit.)
$$\begin{align}
e_1&\equiv1\mod21 & e_2&\equiv0\mod21 & e_3&\equiv0\mod21\\
e_1&\equiv0\mod10 & e_2&\equiv1\mod10 & e_3&\equiv0\mod10\\
e_1&\equiv0\mod13 & e_2&\equiv0\mod13 & e_3&\equiv1\mod13
\end{align}$$
We can then write the value of $x$ as:
$$x=19e_1+2e_2+e_3$$
We can then find these special values of $e$ as the following:
$$\begin{align}
e_1:
&&e_1&\equiv1\mod21\\
&&e_1&\equiv0\mod10\cdot13\\
&&1&=130a_1-21b_1\\\\
&&4&=130-6\cdot21\\
&&1&=21-5\cdot4\\
&&1&=21-5\cdot(130-6\cdot21)\\
&&1&=31\cdot21-5\cdot130\\\\
&&a_1&=5\\
&&b_1&=-31\\
&&\Aboxed{e_1&=-650}
\end{align}$$
$$\begin{align}
e_2:
&&e_2&\equiv1\mod10\\
&&e_2&\equiv0\mod21\cdot13\\
&&1&=273a_2-10b_2\\
\\
&&3&=273-27\cdot10\\
&&1&=10-3\cdot3\\
&&1&=10-3\cdot(273-27\cdot10)\\
&&1&=-3\cdot273+82\cdot10\\
\\
&&a_2&=-3\\
&&b_2&=82\\
&&\Aboxed{e_2&=-819}
\end{align}$$
$$\begin{align}
e_3:
&&e_2&\equiv1\mod13\\
&&e_2&\equiv0\mod10\cdot21\\
&&1&=210a_3-13b_3\\
\\
&&2&=210-16\cdot13\\
&&1&=13-6\cdot2\\
&&1&=13-6\cdot(210-16\cdot13)\\
&&1&=-6\cdot210+97\cdot13\\
\\
&&a_3&=-6\\
&&b_3&=97\\
&&\Aboxed{e_3&=-1260}
\end{align}$$
Therefore, the final solution can be found to be:
$$\begin{align}
x&=19e_1+2e_2+e_3\\
&=19(-650)+2(-819)+(-1260)\\
&=-12350-1638-1260\\
\Aboxed{x&=-15248}
\end{align}$$
This is one of many answers that could satisfy the above, and in the case cycles every $21\cdot13\cdot10=2730$, and so any multiple of that added to the solution is also a solution.

---
#### Problem 4.C
Find the smallest positive integer $x$ that satisfies the system of congruences from part (a).
Explain your answer.

To change this number to get something equal in this system, we can see that:
$$\begin{align}
x+21\cdot10\cdot13&\equiv19\mod21\\
x+21\cdot10\cdot13&\equiv2\mod10\\
x+21\cdot10\cdot13&\equiv1\mod13\\
\end{align}$$
So if we call $b=21\cdot10\cdot13=2370$, we can add and subtract that from our $x$ and it will still be a solution to our system. That means the following are solutions to the system:
$$\begin{align}
x&=-9788 && (x+2b)\\
x&=-7058 && (x+3b)\\
x&=-4328 && (x+4b)\\
x&=-1598 && (x+5b)\\
x&=+1132 && (x+6b)\\
x&=+3862 && (x+7b)\\
\end{align}$$
The smallest in value that is also positive is $\boxed{x=+1132}$.