---
{"dg-publish":true,"permalink":"/math/complex-numbers/","dgPassFrontmatter":true,"noteIcon":""}
---

## Introduction
An imaginary is defined as $i$ with the following property

$$
i^2 = -1
$$
It corresponds to a $\frac{\pi}{2} rad$ anti-clockwise rotation in the Argand plane 

A complex number is defined as. 
$$
z = a + ib
$$
### Euler's Identity

$$e^{i \theta} = \cos \theta + i \sin \theta$$
#### Proof using Maclaurin Series
[[Math/Derivations/Proof for Euler's Identity using Maclaurin Series\|Proof for Euler's Identity using Maclaurin Series]]

#### Alternative Proof using Calculus
[[Math/Derivations/Proof for Euler's Identity using ODEs\|Proof for Euler's Identity using ODEs]]

### Polar Form
A vector has an angle $\theta$ and a magnitude $r$. It should be self-evident that we can rewrite this using Eulers Identity.
$$
z = r(\cos \theta + i \sin \theta) = re^{i \theta}
$$
The angle $\theta$ can be sufficiently described using this range.

$$
- \pi \leq \theta \leq \pi
$$

The magnitude of a complex number can be expressed as $r = \sqrt{a^2 + b^2} = ||z||$
### Conjugate 
The conjugate of $z$ is 
$$
z^* = a - ib
$$
Or
$$
z^* = re^{-i \theta}
$$
Thus
$$
||z||^2 = z \cdot z^*
$$
### Scaling & Rotations
A complex number **encodes** a rotation and a scaling. When $a$ is multiplied with $b$ where $a,b \in \mathbb{C}$
$$
a \cdot b = r_1r_2 e^{i (\theta_1 + \theta_2)}
$$

$a$ acts on $b$ by scaling it by $r_1$ and rotating it by $\theta_1$

> [! Info] Fun Fact
> Complex numbers can also help us encode rotations in 3d space! It's called Quaternions, but you'll need 4 dimension, 1 real and 3 imaginary part. It powers most gaming/3d simulation software. 

### Argument
Argument is basically the angle between the vector and the x-axis.
$$
arg(z) = arg(re^{i \theta}) = \theta
$$

Hopefully it is obvious that

$$
arg(z_1 \cdot z_2) = arg(z_1) + arg(z_2)
$$
### De Moivre's Theorem

Based on the above, it's pretty evident that 
$$
z^n = r^n e^{in \theta} = r^n \left( \cos n\theta + i \sin n \theta\right)
$$
Correspondingly 
$$
z^{\frac{1}{n}} = r^{\frac{1}{n}} \left( \cos \frac{1}{n} \theta + i \sin \frac{1}{n} \theta\right)
$$
## Solving for nth roots

Solve for 
$$
z^n = C
$$
Fundamental theorem of algebra state that there exist $n$ number of solutions

1. Express C in polar form
2. Apply the De Moivre's theorem to solve for $z$
3. Find the suitable values of $k$

> [! example] Example
> Solve for 
> $$
> z^5 = 1 + i 
> $$
1. Express $1 + i$ in polar form 
$$
1+i = \sqrt{2} \cdot e^{i \left(\frac{\pi}{4} + 2 \pi k\right)}
$$
2. Apply De Moivre's theorem

$$
z = (1 + i)^{\frac{1}{5}} = 2^{\frac{1}{10}}e^{i \left( \frac{\pi}{20} + \frac{2 k \pi}{5}\right)}
$$
3. Find the values of $k$
Since $-\pi \leq \theta \leq \pi$. Thus $k \in \{ -2, -1, 0 , 1, 2\}$
$\therefore QED$

## Expressing $\cos n \theta$, $\sin n \theta$ in terms of $\cos^k \theta$ and $\sin^k \theta$.
Expanding the expression using De Moivre theorem and algebra will yield different results. This allows you to equate and express $\cos n \theta$ and $\sin n \theta$ in unique ways
$$
(\cos \theta + i\sin \theta)^n
$$
1. Expand it algebraically
2. Expand it using De Moivre theorem
3. Equate the reals and imaginaries 

>[! Example]
> Expand $(\cos \theta + i \sin \theta)^3$. Express $\cos 3 \theta$ and $\sin 3 \theta$ in terms of $\cos^k\theta$ and $\sin^k \theta$.

 1. Algebraically
$$
\begin{split}
(\cos \theta + i \sin \theta)^3 &=  \cos^3θ+3\cos^2 \theta (i\sin\theta)+3\cos \theta(i \sin \theta)^2 +(i \sin \theta)^3\\
&= (\cos^3 \theta - 3 \cos \theta \sin^2 \theta) + i (3 \cos^2 \theta \sin \theta - \sin^3 \theta)
\end{split}
$$
2. De Moivre theorem
$$
(\cos \theta + i \sin \theta)^3 = \cos 3 \theta + i \sin 3 \theta
$$
3. Equate the imaginary and real parts. 
Equating the real part
$$
\begin{split}
\cos 3\theta &= \cos^3 \theta - 3 \cos \theta \sin^2 \theta \\
&= \cos^3 \theta - 3 \cos \theta (1 - \cos^2 \theta) \\
&= 4 \cos^3 \theta - 3 \cos \theta
\end{split}
$$
Equating the imaginary part:

$$
\begin{split}
\sin 3\theta &= 3 \cos^2 \theta \sin \theta - \sin^3 \theta \\
&= 3 (1 - \sin^2 \theta) \sin \theta - \sin^3 \theta \\
&= -4 \sin^3 \theta + 3 \sin \theta
\end{split}
$$

## Interesting question

![Pasted image 20250905153329.png](/img/user/Images/Pasted%20image%2020250905153329.png)

Given $n$ lighthouses along a unit circle, suppose an observer is standing inside one of the lighthouse. Find and Express the product of the distance between the observer and all other lighthouses, ($d_0 \cdot d_1 \cdot d_2 \dots$) in terms of $n$.

### Solution

Consider an Argand diagram. The $n$ roots of $x^n = 1$ are spaced equidistance apart along a unit circle. Recall roots of unity.
$$
x^n =1
$$
Suppose the observer stands at point $O$ (on the roots) where $O = L_0 = 1 + 0i$.
![Pasted image 20250905154118.png|500](/img/user/Images/Pasted%20image%2020250905154118.png)

The $n$ roots $L_0, L_1, \dots L_{n-1}$ 
$$
x^n -1 = (x- L_0)(x-L_1)(x-L_2)\dots(x-L_{n-1})
$$
Like vectors, see that $x - L_a$ gives a complex number whose magnitude is equal to the distance between $x$ and $L_a$. Thus the product
$$
\begin{split}
d_0 \cdot d_1 \cdot d_2 \dots d_{n-2} &= |(O-L_1)(O - L_2) \dots (O-L_{n-1})| \\
&= \frac{O^n-1}{O-1}\\
&= 1 + O + O^2 + O^3 \dots O^{n-1}\\
&= n
\end{split}
$$
Source: https://www.youtube.com/watch?v=8GPy_UMV-08

## Relationship with Matrices
An anti-clockwise rotation of a vector by $\theta$ can be described as 

$$
R_\theta = \begin{pmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta 
\end{pmatrix}
$$
Since $i$ represents a $\frac{\pi}{2}$ rotation, it can also be expressed as a matrix

$$
i = \begin{pmatrix}
0 & -1\\
1 & \ 0
\end{pmatrix}
$$
such that
$$
i^2 = \begin{pmatrix}
0 & -1\\
1 & 0
\end{pmatrix}
\begin{pmatrix}
0 & -1\\
1 & 0
\end{pmatrix} = 
\begin{pmatrix}
-1 & 0\\
0 & -1
\end{pmatrix} = -1
$$
A complex number can be rewritten in matrix form as 

$$
z = a + ib = \begin{pmatrix}
a & -b \\
b & a
\end{pmatrix}
$$
In which the conjugate equates to the transpose of the matrix 
$$
z^* = z^T
$$
## Split Complex numbers

Are defined as 
$$
\sqrt{j} = -1
$$
or
$$
j^2 = 1, \qquad j \neq1 \quad j\neq -1
$$

Properties
$$
e^{jx} =  \cosh x + j\sinh x  
$$

Forms a hyperbola
multiplying by $j$ is a reflection about the $y=x$ axis.
and
$$
|j| = i
$$
