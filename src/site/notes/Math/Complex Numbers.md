---
{"dg-publish":true,"permalink":"/math/complex-numbers/"}
---


An imaginary is defined as $i$ with the following property

$$
i^2 = -1
$$
It corresponds to a $\frac{\pi}{2} rad$ anti-clockwise rotation and can also be expressed as a matrix

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
## Euler's Identity

Proof for $e^{i \theta} = \cos \theta + i \sin \theta$
### Proof using Maclaurin Series
[[Math/Derivations/Proof for Euler's Identity using Maclaurin Series\|Proof for Euler's Identity using Maclaurin Series]]

### Alternative Proof using Calculus
[[Math/Derivations/Proof for Euler's Identity using ODEs\|Proof for Euler's Identity using ODEs]]

---
## Introduction
A complex number is defined as. 
$$
z = a + ib
$$
A vector has an angle $\theta$ and a magnitude $r$. It should be self-evident that we can rewrite this as
$$
z = re^{i \theta}
$$

The magnitude of a complex number can be expressed as $r = \sqrt{a^2 + b^2} = ||z||$
### Conjugate 
The conjugate of $z$ is 
$$
z^* = a - ib = r
$$
Thus
$$
||z|| = z \cdot z^*
$$
### Scaling & Rotations
A complex number **encodes** a rotation and a scaling. When $a$ is multiplied with $b$ where $a,b \in \mathbb{C}$
$$
a \cdot b = r_1r_2 e^{i (\theta_1 + \theta_2)}
$$

$a$ acts on $b$ by scaling it by $r_1$ and rotating it by $\theta_1$

The angle $\theta$ can be sufficiently described using this range.

$$
- \pi \leq \theta \leq \pi
$$

### De Moivre's Theorem

Based on the above, it's pretty evident that 
$$
z^n = r^n e^{in \theta} = r^n \left( \cos n\theta + i \sin n \theta\right)
$$

