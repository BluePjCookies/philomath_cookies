---
{"dg-publish":true,"permalink":"/math/statistics/"}
---


> "Statistics is vectors " ~ Joshua

## $r$ Correlation Coefficient  

The $r$ formula (Pearson correlation coefficient) is given as such
$$
r = \frac{\sum (x - \bar{x})(y-\bar{y})}{\sqrt{\sum(x-\bar{x})^2 \cdot \sum (y-\bar{y})^2}}
$$
Look at this monstrosity. But in a sense this is a rather simple formula. 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/math/linear-algebra/#dot-product" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



### Dot Product

The Dot product of two vectors is
$
A \cdot B = |A||B| \cos \theta
$

And
$
A \cdot B = \sum_{n=1} a_nb_n
$

Look at derivation of the formula [[Math/Derivations/Proof for Dot Product\|here]]

---


</div></div>



Suppose we have two vectors 

$$
\tilde{X} = 
\begin{pmatrix}
x_0- \bar{x}\\
x_1- \bar{x}\\
\vdots \\
x_n- \bar{x}\\
\end{pmatrix}
\quad 
\tilde{Y} = 
\begin{pmatrix}
y_0- \bar{y}\\
y_1- \bar{y}\\
\vdots \\
y_n- \bar{y}\\
\end{pmatrix}
$$

Let's look at the formula again,

$$
r = \frac{\sum (x - \bar{x})(y-\bar{y})}{\sqrt{\sum(x-\bar{x})^2 \cdot \sum (y-\bar{y})^2}}
$$
Notice how we can rewrite is as
$$
r = \frac{\tilde{X} \cdot \tilde{Y}}{ ||\tilde{X}|| \cdot ||\tilde{Y}||} = \cos \theta
$$
The dot product determine the similarity of two vectors. If the vectors are pointing in the similar direction, then it will output $\pm1$. But if they are dissimilar (perpendicular) it will output $0$. This thus explains why $r$ tells us the correlation between two variables as it is simply $\cos \theta$.
## Variance

Variance is defined as 

$$
Var(X) = \sum_{i=1}^{N}\frac{(x_i-\bar{x})^2}{N}
$$
## Standard Deviation

$$
Var = \sigma^2
$$
## Why use Mean Squared Error in Regression?

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

