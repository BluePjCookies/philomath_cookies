---
{"dg-publish":true,"permalink":"/math/statistics/","dgPassFrontmatter":true,"noteIcon":""}
---

> "Statistics is vectors " ~ Joshua + a lot of statisticians 

## Introduction

Why is population variance defined as
$$
Var(X) = \sum_{i=1}^{n}\frac{(x_i-\mu)^2}{n}
$$
But sample variance is defined as
$$
Var(X) = \sum_{i=1}^{n}\frac{(x_i-\bar{x})^2}{n-1}
$$
The key difference lies in the **definition and role** of $\mu$ and $\bar{x}$. 

### Population Mean
- $\mu$ is the **population mean** — a **fixed but possibly unknown constant**
- If $X$ is a random variable with a probability distribution, then
$$
\mathbb{E}(X) = \mu
$$
$\mu$ is assumed to be **known** in the population context.

### Sample mean
- In practice, however, we often **don’t know** $\mu$, especially in real-world data. So, we approximate it using the **sample mean**
$$\bar{x} = \frac{1}{N} \sum_{i=1}^N x_i$$

where $\bar{x}$ is a **point estimate** of the unknown $\mu$ based on a random sample.

## Residuals

Residuals have an interesting property, it is expressed as 
$$
x_i - \bar{x}
$$

Now the sum of residuals is always $0$.
Since sample mean $\bar{x} = \frac{1}{n} \sum_{i=1}^n x_i$, thus $n \bar{x} = \sum_{i=1}^n x_i$. Hence
$$
\sum_{i=1}^n (x_i - \bar{x}) = \sum_{i=1}^nx_i - n\bar{x} = 0
$$
Suppose we have two vectors or residuals

$$
\tilde{X} = 
\begin{pmatrix}
x_1- \bar{x}\\
x_2- \bar{x}\\
\vdots \\
x_n- \bar{x}\\
\end{pmatrix}
\quad 
\tilde{Y} = 
\begin{pmatrix}
y_1- \bar{y}\\
y_2- \bar{y}\\
\vdots \\
y_n- \bar{y}\\
\end{pmatrix}
$$

## Sample mean residuals

> A **degree of freedom** is an **independent value** in your dataset that can vary **freely** when estimating a statistic.

Data can be split into two parts, residuals and sample mean.
$$
X = \begin{pmatrix}
x_1\\
x_2\\
\vdots \\
x_n\\
\end{pmatrix} = 
\begin{pmatrix}
x_1- \bar{x} + \bar{x}\\
x_2- \bar{x}+ \bar{x}\\
\vdots \\
x_n- \bar{x}+ \bar{x}\\
\end{pmatrix}
= \overbrace{\begin{pmatrix}
x_1- \bar{x}\\
x_2- \bar{x}\\
\vdots \\
x_n- \bar{x}\\
\end{pmatrix}}^{\text{Residuals ($\bar{X}$)}}   + \overbrace{\bar{x} \begin{pmatrix}
1 \\
1 \\
\vdots \\
1
\end{pmatrix}}^{\text{Sample mean}}
$$
let the residuals be vector $\hat{X}$, we know that the sum of the terms in $\hat{X}$ is $0$. [[Math/Statistics#Residuals\|Statistics#Residuals]]
$$
\sum_{i=1}^{n}x_i - \bar{x} = 0
$$
Thus this limits what the residual could be. Suppose $n=2$ (2 data points). 

$$
\hat{X} = \begin{pmatrix} x \\ 1-x\end{pmatrix}
$$
We find that all possible values of $\hat{X}$ lies on a line $y = 1-x$. Thus its degree of freedom is 1 (as it only moves across a 1d line)

Suppose $n=3$. 
$$
\hat{X} = \begin{pmatrix}x \\ y \\ z \end{pmatrix} \quad x+y+z = 0
$$
The vector $\hat{X}$ must lies on a 2d plane that satisfies $x+y+z = 0$. Thus the degree of freedom of $\hat{X}$ is 2. Extrapolating this, $\hat{X}$  has  $n-1$ degree of freedom.

## Sample Variance
As such, when calculating the variance of the residuals, since the degree of freedom of $\hat{X}$ is $n-1$, we divide by $n-1$ instead to find the average deviation or residual.
$$
Var(X) = \frac{1}{n - 1} \sum_{i=1}^n (x_i - \bar{x})^2
$$
## Sample Covariance
$$
Cov(X,Y) = \frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})
$$
## Population Mean residuals

Population mean is known before calculating the value, it is thus independent of $x_i$.
$$
\sum_{i=1}^{n}x_i - \mu \neq 0
$$
Thus, the residuals $x_i - \mu$  or vector $\hat{X}$ can exist anywhere in the $n$ dimensional space, having $n$ degrees of freedom as its sum is not confined to $0$.

## Population Variance
$$Var(X) = \sum_{i=1}^{n}\frac{(x_i-\mu)^2}{n}$$
We can also rewrite it as
$$
\begin{split}
Var(X) &= \sum_{i=1}^{n}\frac{(x_i-\mu)^2}{n} \\
&=  \sum_{i=1}^{n}\frac{x_i^2 -2 x_iE(X) + E(X)^2}{n} \\
&= E(X^2) -2  \ E(X)^2 + E(X)^2\\
&= E(X^2) - E(X)^2
\end{split}
$$
## Population Covariance
$$
Cov(X,Y) = \frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})
$$
### Why the covariance of two independent variables is 0

$$
Cov(X,Y) = \frac{\sum_{i=1}^n{(x_i-\bar{x})(y_i - \bar{y})}}{n}
$$
Recall the two independent vectors residual $\hat{X}$ and $\hat{Y}$. We can see that based on dot product rule.

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/linear-algebra/#dot-product" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



### Dot Product

The Dot product of two vectors is
$
A \cdot B = |A||B| \cos \theta
$

And
$
A \cdot B = \sum_{n=1} a_nb_n
$

Look at derivation of the formula [[Math/Derivations/Proof for Dot Product\|here]]

---


</div></div>

$$
Cov(X,Y) = \frac{1}{n} (\hat{X} \cdot \hat{Y})
$$
Thus, if $\hat{X}$ and $\hat{Y}$ are independent, they will not be similar (does not point in a similar direction), thus their dot product would be $0$

## Standard Deviation
$$
Var(X) = \sigma^2
$$

---



## $r$ Correlation Coefficient  (A more elegant view of)

The $r$ formula (Pearson correlation coefficient) is given as such
$$
r = \frac{\sum (x - \bar{x})(y-\bar{y})}{\sqrt{\sum(x-\bar{x})^2 \cdot \sum (y-\bar{y})^2}}
$$
Look at this monstrosity. But in a sense this is a rather simple formula. 
Let's look at the formula again,

$$
r = \frac{\sum (x - \bar{x})(y-\bar{y})}{\sqrt{\sum(x-\bar{x})^2 \cdot \sum (y-\bar{y})^2}}
$$
Notice how we can rewrite is as
$$
r = \frac{\tilde{X} \cdot \tilde{Y}}{ ||\tilde{X}|| \cdot ||\tilde{Y}||} = \cos \theta
$$
The dot product determine the similarity of two vectors. If the vectors are pointing in the similar direction, then it will output $\pm1$. But if they are dissimilar (perpendicular) it will output $0$. This thus explains why $r$ tells us the correlation between two variables as it is simply $\cos \theta$.

## Regression

Check this out: [[Math/Misc/Regression using Linear Algebra (for univariate inputs)\|Regression using Linear Algebra (for univariate inputs)]]

The coefficients of the best-fit for univariate functions can be expressed as, where $\hat{X}$ is a Vandermonde Matrix. #Vandermonde_Matrix 
$$
A = (\hat{X}^T\hat{X})^{-1}\hat{X}^T Y
$$
## Interpolation

The coefficients of a uni-variate function can be simply expressed as such as $\hat{X}$ is a square matrix and has an inverse.  (Only when $d = n+1$) where $d$ is the degree of the interpolant, and $n$ is the number of data the interpolant is supposed to pass through.
$$
A = \hat{X}^{-1} Y
$$

## Why use Mean Squared Error in Regression?

Check this out: [[Math/Misc/Rationale Behind MSE for optimisation\|Rationale Behind MSE for optimisation]] 


$$
\begin{split}
w_\text{best} &= \arg \max \sum -  (y_{\text{ideal}} - y_{\text{real}})^2 \\
&= \arg \min \sum (y_\text{ideal} - y_{\text{real}})^2
\end{split}
$$

Where $y_{\text{ideal}} = wx$, and $w$ is the argument, $\arg \min$ outputs the argument that minimises the square of the residual. The above proves that the best function is obtained when we minimise the sum of the squared difference.

# References
1. https://www.youtube.com/watch?v=VDlnuO96p58
2. https://medium.com/@andrew.chamberlain/a-more-elegant-view-of-r-squared-a0a14c177dc3
3. https://www.youtube.com/watch?v=q7seckj1hwM&list=LL&index=63&t=428s