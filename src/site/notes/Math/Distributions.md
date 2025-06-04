---
{"dg-publish":true,"permalink":"/math/distributions/"}
---

It is highly recommended to read [[Math/Probability\|Probability]] beforehand.
## Binomial Distribution

This section handles the instance where a choice between two options has to be made. We can visualise it as a probability tree

![Pasted image 20250604230236.png|centre|400](/img/user/Images/Pasted%20image%2020250604230236.png)
> [!question] Problem
> Suppose there is an equal probability to get a red or blue ball. What is the probability that red has been picked at least 2 times.

$$
P(R \geq 2) = \frac{1}{2^4} \cdot \left[\binom{4}{4} +\binom{4}{3} +\binom{4}{2} \right]
$$
There are 4C4 ways to pick 4 reds, 4C3 to pick 3 and 4C2 ways to pick 2. The total number of possible outcomes is also $2^4$. (recall permutations)

>[!question] Problem
> If the probability of getting a red ball is $0.7$, what is the probability that red has been picked exactly twice?

$$
P(R = 2) = \binom{4}{2} \cdot 0.7^2 \cdot 0.3^2
$$
The probability of traversing down a single path on the tree with 2 red balls is $0.7^2 \cdot 0.3^2$ . Since there are 4C2 paths with 2 red balls. We sum the total probability by multiplying the two together. We can rewrite the above for any value of red balls $(r)$ and tries $(n)$ as.

$$
P(R = r) = \binom{n}{r} p^r (1-p)^{n-r}
$$
Thus
$$
R \sim \text{Bin}(n, p)
$$

If you were to plot $P(R=r)$ against $r$ for large values of $n$. You'll get a smooth bell shaped curve called the binomial distribution.

![Pasted image 20250604233355.png|centre| 400](/img/user/Images/Pasted%20image%2020250604233355.png)

Above shows a binomial distribution where $n = 1000$  and $p = 0.95$. 
>[! Question] Quiz
> A Galton board consist of a narrow opening at the top which allows holes to fall through a series of pins before dropping into a bin at the bottom. Can you explain what distribution the balls will follow and why?

![Pasted image 20250604233829.png|centre|300](/img/user/Images/Pasted%20image%2020250604233829.png)
Ans:
For a ball to fall into pocket J, it chooses to move left or right 8 times. The number of times it moved left is 5 times, and right is 3 times. Since there is an equal possibility of moving left or right, $p = 0.5$.  

Thus, there are 8C5 paths that reaches pocket J. And the probability of each individual path is $0.5^8$.
$$
P(X = J) = \binom{8}{5} (0.5)^8
$$
Extending this to all the other pockets. where $x$ is the number of times the ball has to turn left or right to reach the pocket.
$$
P(X = x) = \binom{n}{x} (0.5)^8
$$
We see that this $P(X=x)$ is a binomial distribution, where $x$ denotes the final position of the ball. Thus, the ball should follow a binomial distribution.
![Pasted image 20250604235835.png|centre|200](/img/user/Images/Pasted%20image%2020250604235835.png)
## Central Limit Theorem


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
