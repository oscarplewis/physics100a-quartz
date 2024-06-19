---
tags:
  - Physics100A
  - 100ANotes
---
---
### Review from Linear Algebra
> [!example] Linear Independence
> A set of vectors $\ket{a_{1}},\ket{a_{2}},\dots \ket{a_{n}}$ is said to be ***linearly independent*** if
>$$
\sum_{i=1}^{n} \alpha_{i}\ket{a_{i}}=\ket{0}  $$
>is true only for the trivial solution where all $\alpha_{i}=0$. ($\ket{0}$ is the null vector.) 
>If a set of vectors is not linearly independent, it is called ***linearly dependent***.

^4d61b3



> [!example] Orthogonality
> Two vectors are said to be ***orthogonal*** if their [[Inner Products#^572aff|inner product]] vanishes.

^167287



> [!example] Dimension of a Linear Vector Space
> A [[Linear Vector Spaces#^1175c0|linear vector space]] $V$ has ***dimension*** $n$ if it can accommodate a maximum of $n$ [[#^4d61b3|linearly independent]] vectors.

^d8142a



This means that any vector $\ket{a} \in V$ (where $V$ is an $n$-dimensional vector space) can be expressed as a linear combination of $n$ linearly independent vectors. 

### Span and Bases

> [!example] Span
> Given an $n$-dimensional [[Linear Vector Spaces#^1175c0|vector space]] $V$, a set of vectors $\ket{a_{i}}$ is said to ***span*** the space if any vector in $V$ can be expressed as a linear combination of them.
> (Note that there must be at least $n$ vectors in a set for the set to span the space.)

^084ecc


> [!example] Basis
> Given an $n$-dimensional [[Linear Vector Spaces#^1175c0|vector space]] $V$, a set of $n$ linearly independent vectors is called a ***basis*** of $V$. Note that this set of vectors must by definition [[#^084ecc|span]] the space. 
> A basis is ***orthonormal*** if it consists of a set of [[#^167287|orthogonal]] vectors of unit [[Inner Products#^db8742|norm]].

^12b0fb

#### Basis of Cartesian Space
A vector space can have many bases. Typically convention will specify a basis, such as the standard basis in Cartesian $n$-dimensional space: $\hat{i},\hat{j},\hat{k},\text{etc.}$
#### Basis of 2x2 Complex Matrices
Another example is the vector space of all 2x2 matrices with complex entries, which can have a basis of the following vectors:
$$
\begin{align}
\ket{1'}  & =\ket{I} = \begin{pmatrix}
1 & 0  \\
0 & 1
\end{pmatrix}, \\
\ket{2'}  & =\ket{\sigma_{1}}=\begin{pmatrix}
0 & 1  \\
1 & 0
\end{pmatrix} , \\
\ket{3'}  & = \ket{\sigma_{2}} =\begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix}, \\
\ket{4'}  & =\ket{\sigma_{3}} =\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}.
\end{align} 
$$
The latter three $\ket{\sigma_{1}},\ket{\sigma_{2}},\ket{\sigma_{3}}$ are called the ***Pauli (spin) matrices***. 

#### Basis of Fourier Space

Consider the set of all complex valued functions of a real variable $x \in(-\infty,\infty)$, and $\psi(x)\in\mathbb{C}$. Now consider functions that are periodic with period $\lambda \in\mathbb{R}$ (that is, $\psi(x+\lambda)=\psi(x)$ for $-\infty<x<\infty$). One can verify that this set of functions forms a complex [[Linear Vector Spaces#^1175c0|linear vector space]] by checking the axioms.

Consider the following set of functions in $V$:
$$
\begin{align}
\{ \ket{\phi_{m}}  \} , & \hspace{0.1cm} m=0,\pm 1, \pm 2,\dots, \\
\ket{\phi_{m}}  & = \phi_{m}(x)=e^{ i(2\pi/\lambda)mx }.
\end{align}
$$
The vectors $\{ \ket{\phi_{m}} \}$ are linearly independent. Moreover, the theory of Fourier series tells us that any periodic function $\ket{\psi}=\psi(x)$ of period $\lambda$ can be written as
$$
\begin{align}
\psi(x) & =\sum_{m=-\infty}^{\infty} \alpha_{m}\phi_{m}(x)=\sum_{m=-\infty}^{\infty} \alpha _{m}e^{ i(2\pi/\lambda)mx }. \\
\ket{\psi}  & =\sum_{m=-\infty}^{\infty} \alpha_{m}\ket{\phi_{m}} .
\end{align}
$$
This means that $\{ \ket{\phi_{m}} \}$ forms a basis of $V$. The coefficients $\alpha_{m}$ in the Fourier series are given by:
$$
\alpha_{m}=\frac{1}{\lambda}\int_{-\lambda/2}^{\lambda/2} e^{ -i(2\pi/\lambda)mx }\psi(x) \, \hspace{0.5mm} dx =\braket{ \phi_{m} | \psi } .
$$
So 
$$
\ket{\psi} =\sum_{m=-\infty}^{\infty} \braket{ \phi_{m} | \psi } \ket{\phi_{m}} =\sum_{m=-\infty}^{\infty} \ket{\phi_{m}} \bra{\phi_{m}} \ket{\psi}. 
$$
This form doesn't just appear in Fourier series. More generally,

> [!note] Coordinates in a Basis
> Given a vector $\ket{a}\in V$ for some $n$-dimensional vector space $V$, 
> $$
\hat{B}=\sum_{i=1}^{n} \ket{i} \bra{i} , $$ 
>is the operator that expands $\ket{a}$ in the orthonormal basis $\{ \ket{i} \}$.

^4b2410

