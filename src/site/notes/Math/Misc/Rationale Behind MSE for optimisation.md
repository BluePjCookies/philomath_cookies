---
{"dg-publish":true,"permalink":"/math/misc/rationale-behind-mse-for-optimisation/","dgPassFrontmatter":true,"noteIcon":""}
---


Look at [[Math/Distributions#Central Limit Theorem\|Central Limit Theorem]]
When collecting data, the data would inevitably be affected by noise. Looking deeper, noise is made up by the summation of random and independent processes (eg. thermal process, electro-magnetic interferences etc). Thus based on the Central Limit theorem, Noise should follow a Normal distribution.
$$
\epsilon \sim N(0, \sigma^2)
$$

$$
y_{\text{real}} = y_{\text{ideal}}+ \epsilon_{\text{noise}}
$$
Typically, the mean ($\mu$) of noise is assumed to be 0. Since each individual processes are random in nature, they have an equal likelihood of having a positive and negative magnitude. Thus, the noise should have no biases in the positive or negative direction.

![Pasted image 20250608131245.png|centre|200](/img/user/Images/Pasted%20image%2020250608131245.png)
The probability of observing an error of value $\epsilon$ is given as
$$
P(y_\text{ideal} - y_\text{real}) = P(\epsilon) = \frac{1}{\sigma \sqrt{2\pi}}e^{-\frac{1}{2}\left(\dfrac{\epsilon}{\sigma} \right)^2}
$$


![Pasted image 20250608132219.png|centre|600](/img/user/Images/Pasted%20image%2020250608132219.png)

The above shows the normal distribution $P(\epsilon)$ denoted in red , where $w^Tx$ is $y_{\text{ideal}}$. It basically states the greater the $\epsilon$, the lower the probability of its occurrence and vice versa. 
Suppose $y_\text{ideal}$ is a linear equation
$$
y_\text{ideal} = wx 
$$
### Optimising the weights
 
For independent events, the probability of multiple events occurring is just the product of all its probabilities.
![Pasted image 20250608134650.png|centre|500](/img/user/Images/Pasted%20image%2020250608134650.png)

Thus the probability that we observe the following data above is  
$$
P(\text{Data}) = P(\epsilon _1) \cdot P(\epsilon _2) \dots P(\epsilon_n)
$$
We can rewrite it as
$$
\begin{split}
P(\text{Data}) = \prod_{i=1}^{N} P(\epsilon_i) &= \prod_{i=1}^{N} P(y_\text{ideal} - y_{\text{real}})\\
&= \prod_{i=1}^{N} P(wx_i - y_i)
\end{split}
$$
Since the smaller the $\epsilon$, the higher the probability of its occurrence $P(\epsilon)$. If we maximise $P(\text{Data})$, that would minimise $\epsilon$.

Thus $w_{\text{best}}$ can be achieved when we maximise $P(\text{Data})$.
$$
w_{\text{best}} = \arg \max \prod_{i = 1}^{N} P(wx_i - y_i)
$$
$\arg \max$ is an operation that finds the argument (or input) that yields the maximum value of a function. Thus we aim to find the input weights ($w$) or coefficients of $y_{\text{ideal}}$  that maximises $P(\text{Data})$.

The argument that maximises $\prod_{i = 1}^{N} P(wx_i - y_i)$  is the same as the argument that maximises of $\ln \prod_{i = 1}^{N} P(wx_i - y_i)$ as, if $a < b$ then $\ln a < \ln b$ .

$$
\begin{split}
w_{\text{best}} &= \arg \max \ln \prod_{i = 1}^{N} P(wx_i - y_i)\\
&= \arg \max \sum_{i=1}^{N} \ln P(wx_i - y_i) \\
&= \arg \max \sum \ln \frac{1}{\sigma \sqrt{2\pi}}e^{-\frac{1}{2}\left(\dfrac{wx_i - y_i}{\sigma} \right)^2} \\
&= \arg \max \sum \ln e^{-\left(wx_i - y_i \right)^2} \\
&= \arg \max \sum -  (wx_i - y_i)^2
\end{split}
$$
Hopefully you understand that taking out the constants $\frac{1}{\sigma \sqrt{2 \pi}}$ and $\frac{1}{2 \sigma^2}$  will still provide an argument that maximises $P(\text{Data})$.

Thus
$$
\begin{split}
w_\text{best} &= \arg \max \sum -  (y_{\text{ideal}} - y_{\text{real}})^2 \\
&= \arg \min \sum (y_\text{ideal} - y_{\text{real}})^2
\end{split}
$$
This is the exactly the Mean squared error formula used in textbooks. And we have proved that finding the argument $w$, that minimises $\sum (wx_i - y_i)^2$ is the best at minimising error $\epsilon$.

From: https://www.youtube.com/watch?v=q7seckj1hwM&list=LL&index=63&t=428s