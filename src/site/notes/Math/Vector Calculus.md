---
{"dg-publish":true,"permalink":"/math/vector-calculus/","dgPassFrontmatter":true,"noteIcon":""}
---


## Vector valued functions

A curve $r(t)$ can be defined by 
$$
\begin{split}
\mathbf{r}(t) &= \langle x(t), y(t),z(t) \rangle\\
&= x(t)\mathbf{i} +  y(t) \mathbf{j} + z(t)\mathbf{j}
\end{split}
$$
where
$$
\frac{d}{dt}\mathbf{r}(t) = x'(t)\mathbf{i} +  y'(t) \mathbf{j} + z'(t)\mathbf{j}
$$

Objects can take the motion of these curves in space. 

## Scalar Field

A scalar field is defined as a function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ 

An example would be $f(x,y) = x^2 + y^2$. It maps every coordinate to a number.

## Vector Field

A vector field is defined as a function $f : \mathbb{R}^n \rightarrow \mathbb{R}^m$ 

An example would be $\mathbf{F}(x,y) = M(x,y) \mathbf{i} + N(x,y) \mathbf{j}$. A vector field maps every coordinate in space to a vector. 


## Line Integral
### Line Integral over Scalar Fields

>[! Question] What is the Surface area of this shape?

![Pasted image 20251014221326.png](/img/user/Images/Pasted%20image%2020251014221326.png)

A function $f(x,y)$ is defined over $\mathbf{r}(t)$. $\mathbf{r}(t)$ is traced out as the orange line on the x-y plane. And we want to find the area under this closed loop.

Let $ds$ be a small arc-length along the curve $r(t)$. Where $ds = ||d \mathbf{r}||$. If we integrate around the contour $C$, summing up the product of $f(x,y)$ and $ds$. It is clear that we get the surface area.
$$
\text{Surface Area} = \int_C f(x,y) \ ds 
$$
We can also rewrite the Surface area as
$$
\int_a^b f(\mathbf{r}(t))\  ds
$$
since
$$
\begin{split}
\mathbf{r}(t) &= x(t)\mathbf{i} + y(t) \mathbf{j}\\
d\mathbf{r} &= x'(t) dt \ \mathbf{i} + y'(t) dt\  \mathbf{j}\\
ds &= ||d\mathbf{r}||  = \sqrt{x'(t)^2 + y'(t)^2}\  dt
\\ &= ||\mathbf{r}'(t)|| dt \qquad \text{--- Eq 1.}
\end{split}
$$
Thus
$$
\begin{split} 
\text{Line Integral} &= \int_a^b f(\mathbf{r}(t)) \sqrt{x'(t)^2 + y'(t)^2}\  dt \\
&= \int_a^b f(\mathbf{r}(t)) \  ||\mathbf{r}'(t)||\  dt
\end{split}
$$


### Line Integral over Vector fields

Supposed we have a vector field and a path an object takes . 
![Pasted image 20251014224332.png](/img/user/Images/Pasted%20image%2020251014224332.png)

The line integral of the vector field is to calculate the work done by the vector field in the direction of the object's motion.
Work done is defined by the product of distance and the force acting in the direction of movement.
![Pasted image 20251014224517.png](/img/user/Images/Pasted%20image%2020251014224517.png)
Assume a small particle moves distance $ds$, with a direction unit vector of $\mathbf{T}$ whilst experiencing a force $\mathbf{F}$. 
The contribution of the field along the segment $ds$ is
$$
\text{WD} = \text{Force} \cdot \text{distance} = (\mathbf{F} \cdot \mathbf{T}) \ ds
$$
The summation of WD along the contour $C$ is. (Sometimes this is called flow integrals as it measures how much the vector field flows along the line C)
$$
\text{WD} = \int_C \mathbf{F} \cdot \mathbf{T} ds
$$
If $\mathbf{F}(x,y) = P(x,y) \mathbf{i} + Q(x,y) \mathbf{j}$ 
$\mathbf{T} = \frac{d\mathbf{r}}{||d\mathbf{r}||}  = \frac{d \mathbf{r}}{ds}$ Thus, $\mathbf{T} ds = d \mathbf{r}$
$$
WD = \int_C \mathbf{F} \cdot d\mathbf{r}
$$
Thus
$$
\begin{split}
WD &= \int_C \mathbf{F} \cdot \frac{d\mathbf{r}}{dt} \cdot dt \\
&= \int_a^b \mathbf{F}(\mathbf{r}(t)) \cdot \mathbf{r'}(t) dt
\end{split}
$$
We can also rewrite the Line integrals as such

$$
\begin{split}
WD &= \int_a^b \left[P(\mathbf{r}(t))\  x'(t) + Q(\mathbf{r}(t)) \ y'(t)\right]  dt \\
&= \int_a^b P(\mathbf{r}(t))\  \frac{dx}{dt} dt  + \int_a^b Q(\mathbf{r}(t)) \ \frac{dy}{dt}dt \\
&= \int_a^b P(\mathbf{r}(t))\ dx  + \int_a^b Q(\mathbf{r}(t)) dy \\
\end{split}
$$


## Gradient Vector Field over Scalar Functions

Given a function $f:\mathbb{R}^n \rightarrow \mathbb{R}$,   The grad of a Scalar field will generate a vector field.
$$
\nabla f = \frac{\partial f}{\partial x} \mathbf{i} + \frac{\partial f}{\partial y} \mathbf{j} + \frac{\partial f}{\partial z} \mathbf{k} + \dots
$$
where
$$
\nabla = \langle \frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z}, \dots \rangle
$$
 ![Pasted image 20251014232215.png](/img/user/Images/Pasted%20image%2020251014232215.png)

The gradient vector points in the direction of steepest increase. The length $|\nabla f|$ tells us how fast $f$ is changing in the direction 

> Side Note
> If the Contour is closed (a loop), we express the integral as $\oint$


## Circulation
Circulation can be defined using flow integrals. Where we find how much a vector field flows along a closed contour (typically a circle)

$$
\oint \mathbf{F} \cdot d\mathbf{r}
$$
The problem is that we can only find the circulation for a macroscopic object (like a big circle). What if want to find the circulation at a point? 
>[! Question] What is the degree of circulation at a point?
![Pasted image 20251015000238.png](/img/user/Images/Pasted%20image%2020251015000238.png)

if $\mathbf{F}(x,y) = P(x,y) \mathbf{i} + Q(x,y) \mathbf{j}$
Recall that
$$
\begin{split}
\mathbf{r}(t) &= x(t)\mathbf{i} + y(t) \mathbf{j}\\
d\mathbf{r} &= x'(t) dt \ \mathbf{i} + y'(t) dt\  \mathbf{j}
\end{split}
$$
Imagine a infinitesimal region, and we want to find the circulation at that region.

$$
\oint_C \mathbf{F} \cdot d \mathbf{r} = \sum_{i=1}^4 \int_{Ci}\mathbf{F} \cdot d\mathbf{r} 
$$
For $C_1$ that spans $\Delta x$, $dy = 0$
$$
\int_{C1}\mathbf{F} \cdot d\mathbf{r} = \int_{x}^{x+\Delta x}\mathbf{F} \cdot d\mathbf{r} = \int_{x}^{x+\Delta x} P(x,y) dx \approx P(x,y)\Delta x
$$
For $C_2$ that spans $\Delta y$, $dx = 0$
$$
\int_{C2}\mathbf{F} \cdot d\mathbf{r} = \int_{y}^{y+\Delta y}\mathbf{F} \cdot d\mathbf{r} = \int_{y}^{y+\Delta y} Q(x+\Delta x,y) dy \approx Q(x+\Delta x,y)\Delta y
$$
For $C_3$ that spans $-\Delta x$, $dy = 0$
$$
\int_{C3} \mathbf{F} \cdot d \mathbf{r} = - \int_{x}^{x + \Delta x} P(x, y+ \Delta y) dx \approx -P(x, y + \Delta y) \Delta x
$$
For $C_4$ that spans $-\Delta y$, $dx = 0$
$$
\int_{C4} \mathbf{F} \cdot d \mathbf{r} = - \int_{y}^{y+\Delta y} Q(x, y) dy = -Q(x, y) \Delta y
$$
---
Based on the partial differentiation formula
$$
\frac{\partial}{\partial x}f = \lim_{\Delta x \rightarrow 0} \frac{f(x+\Delta x) - f(x)}{\Delta x}
$$

Adding $C1$ and $C3$ first
$$
\int_{C1} \mathbf{F} \cdot d\mathbf{r} + \int_{C3}\mathbf{F} \cdot d\mathbf{r} = P(x,y)\Delta x -P(x, y + \Delta y) \Delta x = - \frac{\partial P}{\partial y} \Delta x \Delta y
$$
Adding $C2$ and $C4$

$$
\int_{C2} \mathbf{F} \cdot d\mathbf{r} + \int_{C4}\mathbf{F} \cdot d\mathbf{r} =Q(x+\Delta x,y)\Delta y -  Q(x, y) \Delta y = \frac{\partial Q}{\partial x} \Delta x \Delta y
$$
Thus

$$
\oint \mathbf{F} \cdot d\mathbf{r} = \frac{\partial Q}{\partial x} \Delta x \Delta y - \frac{\partial P}{\partial y} \Delta x \Delta y = \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right)\Delta x \Delta y
$$
$$
\underbrace{\oint \mathbf{F} \cdot d\mathbf{r}}_{\text{Circulation around rectangle}} = \underbrace{\left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right)}_{\text{Circulation Density}} \underbrace{\Delta x \Delta y}_{\text{Area of rectangle}}
$$
## Divergence

Divergence is defined as 
