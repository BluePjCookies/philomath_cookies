---
{"dg-publish":true,"dg-show-backlinks":true,"permalink":"/math/trigonometry/","dgShowBacklinks":true,"dgPassFrontmatter":true,"noteIcon":""}
---


Trigonometry originates from the study of triangles, particularly, the right angled ones.

### Pythagoras Theorem

Pythagoras states that the expression is always be true for any three sides of a right angle triangle, where c is the hypothenuse. 
$$
a^2 + b^2 = c^2
$$

### Trigonometry
$$
\sin x = \frac{\text{opp}}{\text{hyp}}
$$
$$
\cos x = \frac{\text{adj}}{\text{hyp}}
$$
$$
\tan x = \frac{\text{opp}}{\text{adj}}
$$
### Trigonometric Identities
$$
\sin^2(x) + \cos^2(x) = 1
$$
$$
1 + \cot^2(x) = \csc^2(x)
$$
$$
\tan^2(x) + 1 = \sec^2(x)
$$

We obtained the second expression by dividing the first expression throughout by $\sin^2(x)$ and the third by dividing the first expression by $\cos^2(x)$ 


### Sine rule
$$
\frac{\sin a}{A} = \frac{\sin b}{B} = \frac{\sin c}{C}
$$

### Cos rule
$$
c^2 = a^2 + b^2 - 2ab \cos C
$$


### Double angle formula

$$
\sin (a \pm b) = \sin a\cos b \pm \sin b \cos a
$$
$$
\cos (a\pm b) = \cos a \cos b  \mp \sin a \sin b
$$
$$
\tan (a\pm b) = \frac{\tan a \pm \tan b}{1 \mp \tan a \tan{b}}
$$

### Harmonic Addition Theorem

Express $R \sin (\theta + a)$ as $A \cos \theta + B \sin \theta$ .

$$
\begin{split}
R \sin (\theta + a) &= R ( \sin \theta \cos a + \sin a \cos \theta)\\
&= R \cos a \sin \theta + R\sin a \cos \theta
\end{split}
$$

Thus
$$
A = R \sin a
$$
$$ 
B = R \cos a
$$
### Reverse Factor Formulae

$$
2 \sin A \cos B = \sin(A+ B) + \sin (A-B)
$$
$$
2 \cos A \sin B = \sin (A+ B) - \sin (A-B)
$$
$$
2 \cos A \cos B = \cos (A + B) + \cos (A-B)
$$
$$
-2 \sin A \sin B = \cos (A+ B) - \cos (A-B)
$$

### Additional Insights (Very useful)

Let us see the properties of these trigo identities.
This section aims to help us find a shortcut to solving questions like: Use Compound angle formula to prove that $\cos \frac{19 \pi}{12} = \frac{\sqrt{6} - \sqrt{2}}{4}$ etc...

let us define $n$ as
$$
n = k \times a + R
$$
where $R$ is the remainder. And $k,a, R, n \in \mathbb{Z}$.
Look at [[Math/Derivations/Proof for Symmetries in Trigo Identities\|Proof for Symmetries in Trigo Identities]]. We thus get.
$$
\begin{split}
\sin \left( \frac{n}{a} \pi \right) &= (-1)^k \sin \left(\frac{R}{a} \pi \right) \\ 
&= (-1)^k \sin \left(\frac{a-R}{a} \pi\right)
\end{split}
$$
$$
\begin{split}
\cos \left( \frac{n}{a}\right) &= (-1)^k \cos \left( \frac{R}{a} \pi \right)\\
&= (-1)^{k+1} \cos \left(\frac{a-R}{a} \pi\right)
\end{split}
$$
### Joshua's approximation method. Estimating $cos$ $sin$ $tan$ without using their respective functions on a calculator 

Suppose we want to find the value of 
$$
\cos \left( \frac{19}{5} \right)
$$
Using the approximation that $\pi \approx \frac{22}{7}$. And reducing it using the [[Math/Derivations/Proof for Symmetries in Trigo Identities\|Proof for Symmetries in Trigo Identities]] formulas
$$
\begin{split}
\cos \left( \frac{19}{5}\right) &= \cos\left( \frac{19}{5} \frac{7}{22} \pi \right)\\
&= \cos\left( \frac{133}{110} \pi \right)\\
&= (-1)^1 \cos\left(\frac{23}{110} \pi \right)
\end{split}
$$
Next, having reduced $\theta < \frac{\pi}{2}$. using the [[Math/Sequences and Series#Maclaurin Series expansion for $ sin$ and $ cos$\|Maclaurin Series expansion]] for $\cos$ up to the $x^4$ term. 
$$
\begin{split}
-\cos \left( \frac{23}{110} \pi \right) &\approx - \left( 1 - \frac{\left(\frac{23}{110} \pi \right)^2}{2} + \frac{\left(\frac{23}{110} \pi \right)^4}{4!}\right)\\
\end{split}
$$
We see that
$$ 
- \left( 1 - \frac{\left(\frac{23}{110} \pi \right)^2}{2} + \frac{\left(\frac{23}{110} \pi \right)^4}{4!}\right)\\ = -0.792012968067
$$
and using a calculator
$$
\cos \left(\frac{19}{5}\right) = -0.790967711914
$$
Comparing the two solution, my method is accurate up to 2dp with an error of $0.001$ :)
$$
\cos \left(\frac{19}{5}\right) - - \left( 1 - \frac{\left(\frac{23}{110} \pi \right)^2}{2} + \frac{\left(\frac{23}{110} \pi \right)^4}{4!}\right)= 0.001045256153
$$