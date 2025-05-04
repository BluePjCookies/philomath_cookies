---
{"dg-publish":true,"permalink":"/math/notation/"}
---


There are many types of Logic. For the sake of simplicity, we will just explain each notation that is most commonly used by mathematicians.

## Sets
$\mathbb{R}$ - Real numbers 
$\mathbb{Z}$ - Integers
$x \mapsto y$ - elements from set x, maps to y

## Notation
$a \in G$  -  a in G
$\forall a$  - for all values of a
$\exists a$ - there exists a
$\sum_{i=a}^{b} i$ - summation of i from a to b
$\bigcup_{i=a}^{b} S_i$ - The union of all the sets $S_a$ to $S_b$ 
$\lim_{x\rightarrow a} f(x)$ - The value $f(x)$ approaches as $x$ approaches $a$
$\sup_{x \in [a,b]} f(x)$ - The smallest upper bound of $f(x)$ over values of $x$ spanning from $a$ to $b$
$\max_{x \in [a,b]}f(x)$ - the maximum of $f(x)$ over values of $x$ spanning from $a$ to $b$. 
{ #310e11}


## Logical Operators
$\neg a$  - NOT a
$a \wedge b$  - a AND b 
$a \vee b$ - a OR b
$a \rightarrow b$ - a implies b




> [!quote] On the distinction between $sup$ and $max$
> In terms of sets, the maximum is the largest member of the set, while the supremum is the smallest upper bound of the set.
> 
> So, consider $A=\{1,2,3,4\}$. Assuming we're operating with the normal reals, the maximum is 4, as that is the largest element. The supremum is also 4, as four is the smallest upper bound.
> 
> However, consider the set $B=\{x\in \mathbb{R}| x<2\}$. Then, the maximum of B is not 2, as 2 is not a member of the set; in fact, the maximum is not well defined. The supremum, though is well defined: 2 is clearly the smallest upper bound for the set.
