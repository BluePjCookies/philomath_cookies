---
{"dg-publish":true,"permalink":"/math/abstract-algebra/","dgPassFrontmatter":true,"noteIcon":""}
---


https://math.berkeley.edu/~apaulin/AbstractAlgebra.pdf
These are my notes from this university pdf notes


## Defining Unity
The concept of Unity. The number $1$, or $I$ or $e$ ... All represents the same thing. 
Let $\mathbb{B}$ be the set of numbers. And the operator be defined as $*$. If they satisfy 4 properties, they form a [[Math/Group Theory\|Group]]. 
$$
(\mathbb{B}, *) \rightarrow \text{Group}
$$

The unity $e \in \mathbb{B}$ must satisfy $e*a = a, \forall a \in \mathbb{B}$.

## Set Theory basics

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/set-theory/#notation" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



# Notation
Let $S$ and $T$ be two sets

$
S = \{ \text{Notation for elements in S}| \text{Properties which specifies being in S}\}
$
The vertical bar should be read as "such that"
## Complementary Set
If $S \in T$, then $T \setminus S := \{ x \in T | x \notin S\}$ is called the compliment of $S$ in $T$.

## Cartesian Product

$S \times T = \{ (a,b) | a \in S, b \in T\}$ is the cartesian product of $S$ and $T$.


</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/notation/#notation" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## Notation

| Notation                      | Meaning                                               |
| ----------------------------- | ----------------------------------------------------- |
| $a \in G$                     | $a$ in $G$                                            |
| $\forall a$                   | for all values of $a$                                 |
| $\exists\ a$                  | there exists $a$                                      |
| $\exists ! a$                 | there exists unique $a$                               |
| $\sum_{i=a}^{b} i$            | summation of i from a to b                            |
| $\bigcup_{i=a}^{b} S_i$       | the union of all the sets $S_a$ to $S_b$              |
| $\lim_{x \rightarrow a} f(x)$ | the value $f(x)$ approaches as $x$ approaches $a$     |
| $\sup_{x \in [a,b]} f(x)$     | the smallest upper bound of $f(x)$ over $x \in [a,b]$ |
| $\max_{x \in [a,b]} f(x)$     | the maximum of $f(x)$ over $x \in [a,b]$              |
| $\therefore$                  | Therefore                                             |
| $\because$                    | Because                                               |
| $x \mapsto y$                 | Elements from $x$ maps to $y$                         |
| $f:S \to T$                   | function maps elements from $S$ to $T$                |
| $a \implies b$                | $a$ implies $b$ (if $a$ is true, $b$ is true)         |
| $a \iff b$                    | $a$ is true if and only if $b$ is true                |



</div></div>


## Functions

>[!Definition]
>A map (or function) $f$ from $S$ to $T$ is a rule which assigns element of $S$ a unique elements of $T$.

$$
f: S \to T
$$
$$x \mapsto f(x)$$


Eg. $f: \mathbb{Z} \times \mathbb{Z} \to \mathbb{Z}$ can be a map from $(a,b) \mapsto a + b$.

In the case $f : S \to T$

1. $S$ is the domain of $f$ and $T$ is it's codomain (not the same as range)
2. $f$ is the identity map if $f(x) = x, \forall x \in S$ and $S = T$. We can rewrite it as $f = Id_S$
3. $f$ is Injective if $f(x) = f(y) \implies x = y , \forall x,y \in S$. One to one.
4. $f$ is Surjective if  $y \in T,  \ x \in S, \exists x f(x) = y$. All $T$ is mapped
5. $f$ is bijective if it's both Injective and Surjective.

## Equivalence Relation
The notation $x \sim y$ represents "$x$ is equivalent to $y$". Suppose we define equivalence as numbers which has the same parity (both even or odd). Then, if $S = \{ 1,2,3,4\}$, $2$ is equivalent to $4$ as they are both even.  $\therefore 2 \sim 4$ ...

Let $U$ be a relation on set $S$ . $U \subseteq S \times S$ where   $x \sim y \iff (x,y) \in U$ where $x,y \in S$.
### Symmetry Property
$$
x \sim y \implies y \sim x
$$
$$
(x,y) \in U \implies (y,x) \in U
$$
### Reflexive Property
$$
x \sim x, \ \forall x \in S
$$
### Transitive Property
Given $x,y,z \in S$. 
$$
(x,y) \in U \text{ and } (y,z) \in U \implies(x,z) \in U
$$
### Equivalence class
The equivalence class of $x$ is the set of all elements in $S$ that are "equivalent" to $x$.
$$
[x]:=\{y∈S ∣ y∼x\} \subset S
$$
$[2] = \{ 2,4\}$ and $[1] = \{ 1,3\}$ are examples.
### Remarks
Implies that 
1. $x \in [x]$, hence $[x] \neq \emptyset$
2. $y \in [x] \iff [y] = [x]$. Hence two equivalent classes are either equal or disjoint. 

### Partitions
A partition $\{X_i\}$ of set $S$ is defined such that its union is $S$, $\bigcup_{i \in I}X_i = S$, none of its elements is empty, $X_{i\in I} \neq \emptyset$ and it is pairwise disjoint, $X_i \cap X_j = \emptyset \quad \forall i,j \in I \quad i\neq j$. Notice how our equivalence class are partitions of set $S$.



## The study of $\mathbb{Z}$

We can express addition and multiplication as such
$$
+: \mathbb{Z} \times \mathbb{Z} \to \mathbb{Z}
$$
$$
(a,b) \mapsto a+b
$$

$$
\times: \mathbb{Z} \times \mathbb{Z} \to \mathbb{Z}
$$
$$
(a,b) \mapsto a \times b
$$

Recall [[Math/Group Theory\|Group Theory]],