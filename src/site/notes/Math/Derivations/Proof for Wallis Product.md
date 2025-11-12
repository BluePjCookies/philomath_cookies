---
{"dg-publish":true,"permalink":"/math/derivations/proof-for-wallis-product/","dgPassFrontmatter":true,"noteIcon":""}
---

Let 
$$
I_n = \int_0^\pi \sin^n \theta  d\theta
$$
Via integration by parts, solving for $I_n$.
$\int u'v = uv - \int uv'$ where $(u' = \sin \theta, \ v = \sin^{n-1}\theta)$
$$
\begin{split}

\int \sin^n \theta d\theta &= -\cos \theta \sin^{n-1}\theta + \int\cos^2\theta (n-1) \sin^{n-2}\theta d\theta \\
&= -\cos \theta \sin^{n-1}\theta + \int(1-\sin^2\theta)(n-1) \sin^{n-2}\theta d\theta \\
&= -\cos \theta \sin^{n-1}\theta + (n-1)\left[\int\sin^{n-2}\theta d\theta-\int \sin^{n}\theta d\theta\right] \\
I_n &= -\cos \theta \sin^{n-1}\theta + (n-1)\left[I_{n-2}- I_n\right] \\
nI_n &= -\cos \theta \sin^{n-1}\theta + (n-1)\left[I_{n-2}\right] \\
I_n &= \frac{1}{n}\left[-\cos \theta \sin^{n-1}\theta + (n-1)\left(I_{n-2}\right) \right]^{\pi}_0 \\
&= \frac{n-1}{n}I_{n-2}
\end{split}
$$
So we proved that
$$
I_n = \frac{n-1}{n}I_{n-2}
$$
Since $I_0 = \pi$. Thus
$$
I_{2n} = \pi \prod_{k=1}^n \frac{2k-1}{2k}
$$
And $I_1 = 2$
$$
I_{2n+1} = 2 \prod_{k=1}^{n} \frac{2k}{2k+1} 
$$
The inequality below holds because $\sin \theta \in [-1, 1]$ which gets smaller as $n$ increases. Thus we are summing up smaller values of $\sin^n\theta$ as $n$ increases.
$$
I_{2n+1} \leq I_{2n} \leq I_{2n-1}
$$
 $I_{2n+1}$ is given as
$$
I_{2n + 1} = \frac{2n}{2n+1} I_{2n-1}
$$
The limit of $\frac{I_{2n-1}}{I_{2n+1}}$ as $n$ approaches infinity is
$$
\lim_{n \rightarrow \infty} \frac{I_{2n-1}}{I_{2n+1}} = \lim_{n \rightarrow \infty} \frac{2n+1}{2n} = 1
$$
Using our inequality previously, dividing it throughout by $I_{2n+1}$, and taking the limit of $n$ to $\infty$
$$
1 \leq \frac{I_{2n}}{I_{2n+1}} \leq 1
$$
Thus, 
$$
\lim_{n \rightarrow \infty} \frac{I_{2n}}{I_{2n+1}} = 1
$$
We can thus substitute the previously defined values for $I_n$ and $I_{2n+1}$

$$
\begin{split}
\frac{I_{2n}}{I_{2n+1}} &= \frac{\pi}{2} \prod_{k=1}^\infty \dfrac{\frac{2k-1}{2k}}{\frac{2k}{2k+1}} \\
1 &= \frac{\pi}{2} \prod_{k=1}^\infty \frac{4k^2-1}{4k^2}\\
\end{split}
$$
Thus we have formulated the proof that

$$
\pi= 2 \prod_{k=1}^\infty \left(\frac{4k^2}{4k^2-1} \right)
$$

