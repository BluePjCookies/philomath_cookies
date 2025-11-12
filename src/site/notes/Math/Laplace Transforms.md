---
{"dg-publish":true,"permalink":"/math/laplace-transforms/","dgPassFrontmatter":true,"noteIcon":""}
---


## Introduction

Recall in [[Math/Derivations/Proof for Euler's Identity using Maclaurin Series\|Proof for Euler's Identity using Maclaurin Series]], and [[Math/Derivations/Proof for Euler's Identity using ODEs\|Proof for Euler's Identity using ODEs]]. We derived that $g(t) = e^{it} = \cos t + i\sin t$.  where $g$ maps $t$ (time) to a position on the complex plane. $g: \mathbb{R} \mapsto \mathbb{C}$

Suppose a particle follows the path of $g(t)$. It's velocity is given by $\frac{d}{dt}g(t) = i g(t)$. Thus its velocity vector is always **perpendicular** to its position _(Recall that $i$ is a $90$ degree rotation)_. As such, it will move in a circular motion. $x = \cos t$ and $y = \sin t$. 

### Generalisation

Suppose a particle follows the path of $f(t) = e^{st}$ where $s \in \mathbb{C}$ and $f : \mathbb{R} \mapsto \mathbb{C}$. Let $s = a+bi$. 
$$
f(t) = e^{st}
$$
#### Intuition

 Consider initial position at $f(0) = 1$. The velocity of the particle is $\frac{d}{dt}f(t) = sf(t)$. Thus, the particle at $1 +0i$ will have a velocity $s$. If $a < 0$, $s$ is pulling the particle inwards, causing it to spiral inwards. If $a > 0$, $s$ is pushing the particle outwards, causing it to spiral outwards. As $|b|$ increases, it's angular frequency $\omega = \frac{d \theta}{dt} = \frac{d bt}{dt} = b$ increases, causing it to move faster in a circular motion. Thus $x = e^{at} \cos(bt)$ , $y = e^{at} \sin (bt)$.
$$\begin{split}
e^{(a + ib)t} &= \overbrace{e^{at}}^{\text{Magnitude}} \overbrace{e^{ibt}}^{\omega} \\
&= e^{at} \left[\cos(bt) + i \sin(bt) \right]
\end{split}
$$

$Re(s)$ determines the rate of change of magnitude.
$Im(s)$ determines the angular frequency of the particle ($\omega$).

### Why do we care?

Consider a scenario of a mass on spring placed horizontally.
The force acting on the mass can be modelled as such.

$$F = -kx - \mu v$$
$k$ : spring constant
$\mu$ : damping term (friction, air resistance)
$x$ : displacement from equilibrium.
$v$  : velocity

It describes how the spring and damping will exert a force $F$ on the mass to resist its direction of motion. We can rewrite it as

$$m x''(t) + k x(t) + \mu x'(t) = 0$$
Let's guess that the solution of $x(t)$ is $e^{st}$. Thus
$$
\begin{split}
ms^2 e^{st} + ke^{st} + \mu s e^{st} &= 0\\
e^{st}(ms^2 + \mu s + k) &= 0\\
ms^2 + \mu s +k &= 0
\end{split}
$$
Solving for $s$ gives 
$$
s = \frac{-\mu \pm \sqrt{\mu^2 -4(mk)}}{2m}
$$
For simplicity, let's assume that $\mu$ is $0$.
$$
\begin{split}
ms^2 &= -k\\
s &= \pm \sqrt{-\frac{k}{m}} = \pm i \sqrt{\frac{k}{m}} = \omega
\end{split}
$$
What does this mean? It basically means that the natural frequency of the system is $Im(s) = \omega = \pm \sqrt{\frac{k}{m}}$. Since $Re(s) = 0$, its amplitude does not change.

BUT WAIT!!! There are two solutions for $s$, but in fact, there are a whole family of solutions for $x(t)$!

#### Linearity

If $x_1$ solves 
$$m x_1''(t) + k x_1(t) = 0$$
and $x_2$ solves
$$
m x_2''(t) + k x_2(t) = 0
$$
Then $(c_1x_1 + c_2x_2)$ solves it as well.
$$
m [c_1x_1''(t) + c_2x_2''(t)] + k [c_1x_1(t) + c_2x_2(t)]  = 0
$$
Thus, there are a whole family of equations $x(t)$ that satisfy the conditions $m x''(t) + k x(t) = 0$
$$
x(t) = c_1 e^{s_1 t} + c_2 e^{s_2 t}
$$
Thus, the equation is just the linear combination of the complex exponential of $s$.

In physics, a lot of functions can be expressed as 
$$
f(t) = \sum_{n=1}^N c_n e^{s_nt}
$$

## Introduction

A Laplace transform is a "function" that maps one function in time-domain to another function in the s domain. where $t \in \mathbb{R}, s \in \mathbb{C}$
$$
F(s) = \int_0^{\infty} f(t) e^{-st} dt
$$
And
$$
\mathcal{L}\{f(t) \} = F(s)
$$
Lets consider the simplest case where $f(t) = 1$
$$
\begin{split}
\int_0^{\infty}e^{-st} dt &= \left[ -\frac{1}{s}e^{-st}\right]^\infty_0 \\
&= \frac{1}{s}
\end{split}
$$
Consider now, $f(t) = e^{at}$
$$
e^{at} \xrightarrow{\mathcal{L}} \int_0^{\infty}e^{at}e^{-st}dt = \frac{1}{s-a}
$$
The Laplace transform of $e^{at}$ has a pole at $a$ where $F(a) = \infty$. Thus we have figured out what values of $a$ are embedded in the function $f(t)$.

Consider now $f(t) = \cos(\omega t)$. $\cos(\omega t) = \frac{1}{2}e^{i\omega t} + \frac{1}{2}e^{-i\omega t}$. (Recall [[Math/Complex Numbers\|Complex Numbers]])
Its Laplace transform is
$$
\begin{split}
\cos(\omega t) &\xrightarrow{\mathcal{L}} \int_0^{\infty} \left[ \frac{1}{2}e^{i\omega t} + \frac{1}{2}e^{-i\omega t} \right] e^{-st} dt  \\
\mathcal{L} \{ \cos \omega t \}&= \int_0^\infty \frac{1}{2}e^{i\omega t} e^{-st} + \int_0^\infty \frac{1}{2}e^{-i \omega t} e^{-st} \\
&= \frac{1}{2(s-\omega i)} + \frac{1}{2(s+\omega i)}\\
&= \frac{s}{s^2 + \omega^2}
\end{split}
$$
The poles in its Laplace transform at $s = \pm i \omega$ helps us identify the family of equations that describes $\cos(\omega t)$. Typically, the expression $\cos(\omega t) = \frac{1}{2}e^{i\omega t} + \frac{1}{2}e^{-i\omega t}$ is unknown, thus integration by parts is usually used to get the poles of the equation.

