---
tags:
  - Physics100A
  - 100ANotes
---
---
### Formal Definition of Linear Operators





> [!example] Linear Operator
> Given a [[Linear Vector Spaces#^1175c0|linear vector space]] $V$, a ***linear operator*** $\hat{A}$ is a linear mapping which assigns to each vector $\ket{a} \in V$ another vector $\ket{b}\in V$. That is, linear operators map between elements in a vector space. $$
\begin{a[](Linear%20Vector%20Spaces.md#^1175c0){a} =\ket{b}. 
\end{align} $$

^9dd697

Linear operators have the property of linearity. That is,
$$
\hat{A}(\alpha_{1}\ket{a_{1}} +\alpha_{2}\ket{a_{2}} )=\alpha_{1}\hat{A}\ket{a_{1}} +\alpha_{2}\hat{A}\ket{a_{2}},
$$
for all $\ket{a_{1}},\ket{a_{2}} \in V$ and $\alpha_{1},\alpha_{2}\in \mathbb{C}, \mathbb{R}$. 
### Example: $n\times n$ matrices
The most familiar examples of linear operators are $n\times n$ matrices acting on $n$-dimensional vectors.
$$
\begin{align}
\hat{A}\ket{c}  & =\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix}\begin{pmatrix}
c_{1} \\
c_{2}
\end{pmatrix}, \\
 & = \begin{pmatrix}
a_{11}c_{1}+a_{12}c_{2} \\
a_{21}c_{1}+a_{22}c_{2}
\end{pmatrix} \in V.
\end{align}
$$
It can be shown that an $n\times n$ matrix satisfies the condition of linearity.

The identity operator $\hat{I}$ satisfied
$$
\hat{I}\ket{a} =\ket{a} \hspace{1 mm} \forall \hspace{1 mm} \ket{a} \in V.
$$
For $n\times n$ matrices
$$
\hat{I}=\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}.
$$

### Linear Operators Acting on Dual Spaces
Linear operators can also act on the [[Dirac Notation#^a68e20|dual space]] $V^{*}$. 
If the linear vector space $V$ has an [[Inner Products#^572aff|inner product]] defined on it, any linear operator $\hat{A}$ on $V$ also acts on the dual space $V^{*}$ as follows:
$$
\begin{align}
V^{*} &  \xrightarrow{\hat{A}}V^{*}, \\
\bra{c} & \to \bra{c}\hat{A}=\bra{d}.  
\end{align}
$$
More explicitly, the operator $\hat{A}$ assigns to each element $\bra{c} \in V^{*}$ another element $\bra{d} \in V^{*}$. Because these are maps, $\bra{d}$ is determined by the action on elements $\ket{a} \in V$. This means
$$
\begin{align}
\braket{ d | a }  & = (\bra{c} \hat{A})\ket{a},  \\
 & = \bra{c} (\hat{A}\ket{a} ), \\
 & = \braket{ c | b }. 
\end{align}
$$
Here, $\braket{ d}$ is the image of $\bra{c}$ under $\hat{A}$. This means that knowing how $\hat{A}$ acts on elements of $V$ allows us to determine how $\hat{A}$ acts on elements of $V^{*}$. 
We can notate this in the following manner:
$$
\braket{c| \hat{A}|a}=(\bra{c} \hat{A})\ket{a} =\bra{c} (\hat{A}\ket{a} ).  
$$
It's important to remember that the linear operator $\hat{A}$ acts on kets from the left, giving another ket, and on bras from the right, giving another bra. Furthermore, $\hat{A}$ still has linearity when acting on the dual space $V^{*}$. 

### Function Space Example

We define the function space $C_{\infty}$ as the set of all functions which are continuous and infinitely differentiable over the interval.
Then $\hat{A}=\frac{ d  }{ d x }$ is a linear operator. For $\ket{f}, \ket{g} \in V$, $\hat{A}\ket{f}=\ket{\frac{ d f }{ d x }}=\frac{ d f }{ d x } \in C_{\infty}.$ We can similarly prove the linearity of $\hat{A}$ rather simply.

We can construct an inner product for $C_{\infty}$, such as
$$
\braket{ f | g } =\int_{a}^{b} f^{*}(x)g(x) \, \hspace{0.5mm} dx,
$$
and define the action of $\hat{A}=\frac{d}{dx}$ on objects $\braket{ f}$ in the dual space using integration by parts. 
$$
\braket{ f  | \hat{A}   | g } =\int_{a}^{b} f^{*}(x)\frac{dg}{dx} \, \hspace{0.5mm} dx = f^{*}(x)g(x) \biggr |_{a}^{b}-\int_{a}^{b} \frac{df^{*}}{dx}g(x)  \, \hspace{0.5mm} dx. 
$$
In many cases these boundary terms will vanish because of the boundary conditions placed upon a problem. In those cases, we can then write
$$
\bra{f} \hat{A}=-\int_{a}^{b} \frac{df^{*}}{dx} \circ \, \hspace{0.5mm} dx ,
$$
or
$$
\braket{ f | \frac{d}{dx}  |g  }=-\braket{ \frac{df}{dx} | g } . 
$$

The primary motive for studying linear vector spaces abstractly is because they're one of the main tools for solving the linear differential and integral equations of physics (QM, E&M, mechanics, etc). Many powerful mathematical tools are derived from these methods.

### Example: $\ket{a}\bra{b}$ as a Linear Operator

This operator is important when changing bases, computing Green's functions, etc. We can verify linearity as follows, letting the operator $\hat{C}\equiv \ket{a}\bra{b}$, such that $\hat{C}:V \to V$. For all $\ket{x} \in V$:
$$
\ket{x} \to (\ket{a} \bra{b} )\ket{x} =\braket{ b | x } \ket{a}.
$$
And for all $\bra{x} \in V^{*}$:
$$
\bra{x} \to \bra{x} (\ket{a} \bra{b} )=\braket{ x | a } \bra{b}. 
$$
It can be shown that $\hat{C}$ is a linear operator in $V$:
$$
\begin{align}
(\ket{a} \bra{b} )(\alpha \ket{x} +\beta \ket{y} ) & = (\ket{a} \bra{b} )\ket{\alpha x+\beta y}, \\
&= \alpha \ket{a}\braket{ b | x } +\beta \ket{a} \braket{ b | y }, \\
 & = \alpha(\ket{a} \bra{b} )\ket{x}+\beta(\ket{a} \bra{b} )\ket{y}.  
\end{align}
$$
And in $V^{*}$:
$$
\begin{align}
(\alpha \bra{x} +\beta \bra{y} )(\ket{a} \bra{b} )  & = \alpha \braket{ x | a } \bra{b} +\beta \braket{ y | a } \bra{b},  \\
 & =  \alpha \bra{x} (\ket{a} \bra{b} )+\beta \bra{y}( \ket{a} \bra{b} ).
\end{align}
$$
Note that $\ket{a} \bra{b}$ (a linear operator) is a completely different object from $\braket{ b | a }$ (a scalar). This operator is called the [outer product](https://en.wikipedia.org/wiki/Outer_product).

### Operations with Linear Operators

Given two linear operators
$$
V \xrightarrow{ \hat{A} }V \text{ and } V \xrightarrow{ \hat{B} } V,
$$
as well as a scalar $\alpha \in\mathbb{C}$, we can define the following operations of two linear operators:
$$
\begin{align}
\text{Addition: } & \hat{C}=\hat{A}+\hat{B}   :\hat{C}\ket{a} =(\hat{A}+\hat{B})\ket{a} =\hat{A}\ket{a} +\hat{B}\ket{a}, \\
\text{Scalar multiplication: } & \hat{D}=\alpha \hat{A} : \hat{D}\ket{a} =(\alpha \hat{A})\ket{a} =\alpha (\hat{A}\ket{a} ), \\
\text{Product: } & \hat{F}=\hat{A}\hat{B}:\hat{F}\ket{a} =\hat{A}(\hat{B}\ket{a})=\hat{A}\hat{B}\ket{a}, \\
\text{Powers: } & \hat{G}=\hat{A}^{m}:\hat{G}\ket{a} =\hat{A}^{m}\ket{a} = \underbrace{ \hat{A}\hat{A}\hat{A}\dots \hat{A} }_{ m \text{ times} } \ket{a}. 
\end{align}
$$

### Commutator

Two linear operators $\hat{A}$ and $\hat{B}$ ***commute*** if
$$
\hat{A}\hat{B}\ket{a}=\hat{B}\hat{A}\ket{a}.  
$$
Generally, operators tend not to commute.
$$
\hat{A}\hat{B}\neq \hat{B}\hat{A}.
$$
We can then define:

> [!example] Commutator
> The ***commutator*** of two [[#^9dd697|linear operators]] $\hat{A}$ and $\hat{B}$ is defined as
> $$
[\hat{A},\hat{B}]\equiv \hat{A}\hat{B}-\hat{B}\hat{A}. $$ 
>If $[\hat{A},\hat{B}]=0$, then the two operators commute.
>(Note that the commutator is itself a linear operator.)

^410dd4

Also note that if $\hat{A}$ and $\hat{B}$ commute, then $[\hat{A},\hat{B}]=[\hat{B},\hat{A}]$. 


### Exponential of an Operator

The [[Basics of Series Expansions#Expanding Functions in Power Series|power series expansion]] of $e^{ z }$ for $z\in\mathbb{C}$ is
$$
e^{ z}=1+z+\frac{z^{2}}{2}+\frac{z^{3}}{6}+\dots=\sum_{n=1}^{\infty} \frac{z^{n}}{n!}.
$$
We can similarly define the exponential $e^{ \hat{A} }$ by a power series expansion:
$$
e^{ \hat{A} }=\hat{I}+\hat{A}+\frac{\hat{A}^{2}}{2}+\frac{\hat{A}^{3}}{6}+\dots=\sum_{n=1}^{\infty} \frac{\hat{A}^{n}}{n!},
$$
where $\hat{A}^{0}=\hat{I}$, the identity operator. 


> [!tip] A lot of complicated equations can be simplified using exponentials and other functions of linear operators

Other functions can be used, with similar methods of series manipulation.




### Inverses of Linear Operators

The inverse of a linear operator $\hat{A}$ is defined as
$$
\hat{A}^{-1}\hat{A}=\hat{A}\hat{A}^{-1}=\hat{I},
$$
where $\hat{I}$ is the identity operator. $\hat{A}^{-1}$ is called the inverse of $\hat{A}$, and is also a linear operator acting on the same vector space. 
Not every operator has an inverse.

This definition means that if $\hat{A}\ket{a}=\ket{b}$, then $\hat{A}^{-1}\ket{b}=\ket{a}$. 

If for two linear operators $\hat{A}$ and $\hat{B}$, there exists an inverse $\hat{A}^{-1}$ and $\hat{B}^{-1}$, then
$$
(\hat{A}\hat{B})^{-1}=\hat{B}^{-1}\hat{A}^{-1}.
$$
This is how to calculate the inverse of a product of operators. Similarly
$$
(\hat{A}\hat{B})(\hat{A}\hat{B})^{-1}=(\hat{A}\hat{B})^{-1}(\hat{A}\hat{B})=\hat{I}.
$$
Generally, for any number of linear operators,
$$
(\hat{A}\hat{B}\hat{C}\hat{D})^{-1}=\hat{D}^{-1}\hat{C}^{-1}\hat{B}^{-1}\hat{A}^{-1}.
$$

^1df564

The order is reversed, that is.



### Adjoints of Linear Operators
Let $V$ be a complex linear vector space with inner product and let $\hat{A}$ be a linear operator, and let an arbitrary vector $\ket{c}\in V$. Previously, we discussed the [[Dirac Notation#^d66d90|dagger mapping]], which assigns to each ket vector a corresponding bra vector.
$$
\ket{c} \to \bra{c} = \ket{c} ^{\dagger}.
$$
First consider the ket vector $\ket{d}=\alpha \ket{c}$, where $\alpha \in \mathbb{C}$. From the properties of the adjoint, we have
$$
\ket{d} ^{\dagger}=(\alpha \ket{c} )^{\dagger}=\alpha ^{*}\bra{c} .
$$
Generally, $\ket{d}^{\dagger}\neq \ket{d}$ unless $\alpha$ is real. Now, instead of just multiplying $\ket{c}$ by a scalar $\alpha$ to obtain $\ket{d}$, let's act on $\ket{c}$ with a linear operator $\hat{A}$:
$$
\ket{d} =\hat{A}\ket{c} .
$$
The corresponding bra vector is
$$
\bra{d} =\ket{d} ^{\dagger}=(\hat{A}\ket{c} )^{\dagger}.
$$
It turns out that in general, $(\hat{A}\ket{c})^{\dagger}\neq \bra{c}\hat{A}$. Rather, instead we have some operator $\hat{A}^{\dagger}$. So
$$
\bra{d} = (\hat{A}\ket{c} )^{\dagger}=\bra{c} \hat{A}^{\dagger}.
$$
This can be considered a definition of $A^{\dagger}$. 

> [!example] Adjoint of Linear Operators
> Given a [[Linear Operators#^9dd697|linear operator]] $\hat{A}$ acting on a [[Linear Vector Spaces#^1175c0|vector space]] $V$, and letting $\ket{a}\in V$, we define the adjoint $A^{\dagger}$ as
> $$
(\hat[](Linear%20Operators.md#^9dd697)e operator $[](Linear%2[](Linear%20Vector%20Spaces.md#^1175c0)on follows from the [[Linear Operators#^9a9d53|adjoint property]].

^000f44

The linear operator $A^{\dagger}$ satisfies the following "adjoint property" whi[](Linear%20Operators.md#^9a9d53)agger}$. Letting this statement act on some $\ket{a}\in V$:
$$
\braket{ d | a } = \braket{ c | \hat{A}^{\dagger} | a } .
$$
Recalling $\ket{d}=\hat{A}\ket{c}$, we also have
$$
\braket{ a | d } = \braket{ a | \hat{A} | c } .
$$
From the [[Inner Products#^572aff|first axiom of the inner product]], we know that $\braket{ d | a }=\braket{ a | d }^{*}$. Combining these two, we have the

> [!example] Adjoint Property
> Given any two vectors $\ket{a},\ket{b}\in V$ for some [[Linear Vector Spaces#^1175c0|linear vector space]] $V$ and some [[Linear Operators#^9dd697|linear operator]] $\hat{A}$ acting on $V$, the following statement is definitively true. 
> $$
\braket{ b | \hat{A}^{\dagger} | a } = \braket{ a |[](Linear%20Vector%20Spaces.md#^1175c0)[[](Linear%20O[](Linear%20Operators.md#^9dd697)For a given basis, linear ope[](Linear%20Operators.md#^000f44)$
\begin{align}
(\hat{A}^{\dagger})_{ij} &  =\braket{ i | \hat{A}^{\dagger} | j }= \braket{ \hat{A}i | j }  \\
 & = \braket{ j | \hat{A}i } ^{*}=\braket{ j | \hat{A} | i } ^{*}
\end{align}
$$
So ${A}_{ij}^{\dagger}={A}_{ji}^{*}$. 

> [!tip] Adjoint Operation in a Basis
> In a given basis, the adjoint operation - be it on kets, bras, or linear operators - is equivalent to taking the conjugate transpose.

This operation obeys the following property:
$$
(\hat{A}\hat{B})^{\dagger}=\hat{B}^{\dagger}\hat{A}^{\dagger},
$$
which it is left to the reader to prove.

> [!warning] prove that ig
> 


More generally,

> [!tip] Adjoints of Products
> When a product of linear operators, bras, kets, and explicit numerical coefficients is encountered, reverse the order of multiplication of all factors and make the substitutions $\hat{A}\to \hat{A}^{\dagger}$, $\ket{}\to \bra{}$, and $\alpha\to\alpha ^{*}$.

^4a5f49




### Hermitian and anti-Hermitian Operators

> [!example] Hermitian and anti-Hermitian Operators
> An operator $\hat{A}$ is called ***Hermitian*** if it satisfies the relation $
\hat{A}^{\dagger}=\hat{A}.$ 
>Likewise, an operator is called ***anti-Hermitian*** if it satisfies the relation $
\hat{A}^{\dagger}=-\hat{A}.$

^63db04

> [!tip] Matrix Representation of Hermitian Operators
> A Hermitian operator in an orthonormal basis is represented by a [[Basis Representations of Vector Spaces#^e3315e|Hermitian matrix]].


Broadly, the adjoint is to an operator what the complex conjuga[](Basis%20Representations%20of%20Vector%20Spaces.md#^e3315e)ators
> Similarly to how we can decompose any number to a sum to real and imaginary components
> $$
> \alpha=\frac{\alpha+\alpha ^{*}}{2}+\frac{\alpha-\alpha ^{*}}{2},
> $$
> we can decompose every operator into its Hermitian and anti-Hermitian parts
> $$
> \hat{A}=\frac{\hat{A}+\hat{A}^{\dagger}}{2}+\frac{\hat{A}-\hat{A}^{\dagger}}{2}.
> $$

^6de676

#### Example - Function Space
Consider the complex linear vector space of functions $f(x)$ defined for $-\infty<x<\infty$, with the property that $f(x)$ is at least twice differentiable, and $f(x)$, $\frac{df}{dx}$, and $\frac{d^{2}f}{dx^{2}}$ are all square integrable. 

> [!tip] Key Property of Square Integrable Functions
> (Note that $\int_{-\infty}^{\infty} |f(x)|^{2} \, \hspace{0.5mm} dx<\infty$ implies that $\lim_{ x \to \pm \infty }|f(x)|=0$.) This is a necessary condition for the integral to converge. We will use this property below.

^0ffc3a

Let the [[Inner Products#^572aff|inner product]] be defined by
$$
\braket{ g | f } = \int_{-\infty}^{\infty} g^{*}(x)f(x) \, \hspace{0.5mm} dx ,
$$
for all functions $\ket{f}=f(x),\ket{g}=g(x)\in V$. 

We define the linear operator $\hat{A}$ by $\hat{A}:f(x)\to \frac{d^{2}f}{dx^{2}}$. Recall the adjoint property, substituting in the equivalence $\hat{A}^{\dagger}=\hat{A}$ of Hermitian operators:
$$
\begin{align}
\braket{ g | \hat{A} | f }  & = \braket{ f | \hat{A} | g } ^{*}, \\
\braket{ g | \frac{d^{2}f}{dx^{2}} }  & = \braket{ f | \frac{d^{2}g}{dx^{2}} } ^{*}, \\
\int_{-\infty}^{\infty} g^{*}(x) \frac{d^{2}f}{dx^{2}} \, \hspace{0.5mm} dx  & =  \int_{-\infty}^{\infty} f(x) \frac{d^{2}g^{*}}{dx^{2}} \, \hspace{0.5mm} dx , \\
g^{*}(x) \frac{df}{dx} \biggr |_{-\infty}^{\infty}-\int_{-\infty}^{\infty} \frac{dg^{*}}{dx} \frac{df}{dx} \, \hspace{0.5mm} dx  & = f(x) \frac{dg^{*}}{dx} \biggr  |_{-\infty}^{\infty}- \int_{-\infty}^{\infty} \frac{df}{dx} \frac{dg^{*}}{dx} \, \hspace{0.5mm} dx .
\end{align}
$$
The definition of the inner product requires that the norm is finite, implying that $|f(x)|$ and $|g(x)|$ both go to zero as $x\to \pm \infty$ (see the Key Property of Square Integrable Functions above). This means that the boundary terms above vanish, and we have
$$
\int_{-\infty}^{\infty} \frac{df}{dx} \frac{dg^{*}}{dx} \, \hspace{0.5mm} dx = \int_{-\infty}^{\infty} \frac{df}{dx} \frac{dg^{*}}{dx} \, \hspace{0.5mm} dx .
$$
Therefore the second derivative $\hat{A}=\frac{d^{2}}{dx^{2}}$ is Hermitian.


### Unitary Operators

> [!example] Unitary Operators
> An operator $\hat{A}$ is called ***unitary*** if it satisfies the relation $
 \hat{A}\hat{A}^{\dagger}=\hat{A}^{\dagger}\hat{A}=\hat{I},$
 >where $\hat{I}$ is the identity operator.

^56f9c5

 
 Note that if an operator is unitary, then its adjoint is identical to its inverse.
$$
\hat{A}^{\dagger}\equiv \hat{A}^{-1}.
$$
A product of unitary operators is likewise unitary, and this can be proven if you want.

> [!tip] Important Properties of Unitary Operators
> >- Unitary operators preserve vector norms and the inner product. A proof of this property is [[Active Learning Master List#Active Learning 4|here]].
> >- The matrix representing a unitary operator in an orthonormal basis is a [[Basis Representat[](Active%20Learning%20Master%20List.md#Active%20Learning%204)ing%204)4a

On a real vector space, it becomes the case that $U^{-1}=U^{T}$, [](Phys%20100A%20-%20Methods%20of%20Theoretical%20Physics,%20Part%201/Notes/Basis%20Representations%20of%20Vector%20Spaces.md#^3c28cf) orthonormal).

Suppose we subject all vectors $\ket{v}\in V$ to a unitary transformation $\hat{U}$. 
$$
\ket{v} \to \hat{U}\ket{v}. 
$$
Under this transformation, the matrix elements of any operator $\hat{A}$ are modified as follows:
$$
\braket{ v'  |  \hat{A} | v }\to \braket{ \hat{U}v' | \hat{A}|\hat{U}v }=\braket{ v' | \hat{U}^{\dagger}\hat{A}\hat{U} |v  }.   
$$
This is called an ***active transformation***, where vectors are affected.
The same change is effected if we leave alone the vectors and subject all operators acting on $V$ to the change
$$
\hat{A}\to \hat{U}^{\dagger}\hat{A}\hat{U}.
$$
This is called a ***passive transformation***, where vectors are left alone. 

### Derivatives of Linear Operators

Consider a linear operator $\theta(\lambda)$ that depends on some parameter $\lambda$. Its derivative with respect to $\lambda$ is
$$
\frac{d\theta(\lambda)}{d\lambda}=\lim_{ \Delta\lambda \to 0 } \left[ \frac{\theta(\lambda+\Delta\lambda)-\theta(\lambda)}{\Delta\lambda} \right] .
$$
If $\theta$ can be represented as a matrix this is rather simple - just differentiate the elements of the matrix. Let's consider the option, however, where $\theta(\lambda)=e^{ \lambda \Omega}$, where $\Omega$ is Hermitian. Going to the eigenbasis of $\Omega$ we can show that
$$
\frac{ d \theta(\lambda) }{ d \lambda } =\Omega e^{ \lambda\Omega }=e^{ \lambda\Omega }\Omega=\theta(\lambda)\Omega.
$$
This is also true if $\Omega$ is not Hermitian.

### Surjectivity and Injectivity

> [!example] Surjective
> A map $f:S\to T$ is called ***onto*** or ***surjective*** if for all ${} b\in T$ there exists at least one $a\in S$ such that $f(a)=b$.
^ac8938


> [!example] Injective
> A map $f$ is called ***one-to-one*** or ***injective*** if its kernel is trivial. Equivalently, if
> $$
f(a)=f(b) \iff a=b.$$

^3e384b

> [!example] Bijective
> A map is called ***bijective*** if it is both [[#^ac8938|surjective/onto]] and [[#^3e384b|injective/one-to-one]].
> Bijectivity implies invertibility, and the converse is also true.
^9883b3

