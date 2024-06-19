---
tags:
  - Physics100A
  - 100ANotes
---
---
### Defining Eigenvectors and Eigenvalues

> [!example] Eigenvectors and Eigenvalues
> Let $\hat{A}$ be a linear operator in a linear vector space $V$. A ket vector $\ket{a}\neq \ket{0}$ (the null vector) in $V$ is called an ***eigenvector*** of $\hat{A}$ with ***eigenvalue*** $\lambda \in\mathbb{C}$ (a scalar) if it satisfies the statement:
> $$
> \hat{A}\ket{a} =\lambda \ket{a} .$$
> Note that the null vector can never be an eigenvector.

^56e47a

As an example, consider $\hat{A}=\hat{I}$, the identity operator. Then all ket vectors $\ket{a}\neq \ket{0}$ are eigenvectors with eigenvalue $\lambda=1$. 
$$
\hat{I}\ket{a} = 1\ket{a} .
$$
### Eigenvectors and Eigenvalues of Hermitian Operators
Hermitian operators play a very important role in physics, mathematics, and engineering. They have important and simple properties.


> [!example] Real Eigenvalue Property of Hermitian Operators
> Any [[#^56e47a|eigenvalue]] of a [[Linear Operators#^63db04|Hermitian operator]] $\hat{H}$ is real.

^f5cc29


> [!NOTE] Proof of the Real Eigenvalue Property
> Suppose $\hat{H}\ket{a}=\lambda \ket{a}$. Then
> $$
> \begin{align}
> \braket{ a | \hat{H} | a }  & = \braket{ a | \hat{H}^{\dagger} | a } ^{*}, \tag{adjoint property}\\
>  & = \braket{ a | \hat{H} | a } , \tag{$\hat{H}=\hat{H}^{\dagger}$ b/c Hermitian}\\
> & = \left[\lambda \braket{ a | a }  \right] ^{*}, \tag{$\hat{H}\ket{a} =\lambda \ket{a} $}\\
> & = \lambda ^{*}\braket{ a | a } ^{*} , \\
> & = \lambda ^{*}\braket{ a | a } ,\tag{the norm is real}\\
> \lambda \braket{ a | a } & = \lambda ^{*}\braket{ a | a } .
> \end{align}$$
> This implies that $\lambda=\lambda ^{*}$, and so is real. Therefore any eigenvalue of a Hermitian operator is real.
> QED.



> [!example] Orthogonal Eigenvector Property of Hermitian Operators
> [[#^ecd733|Eigenvectors]] of [[Linear Operators#^63db04|Hermitian operators]] corresponding to different eigenvalues are [[Linear Independence & Basis#^167287|mutually orthogonal]].

^6eb0f5

> [!NOTE]+ Proof of Orthogonal Eigenvector Property
> Let $\hat{H}\ket{a_{1}}=\lambda_{1}\ket{a_{1}}$ and $\hat{H}\ket{a_{2}}=\lambda_{2}\ket{a_{2}}$, for $\lambda_{1}\neq \lambda_{2}$. We can thus see that $\ket{a_{1}}$ and $\ket{a_{2}}$ are eigenvectors of the Hermitian operator $\hat{H}$. By the [[#^f5cc29|Real Eigenvalue Property]], both $\lambda_{1}$ and $\lambda_{2}$ are real. Then:
> $$
> \begin{align}
> \braket{ a_{1} | \hat{H} | a_{2} }  & = \lambda_{2}\braket{ a_{1} | a_{2}} \tag{$\hat{H}\ket{a_{2}}=\lambda_{2}\ket{a_{2}}  $}.\\
> \braket{ a_{2} | \hat{H}^{\dagger} | a_{1} } ^{*} & = \braket{ a_{2} | \hat{H} | a_{1} } ^{*} \tag{adjoint property, $\hat{H}^{\dagger}=\hat{H}$}, \\
> & = \left[ \lambda_{1} \braket{ a_{2} | a_{1} }  \right] ^{*}.
> \end{align}$$
> By the [[Inner Products#^572aff|first axiom of the inner product]], $\braket{ a_{2} | a_{1} }^{*}=\braket{ a_{1} | a_{2} }$. Further, $\lambda_{1}$ is real. So we have
> $$
> \begin{align}
> \lambda_{2}\braket{ a_{1} | a_{2} }  & = \lambda_{1}\braket{ a_{1} | a_{2} }, \\
> (\lambda_{2}-\lambda_{1})\braket{ a_{1} | a_{2} } & = 0. 
> \end{align}$$
> We know that $\lambda_{1}\neq\lambda_{2}$, so for this statement to always be true,
> $$
> \braket{ a_{1} | a_{2} } =0.$$
> That is, $\ket{a_{1}}$ and $\ket{a_{2}}$ are orthogonal. 
> QED.

### Eigenvectors and Eigenvalues of Unitary Operators

> [!tip] Eigen______ of Unitary Operators
> For a unitary operator, its eigenvalues are complex numbers of unit modulus (***unimodular***) and its eigenvectors are mutually orthogonal (assuming no degeneracy).

^9db033

### In a Basis

Let $\{ \ket{i} \}$ be a basis of the vector space $V$. Note that this basis is not necessarily orthogonal. Consider
$$
\hat{A}\ket{a} =\lambda \ket{a}. 
$$

^11bb54

In this basis, the vector $\ket{a}=\sum_{j=1}^{n}\alpha_{j}\ket{j}$ is represented by the column vector
$$
\vec{\alpha}=\begin{pmatrix}
\alpha_{1} \\
\vdots \\
\alpha_{n}
\end{pmatrix}.
$$
The operator $\hat{A}$ is represented by a matrix $A$ with column vectors $\hat{A}\ket{j}$. [[#^11bb54]] implies that in the basis $\{ \ket{i} \}$, 
$$
A\vec{\alpha}=\lambda\vec{\alpha}.
$$
This can also be written
$$
\begin{align}
A\vec{\alpha} & =\lambda I\vec{\alpha}, \\
(A-\lambda I)\vec{\alpha} & = \vec{0}.
\end{align}
$$
where $I$ is the identity matrix and $\vec{0}$ is the basis representation of the null vector. Let 
$$
B=A-\lambda I.
$$
So we have
$$
B\vec{\alpha}=\vec{0}.
$$

^9084af

This is a restatement of [[#^11bb54]]. 

> [!summary] Lemma 1
> **Lemma 1:** If a matrix $M$ is singular, then its determinant is zero.
> **Proof:** For the sake of contradiction, assume $\det M = 0$ and $M$ is invertible, so $M^{-1}$ exists. Then by definition of the inverse,
> $$
> M^{-1}M=MM^{-1}=I,$$
> where $I$ is the identity matrix. Taking the determinant of this expression, we have
> $$
> \begin{align}
> (\det M^{-1})(\det M) & =(\det M)(\det M^{-1})=\det I, \\
> (\det M^{-1})\cdot 0  & = 0\cdot(\det M^{-1})=1, \\
> 0 & =1.
> \end{align}
> $$
> There is a contradiction, so $M$ must be singular.
> > [!warning] I don't think this proof is satisfactory, as it proves the converse of Lemma 1. I can't think of how to prove the lemma though, and I know that it must be true, so I'm moving on lol.
> > 
> 

^124f87

Assume for the sake of contradiction that $B^{-1}$ exists. Then, multiplying [[#^9084af]] by $B^{-1}$, we have
$$
\begin{align}
B^{-1}B\vec{\alpha} & =B^{-1}\vec{0}, \\
\vec{\alpha} & = \vec{0}.
\end{align}
$$
However, by definition [[#^ecd733|the null vector is not an eigenvector]], implying that neither is $\ket{a}$, a statement we know to be false by [[#^9084af]] (because for a given value $\lambda$ we then can find no associated eigenvectors, so $\lambda$ must not be an eigenvalue, which makes the equation self-contradictory). So $B^{-1}$ must not exist, and $B$ is a singular matrix. By [[#^124f87|Lemma 1]], we then know that $\det B=0$. So only values $\lambda$ which satisfy the following equation are eigenvalues:
$$
\det(A-\lambda I)=0.\tag{3}
$$

> [!example] Characteristic Polynomial
> Given a matrix $A$, it's [[#^ecd733|eigenvalues]] $\lambda$ satisfy the equation 
> $$
\det(A-\lambda I)=0,$$
>where $I$ is the [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^85a5f8|identity matrix]]. We can write this as $P(\lambda)=\det(A-\lambda I)=0$, which is a polynomial in the variable $\lambda$ of degree $n$, called the ***characteristic polynomial of the matrix $A$***. That is,
> $$
> P(\lambda)=\sum_{k=0}^{n} \beta_{k}\lambda^{k}=0. $$
> $P(\lambda)$ has $n$ not necessarily distinct solutions (a general property of polynomials of degree $n$), which we denote $\lambda_{1},\lambda_{2},\dots,\lambda_{n}$. We call these the eigenvalues of the matrix $A$ and the operator $\hat{A}$. 
>

^db16a3

> [!example] Eigenvalue Basis Independence
> The [[#^db16a3|characteristic polynomial]] $P(\lambda)$ of a matrix representation $A$ of a linear operator $\hat{A}$ is dependent only on the linear operator and is independent of the chosen [[Linear Independence & Basis#^12b0fb|basis]]. Therefore the [[#^ecd733|eigenvalues]] of $\hat{A}$ are independent of basis as well. 

^6bc0e1

> [!NOTE] Proof of Eigenvalue Basis Independence
> Consider the matrix $R^{-1}AR$, for the matrix representation $A$ of the linear operator $\hat{A}$ and some change of basis matrix $R$. 
> $$
> \begin{align}
> \det(R^{-1}AR) & = (\det R^{-1})(\det A)(\det R), \\
>  & = \underbrace{ (\det R^{-1})(\det R) }_{ \det I=1 } (\det A), \\
>  & = \det A.
> \end{align}
> $$
> So for the matrix $B=A-\lambda I$, then:
> $$
> \begin{align}
> R^{-1}BR & =R^{-1}AR-\lambda R^{-1}IR=R^{-1}AR-\lambda I. \\
> 
> \end{align}
> $$
> So $B$ for a change of basis can simply be computed by $R^{-1}BR$ instead of needing to take $R^{-1}AR$ and then do a further calculation. Further,
> $$
> \begin{align}
> \det(R^{-1}BR) & = \det B, \\
> \det(A'-\lambda' I) & = \det(A-\lambda I), \\
> P'(\lambda') & = P(\lambda).
> \end{align}
> $$
> Therefore $\lambda'=\lambda$, and so the characteristic polynomials and eigenvalues are independent of basis.

### Degeneracy
It sometimes is the case that not all eigenvalues $\lambda_{i}$ are distinct. For example, consider a $4\times 4$ matrix with eigenvalues $\lambda=\lambda_{1}=\lambda_{2}=\lambda_{3}$, $\lambda_{4}=\mu\neq\lambda$. In this case there are three linearly independent eigenvectors $\ket{v_{1}},\ket{v_{2}},\ket{v_{3}}$ which all correspond to the same eigenvalue:
$$
\begin{align}
\hat{A}\ket{v_{i}} = \lambda \ket{v_{i}} ,i=1,2,3.
\end{align}
$$
We therefore say that the *eigenvalue $\lambda$ is threefold degenerate* (appearing for three different eigenvectors).

> [!example] Degeneracy
> The [[#^56e47a|eigenvalue]] $\lambda$ of the [[Linear Operators#^9dd697|linear operator]] $\hat{A}$ is called ***degenerate*** if there are two or more [[Linear Independence & Basis#^4d61b3|linearly independent]] eigenvectors with the same eigenvalue.

^fa99f5

^5d2551
### Diagonalizable Operators
Let $V$ be an $n$ dimensional vector space, $\hat{A}:V\to V$ be a linear operator, and $\{ \ket{1},\dots,\ket{n} \}$ be a not necessarily orthonormal basis of $V$ (the "old basis").

> [!example] Diagonalizable Operators
> A linear operator $\hat{A}$ is called ***diagonalizable*** *if and only if* there exists a basis $\{ \ket{v_{1}},\dots,\ket{v_{2}} \}$ of $V$ which consists of eigenvectors of the operator $\hat{A}$. 
> $$
> \hat{A}\ket{v_{i}}=\lambda_{i}\ket{v_{i}},i=1,\dots,n,$$
> with summation not implied.

^1d5304

Let $\ket{v_{i}}=\sum_{j=1}^{n}R_{ji}\ket{j}$, for a new basis $\{ \ket{v_{i}} \}$ and an old basis $\{ \ket{i} \}$, with change of basis matrix $R$. We can write:
$$
R=\begin{pmatrix}
R_{11} & R_{12} & \dots & R_{1n} \\
R_{21}  & R_{22} & \dots & R_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
R_{n1} & R_{n2} & \dots & R_{nn}
\end{pmatrix}\equiv \begin{pmatrix}
v_{11} & v_{12} & \dots & v_{1n} \\
v_{21}  & v_{22} & \dots & v_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
v_{n1} & v_{n2} & \dots & v_{nn}
\end{pmatrix}.
$$

^451c97

We're letting $v_{ij}$ be the components of $R$ in the old basis $\{ \ket{i} \}$. In the old basis:
$$
\ket{v_{i}} \leftrightarrow \vec{v}_{i}=\begin{pmatrix}
v_{1i} \\
v_{2i} \\
\vdots \\
v_{ni}
\end{pmatrix} .
$$

> [!tip] A Note on Notation
> The double headed arrow is read out "is represented by" in this instance, and represents an abstract vector being explicitly represented by a set of coordinates in a given basis.

Let $A$ be the matrix representing a [[#^1d5304|diagonalizable operator]] $\hat{A}$ with eigenvectors $\{ \ket{v_{i}} \}$ in the old basis $\{ \ket{i} \}$. So we know
$$
\hat{A}\ket{v_{j}}=\lambda_{j}\ket{v_{j}} . 
$$
We can write this in terms of components;
$$
\begin{align}
A\vec{v}_{j} & =\lambda_{j}\vec{v}_{j}, \\
\sum_{k=1}^{n} A_{ik}v_{kj} & = \lambda_{j}v_{ij}.
\end{align}
$$

^9cc7cf

> [!tip] A Note on Notation
> Note that here $k$ is the dummy index representing the matrix multiplication, $j$ is the index determining which eigenvectors and eigenvalues we're referring to, and $i$ is the index representing the components of the vectors. Summation is never implied.

Now we introduce the [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^f2a33e|diagonal matrix]] $D$ with matrix elements
$$
D_{ij}=\lambda_{j}\delta_{ij}.
$$
We can now rewrite [[#^9cc7cf]] as
$$
\sum_{k=1}^{n} A_{ik}v_{kj}=\sum_{k=1}^{n} v_{ik}\delta_{kj}\lambda_{j}=\sum_{k=1}^{n} v_{ik}D_{kj}.
$$
Recalling our definition of the change of basis matrix $R$ in [[#^451c97]], this becomes
$$
AR=RD.
$$
And since $R$ is invertible, we can multiply both sides by its inverse, yielding
$$
D=R^{-1}AR.
$$
To summarize:
- $\hat{A}$ is a diagonalizable operator.
- $A$ is the matrix representing $\hat{A}$ in the basis $\{ \ket{1},\dots,\ket{n} \}$.
- $\vec{v}_{j}=\sum_{i=1}^{n}v_{ij}\ket{i}$ is the basis representation of the $j$-th eigenvector $\ket{v_{j}}$ of the linear operator $\hat{A}$ in this basis.
- $R$ is the change of basis matrix from the old basis to a basis of the eigenvectors of $\hat{A}$, and has column vectors $\vec{v}_{j}$.
Then $R$ brings $A$ into a diagonal form, $D=R^{-1}AR$. This is called a similarity transformation, and the matrices $D$ and $A$ are called similar.

> [!example] Matrix Similarity
> Given two matrices $A$ and $B$, then a ***similarity transformation*** on $A$ is given by
> $$
A \to B^{-1}AB.$$
>We say that the matrices $A$ and $B^{-1}AB$ are ***similar***. 

^d652df


> [!tip] Diagonalizing Matrices
> A matrix $A$ is called ***diagonalizable*** if it is similar to a [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^f2a33e|diagonal matrix]] $D$, whose diagonal elements are the [[#^56e47a|eigenvalues]] of $A$. The matrix $R$, whose columns are the eigenvectors of $A$, diagonalizes $A$.
> So to diagonalize any (square) matrix, we first find its eigenvalues to create $D$ and eigenvectors to create $R$. Note that in the case of a [[Linear Independence & Basis#^4d61b3|linearly dependent]] set of eigenvectors a matrix is not diagonalizable.
> *This implies that a if a matrix is diagonalizable, there exists a basis of its eigenvectors for its vector space.*

^727463


#### Different Bases
Consider the linear operator ${} \hat{A}:V\to V {}$ for an $n$ dimensional vector space $V$ and two different bases $\{ \ket{i} \}$ and $\{ \ket{i'} \}$. If $\hat{A}$ is diagonalizable, then we have a third basis of $V$, the eigenvectors of $\hat{A}$. 
$$
\{ \ket{v_{i}}  \} \to D_{ij}=\lambda_{i}\delta_{ij}.
$$
We want to find the relationship between the matrices $A$, $A'$, and $D$. First we can express the eigenkets is the two bases:
$$
\begin{align}
\ket{v_{i}} & =\sum_{j=1}^{n} R_{ji}\ket{j},  \\
 & = \sum_{j=1}^{n} (R')_{ji}\ket{j'} .
\end{align}
$$
This means that $R$ is the change of basis matrix from the basis $\{ \ket{i} \}$ to the basis $\{ \ket{v_{i}} \}$, and $R'$ is the change of basis matrix from the basis $\{ \ket{i'} \}$ to the basis $\{ \ket{v_{i}} \}$. 

> [!tip] Finding $R$
> If we know the representations of the eigenvectors in the bases $\{ \ket{i} \}$ and $\{ \ket{i'} \}$, then we can write $R$ and $R'$ rather easily: the basis representations of the eigenvectors are just the column vectors of the change of basis matrix.

^849345

We can represent the operator $\hat{A}$ in these bases as:
$$
\begin{align}
 A=\underbrace{ RDR^{-1} }_{ \{ \ket{i}  \} } \stackrel{R}{\leftrightarrow }\underbrace{ D }_{ \{ \ket{v_{i}}  \} } \stackrel{R'}{\leftrightarrow } \underbrace{ R'D(R')^{-1} }_{ \{ \ket{i'}  \} } =A'.
\end{align}
$$
(The three matrices $A$, $A'$, and $D$ are [[#^d652df|similar]].) Letting $\vec{v}_{i}$ be the column vector of components of the eigenvectors in the basis $\{ \ket{i} \}$ and $\vec{v}_{i}'$ be the column vector of components of the eigenvectors in the basis $\{ \ket{i'} \}$. Then:
$$
\begin{align}
A\vec{v}_{i} & = \lambda_{i}\vec{v}_{i}, \\
A'\vec{v}_{i}' & = \lambda_{i}\vec{v}_{i}'.
\end{align}
$$
We can relate the matrices $A$ and $A'$ as follows. Begin with $A=RDR^{-1}\to D=R^{-1}AR$. Then
$$
\begin{align}
A' & =R'D(R')^{-1}, \\
 & = R'(R^{-1}AR)(R')^{-1}, \\
 & = (R'R^{-1})A(R'R^{-1})^{-1}.
\end{align}
$$
Comparing this with the [[Change of Basis#^82646b|equation for the change of basis acting on the matrix representation of a linear operator]], we see that the matrix $(R'R^{-1})^{-1}$ is therefore the change of basis matrix from $\{ \ket{i} \}$ to $\{ \ket{i'} \}$; or in a simpler statement, the matrix $R'R^{-1}$ is the change of basis matrix from $\{ \ket{i'} \}$ to $\{ \ket{i} \}$. 
 
### Spectral Decomposition of Linear Operators

> [!example] Spectrum
> The set of [[#^56e47a|eigenvalues]] of a [[Linear Operators#^9dd697|linear operator]] $\hat{A}$ is called the ***spectrum*** of $\hat{A}$.

^9df0a3

Spectral decomposition of a matrix is the process of [eigendecomposition](https://en.wikipedia.org/wiki/Eigendecomposition_of_a_matrix) applied to specific types of matrices, specifically normal, Hermitian, or unitary matrices. Eigendecomposition is the process of factoring a matrix into components using its eigenvectors and eigenvalues.

#### Spectral Theorem for Hermitian Operators

> [!example] Spectral Theorem of Hermitian Operators
> Let ${} \hat{H}:V \to V {}$ be a [[Linear Operators#^63db04|Hermitian operator]]. Then $V$ has an orthonormal [[Linear Independence & Basis#^12b0fb|basis]] $\{ \ket{v_{i}} \}$ of [[#^56e47a|eigenvectors]] of $\hat{H}$ if $\hat{H}$ is invertible. 
> $$
> \begin{align}
> \hat{H}\ket{v_{i}}  & = \lambda_{i}\ket{v_{i}}, \tag{def. of eigenvectors}\\
> \braket{ v_{i} | v_{j} }  & = \delta_{ij}, \tag{orthonormality}\\
> \{ \ket{v_{i}}  \} &\text{ forms a basis of $V$.}
> \end{align}$$
> Note that this implies $\hat{H}$ is [[#^1d5304|diagonalizable]].

^7d228b

The proof is not given here. 

Note that since $\{ \ket{v_{i}} \}$ form an orthonormal basis, for any ket $\ket{a}\in V$ we can write:
$$
\begin{align}
\ket{a}  & = \sum_{i=1}^{n} \alpha_{i}\ket{v_{i}} = \sum_{i=1}^{n} \braket{ v_{i} | a } \ket{v_{i}} , \tag{by the completeness relation}\\
\end{align}
$$
#### Spectral Decomposition of a Nonsingular Hermitian Operator

The operator $\hat{H}$ can be decomposed in a basis of its own eigenvectors.
$$
\begin{align}
\hat{H}=\hat{I}\hat{H}\hat{I} & =\left( \sum_{i=1}^{n} \ket{v_{i}} \bra{v_{i}}  \right)\hat{H}\left( \sum_{i=1}^{n} \ket{v_{j}} \bra{v_{j}}  \right), \\
 & = \sum_{i,j=1}^{n} \ket{v_{i}} \braket{ v_{i} | \hat{H} | v_{j} } \bra{v_{j}} , \\
 & = \sum_{i,j=1}^{n} \ket{v_{i}} (\lambda_{j}\underbrace{ \braket{ v_{i} | v_{j} } }_{ \delta_{ij} }  )\bra{v_{j}} , \tag{eigenvalue definition} \\
\hat{H} & = \sum_{i=1}^{n} \ket{v_{i}} \lambda_{i} \bra{v_{i}} \tag{delta reduction}.
\end{align}
$$
This is called the spectral decomposition of $\hat{H}$. 

> [!example] Spectral Decomposition of Hermitian Operators
> Let ${} \hat{H}:V\to V {}$ be an invertible Hermitian operator with a set of orthonormal eigenvectors $\{ \ket{v_{i}} \}$. The ***spectral decomposition*** of the operator $\hat{H}$ is given by
> $$
> \hat{H}=\sum_{i=1}^{n} \ket{v_{i}} \lambda_{i} \bra{v_{i}}.$$

^5d168d

>[!warning] note the comparison between this and representing a linear operator in a basis

This implies that $\ket{v_{j}}$ is an eigenvector of $\hat{H}$ with eigenvalue $\lambda_{j}$. 
$$
\begin{align}
\hat{H}\ket{v_{j}}  & = \left( \sum_{i=1}^{n} \ket{v_{i}} \lambda_{i} \bra{v_{i}}  \right)\ket{v_{j}} , \\
& = \sum_{i=1}^{n} \ket{v_{i}} \lambda_{i}\underbrace{ \braket{ v_{i} | v_{j}
} }_{ \delta_{ij} }, \\
 & = \lambda_{j}\ket{v_{j}}. 
\end{align}
$$
#### Spectral Decomposition of an Arbitrary Operator

In contrast to this, let $\hat{A}:V\to V$ be any linear operator, and $\{ \ket{e_{i}} \}$ be any orthonormal basis (not necessarily eigenvectors).   
$$
\hat{A}=\hat{I}\hat{A}\hat{I}=\sum_{i,j=1}^{n} \ket{e_{i}} \braket{e_{i}|\hat{A} | e_{j}}\bra{e_{j}}=\sum_{i,j=1}^{n} \ket{e_{i}} A_{ij}\bra{e_{j}} .
$$
This is the spectral decomposition of $\hat{A}$. 


> [!example] Spectral Decomposition of Linear Operators
> Let ${} \hat{A}:V\to V {}$ be a linear operator and let $\{ \ket{e_{i}} \}$ be an orthonormal basis of $V$. The ***spectral decomposition*** of the operator $\hat{A}$ is given by
> $$
\hat{A}=\sum_{i,j=1}^{n} \ket{e_{i}} A_{ij}\bra{e_{j}} .$$

^529753



### Diagonalization of Hermitian Matrices

Let $\hat{H}$ be a Hermitian operator and let $\{ \ket{e_{i}}, \dots,\ket{e_{n}} \}$ be an orthonormal basis. We know the matrix $H$ which represents $\hat{H}$ in this orthonormal basis is a Hermitian matrix ($(H^{\dagger})_{ij}=H_{ij}$), and the converse is likewise true, again specifically for orthonormal bases, as discussed [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#Orthonormal Bases|here]].

> [!example] Theorem of Diagonalization of Hermitian Matrices
> Any Hermitian matrix $H$ can be diagonalized by a unitary matrix $U$.

^2a6d0f

This follows directly from the spectral theorem of Hermitian operators and the discussion of [[#Diagonalizable Operators|diagonalizable operators]]. Let $H$ be a Hermitian matrix with elements $H_{ij}$. Then $H$ may be viewed as the matrix representing an abstract Hermitian operator $\hat{H}$ in some orthonormal basis $\{ \ket{e_{i}},\dots,\ket{e_{n}} \}$. 
By the [[#^7d228b|Spectral Theorem for Hermitian Operators]], $\hat{H}$ has an orthonormal basis of eigenvectors $\{ \ket{v_{i}} \}$. 
Since a Hermitian operator is diagonalizable by the Spectral Theorem, we can apply our [[#Diagonalizable Operators|previous discussion of diagonalizable operators]] to the Hermitian case.

|                                |                                                                        |                                                                                                                      |
| ------------------------------ | ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
|                                | **Arbitrary case**                                                     | **Hermitian case**                                                                                                   |
| operator                       | $\hat{A}$                                                              | $\hat{H}$ (Hermitian)                                                                                                |
| old basis                      | $\{ \ket{1},\dots,\ket{n} \}$ (not necessarily<br>orthonormal)         | $\{ \ket{e_{1}},\dots,\ket{e_{n}} \}$ (orthonormal)                                                                  |
| new basis                      | $\{ \ket{v_{1}},\dots,\ket{v_{n}} \}$ (not necessarily<br>orthonormal) | $\{ \ket{v_{1}},\dots,\ket{v_{n}} \}$ (orthonormal)                                                                  |
| eigenvector<br>equation<br>    | $\hat{A}\ket{v_{i}}=\lambda_{i}\ket{v_{i}}.$                           | $\hat{H}\ket{v_{i}}=\lambda_{i}\ket{v_{i}}.$                                                                         |
| change of <br>basis matrix<br> | $\ket{v_{i}}=\sum_{j=1}^{n}R_{ji}\ket{j}.$                             | $\underbrace{ \ket{v_{i}} }_{ \text{ON basis} }=\sum_{j=1}^{n}U_{ji}\underbrace{ \ket{e_{j}} }_{ \text{ON basis} }.$ |

^a92892

We already know that the [[Change of Basis#^eb87a9|change of basis matrix between orthonormal bases is unitary]], so for the Hermitian case the matrix for the change of basis $R=U$, we know that $U^{\dagger}=U^{-1}$, and so is unitary.

From our [[#Diagonalizable Operators|discussion of diagonalizable operators]], we know
$$
U^{-1}HU=U^{\dagger}HU=D=[\lambda_{i}\delta_{ij}],
$$
where $\lambda_{1},\dots,\lambda_{n}$ are the (not necessarily distinct) eigenvalues of $H$. 

#### Simultaneous Diagonalization of Two Hermitian Operators

> [!example] Simultaneous Eigenvectors of Hermitian Operators
> Let $\hat{H}_{1}$ and $\hat{H}_{2}$ be two Hermitian operators. Then exists an orthonormal basis $\{ \ket{v_{1}},\dots,\ket{v_{n}} \}$ of simultaneous eigenvectors of $\hat{H}_{1}$ and $\hat{H}_{2}$, such that
> $$
> \begin{align}
> \hat{H}_{1}\ket{v_{i}}  & =\lambda_{i}\ket{v_{i}} , \\
> \hat{H}_{2}\ket{v_{i}} &  = \mu_{i}\ket{v_{i}} ,
> \end{align}
> $$
> *if and only if* $[\hat{H}_{1},\hat{H}_{2}]=0$ (i.e., $\hat{H}_{1}$ and $\hat{H}_{2}$ commute).

^370420

> [!NOTE] Proof of Simultaneous Eigenvectors of Hermitian Operators
> The proof is not given here. See, for example, Matthews and Walker, *Mathematical Methods of Physics*, 2e, p.159.

Note that by the [[#^7d228b|Spectral Theorem for Hermitian Operators]], we already know that there exists an orthonormal basis $\{ \ket{v_{1}},\dots,\ket{v_{n}} \}$ of $\hat{H}_{1}$, with $\hat{H}_{1}\ket{v_{i}}=\lambda_{i}\ket{v_{i}}$, and an orthonormal basis $\{ \ket{w_{1}},\dots,\ket{w_{n}} \}$ of $\hat{H}_{2}$ with $\hat{H}_{2}\ket{w_{i}}=\mu_{i}\ket{w_{i}}$, but the two bases are in general, different. That is, $\hat{H}_{2}\ket{v_{i}}\neq\lambda_{i}\ket{v_{i}}$. 
In general, the eigenvectors $\{ \ket{v_{i}} \}$ of one Hermitian operator $\hat{H}_{1}$ will not be the same as the eigenvectors $\{ \ket{w_{i}} \}$ of another Hermitian operator $\hat{H}_{2}$. 

By our [[Eigenvectors and Eigenvalues#^2a6d0f|previous theorem on Hermitian diagonalization]], we can reformulate [[#^370420|this theorem]]. 

> [!example] Simultaneous Diagonalization of Hermitian Matrices
> The Hermitian matrices $H_{1}$ and $H_{2}$ which represent two Hermitian operators $\hat{H}_{1}$ and $\hat{H}_{2}$ in some orthonormal basis $\{ \ket{e_{1}},\dots,\ket{e_{n}} \}$ can be brought into diagonal form by the *same* unitary matrix $U$
> $$
> \begin{align}
> U^{\dagger}H_{1}U & = D_{1}=\lambda_{i}\delta_{ij}, \\
> U^{\dagger}H_{2}U & = D_{2} = \mu_{i}\delta_{ij},
> \end{align}
> $$
> *if and only if* they commute ($[H_{1},H_{2}]=0$). 

^e76aec

I prove this in this document, see [[Physics 100A Week 7 Problem Set#^0cf2a0]].

Note that we know Hermitian matrices can be brought into diagonal form by a unitary matrix, but the result is more general than that. 
There is a simple condition which determines when a matrix $A$ is diagonalizable by a unitary matrix, which we now discuss.

> [!tip] Hermitian Decomposition of a Linear Operator
> Any linear operator $\hat{A}$ can be [[Linear Operators#^6de676|written in the form]] $\hat{A}=\hat{H}_{1}+i\hat{H}_{2}$, where $\hat{H}_{1}$ and $\hat{H}_{2}$ are Hermitian operators (note that $i\hat{H}$ is anti-Hermitian if $\hat{H}$ is Hermitian). 
> We can rewrite this in the statements
> $$
\begin{align}
\hat{H}_{1} & = \frac{1}{2}(\hat{A}^{\dagger}+\hat{A}), \\
\hat{H}_{2} & = \frac{i}{2}(\hat{A}^{\dagger}-\hat{A}),
\end{align}$$ 
>which allow us to compute the Hermitian decomposition of $\hat{A}$. 

^694fbf

### Spectral Theorem for Normal Operators


> [!example] Normal Operators
> A [[Linear Operators#^9dd697|linear operator]] $\hat{A}$ is called ***normal*** if it [[Linear Operators#Commutator|commutes]] with its adjoint. That is, $[\hat{A},\hat{A}^{\dagger}]=0$.  

^814df6

> [!example] Spectral Theorem for Normal Operators
> Let ${} \hat{A}:V\to V {}$ be a [[#^814df6|normal operator]] of an [[Inner Products#^3cf67b|inner product space]]. Then there exists an orthonormal [[Linear Independence & Basis#^12b0fb|basis]] of [[#^56e47a|eigenvectors]] of $\hat{A}$,
> $$
> \begin{align}
> \hat{A}\ket{v_{i}}  & =\lambda_{i}\ket{v_{i}} , \\
> \braket{ v_{i} | v_{j} }  & = \delta_{ij}, \\
\{ \ket{v_{i}}  \} & \text{ forms a basis of } V.
> \end{align}$$
^562500


> [!note] Proof of Spectral Theorem for Normal Operators
> 
> If $\hat{A}$ has an orthonormal basis of eigenvectors $\{ \ket{v_{i}} \}$, then we know the [[Orthonormality#^aef684|completeness relation]] applies.
> $$
> \hat{I}=\sum_{i=1}^{n} \ket{v_{i}} \bra{v_{i}} .
> $$
> We can find the [[#^529753|spectral decomposition]] of $\hat{A}$ as follows:
> $$
> \hat{A}=\hat{I}\hat{A}\hat{I}=\sum_{i=1}^{n} \ket{v_{i}} \lambda_{i} \bra{v_{i}}.\tag{1}
> $$
> Taking the adjoint of this equation, we have
> $$
> \hat{A}^{\dagger}=\sum_{i=1}^{n} \ket{v_{i}} \lambda_{i}^{*}\bra{v_{i}}.\tag{2} 
> $$
> Combining Equations 1 and 2, it follows that
> $$
> \hat{A}\hat{A}^{\dagger}=\hat{A}^{\dagger}\hat{A}.
> $$
> So $\hat{A}$ is normal. In other words,
> 
> > [!tip] Condition for a Normal Operator
> > If a linear operator $\hat{A}$ has an orthonormal basis of eigenvectors, then $\hat{A}$ is normal. The converse is likewise true, and follows from the theorem for [[#^370420|simultaneous diagonalization of Hermitian operators]].
> 
> We proceed to show the veracity of the converse. If $\hat{A}$ is normal, then $\hat{A}\hat{A}^{\dagger}=\hat{A}^{\dagger}\hat{A}$. We can then decompose $\hat{A}$ into a [[#^694fbf|linear combination of Hermitian operators]]. Using these definitions of $\hat{H}_{1}$ and $\hat{H}_{2}$, we can calculate:
> $$
> \begin{align}
> \hat{H}_{1}\hat{H}_{2} & = \frac{i}{4}(\hat{A}^{\dagger}+\hat{A})(\hat{A}^{\dagger}-\hat{A}), \\
>  & = \frac{i}{4}\left[ (\hat{A}^{\dagger})^{2}-(\hat{A})^{2}+\underbrace{ \hat{A}\hat{A}^{\dagger}-\hat{A}^{\dagger}\hat{A} }_{ 0\text{ ($\hat{A}$ is normal)} }  \right] ,\\
>  & = \frac{i}{4}\left[ (\hat{A}^{\dagger})^{2}-(\hat{A})^{2} \right]. \\
>  \hat{H}_{2}\hat{H}_{1} & = \frac{i}{4}(\hat{A}^{\dagger}-\hat{A})(\hat{A}^{\dagger}+\hat{A}),\\
>  & = \frac{i}{4}\left[ (\hat{A}^{\dagger})^{2}-(\hat{A})^{2} \right] .
> \end{align}
> $$
> Hence $\hat{H}_{1}\hat{H}_{2}=\hat{H}_{2}\hat{H}_{1}$, or $[\hat{H}_{1},\hat{H}_{2}]=0$. By the [[#^370420|theorem for simultaneous diagonalization of Hermitian operators]], we then know that there exists a common orthonormal basis of eigenvectors $\{ \ket{v_{i}} \}$ of $\hat{H}_{1}$ and $\hat{H}_{2}$. 
> $$
> \begin{align}
> \hat{H}_{1}\ket{v_{i}}  & =\lambda_{i}\ket{v_{i}}, \\
>  \hat{H}_{2}\ket{v_{i}}  & = \mu_{i}\ket{v_{i}} .
> \end{align}
> $$
> Recalling that $\hat{A}=\hat{H}_{1}+i\hat{H}_{2}$, we find that
> $$
> \begin{align}
> \hat{A}\ket{v_{i}}  & = (\hat{H}_{1}+\hat{H}_{2})\ket{v_{i}},  \\
>  & =\hat{H}_{1}\ket{v_{i}} +\hat{H}_{2}\ket{v_{i}} , \\
>  & = (\lambda_{i}+i\mu_{i})\ket{v_{i}} .
> \end{align}
> $$
> So $\{ \ket{v_{i}} \}$ is also a set of eigenvectors of $\hat{A}$, and therefore it is an orthonormal basis of the vector space $V$. 


### Spectral Theorem for Unitary Operators

> [!example] Spectral Theorem for Unitary Operators
> Let ${} \hat{U}:V\to V {}$ be a [[Linear Operators#^56f9c5|unitary operator]]. Then there exists an orthonormal [[Linear Independence & Basis#^12b0fb|basis]] of $V$ consisting of [[#^56e47a|eigenvectors]] of $\hat{U}$.
> $$
> \begin{align}
> \hat{U}\ket{v_{i}}  & = \lambda_{i}\ket{v_{i}} , \\
> \braket{ v_{i} | v_{j} }  & = \delta_{ij}, \\
> \{ \ket{v_{i}}  \} & \text{ forms a basis of }V . 
> \end{align} $$

^574b61


> [!note] Proof of Spectral Theorem for Unitary Operators
> Use the [[#^562500|Spectral Theorem for Normal Operators]], and note that 
> $$
> [\hat{U},\hat{U}^{\dagger}]=\underbrace{ \hat{U}\hat{U}^{\dagger} }_{ \hat{I} } -\underbrace{ \hat{U}^{\dagger}\hat{U} }_{ \hat{I} } =0.
> $$
> So unitary operators are also normal, and therefore have an orthonormal basis of eigenvectors.

### Green's Functions

Suppose $\hat{H}$ is a Hermitian operator with eigenfunctions $\{ \ket{v_{i}} \}$ that form an orthonormal basis of a vector space $V$.
$$
\hat{H}\ket{v_{j}} = \lambda_{j}\ket{v_{j}} .
$$
Consider the following equation,
$$
\hat{H}\ket{a} -\gamma \ket{a} =\ket{w} ,\tag{1}
$$
which we want to solve for $\ket{a}$, for $\gamma \in\mathbb{C}$, $\ket{w}\in V$. Because the eigenvectors form a basis, we can write the solution as
$$
\ket{a} =\sum_{j=1}^{n} \alpha_{j}\ket{v_{j}} .\tag{2}
$$
Then Equation 1 becomes
$$
\sum_{j=1}^{n} \left( \alpha_{j}\lambda_{j}\ket{v_{j}} -\alpha_{j}\gamma \right) \ket{v_{j}} = \ket{w} .
$$
Taking the inner product with $\ket{v_{i}}$ and noting that $\braket{ v_{i} | v_{j} }=\delta_{ij}$, we find
$$
\begin{align}
\alpha_{i}(\lambda_{i}-\gamma) & =\braket{ v_{i} | w } , \\
\alpha_{i} & = \frac{\braket{ v_{i} | w }}{\lambda_{i}-\gamma}.
\end{align}
$$
Substituting this back into Equation 2, we have
$$
\ket{a} = \sum_{i=1}^{n} \frac{\braket{ v_{i} | w }}{\lambda_{i}-\gamma}\ket{v_{i}}.
$$
We can express this as 
$$
\ket{a}=\hat{G}\ket{w} \tag{3}, 
$$
where 
$$
\hat{G}=\sum_{i=1}^{n} \frac{\ket{v_{i}}\bra{v_{i}}}{\lambda_{i}-\gamma}.\tag{4}
$$
The operator $\hat{G}$ is called ***Green's function***. 

> [!tip] Key Point
> Note that $\hat{G}$ is independent of the "nonhomogenous"/"driving" part of the equation, $\ket{w}$. It depends only on the operator $\hat{H}$ and $\gamma$, things that act on the solution we're trying to find.

> [!example] Green's Function
> Let ${} \hat{H}:V\to V {}$ be a linear operator with eigenvectors $\{ \ket{v_{i}} \}$, and let $\ket{a},\ket{g}\in V$ and $\gamma \in\mathbb{C}$. Then for an equation of the form
> $$
> \hat{H}\ket{a} -\gamma \ket{a} =\ket{g} ,$$
> the solution takes the form
> $$
> \begin{align}
> \ket{a}  & =\hat{G}\ket{g} , \\
> \hat{G} & = \sum_{n=i}^{\infty} \frac{\ket{v_{i}} \bra{v_{i}} }{\lambda_{i}-\gamma}.
> \end{align}$$
> The operator $\hat{G}$ is called ***Green's function***. 

^09b206

