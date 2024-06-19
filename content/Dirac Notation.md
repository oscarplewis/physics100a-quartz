---
tags:
  - Physics100A
  - 100ANotes
---
---
#### Bras and Kets
In bra-ket notation, vectors such as $\vec{a}$ and $\vec{v}$ are now denoted $\ket{a}$ and $\ket{v}$. These are called ***kets***.
Similarly we define objects denoted $\bra{a}$ and $\bra{v}$. These are called ***bras***. We'll expand on these more later.

#### Scalar Product in Bra-Ket Notation
The scalar/dot product is now denoted in bra-ket notation as $\vec{a}\cdot \vec{b}\equiv \braket{ a | b }$. This means that $\bra{a}$ is actually a map operating on $\ket{b} \in V$ and taking it to a scalar element of the [[Linear Vector Spaces#^7db33e|field]] $V$ is operating over.

For instance, if we define $\ket{a}=\begin{pmatrix}a_{1} \\ a_{2}\\a_{3} \end{pmatrix}$ and $\ket{b}=\begin{pmatrix}b_{1}\\b_{2}\\b_{3}\end{pmatrix}$, then $\bra{a}=\begin{pmatrix}a_{1}^{*}&a_{2}^{*}&a_{3}^{*}\end{pmatrix}$ and $\bra{b}=\begin{pmatrix}b_{1}^{*}&b_{2}^{*}&b_{3}^{*}\end{pmatrix}$. So then the [[Inner Products#^a0d654|scalar product]] on $\ket{a}$ and $\ket{b}$ is 
$$
\braket{ a | b } =a_{1}^{*}b_{1}+a_{2}^{*}b_{2}+a_{3}^{*}b_{3}
$$
So $\bra{a}$ is a linear map acting on $\ket{b}$, taking it to $\mathbb{C}$. 
$$
\bra{a} :V\to \mathbb{C}
$$
We can prove this map is linear like so:
$$
\bra{a} (\alpha \ket{c}+\beta \ket{d})  =\alpha \braket{ a | c } +\beta \braket{ a | d } 
$$
This follows from Axiom 2 for the [[Inner Products#^572aff|inner product]]. 

#### Dual Space
Note that $\bra{a}\neq \ket{a}$. In fact, $\bra{a}$ is part of a completely different vector space called the dual space.
This means you cannot add two vectors $\bra{a}$ and $\ket{b}$ because they are from different vector spaces; the result is undefined.

> [!example] Dual Space
> The ***dual space*** $V^{*}$ of a [[Linear Vector Spaces#^1175c0|vector space]] $V$ is the set of all linear mappings $\bra{a}:V \to \mathbb{C}$, and is itself a vector space. 
> (Note that an inner product must be defined on the vector space $V$ in order for the dual space to exist. Furthermore, the dual space is particular to the inner product - a different definition of the dual space changes the  dual space.)

^a68e20

In the dual space, we define:
1. Addition: $\bra{a}+\bra{b}: \ket{c} \to (\bra{a}+\bra{b})\ket{c}=\braket{ a | c }+\braket{ b | c }$. 
2. Scalar multiplication: $\alpha \bra{a}: \ket{c}  \to (\alpha \bra{a})\ket{c}=\alpha \braket{ a | c }$.
		(Note that a scalar acting on elements of $V^{*}$ stays outside the bra, and therefore does not pick up a conjugation.)
3. Zero element: $\bra{0}:\ket{c} \to \braket{ 0 | c }=0 \in \mathbb{C}$. 

Note that operations on elements of $V^{*}$ are defined by their actions on elements of $V$. This is because all the elements of $V^{*}$ are linear maps rather than objects themselves. 


> [!tip] Thinking About Bras
> It's very crucial that we think about bras in terms of their actions upon kets. They are fundamentally different objects - they are linear maps, not vectors - and should be conceptually thought of as such.




It can be shown that the axioms of a linear vector space are satisfied for an arbitrary dual space.

#### Adjoint of a Vector
Let $V$ be a linear vector space. If an inner product is defined on $V$, then we can associate with any vector $\ket{c} \in V$ a unique element $\bra{c} \in V^{*}$ of the dual space as follows.

In order to define $\bra{c} \in V^{*}$, we need only specify how $\bra{c}$ acts on any $\ket{a} \in V$. Using the inner product we define this action as
$$
\begin{align}
\bra{c}  :& V\to \mathbb{C} \\
 & \ket{a} \to \braket{ c | a } 
\end{align}
$$
(That is, we define the adjoint of $\ket{c}$ by the action of the inner product.)
This constitutes a map from elements of $V$ to elements of $V^{*}$. We denote this map by the dagger $^{\dagger}$. 
$$
\begin{align}
V  & \xrightarrow{{\dagger}} V^{*} \\
\ket{a}  & \xrightarrow{\dagger} \bra{a}=\ket{a} ^{\dagger}  \\
\begin{pmatrix}
a_{1} \\
a_{2} \\
a_{3}
\end{pmatrix}  & \xrightarrow{\dagger} \begin{pmatrix}
a_{1}^{*} & a_{2}^{*} & a_{3}^{*}
\end{pmatrix}
\end{align}
$$

> [!example] Adjoint of a Vector
> The ***adjoint*** of a vector $\ket{a} \in V$ is notated $\bra{a} \in V^{*}$, where $V^{*}$ is the [[#^a68e20|dual space]] of $V$. It is defined by $$
\begin{align}
\bra{a}  & = \ket{a} ^{\dagger} \\
  \begin{pmatrix}
a_{1}^{*} & a_{2}^{*} & \dots & a_{n}^{*}
\end{pmatrix} & = \begin{pmatrix}
a_{1} \\
a_{2} \\
\vdots \\
a_{n}
\end{pmatrix}^{\dagger}.
\end{align} $$

^d66d90

> [!example] General Property of Dagger Mapping
> For all $\ket{c},\ket{d} \in V$ and $\gamma,\delta \in \mathbb{C}$:
> $$
\begin{align}
(\gamma \ket{c} +\delta \ket{d} )^{\dagger} & =\gamma ^{*}\ket{c} ^{\dagger}+\delta ^{*}\ket{d} ^{\dagger} \\
 & = \gamma ^{*}\bra{c} +\delta ^{*}\bra{d}
\end{align} $$

^6e3639

>[!note] Proof of General Property of Dagger Mapping
>Because the postulate involves maps in $V^{*}$, we verify the validity by the action on an arbitrary element $\ket{a}\in V$. 
>Recalling $(\gamma \ket{c}+\delta \ket{d})^{\dagger}=\ket{\gamma c+\delta d}^{\dagger}$, this yields $$
\braket{ \gamma c+\delta d | a } = \gamma ^{*}\braket{ c | a } +\delta ^{*}\braket{ d | a } \text{ (by antilinearity of inner product)} $$
>This is true for all $\ket{a}\in V$, we have $$
\bra{\gamma c+\delta d} =(\gamma \ket{c} +\delta \ket{d} )^{\dagger} =\gamma ^{*}\bra{c} +\delta ^{*}\bra{d}  $$
QED.

Note that the scalars act on elements of $V$, and so they pick up a conjugation under the dagger mapping.

Adjoint operations/dagger mapping can also be taken on linear operators, as explained [[Linear Operators#Adjoints of Linear Operators|here]].

### Einstein Index Notation

In the vast majority of notes for this class, [[CCS Physics Series/Tensor Notation|Einstein index notation]] is avoided and standard summation notation is preferred. This will be the rule except where indicated.