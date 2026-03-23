---
{"dg-publish":true,"permalink":"/math/fourier-series/","dgPassFrontmatter":true,"noteIcon":""}
---


What is a Fourier series? 
> A Fourier series allows you to decompose a periodic function into a sum of complex sinusoidal waves of frequencies that is integer multiple of its fundamental frequency.

## Introduction
![Pasted image 20251122220856.png](/img/user/Images/Pasted%20image%2020251122220856.png)
We can express any closed function as a vector sum of rotating circles moving at different speeds, initial angle and amplitude.
> [!note]
> For a function $e^{n\cdot 2i \pi t}$. It is rotating $n$ times about the origin within a span of $1s$

So any function can be expressed as $f(t)$, $f:\mathbb{R} \mapsto \mathbb{C}$. Where $f$ is a linear combination of rotating complex numbers in the form of $re^{it}$ where $t\in[0,1]$
$$
f(t) = \dots + c_{-1}e^{-1\cdot2\pi i t} + c_{0}e^{0\cdot 2\pi it} + c_1e^{1 \cdot 2 \pi it} \dots
$$
or more simply
$$
f(t) = \sum_{n=-\infty}^{\infty} c_{n}e^{n\cdot 2\pi it} 
$$
In addition, since
$$
\int e^{ax} dx = \frac{1}{a}e^{ax}, \quad a \neq 0
$$
thus
$$
\int_{0}^{1} e^{n2 \pi i t} dt = \frac{1}{2 \pi in} \left[e^{2n\pi i t} \right]^1_0 = \frac{1}{2 \pi i n} (1 - 1) = 0, \qquad n \neq 0
$$
However, if $n = 0$.
$$
\int^1_0 e^{0 \cdot 2 \pi i t} dt = 1
$$
To find $c_0$ we can take the integral of $f(t)$ from $0$ to $1$.
$$
\begin{split}
c_0 &= \int_0^1 f(t)dt\\
&= \dots + c_{-1} \int_0^1 e^{-1\cdot 2\pi it} dt+ c_{0}\int_0^1 e^{0\cdot 2\pi it} dt + c_{1}\int_0^1  e^{1\cdot 2\pi it} dt + \dots\\
& =  \dots 0 + 0 + c_0 + 0 + 0 \cdots
\end{split}
$$

In addition, to find $c_1$, we can take the integral of $f(t) \cdot e^{-1 \cdot 2 \pi it}$ from $0$ to $1$.
$$
\begin{split}
c_1 &= \int_0^1 f(t) \cdot e^{-1 \cdot 2 \pi it}dt\\
&=  \dots + c_{-1} \int_0^1 e^{(-1-1)\cdot 2\pi it} dt+ c_{0}\int_0^1 e^{(0-1)\cdot 2\pi it} dt + c_{1}\int_0^1  e^{(1-1)\cdot 2\pi it} dt + \dots\\
&= c_1
\end{split}
$$
Thus, we essentially make the integral in the $c_1$ expression equate to 1. More generally
$$
c_n = \int_{0}^{1} f(t) e^{-n\cdot 2 \pi it} dt
$$
