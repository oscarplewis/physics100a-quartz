---
tags:
  - Physics100A
  - 100ANotes
---
---


A linear vector space $V$ is a set of objects (vectors) $\vec{a},\vec{b},\vec{c}$ on which two operations are defined:
1. Addition: $\vec{a}+\vec{b}$
2. Scalar multiplication: $\lambda \vec{a}$, for $\lambda \in \mathbb{R},\mathbb{C}$. 

>[!example] Field
>A ***field*** $F$ is a set of objects defined with two binary operations on $F$ called *addition* and *multiplication*, notated ${a}+{b}$ and ${a}\cdot {b}$ respectively. In order to be a field, these operations behave according to the following five axioms:
>- Associativity of addition and multiplication
>- Commutativity of addition and multiplication
>- Additive and multiplicative identity
>- Additive and multiplicative inverses
>- Distributivity of multiplication over addition
>
> Examples of fields include the real numbers, $\mathbb{R}$, and the complex numbers, $\mathbb{C}$. 

^7db33e

##### Axioms of Linear Vector Spaces
Let $\vec{a}$, $\vec{b}$, and $\vec{c}$ be elements of a linear vector space $V$, and let $\lambda$ be an element of the field $\mathbb{F}$ (where $\mathbb{F}$ is either $\mathbb{R}$ or $\mathbb{C}$). Then $V$ behaves according to the following axioms. ^832225

>[!example] Formal Definition of a Linear Vector Space
>If $V$ is a set of vectors, then $V$ is a linear vector space if and only if (for $\vec{a},\vec{b},\vec{c} \in V$ and $\lambda \in \mathbb{C}$): 
> 1. Closure under addition and scalar multiplication: $\vec{a}+\vec{b}\in V, \lambda \vec{a}\in V$.
>2. Addition is commutative: $\vec{a} + \vec{b}=\vec{b}+\vec{a}$.
>3. Addition is associative: $\vec{a}+(\vec{b}+\vec{c})=(\vec{a}+\vec{b})+\vec{c}$.
>4. Scalar multiplication is distributive in vectors: $\lambda(\vec{a}+\vec{b})=\lambda \vec{a}+\lambda \vec{b}$
>5. Scalar multiplication is distributive in scalars: $(\lambda+\gamma)\vec{a}=\lambda \vec{a}+\gamma \vec{a}$.
>6. Scalar multiplication is associative: $\lambda(\gamma \vec{a})=(\lambda\gamma)\vec{a}$.
>7. There is a multiplicative identity: $1 \in \mathbb{F} \text{ s.t. } 1\vec{a}=\vec{a}$.
>8. There is an additive identity: $\vec{0} \in V$ s.t. $\vec{a}+\vec{0} = \vec{0}+\vec{a}=\vec{a}$.
>9. There is an additive inverse: $\exists -\vec{a} \in V \text{ }\forall \text{ } \vec{a} \in V$ s.t. $\vec{a}+(-\vec{a})=\vec{0}$.

^1175c0

Let's consider a vector space $U$, all of whose vectors are also in the vector space $V$. We can then say that $U$ is a subspace of $V$. 


> [!example] Formal Definition of a Subspace
> Given a vector space $V$, a subset of its elements that form a vector space $U$ among themselves is called a ***subspace***. 
> 

A subspace $U$ of $V$ can also include all elements of $V$. In this case, $U=V$, so any vector space can be a subspace of itself.
Subspaces are denoted
$$
U\subseteq V.
$$
If we know that $V$ includes at least one element that isn't in $U$, then $U$ is called a proper subspace of $V$, and we write
$$
U\subset V.
$$
Given two subspaces $U,W$, their sum is defined
$$
U \oplus W=V
$$
where $V$ is a vector space including all elements of $U$, all elements of $W$, and all possible linear combinations of the above.

##### Examples of Linear Vector Spaces
1. **3-tuples (Cartesian vectors)**

![[Screenshot 2024-04-01 at 10.39.39.png]]
$$
\vec{a}=\begin{pmatrix}
a_{1} \\
a_{2} \\
a_{3}
\end{pmatrix}
$$
It can be shown that all axioms hold for Cartesian 3-space.
2. **Square matrices**
For instance, the set of all 2x2 square matrices is a linear vector space.
$$
\vec{a}=\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix}
$$
It can be shown that all axioms hold for a space containing all 2x2 matrices.
3. **Function spaces**
Let $f(x) \in \mathbb{R}$ and $x \in [0,1]$, such that the all functions in the function space $F$ are continuous on the interval and zero at the endpoints: $f(0)=f(1)=0$. Then $F$ is a linear vector space, and it can be shown that all axioms hold.
You can similarly construct other function spaces, such as the set of all square integrable functions $f(x)$ defined on the interval $x \in [-1,1]$. 
>[!example] Square Integrable Functions
>A function is square integrable if and only if
>$$
\int_{-1}^{1} |f(x)|^{2}\, \hspace{0.5mm} dx =\int_{-1}^{1} f^{*}(x)f(x) \, \hspace{0.5mm} dx = \text{finite (i.e. exists)} $$

^8241e8

This forms a complex function space $L^{2}[-1,1]=V$. 
In order to check closure of $V$, we need the ***[[Inner Products#^5f92de|Schwarz inequality]]***.
