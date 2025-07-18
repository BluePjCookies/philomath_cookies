---
{"aliases":["Matrices","Vectors"],"dg-publish":true,"permalink":"/math/linear-algebra/","dgPassFrontmatter":true,"noteIcon":""}
---

# Linear Algebra (Elementary)
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

### Dot Product

The Dot product of two vectors is
$$
A \cdot B = |A||B| \cos \theta
$$

And
$$
A \cdot B = \sum_{n=1} a_nb_n
$$

Look at derivation of the formula [[Math/Derivations/Proof for Dot Product\|here]]

---

### Cross Product
The cross product of two vectors creates another vector that is *perpendicular* to both vectors.
$$
A \times B = |A||B| \sin \theta \ \hat{\mathbf{n}}
$$
Where $\hat{\mathbf{n}}$ is a unit vector perpendicular to A and B. The direction of $\hat{\mathbf{n}}$ can be determined using the right hand grip rule.

![Pasted image 20250423155913.png|centre | 200](/img/user/Images/Pasted%20image%2020250423155913.png)


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

### Area bounded by Vectors

![Pasted image 20250423155837.png|centre | 300](/img/user/Images/Pasted%20image%2020250423155837.png)

The area of the parallelogram can be deduced. Let $u$ be the base and $h$ be the height. The Area would be $|u|h$.  $h$ can be expressed as.

$$
h = |v|\sin \theta
$$
Thus
$$
|u|h = |u||v| \sin \theta = |u \times v|
$$
Thus the area of the parallelogram can be determined by the magnitude of the cross product of $u$ and $v$.

Sample qn: Prove that the volume of a cuboid is. (This result is widely used in determinants and cross products)
$$
\text{Volume of Cuboid} = |a \cdot (b\times c)|
$$

## Points, Lines, Planes
### Point
A point is self-evidently a point in 3d space.

### Lines

Starting from what we know best
$$
y = mx + b
$$
A line in a vector space can be described as
$$
\hat{r} = \hat{a} + t \hat{b}
$$
#### Distance between Point and Line

The distance between $\hat{c}$ and $\hat{r} = \hat{a} + t \hat{b}$ is
$$
d = \frac{1}{||\hat{b}||}||(\hat{c} - \hat{a}) \times \hat{b}||
$$

### Planes

Starting from what we know. The equation of a plane in Cartesian form is
$$
ax + by + cz = D
$$
Using the properties of dot product, it can be rewritten as
$$
\begin{pmatrix}
x \\
y \\ 
z
\end{pmatrix}
\cdot
\begin{pmatrix}
a \\
b \\ 
c
\end{pmatrix}
= D$$
or
$$
r \cdot \hat{n} = D
$$
where $\hat{n}$ is the normal vector of the plane. And $r$ is a vector that lies on the plane
#### Line of Intersection between two planes

Given two planes 

$$
\begin{split}
x + y + z = 1 \\
2x + 3y +z = 5
\end{split}
$$
The line of intersection can be found by keying this into GDC (menu - 3 - 2)
![Pasted image 20250712194534.png|centre| 400](/img/user/Images/Pasted%20image%2020250712194534.png)

Thus
$$
\begin{split}
x = -2z -2 \qquad y &= z + 3 \qquad z = z\\ \\\
\frac{x + 2}{-2} &= \frac{y-3}{1} = z \\ \\
\begin{pmatrix} x \\ y \\ z \end{pmatrix} &= \begin{pmatrix} -2 \\ 3 \\  0\end{pmatrix} + \lambda \begin{pmatrix}-2 \\ 1 \\ 1 \end{pmatrix}
\end{split}
$$
#### Intersection of Planes

Given three planes ($\prod_1, \prod_2, \prod_3$), the plane must intersect at a unique point when

$$
n_1 \cdot (n_2 \times n_3) \neq 0
$$

However, the planes has $0$ or $\infty$ solutions when
$$
n_1 \cdot (n_2 \times n_3) = 0
$$

##### Distinguishing between no solutions & Infinite solutions 
>! If $n_1 \cdot (n_2 \times n_3) = 0$: 
1. Find $l$ :  the line of intersection between $n_2$ and $n_3$ 
$$
l = \begin{pmatrix}a \\ b \\ c \end{pmatrix} + \lambda \left(n_2 \times n_3 \right)
$$
2. Check if the below condition is true. If yes, then $(a,b,0)$ lies on $\prod_3$, suggesting that there are **infinite solutions**. If not, there are **no solutions**
$$
\begin{pmatrix} a \\ b \\ c \end{pmatrix} \cdot n_1 = D_3
$$


#### Distance between two parallel planes
where $D_1$ and $D_2$ are $r \cdot n = D_1$ and $r \cdot n = D_2$.
$$
d = \frac{D_2-D_1}{||n||}
$$

# Linearity

Formal definition of Linearity #Linearity
1. Additivity: $L(\vec{v} + \vec{w}) = L(\vec{v}) + L(\vec{w})$
2. Scaling: $L(c\vec{v}) = c \ L(\vec{v})$

Where $L$ is a linear transformation on a corresponding vector.
 
# Matrices
Recall how a function in algebra **transforms** x to y?
$$
f(x) = y
$$
In linear algebra, instead of x and y's which are scalar values, linear algebra **transforms** vectors into another vector.

$$
f  (\vec{x}) = \vec{y}
$$
However, to make the distinction clearer, mathematicians use A instead of f.
$$
A \vec{x} = \vec{b}
$$
---
We need special tools to work with vectors, and this is where matrices comes in. A matrix encodes a **Linear transformation** on a vector, similar to how a function (f) encodes a transformation of x to y.

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
$$
\begin{pmatrix}
a & b\\
c & d
\end{pmatrix}
\begin{pmatrix}
x\\
y
\end{pmatrix}
=
\begin{pmatrix}
ax+ by\\
cx + dy
\end{pmatrix}
$$

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
## Transpose

Transpose means to flip a vector or a matrix around a diagonal #Transpose 

$$
\begin{pmatrix}
x_0 \\
x_1 \\
x_2 \\
\end{pmatrix}^T = \begin{pmatrix} x_0 & x_1 & x_2 \end{pmatrix}
$$
Thus
$$
v^Tv = v \cdot v
$$
In the case of matrices
$$
\begin{pmatrix}
a_{00} & a_{01} & a_{02} \\
a_{10} & a_{11} & a_{12} 
\end{pmatrix}^T = 

\begin{pmatrix}
a_{00} & a_{10} \\
a_{01} & a_{11} \\
a_{02} & a_{12}
\end{pmatrix}
$$

Another property is that $A^T A$ always result in a square matrix. As one matrix transforms a vector $m \times1$ to $n \times 1$, and the other transforms it from $n \times 1$ to $m \times 1$. Together, the two transformation transforms a vector from $m\times 1$ to $m\times 1$. Which is a property of a square matrix.

---

## Determinant

Determinant measures the transformation of space and volume.

A matrix that maps basis vector $e_1. e_2, e_3$ to vectors $\mathbf{a},\mathbf{b},\mathbf{c}$ can be expressed as.
$$
A = [\mathbf{a} \quad \mathbf{b} \quad \mathbf{c}]
$$
The volume by the three basis vectors is given as $\epsilon^3$ or $|e|^3$

The determinant, measures ratio between the initial volume of three basis vectors, and its final volume after being scaled by $A$. 

$$
\det(A) = (\mathbf{a} \times \mathbf{b}) \cdot \mathbf{c}
$$
where $(a \times b) \cdot c$ is the volume of the cuboid.
$$
\det(A) = c_1(a_2b_3-b_2a_3) - c_2(a_1b_3-b_1a_3) + c_3 (a_1b_2 - b_1a_2)
$$

Fun fact 

$$
\vec{a} \times \vec{b} = \det\begin{pmatrix} i & a_1 &  b_1 \\ j & a_2 & b_2  \\ k & a_3 & c_3\end{pmatrix}
$$

The determinant tells us about the invertibility of the Matrix

---
## Eigenvector and Eigenvalue


An eigenvector of a matrix is a nonzero vector that, when the matrix is applied to it, is scaled by a factor $\lambda$ (the eigenvalue) but does not change direction.

$$
\begin{split}
Av &= \lambda v \\
Av - \lambda v &= 0\\
(A - \lambda I) \ v &= 0
\end{split}
$$
A linear system $Mx=0$ has non zero solution of $x$ if $\det(M) =0$. (Suggesting that M is singular).

Thus to find non zero solution of $v$.
$$
\det(A - \lambda I) = 0
$$
Solving for $\lambda$ would allow us to solve for eigenvector $v$.

---
# Linear Algebra (Modern)
## Infinite Vectors and Functional Spaces

> "The only thing limiting us in Math is our imagination" ~ Joshua

Functions are vectors. What? Yes it's true. All functions are an infinite vector and these infinite vectors live within something called a Functional Space. 
### Introduction to Infinite-dimensional vectors functions

Take a function $f(x)$. Suppose we get all values of $f(x)$ from $0 \leq x \leq n$ . And formulate them in a vector.
$$
f(x) = \begin{pmatrix}
f(0) \\
f(0.00\dots 1)\\
\vdots \\
f(n)
\end{pmatrix}
$$
### Orthogonal Basis
Suppose $f(x) = \sin x$. Since  $\sin$ is an oscillatory function, the domain of $x$ that we are interested in is thus $x \in \{\mathbb{R}| 0 \leq x \leq 2\pi \}$ 

Recall that in Euclidean space, a linear combination of two orthogonal (perpendicular) vectors, $\hat{i}$ and $\hat{j}$  can describe any point on the plane? Similarly, to describe any point/functions within this Functional space, we want to find orthogonal vectors or functions.

Thus we need to find two functions where its dot product is 0.
$$
\hat{f}(x) \cdot \hat{g}(x) = 0
$$
When dealing with finite vectors, the dot product is defined as [[Math/Linear Algebra#Dot Product\|such]], where each element in the vector is multiplied and summed together.

$$
\hat{A} \cdot \hat{B} = \sum_{n=1} a_nb_n
$$
Similarly, in the context of infinite vectors, it is defined as 
$$
\hat{f}(x) \cdot \hat{g}(x) = \int f(x)\ g(x) \ dx
$$
Fourier discovered that the two functions $f(x)$ and $g(x)$ are $\sin x$ and $\cos x$ respectively. As
$$
\int_0^{2\pi} \sin x \cos x \ dx  = 0
$$
Thus, $\sin$ and $\cos$ act as orthogonal basis vectors in Functional space. Proving that every single function can be expressed as a linear combination of $\sin$ and $\cos$ waves.

## References
1. https://www.youtube.com/watch?v=dT30kLnQNUE