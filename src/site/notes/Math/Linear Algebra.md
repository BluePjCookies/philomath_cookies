---
{"dg-publish":true,"permalink":"/math/linear-algebra/"}
---

# Linear Algebra
Recall how a function in algebra **transforms** x to y?
$$
f(x) = y
$$
In linear algebra, instead of x and y's which are scalar values, linear algebra **transforms**  into another.

$$
f  (\vec{x}) = \vec{y}
$$
However, to make the distinction clearer, mathematicians use A instead of f.
$$
A \vec{x} = \vec{y}
$$
---

## Vectors

Vectors are usually represented as column of numbers that encode a direction and magnitude.

$$
\vec{v} = 
\begin{pmatrix}
x_1\\
x_2\\
\vdots \\
x_n
\end{pmatrix}
$$

The magnitude of a vector can be determined by summing the square of each term in the column and square rooting the result.

$$
|\vec{v}| = \sqrt{x_1^2 + x_2^2 + \dots + x_n^2} = \sqrt{\sum_{n=1}{x_n^2}}
$$

**Dot Product**

The Dot product of two vectors are
$$
A \cdot B = |A||B| \cos \theta
$$
Let AB, be a vector from A to B. Based on the cos rule. [[Math/Trigonometry#Cos rule\|Cos Rule]]
$$
\vec{AB} = \vec{OB} - \vec{OA}
$$
$$
|AB|^2 = |OA|^2 + |OB|^2 - 2|OA||OB| \cos \theta
$$

Let $OA = A$ and $OB = B$.
$$
\begin{aligned}
|A||B| \cos \theta &= \frac{1}{2}\left( |A|^2 + |B|^2 - |B-A|^2\right) \\
&= \frac{1}{2} \left( \sum_{n=1} (a_n^2 + b_n^2) - \sum_{n=1} (b_n-a_n)^2\right) \\
&=
\frac{1}{2} \left( \sum_{n=1} (a_n^2 + b_n^2) - \sum_{n=1} (b_n^2-2a_nb_n + a_n^2)\right) \\
&= 
\sum_{n=1} a_nb_n
\end{aligned}
$$
Thus
$$
A \cdot B = \sum_{n=1} a_nb_n
$$
Lets take a closer look at the formula

$$ 
A \cdot B = |A||B| \cos \theta
$$
You can see that $|B| \cos \theta$ is a projection of B on A. Whereas $|A|\cos \theta$ is the projection of A on B.

---

**Cross Product**
The cross product of two vectors creates another vector that is *perpendicular* to both vectors.
$$
A \times B = |A||B| \sin \theta \ \hat{\mathbf{n}}
$$
Where $\hat{\mathbf{n}}$ is a unit vector perpendicular to A and B. The direction of $\hat{\mathbf{n}}$ can be determined using the right hand grip rule.

![Pasted image 20250423155913.png|200](/img/user/Images/Pasted%20image%2020250423155913.png)


Your fingers curl from vector a to b, while your thumb represents the direction of  $a \times b$

Thus
$$
A \times B = - B \times A
$$


The **determinant** trick to finding cross product.
$$
\begin{pmatrix} a_1\\ a_2\\ a_3 \end{pmatrix} \times \begin{pmatrix} b_1\\ b_2\\ b_3 \end{pmatrix} = \begin{pmatrix} a_2b_3-b_2a_3\\ - (a_1b_3-b_1a_3)\\ a_1b_2 - b_1a_2 \end{pmatrix}
$$
1. Cover up the first row
2. Multiply both sides diagonally and subtract it. (First element)
3. Cover up second row
4. Multiply both sides diagonally  and subtract it. Multiply by -1. (Second element)
5. Cover up third row
6. Repeat step 2  (third element)

---

**Area**

![Pasted image 20250423155837.png|300](/img/user/Images/Pasted%20image%2020250423155837.png)

The area of the parallelogram can be deduced. Let $u$ be the base and $h$ be the height. The Area would be $|u|h$.  $h$ can be expressed as.

$$
h = |v|\sin \theta
$$
Thus
$$
|u|h = |u||v| \sin \theta = |u \times v|
$$
Thus the area of the parallelogram can be determined by the magnitude of the cross product of $u$ and $v$.

Sample qn: Prove that the volume of a cuboid is.
$$
\text{Volume of Cuboid} = |a \cdot (b\times c)|
$$

## Planes

A plane is defined as
$$
r \cdot \hat{n} = D
$$
where $\hat{n}$ is the normal vector of the plane

If
$$
n_1 \cdot (n_2 \times n_3) \neq 0
$$
then the plane must intersect at a unique point
![Pasted image 20250423155647.png|300](/img/user/Images/Pasted%20image%2020250423155647.png)
However if $n_1 \cdot (n_2 \times n_3) = 0$, then you have to sub x as 0 to determine D, which determines whether it has infinite solutions or form a triangle (no solutions) 
## Matrices

We need special tools to work with vectors, and this is where matrices comes in. A matrix encodes a transformation on a vector, similar to how a function (f) encodes a transformation of x to y.

eg. 
$$
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
\hat{x} = \hat{y}
$$ 
where A is a matrix and $A = \begin{pmatrix}1 & 2 \\ 3 & 4 \end{pmatrix}$ 
$$
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
\begin{pmatrix}
x_1 \\ x_2\end{pmatrix}=
\begin{pmatrix}y_1 \\ y_2 \end{pmatrix}
$$
Note that the dim of a vector has to be the same as the number of columns of matrix (A).

---

### Matrix Multiplication (How does it transform between $\hat{x}$ to $\hat{y}$?)

**Matrix multiplication**
1. Take the nth row of numbers in A
2. Pivot it clockwise by 90 degrees into the mth column in $\hat{x}$
3. Multiply it respectively with the variable associated with it
4. Add up all the numbers in the column
5. The value would be on the nth row and mth column in $\hat{y}$ 

Thus
$$
\begin{pmatrix}
1 & 2\\
3 & 4
\end{pmatrix}
\begin{pmatrix}
x_1\\
x_2
\end{pmatrix}
=
\begin{pmatrix}
x_1 + 2x_2\\
3x_1 + 4x_2
\end{pmatrix}
$$
Bravo!! We have transformed $\hat{x}$ into a completely new vector $\hat{y}$ !!

---

### System of Linear Equations

A matrix also encodes a system of linear equations. Suppose there are 2 equations as shown, and we want to solve for a and b. 
$$
\begin{cases}
a + b = 20\\
2a +b = 23
\end{cases}
$$

A matrix representation of the above is as given

$$
\begin{pmatrix}
1 & 1\\
2 & 1
\end{pmatrix}
\begin{pmatrix}
a\\
b
\end{pmatrix}
 =
\begin{pmatrix}
a + b \\
2a + b
\end{pmatrix}
=
\begin{pmatrix}
20\\
23
\end{pmatrix}
$$

look, aren't they equivalent??

Solving for the coefficients are as easy as
$$
\begin{pmatrix}
a\\
b
\end{pmatrix}
 = 
\begin{pmatrix}
1 & 1\\
2 & 1
\end{pmatrix}^{-1} \begin{pmatrix}20 \\ 23 \end{pmatrix}
$$

Where the inverse of the matrix is essentially the reverse of its transformation, similar to how $f:x \mapsto y$ , thus $f^{-1} :y \mapsto x$ . Note, the inverse does not exist if the transformation is not one to one. But for square matrices, there is always an inverse 99% of the time.

---

Matrices belong in an non-abelian group


[[Math/Complex Numbers\|Complex Numbers]]

---

