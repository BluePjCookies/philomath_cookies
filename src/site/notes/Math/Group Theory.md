---
{"dg-publish":true,"permalink":"/math/group-theory/"}
---


Group theory is a fascinating study of systems and groups. It studies transformations that lead to some sort of symmetry. The field might be a little abstract but bear with me as I try to explain it. 

## What is a Group?

A group required a set of elements (G) and an operation $(\cdot)$. For something to be considered a group, it must satisfy 4 conditions.

### Closure
A group has to be closed. Thus $\forall a,b \in G$.
$$
a \cdot b \in G
$$
### Associative
A group has to satisfy associative properties. Thus $\forall a,b,c \in G$.
$$
a \cdot (b \cdot c) = (a \cdot b) \cdot c
$$
### Identity 
A group has to satisfy Identity properties. Thus, there  $\exists e \in G$ where $\forall a \in G$
$$
e \cdot a = a \cdot e = a
$$
### Inverse
A group has to satisfy Inverse properties. Thus $\exists b \in G$  where $\forall a \in G$.
$$
a \cdot b = e = b \cdot a
$$

Understand Logic notation [[Math/Notation\|Notation]]

## Examples of a Group

> [!Example]
> An example of a Group is $(\mathbb{Z}, +)$.  We define the operator as $(+)$. Recall that $\mathbb{Z}$ is a set of all integers including 0. 

### Why is it a Group?
- [x] Closure 
	-  The addition of two integers logically results in another integer.
- [x] Associative
	- The addition of integers is not dependent on the order in which it is applied.
- [x] Identity
	- The identity element of $\mathbb{Z}$ is $0$.
- [x] Inverse
	- The inverse $\forall a \in \mathbb{Z}$ is $-a$.

> [!Example]
> An example that is not a group is $(\mathbb{Z}, \cdot)$. We define the operator as $(\cdot)$.
### Why is it not a Group?
- [x] Closure 
	-  The multiplication of any integers always results in another integer
- [x] Associative
	- It is independent of the order in which it is applied 
- [x] Identity
	- The identity of this system is 1.
- [ ] Inverse
	- It does not have an inverse. since inverse of $a$ is $\frac{1}{a}$. But $\mathbb{Z}$ is for integers only. Not fractions.

### Commutativity
A group which satisfy commutative properties are considered **abelian**. such that $\forall a,b \in G$
$$
a \cdot b =b \cdot a
$$

---
Group theory finds transformations on elements in a set that preserves a certain structure and symmetry within the group. Read more here: [[Math/Structures\|Structures]] (Still working on it)
