**Name:** Stanley Goodwin
**Date:** 4/9/2025

---
### Rational Points on Curves
**Question:** Which points $(x,y)$, such that $x,y\in\mathbb{Q}$ lie on the unit circle?
The rational parametrization of the unit circle is:
$$\left(\dfrac{1-t^2}{1+t^2},\dfrac{2t}{1+t^2}\right)$$
Where $t\in\mathbb{Q}$, the point on the circle will also be rational.
If we let $t=\tfrac{m}{n}$, then we can rewrite it as:
$$\left(\dfrac{n^2-m^2}{n^2+m^2},\dfrac{2nm}{n^2+m^2}\right)$$
Where $n,m\in\mathbb{Q}$ where $\gcd(n,m)=1$.

### Definition of Elliptic Curves
An elliptic curve is a curve of the form:
$$y^2=x^3+ax+b$$
where $a,b$ are such that $4a^3+27b^2\neq0$.
If $4a^3+27b^2<0$, there are 3 real roots.
If $4a^3+27b^2>0$, there is 1 real root.

Points on an elliptic curve form an Abelian group.

### Elliptic Curve Addition
Our goal is to define an Abelian group where the elements are points $(x,y)$ on an elliptic curve.
#### Idea
Take 2 points, $P$ and $Q$, on the elliptic curve. Pass a line through $P$ and $Q$.
It will intersect the curve at exactly 1 more point (cubic polynomial).

Reflect that point across the x-axis and call that point $P+Q$.
By convention, we say lines "through the point at $\infty$" are vertical lines.
So, if $Q=\infty$, then the line through some point $P$ and $Q=\infty$ will be a vertical line through the point $P$.

When we pass a vertical line through $P=(x,y)$, the other point on the curve (beside $P$ and $Q=\infty$) is the reflection of $P$ across the $x$-axis.
So then when we reflect back across the $x$-axis, we see that $P+\infty=P$.

So $\infty$ is acting as an identity. If we add $P$ to its reflection, we get $\infty$.
Therefore, $(x,-y)$ is the inverse of $P=(x,y)$.

The points $(x,y)$ on an elliptic curve $y^2=x^3+ax+b$ form an Abelian group!
 - There exists an Identity element $e=\infty$.
 - There exists unique inverses $P^{-1}=(x,-y)$ such that $P+P^{-1}=e$.
#### Example
Let $E: y^2=x^3+73$. There is only 1 real root.
Let $P_1=(2,9)$ and $P_2=(3,10)$.
The line through $P_1$ and $P_2$ has slope and form:
$$\begin{align}
m&=\dfrac{10-9}{3-2}=1\\
y&=x+7
\end{align}$$
Substituting, we get:
$$\begin{align}
(x+7)^2=x^3+73\\
x^2+14x+49&=x^3+73\\
x^3-x^2-14x+24&=0\\
\end{align}$$
We know that 2 roots are found at $x=2$ and $x=3$.
We also know that the sum of the 3 roots will be $-a$ (coefficient of $x^2$).
$$\begin{align}
2+3+x&=-(-1)\\
x&=-4\\
y&=3
\end{align}$$
Which leads to the point $(-4,3)$, which is the 3rd intersect of the line on $E$.
Reflecting that across the $x$-axis, we get:
$$\begin{align}
P_1+P_2&=P_3\\
(2,9)+(3,10)&=(-4,-3)
\end{align}$$
#### Addition of a Point to Itself
Instead of the secant line, we'll need to find the tangent line instead.
In our example of $y^2=x^3+73$, lets do $P_3+P_3$ where $P_3=(-4,-3)$.

The derivative of the curve at $P_3$ is:
$$\begin{align}
2y\dfrac{dy}{dx}&=3x^2\\
\dfrac{dy}{dx}&=\dfrac{3x^2}{2y}\\
&=\dfrac{3(-4)^2}{2(-3)}\\
\Aboxed{\dfrac{dy}{dx}&=-8}
\end{align}$$
And so the tangent line is:
$$\begin{align}
y&=-8x-35
\end{align}$$
We need the 3rd point that passes through this line, and so:
$$\begin{align}
(-8x-35)^2=x^3+73\\
64x^2+560x+1225&=x^3+73\\
x^3-64x^2-560x-1152&=0\\
\end{align}$$
So we can find, with the sum of 3 roots, that:
$$\begin{align}
(-4)+(-4)+x&=-(-8)^2\\
x&=72\\
y&=-611
\end{align}$$
Our 3rd point is $(72,-611)$ and so we reflect to get $(72,611)$.
Therefore:
$$\begin{align}
P_3+P_3&=(72,611)\\
(-4,-3)+(-4,-3)&=(72,611)
\end{align}$$
