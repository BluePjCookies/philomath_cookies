---
{"dg-publish":true,"permalink":"/math/sequences-and-series/"}
---


### Arithmetic sequence
$$
u_n = u_1 + (n-1)\cdot k
$$
$$
S_n - S_{n-1} = u_n
$$
$$
S_n = \sum_{n=i}^{j}{u_1 + (n-1) \cdot k} = \frac{j-i+1}{2}\cdot{(u_i + u_j)}
$$


### Geometric sequence

$$
u_n = u_1 \cdot r^{n-1}
$$

$$
S_n = \frac{u_1 (1-r^n)}{1-r}

$$

$$
S_{\infty} = \frac{u_1}{1-r}
$$
## Binomial Expansion

$$
\begin{pmatrix} n \\r \end{pmatrix} = \frac{n!}{r! (n-r)!}
$$

$$
T_{r+1} = nCr  \cdot a^{r} \cdot b^{n-r}
$$
$$
(ax + b)^n = b^n \sum_{r=0}^{\infty} 
\begin{pmatrix} n \\ r \end{pmatrix} 
\left(\frac{ax}{b}\right)^r
$$
$$
|x| < \left|\frac{b}{a}\right|
$$

## Maclaurin Series
> [!theorem] The Weierstrass Approximation Theorem
> The Weierstrass Approximation Theorem shows that any continuous function on a compact interval can be uniformly approximated by polynomials.
> $\text{Let } f : [a, b] \to \mathbb{R} \text{ be a continuous function. } \text{Then,} \forall \varepsilon > 0, \text{there exists a polynomial } P(x)$ 
> $\text{such that}$
> $$\sup_{x \in [a, b]} |f(x) - P(x)| < \varepsilon.$$

Refer to [[Math/Notation#^310e11\|Definitions of Supremum]] if unclear.
As such, we can define $\epsilon$ to be infinitely close to 0 and have a polynomial closely fit $f(x)$.

Thus suppose any function can be expressed in terms of a polynomial
$$
f(x) \approx a_0 + a_1x + a_2x^2 + a_3x^3 \dots  
$$
or
$$
f(x) \approx \sum_{n=0}^{\infty} a_n x^n
$$

To find $a_0$, we can sub $x=0$ into $f(x)$. 
To find $a_1$, we can [[Math/Calculus#Differentiation\|differentiate]] $f(x)$ to obtain $f'(x)$. Substitute $x$ as 0, to obtain $a_1$. Thus
$$
f'(x) = a_1 + 2 a_2x + 3a_3 x^2 + 4a_4x^3 \dots 
$$
$$
\begin{split}
f(0) &= a_0\\
f'(0) &= a_1\\
f^{''} (0) &= 2 \cdot a_2\\
f^{'''}(0) &= 3\cdot 2\cdot a_3\\
f^{''''}(0) &= 4 \cdot 3 \cdot 2 \cdot 1 \cdot a_4\\
\vdots\\
f^{(n)}(0) &= n! \cdot a_n
\end{split}
$$

Thus
$$
a_n = \frac{f^{(n)}(0)}{n!}
$$
Substituting it into the approximation equation above
$$
f(x) \approx \sum_{n=0}^{\infty} \frac{f^{(n)}(0)}{n!} x^n
$$
>[!Question]
>What is the Maclaurin Series expansion for $e^x$?

Solution: Since differentiating $e^x$ is always $e^x$ and $e^0$ is $1$. Then
$$
e^x = \sum_{n=0}^{\infty}\frac{x^n}{n!}
$$
{ #fa41a8}


### Maclaurin Series expansion for $\sin$ and $\cos$

$$
\sin x = \sum_{n=0}^{\infty} \frac{(-1)^n}{(2n+1)!}x^{2n+1}
$$
$$
\cos x = \sum_{n=0}^{\infty}\frac{(-1)^n}{(2n)!}x^{2n}
$$

Refer to [[Math/Complex Numbers\|Complex Numbers]] to see the link between trigonometry and exponential functions.

