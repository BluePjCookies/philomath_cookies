---
{"dg-publish":true,"permalink":"/math/derivations/proof-for-3d-contradiction-quaternions/"}
---


Prove by Contradiction. Why 1 real and 2 complex numbers won't work.

Suppose we only have 2 complex numbers. $i,j \in \mathbb{C}$. Assuming closed multiplication, the multiplication between the two numbers would result in another value consisting of the two numbers. 
Where $a, b, c \in \mathbb{R}$
$$
ij = a + ib + jc
$$
Multiply the left hand side by $i$.
$$
-j = -b + ia + ijc
$$
Substituting $ij$ into the above expression.
$$
\begin{split}
-j &= -b + ia + (a+ ib + jc)c \\
0 + i0+ j0 &= (a-b)+ i(a+b) + j(c^2+ 1)
\end{split}
$$
Thus this contradicts the statement that $a,b,c \in \mathbb{R}$.
$$
c^2 =-1
$$
