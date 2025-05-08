---
{"dg-publish":true,"permalink":"/math/distributions/"}
---


The Gaussian Distribution is given as
$$
\frac{1}{\sigma \sqrt{2\pi}}e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma} \right)^2}
$$

But for the sake of our sanity, lets just ignore all this and reduce the formula to the below. Basically all normal distributions are usually in this form
$$
e^{-x^2}
$$

> [!info] Fun fact
> Do you know that the expression below simply cannot be defined using known identities? (No arrangement of $\sin, \cos, \ln etc$ can arrive at the solution). 
> $$
> \int e^{-x^2} \ dx
> $$
> But Mathematicians were able to figure out that  ([[Math/Derivations/Proof for Area under Gaussian distribution\|proof]]) Its a really beautiful proof (Go check it out)
> $$
\int_{-\infty}^{\infty} e^{-x^2} \ dx = \sqrt{\pi}
$$
