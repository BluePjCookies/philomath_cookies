---
{"dg-publish":true,"permalink":"/math/misc/regression-using-linear-algebra-for-univariate-inputs/"}
---

Regression aims to find the best fit of a function from a set of given data points. Suppose we want to fit $n$ data points to $y$, where $y$ is a function of $x$.
$$
y = a_0 + a_1 x + a_2 x^2 \dots a_d x^d
$$

We have $n$ data points

$$
X = 
\begin{pmatrix}
x_0\\
x_1\\
\vdots \\
x_n\\
\end{pmatrix}
\quad 
Y = 
\begin{pmatrix}
y_0\\
y_1\\
\vdots \\
y_n\\
\end{pmatrix}
$$

## Vandermonde Matrix
A Vandermonde Matrix is defined as such. It describes a polynomial function of degree $d$. #Vandermonde_Matrix

$$
\hat{X} = V(x_0, x_1, x_2, \dots x_n) = \begin{pmatrix}
1 & x_0 & x_0^2 & \dots & x_0^d \\
1 & x_1 & x_1^2 & \dots & x_1^d \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & x_n & x_n^2 & \dots & x_n^d \\
\end{pmatrix}
$$
---

$y$ can be re-expressed as

$$
Y = \hat{X}A
$$
where 
$$
A = \begin{pmatrix}
a_0\\
a_1 \\
a_2 \\
\vdots\\
a_d
\end{pmatrix}
$$
To solve for $A$, $\hat{X}$ typically does not have an inverse as $d \neq n+1$. However, we can multiply the Vandermonde matrix by its transpose, thus "squaring" it, which allows us to solve for its inverse.

$$
\begin{split}
\hat{X}^T Y &= (\hat{X}^T\hat{X}) A \\
A &= (\hat{X}^T\hat{X})^{-1}\hat{X}^T Y
\end{split}
$$
