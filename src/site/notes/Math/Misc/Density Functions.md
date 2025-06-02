---
{"dg-publish":true,"permalink":"/math/misc/density-functions/"}
---



**Probability Density Function (PDF)**

The probability density function can be used to measure the probability that X would fall within a specific interval. This is done by finding the area under the probability density function.
$$
P(a \leq X \leq b) = \int_a^b f_X(x) dx
$$

We can also rewrite it as such where $\delta$ is a small infinitesimal value. 
$$
P(x \leq X \leq x + \delta ) = \int_x^{x+\delta} f_X(x) dx \approx \delta f_X(x)
$$
And
$$
f_X(x) = \frac{P(x \leq X \leq x + \delta)}{\delta}
$$
Thus, $f_X(x)$ measures how probable X would be near x.

**Joint Probability Density**

For two or more variables, their joint probability density can be given as such.

$$
P(a \leq X \leq b, c \leq Y \leq d) = \int_a^b \int_c^d xy f_{XY}(x,y) dy dx
$$

