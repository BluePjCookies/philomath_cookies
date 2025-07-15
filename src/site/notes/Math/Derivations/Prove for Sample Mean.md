---
{"dg-publish":true,"permalink":"/math/derivations/prove-for-sample-mean/","dgPassFrontmatter":true,"noteIcon":""}
---


Suppose we have variable $X$ following a distribution where $E(X) = \mu$. But we don't know $\mu$, instead we have multiple observations of $X$, like $X_1, X_2, X_3 \dots$ 


let
$$
X = \begin{pmatrix}
X_1 \\
X_2 \\ 
\vdots \\
X_n
\end{pmatrix}
$$
and the mean is
$$
\hat{\mu} = \begin{pmatrix}
\mu \\
\mu \\
\vdots \\
\mu
\end{pmatrix}
$$

![Pasted image 20250708182804.png|centre|600](/img/user/Images/Pasted%20image%2020250708182804.png) 

We want to find a value of $\mu$ that minimises $X - \hat{\mu}$. The residual vector (in red) should thus be minimised. Thus, $X - \hat{\mu}$ should be perpendicular to $\hat{\mu}$. Using Pythagoras theorem

$$
||\hat{\mu}||^2 + ||X - \hat{\mu}||^2 = ||X||^2
$$
$$
\begin{split}
\sum^N \mu^2  + \sum_{i=1}^N (X_i - \mu )^2 &= \sum_{i=1}^N X_i^2 \\
\sum_{i=1}^N \mu^2 + X_i^2-2\mu X_i + \mu^2 
&= \sum_{i=1}^N X_i^2\\
2N \mu^2 - 2 \mu \sum_{i=1}^N
X_i &= 0 \\
2N \mu^2&= 2 \mu \sum_{i=1}^N
X_i \\
\mu &= \frac{1}{N} \sum_{i=1}^N
X_i
\end{split}
$$
