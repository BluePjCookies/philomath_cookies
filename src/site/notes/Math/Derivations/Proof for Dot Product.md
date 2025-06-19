---
{"dg-publish":true,"permalink":"/math/derivations/proof-for-dot-product/","dgPassFrontmatter":true,"noteIcon":""}
---

![Pasted image 20250525172147.png|centre|300](/img/user/Images/Pasted%20image%2020250525172147.png)

Let AB, be a vector from A to B. Based on the cos rule. [[Math/Trigonometry#Cos rule\|Cos Rule]]
$$
\vec{AB} = \vec{OB} - \vec{OA}
$$
$$
|AB|^2 = |OA|^2 + |OB|^2 - 2|OA||OB| \cos \theta
$$

Let $OA = A$ and $OB = B$.
$$
\begin{aligned}
|A||B| \cos \theta &= \frac{1}{2}\left( |A|^2 + |B|^2 - |B-A|^2\right) \\
&= \frac{1}{2} \left( \sum_{n=1} (a_n^2 + b_n^2) - \sum_{n=1} (b_n-a_n)^2\right) \\
&=
\frac{1}{2} \left( \sum_{n=1} (a_n^2 + b_n^2) - \sum_{n=1} (b_n^2-2a_nb_n + a_n^2)\right) \\
&= 
\sum_{n=1} a_nb_n
\end{aligned}
$$
Thus
$$
A \cdot B = \sum_{n=1} a_nb_n
$$
