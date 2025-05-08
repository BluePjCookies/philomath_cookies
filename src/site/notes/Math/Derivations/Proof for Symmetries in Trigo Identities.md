---
{"dg-publish":true,"permalink":"/math/derivations/proof-for-symmetries-in-trigo-identities/"}
---


Let us see the properties of these trigo identiti1es.
This section aims to help us find a shortcut to solving questions like: Use Compound angle formula to prove that $\cos \frac{19 \pi}{12} = \frac{\sqrt{6} - \sqrt{2}}{4}$ etc...

let us define $n$ as
$$
n = k \times a + R
$$
where $R$ is the remainder, and cannot be divided by $a$. And $k,a,R,n \in \mathbb{Z}$ 
For example
$$
19 = 1 \times 12 \ + 7
$$
## Reducing $\theta$ value 
Expanding using the double angle formulae
$$\begin{split}
\sin\left(\frac{n}{a} \pi \right) &= \sin \left(k\pi + \frac{R}{a}\pi \right) \\
&= \cos (k\pi)\sin \left(\frac{R}{a}\pi\right) + \sin (k \pi)\cos \left(\frac{R}{a}\pi\right)\\
&= \cos (k\pi)\sin \left(\frac{R}{a}\pi\right)\\
&= (-1)^k \sin \left( \frac{R}{a} \pi \right)
\end{split}
$$
Similarly

$$\begin{split}
\cos\left( \frac{n \pi}{a}\right) &=  \cos (k \pi) \cos \left(\frac{R}{a} \pi \right)\\
&= (-1)^k \cos \left( \frac{R}{a} \pi \right)\\
\end{split}
$$
## Further reduction of $\theta$
Since
$$
\sin(\pi-x)= \sin x
$$
$$
\cos(\pi -x) = -\cos x
$$
Thus
$$
\sin \left( \frac{n}{a} \pi\right) = (-1)^k \sin\left(\frac{a-R}{a} \pi \right)
$$
$$
\cos(\frac{n}{a}\pi) = (-1)^{k+1} \cos\left(\frac{a-R}{a} \pi\right)
$$

>[! Info] Example
>$$
>\cos\left(\frac{19}{12} \pi \right) = \cos(\pi + \frac{7}{12}\pi) = \cos (\pi)\cos \left(\frac{7}{12}\pi \right) = -1 \cdot \cos \left(\frac{7}{12}\pi \right)
>$$
Then we can reduce $\theta$ further
>$$
> - \cos \frac{7}{12} \pi = \cos \frac{12-7}{12} \pi = \cos \frac{5}{12} \pi
>$$

Having reduced $\theta$. We can thus find the value of $\cos \frac{5}{12} \pi$ easily.
$$
\begin{split}
\cos \frac{5}{12} \pi &= \cos \left(\frac{\pi}{4} + \frac{\pi}{6} \right)\\
&= \cos \frac{\pi}{4} \cos \frac{\pi}{6} - \sin \frac{\pi}{4} \sin \frac{\pi}{6}\\
&= \frac{\sqrt{6} - \sqrt{2}}{4}
\end{split}
$$
