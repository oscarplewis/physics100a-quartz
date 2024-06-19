---
tags:
  - Physics100A
  - 100ANotes
---
---
Note: defining an inner product on a [[Linear Vector Spaces|linear vector space]] gives us a notion of "length" and "angle" (orthogonality) of vectors.

>[!example] Inner Product
>Given a complex (or real) [[Linear Vector Spaces#^1175c0|linear vector space]] $V$, an inner product maps from a pair of vectors $\vec{a},\vec{b} \in V$ to a scalar element of $\mathbb{C}$: $\vec{a}\cdot \vec{b}\in\mathbb{C}$. 
>Inner products on linear vector spaces must satisfy the following axioms:
>1. Conjugate Symmetry
	>- If $\vec{a}\cdot \vec{b}=\lambda$, s.t. $\lambda \in\mathbb{C}$, then $\vec{b}\cdot \vec{a}=\lambda ^{*}$. 
	>- So, $(\vec{a}\cdot \vec{b})^{*}=\vec{b}\cdot \vec{a}$. 
>2. Linearity
>$$
\vec{c}\cdot(\alpha \vec{a}+\beta \vec{b})=\alpha(\vec{c}\cdot \vec{a})+\beta(\vec{c}\cdot \vec{b}) $$
>3. Positive Semidefiniteness $$\vec{a}\cdot \vec{a}\geq 0.$$ (Note that by Axiom 1, $\vec{a}\cdot \vec{a}\in\mathbb{R}$.)
^572aff


> [!example] Inner Product Space
> An ***inner product space*** is a [[Linear Vector Spaces#^1175c0|vector space]] with an [[#^572aff|inner product]] defined on it.

^3cf67b





From this we can show that the inner product when defined for the complex field has the property of ***anti-linearity***:
$$
\begin{align}
(\alpha \vec{a}+\beta \vec{b})\cdot \vec{c} & = \left[ \vec{c}\cdot(\alpha \vec{a}+\beta \vec{b}) \right] ^{*}, \\
 & =\left[ \alpha \vec{c}\cdot \vec{a}+\beta \vec{c}\cdot \vec{b} \right] ^{*,} \\
 & = \alpha ^{*}(\vec{a}\cdot \vec{c})+\beta ^{*}(\vec{b}\cdot \vec{c}).
\end{align}
$$

^d21dac


We can show that for n-tuples with complex entries (a linear vector space over the complex field), the inner product axioms hold.
$$
\vec{a}\cdot \vec{b}=\begin{pmatrix}
a_{1}^{*} & a_{2}^{*} & \dots & a_{n}^{*}
\end{pmatrix} \begin{pmatrix}
b_{1} \\
b_{2} \\
\vdots \\
b_{n}
\end{pmatrix}=a_{1}^{*}b_{1}+a_{2}^{*}b_{2}+\dots+a_{n}^{*}b_{n}
$$
$$
\begin{align}
\vec{a}\cdot \vec{b} & = \begin{pmatrix}
b_{1}^{*} & b_{2}^{*} & \dots & b_{n}^{*}
\end{pmatrix}\begin{pmatrix}
a_{1} \\
a_{2} \\ \\
\vdots
a_{n}
\end{pmatrix} \\
& = b_{1}^{*}a_{1}+b_{2}^{*}a_{2}+\dots+b_{n}^{*}a_{n} \\
& = (\vec{a}\cdot \vec{b})^{*}
\end{align}
$$
(Note that the complex conjugate need not exclusively be taken on the left vector, both work so long as the choice is consistent. It does make more sense for it to be on the left though because of the matrix multiplication aspect.)

The inner product does not have to be defined in any specific way: any bilinear form you can create is valid so long as the axioms are satisfied. This means that we often define an inner product for a given vector space and field simply for its convenience and interesting properties. For instance, the classic dot product is defined because of its convenience in Euclidian geometry.
#### Vector Scalar Product

> [!example] Dot Product (Inner Product of n-tuples)
> Given two vectors $\vec{a}=(a_{1},a_{2},\dots,a_{n})$ and $\vec{b}=(b_{1},b_{2},\dots,b_{n})$, where $a_{i},b_{j} \in \mathbb{C}$, their scalar product is defined as $$
\vec{a}\cdot \vec{b}=a_{1}^{*}b_{1}+a_{2}^{*}b_{2}+\dots+a_{n}^{*}b_{n}^{}.$$

^a0d654


Generalizing this to different bases, two vectors $\ket{x}=\sum_{i}^{}x_{i}\ket{e_{i}}$ and $\ket{y}=\sum_{j}^{}y_{j}\ket{e_{j}}$ have an inner product
$$
\braket{ x | y } =\sum_{i}^{} \sum_{j}^{} x_{i}^{*}y_{j}\braket{ e_{i} | e_{j} }. 
$$
#### Function Space Example of an Inner Product

Let's take a linear vector space of square integrable functions on the interval $x \in [a,b]$, $V=L^{2}[a,b]$. Let $\vec{f}=f(x), \vec{g}=g(x)$, such that $f$ and $g$ are the complex value functions of the real variable $x$ on the defined interval.
From the definition of a square integrable function, we can more broadly define an inner product on $V$ as
$$
\vec{f}\cdot \vec{g}=\int_{a}^{b} f^{*}(x)g(x) \, \hspace{0.5mm} dx .
$$

^0605db

It can be shown that this inner product behaves according to all the axioms of an inner product.

#### Norm of a Vector

>[!example] Norm
>The norm of a vector $\ket{a}$ is defined as $$\lVert a \rVert  \equiv \sqrt{ \braket{ a | a }  }\geq 0.$$

^db8742

(Note that for Cartesian vectors, this is the vector's length.)

The norm has two important properties.
1. Schwarz Inequality: $\forall \text{ } \ket{a},\ket{b}\in V$, $| \braket{ a | b } |\leq ||a||\cdot ||b||$. ^5f92de
2. Triangle Inequality: $\forall \text{ } \ket{a},\ket{b}\in V$, $||a+b||\leq||a||+||b||$. ^168e72


##### Proof of Schwarz Inequality
Given $(\vec{a}+\alpha \vec{b})$ for $\vec{a},\vec{b} \in \mathbb{C}^{n}$ and $\alpha \in \mathbb{C}$:
$$
\begin{align}
(\vec{a} +\alpha \vec{b})\cdot(\vec{a}+\alpha \vec{b}) & \geq 0 \tag{by Axiom 2}, \\
\vec{a}\cdot \vec{a}+\alpha \vec{a}\cdot \vec{b}+\alpha ^{*}\vec{b}\cdot \vec{a}+\alpha ^{*}\alpha\vec{b}\cdot \vec{b} & \geq 0. \tag{by anti-linearity}
\end{align}
$$
We now choose $\alpha=\frac{-\vec{b}\cdot \vec{a}}{\vec{b}\cdot \vec{b}}$, and use Axiom 1:
$$
\begin{align}
\vec{a}\cdot \vec{a}-\frac{(\vec{a}\cdot \vec{b})(\vec{b}\cdot \vec{a})}{(\vec{b}\cdot \vec{b})}& \geq 0 \\
(\vec{a}\cdot \vec{a})(\vec{b}\cdot \vec{b}) & \geq (\vec{a}\cdot \vec{b})(\vec{b}\cdot \vec{a}) \\
||\vec{a}||^{2}||\vec{b}||^{2} &  \geq |\vec{a}\cdot \vec{b}|^{2} \\
||\vec{a}||\cdot||\vec{b}||  & \geq |\vec{a}\cdot \vec{b}|
\end{align}
$$
$\mathbb{QED}.$

