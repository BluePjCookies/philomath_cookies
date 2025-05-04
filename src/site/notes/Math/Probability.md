---
{"dg-publish":true,"permalink":"/math/probability/"}
---


## Classical definition of Probability 
- Probability measures the likelihood of an event happening. 

The classical definition of probability, also known as the Laplace definition, states that if an experiment has a finite number of equally likely outcomes, the probability of an event occurring is given by:
$$
P(E) = \frac{\text{Number of favorable outcomes}}{\text{Total number of possible outcomes}}
$$

However, this definition does not account for outcomes with unequal probability distributions or an infinite number of outcomes.
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

### Independence Relation

if Event A and B are independent, then
$$
P(A \cap B) = P(A) P(B)
$$
### **Conditional Probability**

Probability that A happens given B, is the probability that both A and B happens over the probability that B happens. So if we know B has happened, what is the probability that A will occur? (Try to visualise using Venn diagrams)

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

### Discrete Case

The expectation function, reveals the expected value of X in the long term. It is the product of x and the probability of x occurring.

$$
\mathbb{E}(X) = \sum_x{x P(X=x)}
$$
### Continuous Case

**Probability Density Function (PDF)**
For a continuous case, the probability that X would settle on a specific value x, is 0. $P(X=x) = 0$. Thus a probability density function is used. Which measures the probability that X would be close to x. 
$$
\mathbb{E}(X) = \int_{-\infty}^{\infty} x f_X(x) dx
$$
The probability density function can be used to measure the probability that X would fall within a specific interval. This is done by finding the area under the probability density function.
$$
P(a \leq X \leq b) = \int_a^b f_X(x) dx
$$
We can also rewrite it as such where $\delta$ is a small infinitesimal value. 
$$
P(x \leq X \leq x + \delta ) = \int_x^{x+\delta} f_X(x) dx \approx \delta f_X(x)
$$
And
$$
f_X(x) = \frac{P(x \leq X \leq x + \delta)}{\delta}
$$
Thus, $f_X(x)$ measures how probable X would be near x.

**Cumulative Distribution Function**

**F(x)** measures how probable X would be less than or equal to a specific value. It is an S shape curve.
$$
F(x) = P(X \leq x) = \int_{-\infty}^{x} f_X(x) dx
$$

**Joint Probability Density**

For two or more variables, their joint probability density can be given as such.

$$
P(a \leq X \leq b, c \leq Y \leq d) = \int_a^b \int_c^d xy f_{XY}(x,y) dy dx
$$

