---
{"dg-publish":true,"permalink":"/math/calculus/","dgPassFrontmatter":true,"noteIcon":""}
---


## Differentiation

It is the slope of the line. Given by $\frac{dy}{dx}$ . The more proper definition would be.
$$
\frac{dy}{dx} = \lim_{h \rightarrow 0} \frac{f(x+h) - f(x)}{h}
$$
For example,
$$
f(x) = x^2
$$
$$
\begin{eqnarray}
\frac{dy}{dx} &=& \lim_{h \rightarrow 0} \frac{(x+h)^2 - x^2}{h}\\
&=& \lim_{h \rightarrow 0} \frac{x^2 + 2xh + h^2- x^2}{h}\\
&=& 2x 
\end{eqnarray}
$$
### Chain Rule
$$
\frac{d}{dx}f(g(x)) = f'(g(x)) \cdot g'(x)
$$

### Product Rule
$$
\frac{d}{dx} f(x) \cdot g(x) = f'(x) g(x) + f(x) g'(x)
$$

### Quotient Rule
$$
\frac{d}{dx} \frac{f(x)}{g(x)} = \frac{f'(x)g(x) - f(x)g'(x)}{g(x)^2}
$$


| $f(x)$      | $f'(x)$                             |
| ----------- | ----------------------------------- |
| $x^n$       | $nx^{n-1}$                          |
| $e^{f(x)}$  | $f'(x)\cdot e^{f(x)}$               |
| $a^{f(x)}$  | $\ln a \cdot f'(x) \cdot  e^{f(x)}$ |
| $\ln(x)$    | $\frac{1}{x}$                       |
| $\sin x$    | $\cos x$                            |
| $\cos x$    | $- \sin x$                          |
| $\tan x$    | $\sec^2 x$                          |
| $\arcsin x$ | $\frac{1}{\sqrt{1-x^2}}$            |
| $\arccos x$ | $-\frac{1}{\sqrt{1-x^2}}$           |
| $\arctan x$ | $\frac{1}{1 + x^2}$                 |
| $\sec x$    | $\sec x \tan x$                     |
| $\csc x$    | $-\csc x \cot x$                    |
| $\cot x$    | $-\csc^2 x$                         |

## Integration 

Integration is just the opposite of differentiation
### Integration by Substitution

1. Substitute a function as a variable.  
2. Change the limits and dx. Integrate with respect to that said variable

> [!Example]
> This is a sample question from the Math worksheet
> Use substitution of $x = \tan \theta$ to find  $\int^1_0 \dfrac{1}{(x^2+1)^2} dx$

Step 1. Finding $dx$
$$
\begin{split}
\frac{dx}{d \theta } &= \sec^2\theta \\
dx &= \sec^2 \theta \ d \theta
\end{split}
$$
Step 2. Sub in $x = \tan \theta$, and $dx$ and changing the limits
$$
\begin{split}
\int^1_0 \frac{1}{(x^2+1)^2} dx &= \int^{\arctan1}_{\arctan 0} \frac{1}{(\tan^2\theta + 1)^2} \sec^2\theta\  d \theta \quad \text{[Using trigo identities]}\\
&= \int^{\frac{\pi}{4}}_0 \frac{1}{\sec^2 \theta}d\theta = \int^{\frac{\pi}{4}}_0 \cos^2 \theta \ d\theta \quad \text{[Using double angle formulae]}\\
&= \int^{\frac{\pi}{4}}_0 \frac{\cos 2\theta + 1 }{2} \ d\theta \\
&= \left[ \frac{\sin 2 \theta}{4} + \frac{1}{2} x\right]^{\frac{\pi}{4}}_0 = \frac{1}{4} + \frac{\pi}{8} \quad [QED]
\end{split}
$$
### Integration by Parts
$$
\begin{split}
\frac{d}{dx} uv &= u'v + uv'\\
uv &= \int u'v +uv'dx\\
&= \int u'v \ dx + \int uv' \ dx
\end{split}
$$
Thus
$$
\int u'v \ dx  = uv - \int uv' \ dx
$$
> [!Example]
> This is a sample question from the Math worksheet
> Find $\int x \ln x \ dx$
1. sub $v$ for the part that is **hardest** to integrate.
2. sub $u'$ for the part that is **easiest** to integrate

| Substitute if     | $u'$ | $v$ |
| ----------------- | ---- | --- |
| Hard to Integrate |      | $X$ |
| Easy to Integrate | $X$  |     |

Since $\ln x$ is hard to integrate and $x$ is easy to integrate, let $v = \ln x$, and $u' = x$ ,
$$
\begin{split}
\int x \ln x dx = \int u' v \ dx &= uv - \int uv '\ dx\\
&= \frac{x^2}{2}\ln x - \int \frac{x^2}{2}\frac{1}{x} \ dx\\
&= \frac{x^2}{2}(\ln x - \frac{1}{2}) + C
\end{split}
$$
A nice application of this formula is in its immense contribution in [[Math/Derivations/Proof for Wallis Product\|Proof for Wallis Product]].
### Trick for inverse trigo functions:

This type of questions typically asks us to solve for $\int \dfrac{k}{a + (\frac{x}{b})^2} \ dx$  or $\int \dfrac{k}{\sqrt{a + (\frac{x}{b})^2}} \ dx$
But how do we solve it??

1. Force the $a$ in the denominator to be $1$ by factoring $a$ out.
2. Perform integration by substitution on the value $\frac{x}{b}$ 
3. Substitute the appropriate inverse trig identity and solve. 


> [!Example]
> This is a sample question from the Math worksheet
> Find $\int \dfrac{3}{\sqrt{4^2 - (5x+3)^2}} dx$ 

Step 1. Force the $a$ in the denominator to be 1 by factoring out 4.

$$\int \frac{3}{\sqrt{4^2 - (5x+3)^2}} dx = \int \frac{3}{4 \cdot \sqrt{1 - (\frac{5x+3}{4})^2}} dx$$
Step 2. Perform integration by substitution by letting $u = \frac{5x+3}{4}$
$$
\frac{du}{dx} = \frac{5}{4}
$$
$$
\begin{split}
\int \frac{3}{4 \cdot \sqrt{1 - (\frac{5x+3}{4})^2}} dx &= \int \frac{3}{4 \cdot \sqrt{1 - u^2}} \frac{4}{5} du\\
&= \frac{3}{5} \int \frac{1}{\sqrt{1 - u^2}} du
\end{split}
$$

Step 3. Substitute the appropriate inverse trig identity and solve. 

$$
\begin{split}
\frac{3}{5} \int \frac{1}{\sqrt{1 - u^2}} du &= \frac{3}{5} \arcsin u \\
&= \frac{3}{5} \arcsin \frac{5x + 3}{4}
\end{split}
$$

### Solving using Reverse Factor Formulae

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/trigonometry/#reverse-factor-formulae" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



### Reverse Factor Formulae

$
2 \sin A \cos B = \sin(A+ B) + \sin (A-B)
$
$
2 \cos A \sin B = \sin (A+ B) - \sin (A-B)
$
$
2 \cos A \cos B = \cos (A + B) + \cos (A-B)
$
$
-2 \sin A \sin B = \cos (A+ B) - \cos (A-B)
$


</div></div>

> [!Example]
> Find using the reverse factor formulae
> $$
> \int \sin 5x \cos 3x dx
> $$

Step 1. Identify which reverse factor formulae to use.
$$
\sin A \cos B = \frac{1}{2} (\sin (A+ B) + \sin (A-B))
$$
Step 2. Substitute the corresponding values into A and B 
$$
\sin 5x \cos 3x = \frac{1}{2} (\sin 8x + \sin 2x)
$$
Step 3. Integrate the expression above
$$
\int \frac{1}{2} (\sin 8x + \sin 2x) \  dx= - \frac{1}{16} \cos 8x - \frac{1}{4} \cos 2x + C
$$

### Volume of Revolution

Suppose we have $f(x)$, rotating it around the $x-$axis would form a volume of 
$$
V = \pi \int_{a}^{b} f(x)^2 \ dx
$$
## Ordinary Differential Equations (ODE)

### Solving a Variable Separable Differential equation
We can sorta treat $\frac{dy}{dx}$ as fractions. Its quite intuitive.

> [!Example]
> Find the general solution of the following. 
> $$
> \frac{dy}{dx} = \frac{1}{3} \sqrt{5-y^2}
> $$

Step 1. Put all the $y$ on one side and the $x$ on the other
$$
\frac{1}{\sqrt{5-y^2}} \frac{dy}{dx} = \frac{1}{3}
$$
Step 2. Multiply $dx$ on both sides
$$
\frac{1}{\sqrt{5-y^2}} dy = \frac{1}{3} dx
$$
Step 3. Put an Integral sign on both sides and solve
$$
\begin{split}
\int \frac{1}{\sqrt{5-y^2}} dy &= \int \frac{1}{3} dx \\
\end{split}
$$
$$
\begin{split}
\int \frac{1}{\sqrt{5-y^2}} dy &= \int \frac{1}{\sqrt{5} \sqrt{1 - (\frac{y}{\sqrt{5}})^2}} dy,   \quad \text{sub u = $\frac{y}{\sqrt{5}},  \frac{du}{dy} = \frac{1}{\sqrt{5}}$ }\\
&= \int \frac{1}{\sqrt{5}} \frac{1}{\sqrt{1 - u^2}} \sqrt{5}\ du\\
&= \arcsin u +C \\
&= \arcsin \left( \frac{y}{\sqrt{5}}\right) + C = \frac{1}{3}x
\end{split}
$$
Thus
$$
\begin{split}
\arcsin (\frac{y}{\sqrt{5}}) &= \frac{1}{3}x + C\\
y &= \sqrt{5} \sin \left( \frac{1}{3}x + C\right)
\end{split}
$$
### Solving homogeneous differential equations by substituting $y = vx$

It argues that this will make your life easier when solving differential functions $\frac{dy}{dx}$ that can be expressed in terms $\frac{y}{x}$, like $f(\frac{y}{x})$
$$
\frac{dy}{dx}= f\left(\frac{y}{x}\right)
$$
So it assumes when you divide $y$ by $x$, you get a function $v$ . 
$$
y = vx
$$
thus
$$
\frac{dy}{dx} = vx' + v'x = v + \frac{dv}{dx}x = f(v)
$$
I think its best for an example
> [!Example]
> Find the general solution of the following. 
> $$
> \frac{dy}{dx} = \left(\frac{y}{x}\right)^2 + \frac{y}{x} + 1
> $$

Step 1. Substitute $\frac{y}{x}$ as $v$  
$$
\frac{dy}{dx} = v^2 + v + 1
$$
Step 2. Since $\frac{dy}{dx} = v + \frac{dv}{dx} x$ , equate that to the above
$$
v^2 + v + 1 = v + \frac{dv}{dx} x
$$
Step 3. Solve the equation
$$
\begin{split}
\int \frac{1}{x}dx &= \int \frac{1}{v^2 +1} dv\\
\ln |x| + C &= \arctan v \\
v &= \tan (\ln |x| + C)\\
y &= x \cdot \tan (\ln |x| + C)
\end{split}
$$

### Solving a Differential Equation using Integrating Factor

It aims to solve for differential equations in this form
$$
\frac{dy}{dx} + P(x) y = Q(x)
$$
Objectives: I want to separate $y$ on the left and $x$ on the right. We can do this by multiplying throughout by an arbitrary function called Integrating factor $I(x)$

Suppose the Integrating factor $I(x)$ follows this property
$$
I'(x) = P(x)I(x)
$$
Why tho? See that if we multiply throughout by $I(x)$
$$
I(x) \frac{dy}{dx} + I(x)P(x)y = I(x)Q(x)
$$
thus
$$
\begin{split}
I(x) \frac{dy}{dx} + I'(x)y &= I(x)Q(x)\\
\frac{d}{dx} I(x)y &= I(x) Q(x) \quad \text{[Integrate throughout]}\\
I(x)y &= \int I(x) Q(x) \ dx \\
y &= \frac{\int I(x) Q(x) \ dx}{I(x)}
\end{split}
$$
**Defining** $\mathbf{I(x)}$
Since
$$
P(x) = \frac{I'(x)}{I(x)}
$$
Integrating both sides
$$
\begin{split}
\int P(x)\ dx &= \int \frac{I'(x)}{I(x)} \ dx \\
&= \ln |I(x)| + C\\
 I(x) &= e^{\int P(x) \ dx + C}\\
 &=  A e^{\int P(x)\ dx} \quad \text{[where $A = e^C$]}
\end{split}
$$
**Thus**
For simplicity, let $C = 0$, thus $A = 1$
$$
y = \frac{\int e^{\int P(x) \ dx}Q(x) \ dx}{e^{\int P(x) \ dx}}
$$
> [!Example]
> Find the general solution of the following. 
> $$
> \frac{dy}{dx} + y = 3e^x
> $$

> Note that the coefficient of $\frac{dy}{dx}$ has to be $1$

Step 1. Identify $P(x) = 1$, find the integrating factor $I(x)$
$$
I(x) = e^{\int 1 \ dx} = e^x
$$
Step 2. Multiply throughout by $I(x)$
$$
e^x \frac{dy}{dx} + e^x y = 3e^{2x} 
$$
Step 3. Solve
$$
\begin{split}
e^x \frac{dy}{dx} + e^x y &= 3e^{2x} \\
\frac{d}{dx}e^x y &= 3e^{2x} \\
e^x y &= \int 3e^{2x} \ dx = \frac{3}{2}e^{2x} + C\\
y &= \frac{3}{2}e^x + C e^{-x}
\end{split}
$$
### Euler's Method

It attempts to approximate the function by using its derivatives. Suppose
$$
\frac{dy}{dx} = f(x,y) \approx \frac{\Delta y}{\Delta x}
$$
Suppose we know $(x_0, y_0)$, which is a point lying on $y$.
For some small increment in $x$ by $\Delta x$.
$$
\left\{
\begin{aligned}
x_{n+1} &= x_n + \Delta x\\
y_{n+1} &= y_n + \Delta x \cdot f(x_n,y_n) \\
\end{aligned}
\right. \quad \text{, n = 0, 1, 2, 3 ...}
$$
Understand that essentially 
$$
y_{n+1} = y_n + \Delta y
$$



## Limits 

$\lim_{x\rightarrow 0} f(x)$ ask the question, what does the value $f(x)$ approach as $x$ approaches $0$?

We are interested in finding the limits of a function in which just subbing in the values of 
$x$ would yield an undefined solution like $\frac{0}{0}$ or $\frac{\infty}{\infty}$. Suppose $f(0) = g(0) = 0$.

$$
\lim_{x \rightarrow 0} \frac{f(x)}{g(x)} = ???
$$
### L' Hopital rule

It basically says that if the solution is undefined, just differentiate $f(x)$ and $g(x)$ until it yields a valid solution.
> [! example]
> For example
> $$
> \lim_{x \rightarrow 0} \frac{\sin x}{x} = \frac{\cos x}{1} = 1
> $$


Look at [[Math/Sequences and Series#Maclaurin Series\|Maclaurin Series expansion]]

The expansion of $\sin x$ yields
$$
\lim_{x \rightarrow 0} \frac{x + \frac{x^3}{3!} + \dots}{x} = \lim_{x \rightarrow 0} 1 + \frac{x^2}{3!} + \dots = 1
$$
We aim to separate a constant that is independent of $x$ from this fraction.

Look that if we differentiate $\sin x$ and $x$ instead. We can also get a constant of $1$ out.
$$
\lim_{x \rightarrow 0} \frac{x + \frac{x^3}{3!} + \dots}{x} = \lim_{x \rightarrow 0} \frac{1 + \frac{x^2}{2!} + \dots}{1} = 1
$$
Differentiation is now a tool used to factor $x$ from $f(x)$ and $g(x)$. That's why the L'hopital rule works.
