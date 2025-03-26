**Name:** Stanley Goodwin
**Date:** 3/19/2025

---
### Problem 1
#### Problem 1.A
Compute all the cyclic subgroups in $(\mathbb{Z}/14\mathbb{Z}, +)$. Show/justify all of your work.
$$\begin{align}
\braket{0}&=\{0\} & \braket{1}&=\mathbb{Z}_{14}\\
\braket{2}&=2\mathbb{Z}_{14} & \braket{3}&=\mathbb{Z}_{14}\\
\braket{4}&=2\mathbb{Z}_{14} & \braket{5}&=\mathbb{Z}_{14}\\
\braket{6}&=2\mathbb{Z}_{14} & \braket{7}&=\{0,7\}=7\mathbb{Z}_{14}\\
\braket{8}&=2\mathbb{Z}_{14} & \braket{9}&=\mathbb{Z}_{14}\\
\braket{10}&=2\mathbb{Z}_{14} & \braket{11}&=\mathbb{Z}_{14}\\
\braket{12}&=2\mathbb{Z}_{14} & \braket{13}&=\mathbb{Z}_{14}\\
\end{align}$$
> All even generators will have the same result as $\braket{2}$ since they all share a $\gcd(n,14)=2$.
> Since $\gcd(7,14)=7$, the set for $\braket{7}$ will be reduced. I could have done this faster using the factors of $14$, but it was relevant later to do it now.
> The set of possible cyclic subgroups (including itself) are:
$$\begin{align}
\boxed{\{0\}, \{0,7\}, \{0,2,3,6,8,10,12\}, \mathbb{Z}_{14}}
\end{align}$$
---
#### Problem 1.B
From your calculations in part (a), identify all the elements of $(\mathbb{Z}/14\mathbb{Z}, +)$ that generate the
entire group.

> All numbers $0\le n<14$ who are coprime with $14$ will generate the entire group.
> That means that only $\braket{1},\braket{3},\braket{5},\braket{9},\braket{11},\braket{13}$ generate $(\mathbb{Z}/14\mathbb{Z}, +)$.
> Since I know that $\phi(14)=6$, I know I have all values that can generate this group.

#### Problem 1.C
From your calculations in part (a), identify the orders of all the elements of $(\mathbb{Z}/14\mathbb{Z}, +)$.

> We can split this into two simultaneous conditions: $n^k\equiv0\mod 7$ and $n^k\equiv0\mod 2$.
> **Note, when I use exponentiation, I'm using it generally as repeated addition operations.**
> This is is used as an example to show you what I'd do without knowing the above.
$$\begin{align}
2^{7}&\equiv0\mod 7 &\land&& 2^{1}\equiv0\mod 2& 
&\implies&& k&=\text{lcm}(7,1)=7  &\implies&& |2|&=7\\
3^{7}&\equiv0\mod 7 &\land&& 3^{2}\equiv0\mod 2& 
&\implies&& k&=\text{lcm}(2,7)=14  &\implies&& |3|&=14\\
\end{align}$$
> Instead, we can use the fact that for any cyclic group: $\braket{n}_k=k/\gcd(n,k)$, where $k$ is the order of the cyclic group and $n$ is the generator of a subgroup.
$$\begin{align}
|0|&=1 & |1|&=14\\
|2|&=7 & |3|&=14\\
|4|&=7 & |5|&=14\\
|6|&=7 & |7|&=2\\
|8|&=7 & |9|&=14\\
|10|&=7 & |11|&=14\\
|12|&=7 & |13|&=14\\
\end{align}$$

---
### Problem 2
#### Problem 2.A
Compute all the cyclic subgroups in $((\mathbb{Z}/14\mathbb{Z})^\text{x}, \cdot)$. Show/justify all of your work.

> First off, the set this refers to is all numbers coprime to $14$, and so $\left\{1,3,5,9,11,13\right\}$.
> The size of the subgroups, if they exist, must be factors of $6=2\cdot3$.
$$\begin{align}
|S|&=1:\{1\}&&\text{Trivial Subgroup}\\
|S|&=2:\{1,13\}&&\text{ Subgroup}\\
|S|&=3:\{1,9,11\}&&\text{ Subgroup}\\
|S|&=6:\{1,3,5,9,11,13\}&&\text{ Subgroup}\\
\end{align}$$
#### Problem 2.B
From your calculations in part (a), identify all the elements of $((\mathbb{Z}/14\mathbb{Z})^\text{x}, \cdot)$ that generate the entire group.

> Using what I did in part 2.C, we recognize that $\braket{n}_G\iff |G|=|n|$.
> That means that only $\braket{3},\braket{5},\braket{11}$ generate $((\mathbb{Z}/14\mathbb{Z})^\text{x}, \cdot)$.

#### Problem 2.C
From your calculations in part (a), identify the orders of all the elements of $((\mathbb{Z}/14\mathbb{Z})^\text{x}, \cdot)$.

> We can split this into two simultaneous conditions: $n^k\equiv0\mod 7$ and $n^k\equiv0\mod 2$.
> Using Fermat's Little Theorem $a^{p-1}\equiv1\mod p$, we can simplify from there.
$$\begin{align}
1^{1}&\equiv1\mod 7 &\land&& 1^{1}\equiv1\mod 2& 
&\implies&& |1|&=1=\text{lcm}(1,1)\\
3^{7-1}&\equiv1\mod 7 &\land&& 3^{2-1}\equiv1\mod 2& 
&\implies&& |3|&=6=\text{lcm}(6,1)\\
5^{7-1}&\equiv1\mod 7 &\land&& 5^{2-1}\equiv1\mod 2& 
&\implies&& |5|&=6=\text{lcm}(6,1)\\
9^{3}&\equiv1\mod 7 &\land&& 9^{2-1}\equiv1\mod 2& 
&\implies&& |9|&=3=\text{lcm}(3,1)\\
11^{7-1}&\equiv1\mod 7 &\land&& 11^{2-1}\equiv1\mod 2& 
&\implies&& |11|&=6=\text{lcm}(6,1)\\
13^{2}&\equiv1\mod 7 &\land&& 13^{2-1}\equiv1\mod 2& 
&\implies&& |13|&=2=\text{lcm}(2,1)\\
\end{align}$$

---
### Problem 3
The number $5$ is a primitive root modulo $23$.  Find two other primitive roots modulo $23$
Prove your answers are primitive roots by demonstrating they generate all elements in $\mathbb{F}^\times_{23}$.

> We want to find solutions $k\in\mathbb{Z}^\times_{23}$ such that $k^n\not\equiv1\mod23$ for $k<22$.
> The $22$ comes from $\phi(p)=p-1$, since $23$ is a prime it must be that $\phi(23)=22$.
```python
N: int = 23  
for a in range(N):  
    generated_set: set = set()  
    for b in range(N):  
        generated_set.add((a ** b) % N)  
    if len(generated_set) == 22:  
        print(f"{a=}: {generated_set}")
```
After running, I get the solutions $k\in\left\{5,7,10,11,14,15,17,19,20,21\right\}$.
$$\begin{align}
a&=5: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=7: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=10: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=11: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=14: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=15: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=17: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=19: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=20: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}\\
a&=21: \{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22\}
\end{align}$$
Given how my program was made, I had it confirm that it generated the correct group.

---
### Problem 4
Do this problem by hand (basic calculator assistance is fine), and show your work!
#### Problem 4.A
Compute the binary (base-$2$) representation of $1357$.
$$\begin{align}
1357_{10}&=1024_{10}+256_{10}+64_{10}+8_{10}+4_{10}+1_{10}\\
&=2^{10}+2^{8}+2^{6}+2^{3}+2^{2}+2^{0}\\
\Aboxed{1357_{10}&=10101001101_2}
\end{align}$$
#### Problem 4.B
Compute the base-$7$ representation of the number whose base-$5$ representation is $3414$.
$$\begin{align}
3414_5&=3\cdot5^3+4\cdot5^2+1\cdot5^1+4\cdot5^0\\
&=375+100+5+4\\
3414_5&=484_{10}\\\\
484_{10}&=343_{10}+2\cdot 49_{10}+6\cdot7_{10}+1\cdot1_{10}\\
&=1\cdot7^3+2\cdot7^2+6\cdot7^1+1\cdot7^0\\
484_{10}&=1261_7\\\\
\Aboxed{3414_5&=1261_7}
\end{align}$$
#### Problem 4.C
Compute $13^{33} \mod 31$.
Since $31$ is prime, I can exploit using Fermat's Little Theorem:
$$\begin{align}
13^{33} \mod 31&\equiv13^{31-1}\cdot13^{3} \mod 31\\
&\equiv1\cdot(169)\cdot13 \mod 31\\
&\equiv14\cdot13 \mod 31\\
&\equiv182 \mod 31\\
\Aboxed{13^{33} \mod 31&\equiv27 \mod 31}
\end{align}$$

---
### Problem 5
What are the last two digits of a base-$7$ representation of the decimal number $3^{899}$?
Show your work to justify your answer.

> This is a bit tricky, but can be solved using an extension of Fermat's Little Theorem.
> I remember seeing it in a textbook once, but it claims $a^{\phi(n)}\equiv 1\mod n$.
> Since we want the last 2 digits, we need to do the modulus base $49$.
$$\begin{align}
\phi(49)&=42 & \text{(Got this off the internet)}
\end{align}$$
> Therefore, we can rewrite our problem as:
$$\begin{align}
3^{899}&\equiv(3^{21})^{42}\cdot3^{17} & \mod 49\\
&\equiv3(3^{4})^4 & \mod 49\\
&\equiv3(81)^4 & \mod 49\\
&\equiv3(32)^4 & \mod 49\\
&\equiv3(2024)^2 & \mod 49\\
&\equiv3(44)^2 & \mod 49\\
&\equiv132\cdot44 & \mod 49\\
&\equiv34\cdot44 & \mod 49\\
&\equiv1496 & \mod 49\\
\Aboxed{3^{899}&\equiv26} & \mod 49\\
\end{align}$$

---
### Problem 6
You are trapped on a desert island with no electronic devices and you need to compute
$$\begin{align}
2416813579^{65537} \mod 59786543191
\end{align}$$
You meet a pirate (with a computer) who offers to help if you will pay him $1 for each multiplication mod $59786543191$. He’s expecting to make a lot of money on this arrangement but he doesn’t know much about number theory. 

Describe how you can complete this computation while paying the pirate less than $20. 
Include the exact amount you will need to pay the pirate in order to complete the computation.
(You don’t need to perform the calculation for this one. Just describe how it can be done efficiently, costing you less than $20. If you want to use SageMath to find the actual answer, great but it’s not necessary.)

> I've actually seen a problem like this before for taking very large powers using binary partition, and it depends on the system. However, $65537=2^{16}+1$, so a trivial idea would to ask for the following calculations to be done (in order).
> Let $n=2416813579$, then:
$$\begin{align}
n\cdot n&\equiv n^2\mod 59786543191\\
n^2\cdot n^2&\equiv n^4\mod 59786543191\\
n^4\cdot n^4&\equiv n^8\mod 59786543191\\
n^8\cdot n^8&\equiv n^{16}\mod 59786543191\\
\vdots\\
n^{32768}\cdot n^{32768}&\equiv n^{65536}\mod 59786543191\\
n^{65536}\cdot n&\equiv n^{65537}\mod 59786543191\\
\end{align}$$
> This would take 17 steps, where 16 of them are binary scaling and the last has a singular multiple of $n$ to finish off the calculation. Since you want to use less than $20, this satisfies the criterion for our problem. This was only simple since the power was very close to a power of 2. If it wasn't it would have been more challenging to find an optimal approach.

---
### Problem 7
Show your work to justify your answers.
#### Problem 7.A
How many divisors does 2025000 have?
$$\begin{align}
2025000&=45^2\cdot10^3\\
&=(5\cdot3^2)^2\cdot(2\cdot5)^3\\
&=5^2\cdot3^4\cdot2^3\cdot5^3\\
2025000&=2^3\cdot3^4\cdot5^5\\
\end{align}$$
> Looking at each power, there are as many divisors as:
$$\begin{align}
\#\text{ of divisors}&=(3+1)(4+1)(5+1)\\
&=4\cdot5\cdot6\\
\Aboxed{\#\text{ of divisors}&=120}
\end{align}$$
#### Problem 7.B
What is the sum of all the divisors of 2025000?
$$\begin{align}
\text{Sum of divisors}&=(2^0+2^1+2^2+2^3)(3^0+3^1+3^2+3^3+3^4)(5^0+5^1+5^2+5^3+5^4+5^5)\\
&=(15)(121)(3906)\\
\Aboxed{\text{Sum of divisors}&=7089390}
\end{align}$$
#### Problem 7.C
How many positive integers less than 2025000 are relatively prime to 2025000?
$$\begin{align}
\phi(2025000)&=\phi(2^3\cdot3^4\cdot5^5)\\
&=2025000\cdot\left(1-\dfrac{1}{2}\right)\left(1-\dfrac{1}{3}\right)\left(1-\dfrac{1}{5}\right)\\
&=2025000\cdot\left(\dfrac{1}{2}\right)\left(\dfrac{2}{3}\right)\left(\dfrac{4}{5}\right)\\
&=2025000\cdot\dfrac{4}{15}\\
\Aboxed{\phi(2025000)&=540000}
\end{align}$$
> This is the first time in a long time I had to use the product form of the function.
> I think this was correct, but I'm still skeptical since the number is kind of small.
