---
{"dg-publish":true,"permalink":"/math/derivations/proof-for-euler-s-identity-using-od-es/","dgPassFrontmatter":true,"noteIcon":""}
---

Let
$$
z = \cos\theta + i \sin \theta
$$
Differentiate with respect to $\theta$ (Imaginary numbers are just another axis)

$$
\begin{split}
\frac{dz}{d \theta } &= - \sin \theta + i \cos \theta \\
&= i ( i\sin \theta + \cos \theta )\\
&= iz
\end{split}
$$
Using [[Math/Calculus#Solving a Variable Separable Differential equation\|Solving a variable separable differential equation]] under Calculus
$$
\begin{split}
\frac{1}{z} dz &= i d\theta \\
\int \frac{1}{z} dz &= \int i d\theta\\
\ln z &= i \theta +C\\
e^{i \theta +C} &= z
\end{split}
$$
letting $\theta = 0$ 
$$
\begin{split}
e^{i 0 + C} &= \cos 0 + i \sin 0 \\
e^{0} e^{C}&= 1 \\
C &= 0
\end{split}
$$
Thus
$$
e^{i \theta } = z = \cos \theta + i\sin \theta
$$
