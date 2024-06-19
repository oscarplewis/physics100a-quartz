---
tags:
  - Physics100A
  - 100ANotes
---
---
Two vectors are said to be ***orthonormal*** if they both have unit norm and are orthogonal.

### Orthonormal Bases

Given an complex [[Inner Products#^3cf67b|inner product space]] $V$, let $\{\ket{i},i=1,\dots,n\}$ be a basis of $V$. 

Our of the set $\{ \ket{i} \}$, one can always construct a set $\{ \ket{e_{i}},i=1,\dots ,n \}$ of normalized (with unit norm) and mutually orthogonal vectors. That is,
$$
\braket{ e_{i} | e_{j} } =\delta_{ij}=\begin{cases}
1, & i=j \\
0, & i\neq j
\end{cases},
$$
such that each vector $\ket{e_{i}}$ is a linear combination of the original vectors $\{ \ket{i} \}$. This is called the

#### Gram-Schmidt Theorem
> [!example] Gram-Schmidt Theorem
> Given a [[Linear Independence & Basis#^4d61b3|linearly independent]] [[Linear Independence & Basis#^12b0fb|basis]] of a [[Linear Vector Spaces#^1175c0|vector space]] $V$, we can form linear combinations of the basis vectors to obtain an orthonormal basis.

The proof by construction for this is as follows. Consider a complex inner product space $V$, and let $\{ \ket{i},i=1,2,\dots,n \}$ be a linearly independent basis.

First we construct an orthogonal set $\{ \ket{e'_{i}} \}$ which satisfies $\braket{ e'_{i} | e'_{j} }=0$ for $i\neq j$, but is not necessarily normalized:
Let $\ket{e_{1}'}=\ket{1}$. 
Then let $\ket{e_{2}'}=\ket{2}-\beta_{21}\ket{e_{1}'}$, choosing $\beta_{21}$ to make $\ket{e_{2}'}$ orthogonal to $\ket{e_{1}'}$. Requiring that $\braket{ e_{1}' | e_{2}' }=0$ gives
$$
\begin{align}
0=\braket{ e_{1}' | e_{2}' }  & =\braket{ e_{1}' | 2 } -\beta_{21}\braket{ e_{1}' | e_{1}' } , \\
\beta_{21} & =\frac{\braket{ e_{1}' | 2 }}{\braket{ e_{1}' | e_{1}' } }.
\end{align}
$$
Then let $\ket{e_{3}'}=\ket{3}-\beta_{32}\ket{e_{2}'}-\beta_{31}\ket{e_{1}'}$. Requiring that $\braket{ e_{3}' |e_{1}'  }=\braket{ e_{3}' | e_{2}' }=0$ gives
$$
\begin{align}
\beta_{32} & =\frac{\braket{ e_{2}' | 3 } }{\braket{ e_{2}' | e_{2}' } }, \\
\beta_{31} & = \frac{\braket{ e_{1}' | 3 } }{\braket{ e_{1}' | e_{1}' } }.
\end{align}
$$
Then let $\ket{e_{4}'}=\ket{4}-\beta_{43}\ket{e_{3}'}-\beta_{42}\ket{e_{2}'}-\beta_{41}\ket{e_{1}'}$, and so on. Proceeding like this iteratively allows us to construct an orthogonal basis $\{ \ket{e_{i}'},i=1,\dots,n \}$ for $V$.

Finally we normalize the vectors:
$$
\ket{e_{i}} =\frac{1}{\sqrt{ \braket{ e_{i}' |  e_{i}'}  }}\ket{e_{i}'} =\frac{\ket{e_{i}'}}{||e_{i}'||}, i=1,\dots,n.
$$
This yields an orthonormal set $\{ \ket{e_{i}},i=1,\dots ,n \}$ of vectors which span the vector space $V$: an orthonormal basis. 

This method is called Gram-Schmidt Orthonormalization (Theorem).

#### Example - Complex Polynomial Space

Consider the linear vector space $V$ of all complex valued functions $f(x) \in V$ defined on the interval $-1<x<1$, which can be expanded in a Taylor series about any point $x_{0}$ in this interval.

(It can be shown that this set of functions forms a linear vector space by checking the axioms.)

Any vector $\ket{f}\in V$ is a function that can be expanded in a Taylor series about $x_{0}=0$:
$$
\ket{f} =f(x)=f(0)+\frac{f'(0)}{1!}x+\frac{f''(0)}{2!}x^{2}+\frac{f'''(0)}{3!}x^{3}+\dots
$$
Consider the vectors
$$
\ket{m} =\text{functions } \phi_{m}(x)=x^{m},m=0,1,2,\dots
$$
Then from the Taylor series about $x_{0}=0$, we have
$$
\ket{f} =\alpha_{0}\ket{0} +\alpha_{1}\ket{1} +\dots
$$
where $\alpha_{0}=f(0),\alpha_{1}=\frac{f'(0)}{1!},\dots$.
(Note that $\ket{0}$ is not the null vector, but the constant function $\ket{0}=x^{0}=1$.)

The set of vectors $\{ \ket{0},\ket{1},\dots \}$ are linearly independent. This set also forms a basis of the vector space $V$, since any $\ket{f} \in V$ can be expressed as a linear combination of these vectors.
We can then define the inner product
$$
\braket{ f | g } =\int_{-1}^{1} f^{*}(x)g(x) \, \hspace{0.5mm} dx \hspace{0.2cm} \forall \hspace{0.2cm} \ket{f} ,\ket{g} \in V.
$$
We can then use the Gram-Schmidt Orthonormalization method to construct an orthonormal basis from the original $\ket{m}=\phi_{m}(x)=x^{m}$.
1. $\ket{e_{0}'}=\ket{0}=\phi_{0}(x)=1$
2. $\ket{e_{1}'}=\ket{1}-\beta_{10}\ket{e_{0}'}=x-\beta_{10}$
	We require that $\braket{ e_{0}' | e_{1}' }=0$, so $0=\braket{ e_{0}' | 1 }-\beta_{10}\braket{ e_{0}' | e_{0}' }$ and $\beta_{10}=\frac{\int_{-1}^{1} (1)(x) \, \hspace{0.5mm} dx}{\int_{-1}^{1} (1)(1) \, \hspace{0.5mm} dx}=0$.
	So $\ket{e_{1}'}=\ket{1}=\phi_{0}(x)=x$.

... and so on. Continuing in this way we find that
$$
\ket{e_{n}'} \propto P_{n}(x),
$$
where $P_{n}(x)$ is the [Legendre polynomial](https://en.wikipedia.org/wiki/Legendre_polynomials) of degree $n$. 
$$
\begin{align}
P_{0}(x)=1 & \leftrightarrow \ket{e_{0}'}  \\
P_{1}(x)=x & \leftrightarrow \ket{e_{1}'}  \\
P_{2}(x)=\frac{3}{2}\left( \frac{1}{3}(3x^{2}-1) \right) & \leftrightarrow \frac{3}{2}\ket{e_{2}'}  \\
P_{3}(x)=\frac{5}{2} \left( \frac{1}{5}(5x^{3}-3x) \right) & \leftrightarrow \frac{5}{2}\ket{e_{3}'}  \\
 & \vdots
\end{align}
$$
The normalization convention for the Legendre polynomials is $P_{n}(x=1)=1$ for all $n$. In this convention, the Legendre polynomials are all mutually orthogonal and
$$
\braket{ P_{n} | P_{m} }=\int_{-1}^{1} P_{n}(x)P_{m}(x) \, \hspace{0.5mm} dx  = \frac{2\delta_{nm}}{2n+1}, \text{ for } n,m=0,1,2\dots
$$
The normalized versions of these polynomials are
$$
\ket{P_{n}} =\frac{1}{||P_{n}||}\ket{P_{n}} \text{ with } \braket{ P_{n} | P_{m} } =\delta_{nm}.
$$
### Orthonormal Expansions of Vectors
#### Proof: Orthogonality Implies Linear Independence 

> [!thm|*] 
> Given an inner product space $V$, let $\ket{a_{1}},\ket{a_{2}},\dots,\ket{a_{n}}\in V$ be a set of mutually orthogonal vectors of which none is the null vector. That is,
>$$
\begin{align}
\braket{ a_{i} | a_{j} }  & =0 \text{ (for $i\neq j$)}. \\
\braket{ a_{i} | a_{i} }  & \neq 0.
\end{align}$$
>Then this set of vectors is linearly independent.

^e0725e

`\begin{proof}`Assume that
$$
\sum_{i=1}^{n} \alpha_{i}\ket{a_{i}} =\ket{0}. 
$$
We need to show that all $\alpha_{i}=0$. 
We take the inner product of this expression with $\ket{a_{1}}$:
$$
\sum_{i=1}^{n} \alpha_{i}\braket{ a_{1} | a_{i} } =0. 
$$
By the assumption of mutual orthogonality ($\braket{ a_{i} | a_{j} }=0$ for $i\neq j$), all terms except $i=1$ vanish and we have
$$
\begin{align}
\alpha_{1}\braket{ a_{1} | a_{1} }  & =0, \\
\alpha_{1} & =0.
\end{align}
$$
We can repeat this process for all $\ket{a_{1}},\ket{a_{2}},\dots,\ket{a_{n}}$, and so show that all $\alpha_{j}=0$. So we can see that all coefficients must be zero for the statement $$
\sum_{i=1}^{n} \alpha_{i}\ket{a_{i}} =\ket{0} 
	$$to be true. This satisfies the condition for [[Linear Independence & Basis#^4d61b3|linear independence]].`\end{proof}`

> [!tip] This means that mutual orthogonality (excluding the null vector) implies linear independence.

#### Vector Components in an Orthonormal Basis

Now consider an orthonormal basis $\{\ket{e_{1}}, \ket{e_{2}},\dots,\ket{e_{n}} \}$ of an inner product space $V$. This means the basis satisfies
$$
\braket{ e_{i} | e_{j} } =\delta_{ij}.
$$
Any vector $\ket{a}\in V$ can therefore be expressed as a linear combination of these basis vectors.
$$
\ket{a} =\sum_{i=1}^{n} \alpha_{i}\ket{e_{i}}.
$$
To find the components $\alpha_{j}$ of this vector, we take the inner product of $\ket{a}$ with the $j$-th basis vector.
$$
\braket{ e_{j} | a } = \sum_{i=1}^{n} \alpha_{i}\braket{ e_{j} | e_{i} }=\sum_{i=1}^{n} \alpha_{i}\delta_{ij}=\alpha_{j}. 
$$

> [!example] Components of a Vector With an Orthonormal Basis
> Given an orthonormal basis $\{ \ket{e_{i}} \}$ of an inner product space $V$, the components $\alpha_{i}\in \mathbb{C}$ of a vector $\ket{a}\in V$ are defined as $\alpha_{i}=\braket{ e_{i} | a }$. 

Using this definition of the components of a vector with an orthonormal basis, we can rewrite the vector as
$$
\begin{align}
\ket{a}  & =\sum_{i=1}^{n} \braket{ e_{i} | a } \ket{e_{i}},  \\
 & = \sum_{i=1}^{n} \ket{e_{i}} \braket {e_{i}| a} ,\\
 & = \left( \sum_{i=1}^{n} \ket{e_{i}} \bra{e_{i}}  \right)\ket{a} .
\end{align}
$$
Recall that the definition of the identity operator is $\ket{a}=\hat{I}\ket{a}$. So we can see that

> [!example] Completeness Relation
> Given an orthonormal [[Linear Independence & Basis#^12b0fb|basis]] $\{ \ket{e_{i}} \}$ of an [[Inner Products#^3cf67b|inner product space]] $V$, it can be shown that the following relation holds. $$
\sum_{i=1}^{n} \ket{e_{i}} \bra{e_{i}} =\hat{I}, $$ where $\hat{I}$ is the identity operator.

^aef684

From the completeness relation we can derive backwards the form of a vector $\ket{a} \in V$ in an orthonormal basis by the identity relation:
$$
\begin{align}
\ket{a}  & =\hat{I}\ket{a}, \\
 & =\left( \sum_{i=1}^{n} \ket{e_{i}} \bra{e_{i}}  \right)\ket{a} ,  \\
 & = \sum_{i=1}^{n} \braket{ e_{i} | a } \ket{e_{i}} , \\
 & = \sum_{i=1}^{n} \alpha_{i}\ket{e_{i}}. 
\end{align}
$$
Here the operator $P_{i}=\ket{e_{i}} \braket{ e_{i}}$ is called the ***projection operator*** for the ket $\ket{e_{i}}$. Consider a vector $\ket{v}$:
$$
P_{i}\ket{v} =\ket{i} \braket{i |V} =\ket{i} v_{i}.
$$
The operator projects the vector along the vector $\ket{i}$. We can use the projection operator on bras in the same manner:
$$
\bra{v} P_{i}=\braket{ V | i } \bra{i} =v_{i}^{*}\bra{i} .
$$
Furthermore, projection operators corresponding to the vectors of an orthonormal basis obey the following property:
$$
P_{i}P_{j}=\ket{i} \braket{ i | j } \bra{j} = \delta_{ij}P_{j},
$$
(summation not implied). This means that once $P_{i}$ is applied to a vector $\ket{v}$, further applications of $P_{i}$ have no effect. Also, any subsequent application of $P_{j}\hspace{2px}(j\neq i)$ will result in zero; a vector projected along $\ket{i}$ cannot have a projection along an orthogonal vector $\ket{j}$. 

### Example -  Fourier Series

Consider again the vector space of complex valued periodic functions of a real variable $x$. 
$$
\psi(x+\lambda)=\psi(x).
$$
Let $\ket{e_{n}}\leftrightarrow \text{function } \frac{1}{\sqrt{ \lambda }}\psi_{n}(x)=\frac{1}{\sqrt{ \lambda }}e^{ i(2\pi/\lambda)nx }$. We can easily verify that
$$
\begin{align}
\braket{ e_{m} | e_{n} }  & =\int_{-\lambda/2}^{\lambda/2} \left( \frac{1}{\sqrt{ \lambda }}\psi_{m}(x) \right)^{*}\left( \frac{1}{\sqrt{ \lambda }}\psi_{n}(x) \right)  \, \hspace{0.5mm} dx  \\
 & = \frac{1}{\lambda}\int_{-\lambda/2}^{\lambda/2} e^{ i(2\pi/\lambda)(n-m)x } \, \hspace{0.5mm} dx  \\
 & = \begin{cases}
1, & n=m; \\
0, & n\neq m;
\end{cases} = \delta_{mn}.
\end{align}
$$
From the theory of Fourier series, for any vector $\psi(x)=\ket{\psi}\in V$ represented by $\ket{\psi}=\sum_{m=-\infty}^{\infty}\alpha_{m}\ket{e_{m}}$, we can find the coefficients
$$
\alpha_{m}=\braket{ e_{m} | \psi }=\frac{1}{\lambda}\int_{-\infty}^{\infty} e^{ -i(2\pi/\lambda)mx }\psi(x) \, \hspace{0.5mm} dx . 
$$
This is the formula for the coefficients of a Fourier series, but here we see it as an example of the expansion of a vector in an orthonormal basis.
We can then rewrite $\ket{\psi}$:
$$
\psi(x)=\ket{\psi}=\sum_{m=-\infty}^{\infty} \braket{ e_{m} | \psi } \ket{e_{m}}.   
$$

