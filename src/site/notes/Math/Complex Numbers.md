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

Proof for $e^{i \pi} +1 = 0$
### Proof using Maclaurin Series
Based on 
<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/sequences-and-series/#maclaurin-series-expansion-for-sin-and-cos" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



### Maclaurin Series expansion for $\sin$ and $\cos$

$
\sin x = \sum_{n=0}^{\infty} \frac{(-1)^n}{(2n+1)!}x^{2n+1}
$
$
\cos x = \sum_{n=0}^{\infty}\frac{(-1)^n}{(2n)!}x^{2n}
$

Refer to [[Math/Complex Numbers\|Complex Numbers]] to see the link between trigonometry and exponential functions.


</div></div>

And 
<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/sequences-and-series/#fa41a8" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



$
e^x = \sum_{n=0}^{\infty}\frac{x^n}{n!}
$

</div></div>

Suppose $x=i\theta$
$$
\begin{split}
e^{i \theta } &= \sum_{n=0}^{\infty} \frac{(i\theta)^n}{n!}\\
&= 1 + i\theta + \frac{(i\theta)^2}{2!} + \frac{(i\theta)^3}{3!} + \frac{(i\theta)^4}{4!} + \dots\\
&= \overbrace{1 - \frac{\theta^2}{2!}+ \frac{\theta^4}{4!}- \frac{\theta^6}{6!} \dots}^{\cos \theta} +i \overbrace{\left(\theta - \frac{\theta^3}{3!} + \frac{\theta^5}{5!} - \frac{\theta^7}{7!} \dots
\right)}^{\sin \theta} \\
&= \cos \theta + i \sin \theta
\end{split}
$$
Thus
$$
e^{i\theta} = \cos \theta + i \sin \theta
$$
Substituting $\theta$ as $\pi$
$$
e^{i \pi} = -1
$$
### Alternative Proof using Calculus

let
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
