---
{"dg-publish":true,"permalink":"/math/lambda-calculus/"}
---


Lambda calculus is regarded as the most simplest programming language in the world. It serves as a basis for logic that powers applications in Computer Science.

Lambda calculus is made from three templates.

### First
$$
a
$$
### Second
$$
(\lambda a. \_\_)
$$
### Third
$$
(\_\_ \ \_\_)
$$
We can substitute any templates into any of the blanks in any template

> In lambda calculus, everything is a function and can be applied on one another

In lambda calculus. $(\lambda a.a)$  is a function that takes in a to output a

$$
(\overbrace{\lambda a.}^{\text{function + argument}} \ \ \overbrace{a}^{\text{output}})
$$

```python 
def func(a):
	return a
```

to pass in an argument lets say b. we apply function $(\lambda a.a)$ on $b$. Thus, passing $b$ as an input into the function, replacing all values of $a$ with $b$.
$$
((\lambda a. a) \ b)  = b
$$
```python
func(b) # b
```

to pass more than one argument, lets say. Lets assume we have defined $+$
```python
def func(a, b, c):
	return a+b+c
```

we have to define lambda for $a$, $b$ and $c$
$$
(\lambda a. (\lambda b.(\lambda c.a+b+c) \ 3\ )\ 2\ ) \ 1
$$
Going from outer to inner brackets. Replace all $a$ with $1$, $b$ with $2$ and $c$ with $3$.
$$
(\lambda a. (\lambda b.(\lambda c.a+b+c) \ 3\ )\ 2\ ) \ 1 \rightarrow \lambda b.(\lambda c. 1+b+c) \ 3 ) \ 2 \rightarrow (\lambda c. 1+2 + c) \ 3 \rightarrow 1+2+3 
$$

we can express it as a short hand
$$
\lambda a.\lambda b. \lambda c . (a+b+c)
$$

## Boolean Logic

True and False are **selectors**. True selects the first element while False selects the second.

### True: 
$$
T := (\lambda x. \lambda y.x)
$$
### False
$$
F := (\lambda x. \lambda y.y)
$$

For example
$$
(T \ a \ b) = a
$$
And
$$
(F \ a \ b)= b
$$

### NOT
NOT T = F
NOT F = T
$$
\text{NOT} = \lambda x.(x \  \ F \  \ T) $$

Such that 
$$
\begin{split}
\text{NOT} \ T &= (\lambda x.(x \  \ F \ \ T)) \ T\\
&= (T \ F \ T) \\
&= F
\end{split}
$$
And
$$
\begin{split}
\text{NOT} \ F &= \lambda x.(x \  \ F \ \ T) \ F \\
&= (F \ F \ T)\\
&= T
\end{split}
$$
### AND
T AND T = T
T AND F = F
F AND T = F
F AND F = F
$$
\text{AND} = \lambda x.\lambda y. (x \ y \ F)
$$

### OR

T OR T = T
T OR F = T
F OR T = T
F OR F = F

$$
\text{OR} = \lambda x. \lambda y.(x \ T \ y)
$$

### NAND
T NAND T = F
T NAND F = T
F NAND T = T
F NAND F = T

$$
\text{NAND} = \lambda x. \lambda y.(\text{NOT} \ (\text{AND} \ x\ y ))
$$

### NOR
T NOR T = F
T NOR F = F
F NOR T = F
F NOR F = T

$$
\text{NOR} = \lambda x.\lambda y.(\text{NOT} \ (\text{OR} \ x\ y) )
$$

From these gates, you can theoretically compute and create any function that a computer can do. 

