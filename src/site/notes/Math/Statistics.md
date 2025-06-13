---
{"dg-publish":true,"permalink":"/math/statistics/"}
---

> "Statistics is vectors " ~ Joshua
## $r$ Correlation Coefficient  

The $r$ formula (Pearson correlation coefficient) is given as such
$$
r = \frac{\sum (x - \bar{x})(y-\bar{y})}{\sqrt{\sum(x-\bar{x})^2 \cdot \sum (y-\bar{y})^2}}
$$
Look at this monstrosity. But in a sense this is a rather simple formula. 


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



Suppose we have two vectors 

$$
\tilde{X} = 
\begin{pmatrix}
x_0- \bar{x}\\
x_1- \bar{x}\\
\vdots \\
x_n- \bar{x}\\
\end{pmatrix}
\quad 
\tilde{Y} = 
\begin{pmatrix}
y_0- \bar{y}\\
y_1- \bar{y}\\
\vdots \\
y_n- \bar{y}\\
\end{pmatrix}
$$

Let's look at the formula again,

$$
r = \frac{\sum (x - \bar{x})(y-\bar{y})}{\sqrt{\sum(x-\bar{x})^2 \cdot \sum (y-\bar{y})^2}}
$$
Notice how we can rewrite is as
$$
r = \frac{\tilde{X} \cdot \tilde{Y}}{ ||\tilde{X}|| \cdot ||\tilde{Y}||} = \cos \theta
$$
The dot product determine the similarity of two vectors. If the vectors are pointing in the similar direction, then it will output $\pm1$. But if they are dissimilar (perpendicular) it will output $0$. This thus explains why $r$ tells us the correlation between two variables as it is simply $\cos \theta$.
## Variance

Variance is defined as 

$$
Var(X) = \sum_{i=1}^{N}\frac{(x_i-\bar{x})^2}{N}
$$
## Standard Deviation

$$
Var = \sigma^2
$$

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

Where $y_{\text{ideal}} = wx$, and $w$ is the argument, $\arg \min$ outputs the argument that minimises the function. The above proves that the best function is obtained when we minimise the sum of the squared difference.
