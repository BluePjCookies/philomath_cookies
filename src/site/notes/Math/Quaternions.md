---
{"dg-publish":true,"permalink":"/math/quaternions/"}
---


Quaternions provide a clever way to encode a 3d rotation about a particular axis in 3d space. It is widely used in game mechanics and 3d computer aided designs.


A Quaternion is represented by 4 numbers (4 dimensions) which encodes a 3d rotation in 3d space.

$$
q = a + ib + jc + dk
$$
## Imaginary Numbers??? Or vectors?

Recall how an imaginary number encodes a rotation. Let's define $i$, $j$, $k$ axis. Where $i$ represents a $90^\circ$ rotation about the $i$ axis and so on. Rotation is defined using the right hand rule, with the thumb pointing in the direction of the vector.

![IMG_1157.jpeg| 300](/img/user/Images/IMG_1157.jpeg)

Let's define multiplication as such.

$$ij = k$$
This means applying a rotation $i$ on vector $j$. Using your right hand, position the thumb in the direction of $i$, and curl your fingers. $j$ will rotate according to the direction of the curl to become $k$.

Doing so, you can derive other sets of expression. Like
$$
\begin{split}
ij = k \quad ik = -j
\end{split}
$$
Suppose we multiply $i$ on the left side of $ij$ 
$$
iij = ik = -j
$$
Thus
$$
i^2 = -1
$$
We can also prove that 
$$
i^2 = j^2 = k^2 = ijk = -1
$$
![IMG_1158.jpeg](/img/user/Images/IMG_1158.jpeg)

These are all imaginary numbers! What?? Note that $i \neq j \neq k \neq \sqrt{-1}$ . Rather these are matrices that encode rotation.

$$
\begin{split}

i &= \begin{pmatrix}
0 & -1\\
1 & \ 0
\end{pmatrix}

\end{split} \quad j =\begin{pmatrix}
i & 0\\
0 & -i
\end{pmatrix}
\quad
k =\begin{pmatrix}
0 & i\\
i & 0
\end{pmatrix}
$$

If you were to square the matrix, using matrix multiplication, you would obtain $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} = -i = -1$.

### Why four dimensional space?

First of all, why would you introduce 4 dimensions, why can't a quaternion just be $q = a + ib + jc$?? See below.
[[Math/Derivations/Proof for 3d contradiction (Quaternions)\|Proof for 3d contradiction (Quaternions)]]

### Conjugate
The conjugate of a quaternion is as such
$$
q^* = a - ib - jc - kd 
$$
Thus
$$
q \cdot q^* = a^2 + b^2 + c^2 + d^2 = ||q||^2
$$
## Rotations
Let a $u$ be a pure imaginary quaternion or vector where $u \in \mathbb{H}$.
 ($u$ is a quaternion). 

$$\mathbf{u} = \mathbf{i}b + \mathbf{j}c+ \mathbf{k}d = \begin{pmatrix} b \\ c \\ d\end{pmatrix}$$
Where $b^2 + c^2 + d^2 = 1$.

A unit Quaternion existing on the surface of a hypersphere where $||q|| = 1$, can encode a rotation of $\theta$ about unit vector $u$. 
$$
q = \cos \theta+ \mathbf{u}\sin \theta
$$
Where $qq^* = ||q||^2= \cos^2 \theta - (\mathbf{u}^2) \sin^2 \theta$. Think of $\mathbf{u}$ now as a vector 

$$\mathbf{u}^2 = \mathbf{u} \cdot \mathbf{u} = -b^2 -c^2 -d^2 = -1
$$
Thus $||q||^2 = \cos^2 \theta + \sin^2 \theta = 1$.

We can represent a unit quaternion by 

$$
q = e^{\mathbf{u} \cdot  \theta}
$$
The inverse of $q$ is 
$$
q^{-1} = e^{- \mathbf{u} \cdot \theta} = \cos \theta - \mathbf{u} \sin \theta = q^*
$$

To rotate a vector $v$ about $u$ by $2 \theta$ degrees. 
$$
\mathbf{v'} = q \ \mathbf{v} \ q^{-1}
$$

