---
{"dg-publish":true,"permalink":"/math/derivations/proof-for-area-under-gaussian-distribution/","dgPassFrontmatter":true,"noteIcon":""}
---


This section concerns itself with finding the integral of a Gaussian Distribution

$$
\int_{-\infty}^{\infty} e^{-x^2}\ dx = C
$$
Find $C$.

> [!Proof] Proof

Lets consider adding another dimension.
$$
f(x,y) = e^{-x^2 - y^2} = e^{-x^2} \cdot e^{-y^2} = e^{-r^2}
$$
where $r^2 = x^2 + y^2$. Let $r$ be the radius of the circle. Thus all points a distance $r$ from the origin on $e^{-x^2 -y^2}$ would have the same value. We can graph out the function against $x$ and $y$
![Pasted image 20250506202742.png|600](/img/user/Images/Pasted%20image%2020250506202742.png)

We can find the volume under $f(x,y)$ by summing the area under the red line (points of equidistant from the origin) for all values $r$. Unroll the area under the red line to form a rectangle, with length $2\pi r$ and height $e^{-r^2}$, integrate with respect to $r$.

$$
\begin{split}
V &= \int_{0}^{\infty} 2 \pi r \ e^{-r^2} \ dr\\
&= \pi \int_{0}^{\infty} 2 r \ e^{-r^2} \ dr\\
&= \pi \left[ -e^{-r^2} \ \right]^{\infty}_{0}\\
&= \pi
\end{split}
$$

 We can express the volume as a double integral as below, where the inner integral integrates in the $x$ axis, keeping $y$ as a constant. I like to think of the integral as infinitely slicing $f(x,y)$ along the $x$ axis and finding the area bounded by $f(x,y)$ in each slice, expressing it as some value. Next the outer integral sums up all these areas by integrating in the $y$ direction, thus obtaining the volume $(V)$ under $f(x,y)$.
 $$
\begin{split}
V &= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} e^{-x^2-y^2} \ dx \ dy \\
&= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} e^{-x^2} e^{-y^2} \ dx \ dy \\
&= \int_{-\infty}^{\infty} e^{-y^2} \int_{-\infty}^{\infty} e^{-x^2}  \ dx \ dy  \quad \text{[We can factor $e^{-y^2}$ as it is a constant]}\\
&= \int_{-\infty}^{\infty} e^{-y^2} C \ dy \\
&= C \int_{-\infty}^{\infty} e^{-y^2} \ dy \\
&= C^2
\end{split}
$$
Thus
$$
\begin{split}
V = C^2 &= \pi\\
\int_{-\infty}^{\infty} e^{-x^2}\ dx &= C\\
&= \sqrt{\pi}
\end{split}
$$

> [! info] Thus
> $$
> \int_{-\infty}^{\infty} e^{-x^2} \ dx = \sqrt{\pi} 
> $$



Source: https://www.youtube.com/watch?v=cy8r7WSuT1I
