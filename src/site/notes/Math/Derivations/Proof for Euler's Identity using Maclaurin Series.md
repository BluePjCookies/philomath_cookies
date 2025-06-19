---
{"dg-publish":true,"permalink":"/math/derivations/proof-for-euler-s-identity-using-maclaurin-series/","dgPassFrontmatter":true,"noteIcon":""}
---


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
