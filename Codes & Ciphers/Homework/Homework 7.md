**Name:** Stanley Goodwin
**Date:** 4/9/2025

---
### Problem 1
Alice and Bob are using the Rabin crypto-system.
Alice chooses $p = 907$, $q = 719$, and $n = pq = 652133$. 
Alice receives ciphertext $c = 543879$ from Bob. 
Perform Rabin decryption to find the four candidate values for the original plaintext Bob sent to Alice. (Your answer should be 4 positive numbers each less than $n$.)
#### Decryption

| Power   | $1$ | $2$ | $4$ | $8$ | $16$ | $32$ | $64$ | $128$ |
| ------- | --- | --- | --- | --- | ---- | ---- | ---- | ----- |
| $586^n$ | 586 | 550 | 469 | 467 | 409  | 393  | 259  | 870   |
| $315^n$ | 315 | 3   | 9   | 81  | 90   | 191  | 531  | 113   |
Alice computes the following:
$$\begin{align}
m_p&\equiv 543879^{(907+1)/4} &&\mod 907\\
&\equiv 543879^{227} &&\mod 907\\
&\equiv (907\cdot599+586)^{227} &&\mod 907\\
&\equiv 586^{227} &&\mod 907\\
&\equiv 586^{128}\cdot586^{64}\cdot586^{32}\cdot586^{2}\cdot586 &&\mod 907\\
&\equiv (870\cdot259)\cdot(393\cdot550)\cdot586 &&\mod 907\\
&\equiv 394\cdot284\cdot586 &&\mod 907\\
\Aboxed{m_p&\equiv 398} &&\mod 907\\
\end{align}$$
$$\begin{align}
m_q&\equiv 543879^{(719+1)/4} &&\mod 719\\
&\equiv 543879^{180} &&\mod 719\\
&\equiv (756\cdot719+315)^{180} &&\mod 719\\
&\equiv 315^{180} &&\mod 719\\
&\equiv 315^{128}\cdot315^{32}\cdot315^{16}\cdot315^{4} &&\mod 719\\
&\equiv (113\cdot191)\cdot(90\cdot9) &&\mod 719\\
&\equiv 13\cdot91 &&\mod 719\\
\Aboxed{m_q&\equiv 464} &&\mod 719\\
\end{align}$$
She then computes:
$$\begin{align}
\gcd(p,q)&=\gcd(907, 719)\\
907&=1\cdot719+188\\
719&=3\cdot188+155\\
188&=1\cdot155+33\\
155&=4\cdot33+23\\
33&=1\cdot23+10\\
23&=2\cdot10+3\\
10&=3\cdot3+1
\end{align}$$
$$\begin{align}
10-3\cdot3&=1\\
10-3\cdot(23-2\cdot10)&=1\\
-3\cdot23+7\cdot10&=1\\
-3\cdot23+7\cdot(33-1\cdot23)&=1\\
7\cdot33-10\cdot23&=1\\
7\cdot33-10\cdot(155-4\cdot33)&=1\\
-10\cdot155+47\cdot33&=1\\
-10\cdot155+47\cdot(188-1\cdot155)&=1\\
47\cdot188-57\cdot155&=1\\
47\cdot188-57\cdot(719-3\cdot188)&=1\\
-57\cdot719+218\cdot188&=1\\
-57\cdot719+218\cdot(907-1\cdot719)&=1\\
\Aboxed{218\cdot907-275\cdot719&=1}
\end{align}$$
With that, she finds $p=907, m_p=398, y_p=218$ and $q=719, m_p=464, y_p=-275$.
$$\begin{align}
r\equiv(y_ppm_q+y_qqm_p)\mod n\\
s\equiv(y_ppm_q-y_qqm_p)\mod n\\
\end{align}$$
Plugging in the values she has, then:
$$\begin{align}
r&\equiv(y_ppm_q+y_qqm_p)&&\mod n\\
&\equiv(218\cdot907\cdot464+(-275)\cdot719\cdot398)&&\mod 652133\\
&\equiv446244-438590&&\mod 652133\\
\Aboxed{r&\equiv7654}&&\mod 652133\\\\
s&\equiv(y_ppm_q-y_qqm_p)&&\mod n\\
&\equiv(218\cdot907\cdot464-(-275)\cdot719\cdot398)&&\mod 652133\\
&\equiv446244+438590&&\mod 652133\\
\Aboxed{s&\equiv232701}&&\mod 652133\\
\end{align}$$
So the 4 possible messages are:
$$\begin{align}
\boxed{m\in\left\{7654, 232701, 419432, 644479\right\}}
\end{align}$$
#### Encryption
To check validity, we can re-encrypt to see if we recover the ciphertext.
$$\begin{align}
c\equiv7654^2\equiv543879\mod 652133\\
c\equiv232701^2\equiv543879\mod 652133\\
c\equiv419432^2\equiv543879\mod 652133\\
c\equiv644479^2\equiv543879\mod 652133\\
\end{align}$$
All of them evaluate to the correct ciphertext, so I think I did it correctly.

---
### Problem 2
#### Problem 2.A
In a family of five, what is the probability that all of their birthdays are in different months? (Assume all birth months are equally likely.)
$$\begin{align}
p&=\dfrac{n!}{(n-k)!}\cdot n^{-k}\\
&=\dfrac{12!}{(12-5)!}\cdot 12^{-5}\\
&=\dfrac{12\cdot11\cdot10\cdot9\cdot8}{12\cdot12\cdot12\cdot12\cdot12}\\
\Aboxed{p&=\dfrac{55}{144}\approx0.3819}
\end{align}$$
I thought of it like a bag with 12 months on pieces of paper, then had a person in the family draw from it and find out how many of them there were compared to if they replaced them after draw.
#### Problem 2.B
A 4-digit numerical PIN is used on ATM cards. How many ATM cards do you need to collect before it is more likely than not that at least two of them have the same 4-digit PIN? (Assume all 4-digit PINs are equally likely; you may use the approximation method we talked about in class for this.)
$$\begin{align}
p&=\dfrac{n!}{(n-k)!}\cdot n^{-k}\\
\dfrac{1}{2}&=\dfrac{(10000)!}{(10000-k)!}\cdot 10000^{-k}\\
1&=2\dfrac{(10000)!}{(10000-k)!}\cdot 10000^{-k}\\
\end{align}$$
I'm going to use Stirling's approximation since this factorial is HUGE.
$$\begin{align}
p&=\dfrac{n!}{(n-k)!}\cdot n^{-k}\\
&\approx\dfrac{\sqrt{2\pi n}}{\sqrt{2\pi (n-k)}}\dfrac{n^n}{(n-k)^{n}(n-k)^{-k}}\dfrac{e^{-n}}{e^{-n}e^k}\cdot n^{-k}\\
&\approx\sqrt{\dfrac{n}{n-k}}\dfrac{n^n}{(n-k)^{n}}\dfrac{1}{e^k}\dfrac{(n-k)^{k}}{n^{k}}\\
&\approx\dfrac{1}{e^k}\sqrt{\dfrac{n}{n-k}}\left(\dfrac{n}{n-k}\right)^{n-k}\\
&\approx\dfrac{1}{e^k}\sqrt{\dfrac{n}{n-k}}\left(1-\dfrac{k}{n}\right)^{k-n}\\
\Aboxed{p&\approx\dfrac{1}{e^k}\left(1-\dfrac{k}{n}\right)^{k-n-\tfrac{1}{2}}}
\end{align}$$
From there, we can calculate it for $p=1/2$ and $n=10,000$ as:
$$\begin{align}
p&\approx\dfrac{1}{e^k}\left(1-\dfrac{k}{n}\right)^{k-n-\tfrac{1}{2}}\\
\dfrac{1}{2}&\le\dfrac{1}{e^k}\left(1-\dfrac{k}{n}\right)^{k-n-\tfrac{1}{2}}\\
\end{align}$$
This threshold occurs when $\boxed{k=119}$.
Therefore, you'd need about $119$ cards on average to find that there is greater than a 50% chance that two of the cards have the same pin.

If you write a program that can handle these super huge factorials:
```python
import math
def proportion(k):
	N = 10000
	return math.perm(N,k) / (N ** k)
```
You find the true solution is around $\boxed{k=119}$ cards, as calculated before.

#### Problem 2.C
If you use the approximation method we talked about in class for part (b), you will not get the same value as if you compute the probabilities directly. How much is the approximation off in this case, and what is the precise answer for part (b)?

When I use my approximation (sterling's), I find that:
$$\begin{align}
k&=118 & p&=0.5000638082722146\\
k&=119 & p&=0.49416305575628666
\end{align}$$
When I used my exact version, I got:
$$\begin{align}
k&=118 & p&=0.5000637585119401\\
k&=119 & p&=0.4941630061614992
\end{align}$$
Then the error can be calculated as:
$$\begin{align}
k&=118 & |\Delta p|&=4.9761\cdot10^{-8} & \text{error}&=9.9508\cdot10^{-8}\\
k&=119 & |\Delta p|&=4.9595\cdot10^{-8} & \text{error}&=1.0037\cdot10^{-7}
\end{align}$$
With the equation we found in class:
$$\begin{align}
k&\approx117.7410
\end{align}$$
This is actually pretty close, being within about 2 of the real answer.
For an estimate, especially in the asymptotic limit as $N\rightarrow\infty$, this is pretty good.

---
### Problem 3
Use the Pollard rho algorithm to complete the prime factorization of the number $31519267979$. You will need to use the algorithm multiple times but you may ONLY use the Pollard rho algorithm to find (or prove) the factorization. (Show all of your work, and document the steps you follow (including any code or computing assistance you used). You are allowed to “know” what the primes < 100 are without proof.) Note: Use of Sage is highly recommended for this one!

Let $n=31519267979$, with function $f(x)=x^2+1\mod n$.
Let $x=2$ and $y=2$.

| $x$ | $y$         | $\|x-y\|$   | $\gcd(\|x-y\|,n)$ |
| --- | ----------- | ----------- | ----------------- |
| 5   | 26          | 21          | 1                 |
| 26  | 458330      | 458304      | 1                 |
| 677 | 20651687416 | 20651686739 | 1843              |
So 1843 is a factor. Let $n=17102153$.

| $x$     | $y$     | $\|x-y\|$ | $\gcd(\|x-y\|,n)$ |
| ------- | ------- | --------- | ----------------- |
| 5       | 26      | 21        | 1                 |
| 26      | 458330  | 458304    | 1                 |
| 677     | 9388745 | 9388068   | 1                 |
| 458330  | 7084572 | 6626242   | 1                 |
| 643602  | 4644206 | 4000604   | 1                 |
| 9388745 | 3591405 | 5797340   | 289867            |
So 289867 is also a factor. Let $n=59$.
The number $59$ is a known prime, and so the final factorization is:
$$\boxed{31519267979=59\cdot1843\cdot289867}$$
The code I actually used was the python terminal with the following:
```python
from math import gcd
a = pow(a,2,N)+1  # repeated gave me the table
```

---
### Problem 4
#### Problem 4.A
Find at least one Miller-Rabin non-witness for the compositeness of $n = 561$ and at least one Miller-Rabin witness (which proves 561 is composite). Justify your answer fully (including any code or computing assistance you used).

```python
import math  
N = 561  # Composite number  
S = 4    # Highest power of 2 that divides N-1  
D = 35   # Odd number such that N-1 = 2^S * D  
  
# Function to check if a base 'a' is a witness  
def miller_rabin_test(a):  
    x = pow(a, D, N)  
    if x == 1 or x == N - 1:  
        return False      # Not a witness  
    for i in range(1, S):  
        x = pow(x, 2, N)  
        if x == N - 1:  
            return False  # Not a witness  
    return True           # Is a witness to composite
  
# Loop through all bases  
for a in range(2, N):  
    TEST = miller_rabin_test(a)  
    if TEST:  
        print(f"{a} is a witness to the compositeness of {N}.")  
    elif not TEST:  
        print(f"{a} is not a witness (N might be prime for this base).")
```
I found the following non-witnesses:
$$\{50,101,103,256,305,458,460,511, 560\}$$
All other numbers are witnesses to 561's primality. Examples:
$$\{2,3,4,5,6,7,\dots,48,49\}$$

#### Problem 4.B
The value $8976397$ is a prime number. Describe how you would go about proving this with the Miller-Rabin test. (You don’t need to implement this, just describe what you would need to do to be convinced this number was prime using Miller-Rabin. Be specific about what calculations you would need to do to prove this specific number is prime.)

Let $n=8976397$. We can find that $8976397-1=2^2\cdot2244099$.
The deterministic upper-bound for $a$ is:
$$a=\lfloor2\ln(8976397)^2\rfloor=512$$
We would need to check all $a$ such that $2\le a\le 512$ to ensure prime-ness.

We'd need to ensure that:
$$\begin{align}
a^{2244099}\equiv\pm 1\mod 8976397\\
\end{align}$$
And either of the two are satisfied:
$$\begin{align}
a^{2\cdot2244099}\equiv-1\mod 8976397\\
a^{4\cdot2244099}\equiv-1\mod 8976397\\
\end{align}$$
If we can show this for all $a$ from above, then it must be prime.

Using a modified version of the code I had above, $n$ actually is prime.
There are no witnesses of $a$ between 2 and 512, and so it must be prime!
