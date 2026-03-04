---
{"dg-publish":true,"permalink":"/math/calculus-of-variation/","dgPassFrontmatter":true,"noteIcon":""}
---



Calculus of variation aims to determine a function that minimises/maximises a value: distance, time, energy etc.

## Introduction 
A Functional accepts a function to produce a scalar. For eg. Distance functional $I[y]$ calculates the distance traversed by the function $y$ from $x_1$ to $x_2$. By setting the **boundary condition** of $(x_1, y_1)$ and $(x_2, y_2)$ we can get a finite value from the Functional.
$$
\begin{split}
I[y]&= \int_{x_1}^{x_2} \sqrt{\left( dx^2+ dy^2\right)}  \\
 &= \int_{x_1}^{x_2} \sqrt{\left(1 + \left(\frac{dy}{dx}\right)^2\right)} dx

\end{split}
$$
It adds up small arc length $ds$ along $y(x)$. Thus computing the distance effectively.

This particular *integrand* (Function being integrated) $\sqrt{\left(1 + \left(\frac{dy}{dx}\right)^2\right)}$ requires only the derivative of the function, but other types of Integrant might use $x$, $y$ or $y’$. Thus we can make a general integrant given as $F$ below.

Suppose $y= f(x)$ is an extremal (minimises/maximises Functional $I$). The boundary condition is given as $y(x_1) = y_1$ and $y(x_2) = y_2$. 
$$
I[y]= \int_{x_1}^{x_2} F(x, y, y’) dx 
$$
Suppose we slightly perturb $y$ with an arbitrary function $\eta$ to get $\bar{y}$ , to ensure it satisfies a boundary condition we set $\eta(x_1) = 0$  and $\eta(x_2) = 0$. Since $y$ is an extremal. The perturbation will cause a small difference to the Functional $I[\bar{y}]$.

$$
\bar{y}(x) = y(x) + \epsilon \cdot \eta 
$$


If $y$ is truly extremal, then $I$ should be at the minimum/maximum when $\epsilon = 0$.
$$
\left. \frac{dI[\bar{y}]}{d\epsilon} \right|_{\epsilon=0} = 0
$$
Thus 

$$
\begin{split}
\left. \frac{d}{d \epsilon} \int_{x_1}^{x_2} F(x, \bar{y}, \bar{y}’) dx \right|_{\epsilon = 0} &= 0\\
\left. \int_{x_1}^{x_2} \frac{\partial }{\partial \epsilon}F(x, \bar{y}, \bar{y}’) \right|_{\epsilon = 0} dx &= 0\\
\int_{x_1}^{x_2} \left[\frac{\partial F}{\partial \bar{y}} \cdot \frac{\partial \bar{y}}{\partial \epsilon} + \frac{\partial F}{\partial \bar{y}’} \cdot \frac{\partial \bar{y}’}{\partial \epsilon} \right]_{\epsilon = 0} dx &= 0 \\
\int_{x_1}^{x_2} \left[\frac{\partial F}{\partial \bar{y}} \cdot \eta + \frac{\partial F}{\partial \bar{y}’} \cdot \eta’ \right]_{\epsilon = 0} dx &= 0 \\
\end{split} 
$$
Next we evaluate the partial derivatives at $\epsilon = 0$ thus replacing $\bar{y}$ with $y$.

$$
\int_{x_1}^{x_2} \left[\frac{\partial F}{\partial y} \cdot \eta + \frac{\partial F}{\partial y’} \cdot \eta’ \right] dx = 0
$$

Using integration by parts on the second segment of the equation. Let $u = \frac{\partial F}{\partial \bar{y}’}$ and $v’ = \eta’$.

$$
\int uv’ = uv - \int u’v
$$
Since $\eta(x_2) = \eta(x_1) = 0$. 
$$
\begin{split}
\int_{x_1}^{x_2} \frac{\partial F}{\partial y’} \cdot \eta’ dx &= \frac{\partial F}{ \partial \bar{y}} \cdot \left[\eta\right]_{x_1}^{x_2} - \int \frac{d}{dx}\left(\frac{\partial F}{\partial y} \right) \cdot \eta \\
&= 0 - \int \frac{d}{dx}\left(\frac{\partial F}{\partial y} \right) \cdot \eta
\end{split}
$$


Thus plugging it back into the above equation.

$$
\begin{split}
\int_{x_1}^{x_2} \left[\frac{\partial F}{\partial y} \cdot \eta + \frac{\partial F}{\partial y’} \cdot \eta’ \right]  dx &= 0 \\
\int_{x_1}^{x_2} \left[\frac{\partial F}{\partial y} \cdot \eta -\frac{d}{dx}\frac{\partial F}{\partial y’} \cdot \eta \right] dx &= 0 \\
\int_{x_1}^{x_2} \left[\frac{\partial F}{\partial y} -\frac{d}{dx}\frac{\partial F}{\partial y’}  \right] \cdot \eta \  dx &= 0 \\
\end{split}
$$

Since $\eta$ is an arbitrary function (with fixed boundary points). The only way for the integral to be 0. Is if

$$
\frac{\partial F}{\partial y} - \frac{d}{dx} \left(\frac{\partial F}{\partial y’}\right) = 0
$$

This is the most famous Euler Lagrange Equation. 


