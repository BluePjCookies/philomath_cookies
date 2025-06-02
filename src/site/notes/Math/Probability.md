---
{"dg-publish":true,"permalink":"/math/probability/"}
---


## Classical definition of Probability 
- Probability measures the likelihood of an event happening. 

The classical definition of probability, also known as the Laplace definition, states that if an experiment has a finite number of equally likely outcomes, the probability of an event occurring is given by:
$$
P(E) = \frac{\text{Number of favorable outcomes}}{\text{Total number of possible outcomes}}
$$

### Independence Relation

if Event A and B are independent, then
$$
P(A \cap B) = P(A) P(B)
$$
### **Conditional Probability**

Probability that A happens given B, is the probability that both A and B happens over the probability that B happens. (Try to visualise using Venn diagrams)

$$
P(A|B) = \frac{P(A \cap B)}{P(B)}
$$
### **Bayes Theorem**
Based on the conditional probability, 
$$
P(B|A)= \frac{P(A \cap B)}{P(A)}
$$
Thus
$$
P(A|B) = \frac{P(B|A) P(A)}{P(B)}
$$
Since $P(B)$ can be rewritten as $P(B \cap A') + P(B \cap A)$. Rearranging our conditional probability statement
$$
P(A|B) = \frac{P(B|A)P(A)}{P(B|A')P(A') + P(B|A)P(A)}
$$
# Random Variables
## Probability Mass Function (PMF)
It denotes the probability that a **discrete** random variable $X$ would equate to the value $x$. 

$$
P(X= x)
$$
## Probability Density Function (PDF)
For continuous random variable, $P(X = x)$ is not meaningful as it would just be 0. For example, suppose a computer can randomly generate real numbers. It is impossible that it will output $x$  due to the uncountably infinite many other possibilities. However, its output can come ridiculously close to $x$. And the probability that it is close to $x$ is defined by the probability density at $x$.

$$
f_X(x)
$$
where $f_X$ is the probability density function which measures the probability that $X$ would be close to $x$. More about them [[Math/Misc/Density Functions\|here]]

To find the probability that $a \leq X \leq b$
$$
P(a \leq X \leq b) = \int_a^b f_X(x) dx
$$
## Expectation

The expectation function, reveals the expected value of X in the long term. It is the product of x and the probability of x occurring.
### Discrete:
$$
\mathbb{E}(X) = \sum_x{x P(X=x)}
$$
### Continuous:
$$
\mathbb{E}(X) = \int_{-\infty}^{\infty} x f_X(x) dx
$$


### Properties of Expectation

#### Constant
$$
\mathbb{E}(c) = c
$$
#### Scalar Multiplicativity
$$
\mathbb{E}(aX) = a \cdot \mathbb{E}(X)
$$
#### Linearity of Expectation
$$
\mathbb{E}(X + Y) = \mathbb{E}(X) + \mathbb{E}(Y)
$$
#### Product of Two independent Variables
If $X$ and $Y$ are independent
$$
\mathbb{E}(X \cdot Y) = \mathbb{E}(X)
\cdot \mathbb{E}(Y)$$
## Variance

### Formula
Variance is the spread of the random variable $X$ from its mean $\mathbb{E}(X)$
$$
Var(X) = \mathbb{E}(X-\mathbb{E}(X) )^2
$$
We can also rewrite it as
$$
\begin{split}
Var(X) &= \mathbb{E}(X- \mathbb{E}(X))^2 \\
&= \mathbb{E}(X^2 - 2 \cdot \mathbb{E}(X) X + \mathbb{E}(X)^2) \\
&= \mathbb{E}(X^2) - 2 \cdot \mathbb{E}(X)^2 + \mathbb{E}(X)^2 \\
&= \mathbb{E}(X^2) - \mathbb{E}(X)
\end{split}
$$
$\therefore$
$$
Var(X) = \mathbb{E}(X^2) - \mathbb{E}(X) = \sigma^2
$$
It can be equated to $\sigma^2$
### Properties of Variance
#### Constant
$$
Var(c) = 0
$$
#### Scalar Multiplicativity
$$
Var(cX ) = c^2 Var(X)
$$
#### Translation Invariance
$$
Var(X + c) = Var(X)
$$
#### Additivity
$$
Var(X + Y) = Var(X) + 2 Cov(X \cdot Y) + Var(Y)
$$

If $X$ and $Y$ are independent, its covariance is 0. $\therefore$
$$
Var(X + Y) = Var(X) + Var(Y)
$$

## Cumulative distribution Function

Is the summation of the Probability Mass and Density function. It is an S-shaped curve 
### Discrete
$$
F(x) = P( X \leq x) = \sum_{t \leq x} P(X = t)
$$
### Continuous 
$$
F(x) = P(X \leq x) = \int_{-\infty}^x f_X(t) \ dt 
$$

## Modern Axiomatic Definition

It is based on the Kolmogorov probability axioms. Which extends the definition to unequal probability distributions, and also probability with infinite outcomes.
## Kolmogorov Probability Axioms
let $(\Omega, F,P)$ be the measure space where 
$\Omega$ is the sample space (Set of all elements)
$F$ is the event space (Set of all events) $F = \{E_1, E_2 \dots \}$ 
$P$ is the probability measure that outputs a probability of an event $E$ 

1. $P(E) \in \mathbb{R}, P(E) \geq 0 \quad \forall E \in F$  
2. $P(\Omega) = 1$ 
3. $P\left(\bigcup_{i=0}^{\infty} E_i \right) = \sum_{i=0}^{\infty}P(E_i)$  if $E_i$ are disjoint 
