---
{"dg-publish":true,"permalink":"/math/combinations-and-permutations/"}
---


There are $\binom{n}{r}$ ways to pick $r$ objects from $n$ objects

$$
\binom{n}{r} = \frac{n!}{r! (n-r)!}
$$
There are $n!$ ways to rearrange $n$ objects.
$$
n! = n \cdot (n-1) \cdot (n-2) \dots \cdot 
$$

> [!Question] Problem
> John is trying to set up a 6 digit password. Given that he has 12 numeric characters, How many permutations of his passwords are there?

Ans:  $12^6$ permutations.

## Permutations

How many ways can you pick and arrange $r$ objects from $n$ objects.
$$
^{n}P_r = \frac{n!}{(n-r)!}$$
In permutation, order matters. For example, given 3 choices (ABC) and pick two. $\binom{3}{2}$ would only find 3 ways, AB, BC, AC. However, $^3P_2$ will find 6 ways, AB, BA, BC, CB, AC, CA. (NOTE: order matters)

