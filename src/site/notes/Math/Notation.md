---
{"dg-publish":true,"permalink":"/math/notation/","dgPassFrontmatter":true,"noteIcon":""}
---


## Sets
| Sets         | Meaning          |
| ------------ | ---------------- |
| $\mathbb{N}$ | Natural numbers  |
| $\mathbb{Z}$ | Integers         |
| $\mathbb{Q}$ | Rational numbers |
| $\mathbb{R}$ | Real numbers     |
| $\mathbb{C}$ | Complex numbers  |
| $\mathbb{H}$ | Quaternions      |
| $\mathbb{P}$ | Prime numbers    |
| $\emptyset$  | Empty Set        |
|              |                  |
## Notation

| Notation                      | Meaning                                               |
| ----------------------------- | ----------------------------------------------------- |
| $a \in G$                     | a in G                                                |
| $\forall a$                   | for all values of a                                   |
| $\exists\ a$                  | there exists a                                        |
| $\sum_{i=a}^{b} i$            | summation of i from a to b                            |
| $\bigcup_{i=a}^{b} S_i$       | the union of all the sets $S_a$ to $S_b$              |
| $\lim_{x \rightarrow a} f(x)$ | the value $f(x)$ approaches as $x$ approaches $a$     |
| $\sup_{x \in [a,b]} f(x)$     | the smallest upper bound of $f(x)$ over $x \in [a,b]$ |
| $\max_{x \in [a,b]} f(x)$     | the maximum of $f(x)$ over $x \in [a,b]$              |
| $\therefore$                  | Therefore                                             |
| $\because$                    | Because                                               |
| $x \mapsto y$                 | Elements from $x$ maps to $y$                         |


## Logical Operators
| Logic Operators   | Meaning                   |
| ----------------- | ------------------------- |
| $\neg a$          | NOT a                     |
| $a \wedge b$      | a AND b                   |
| $a \vee b$        | a OR b                    |
| $a \rightarrow b$ | IF a THEN b (a implies b) |




> [!quote] On the distinction between $sup$ and $max$
> In terms of sets, the maximum is the largest member of the set, while the supremum is the smallest upper bound of the set.
> 
> So, consider $A=\{1,2,3,4\}$. Assuming we're operating with the normal reals, the maximum is 4, as that is the largest element. The supremum is also 4, as four is the smallest upper bound.
> 
> However, consider the set $B=\{x\in \mathbb{R}| x<2\}$. Then, the maximum of B is not 2, as 2 is not a member of the set; in fact, the maximum is not well defined. The supremum, though is well defined: 2 is clearly the smallest upper bound for the set.

## References
- https://math.libretexts.org/Courses/Mount_Royal_University/Mathematical_Reasoning/1%3A_Basic_Language_of_Mathematics/1.1%3A_Compound_Statements#Example_.5C(.5CPageIndex.7B1.7D.5C):