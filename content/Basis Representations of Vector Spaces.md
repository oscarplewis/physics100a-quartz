---
tags:
  - Physics100A
  - 100ANotes
---
### Coordinate Vectors
Let $V$ be a complex linear vector space with a basis $\{ \ket{i} \}=\{ \ket{1},\ket{2},\dots,\ket{n} \}$. Then any vector $\ket{a}\in V$ can be written as a linear combination of the basis vectors (by definition of basis):
$$
\ket{a} =\sum_{i=1}^{n} \alpha_{i}\ket{i} .
$$
We say that the components $\{ \alpha_{i} \}$ represent the vector $\ket{a}$ in the basis $\{ \ket{i} \}$. We often arrange the components in the form of a column vector of complex numbers:
$$
\vec{\alpha}=\begin{pmatrix}
\alpha_{1} \\
\alpha_{2} \\
\vdots \\
\alpha_{n}
\end{pmatrix}.
$$

> [!tip] Varying Bases
> If we use a different basis $\{ \ket{i'} \}$ of the same space $V$, then the same vector $\ket{a}$ is represented by a different set of components $\{ \alpha_{i}' \}$. $$
\ket{a} = \sum_{i=1}^{n} \alpha_{i}\ket{i'} = \sum_{i=1}^{n} \alpha_{i}\ket{i} .$$

^cc6ce0

### Matrix Representations of Linear Operators
For a linear vector space $V$ with a basis $\{ \ket{i} \}$. Let $\hat{A}$ be a linear operator
$$
V \xrightarrow{ \hat{A} }V.
$$
Consider the action of $\hat{A}$ on the basis vectors: $\hat{A}\ket{1},\dots,\hat{A}\ket{n}$. 
These are all elements of $V$, so each one can be expanded in the basis:
$$
\begin{align}
\hat{A}\ket{1}  & = A_{11}\ket{1}+A_{21}\ket{2}+\dots+A_{n1}\ket{n}, \\
\hat{A}\ket{2}  & = A_{12}\ket{1}+A_{22}\ket{2}+\dots+A_{n2}\ket{n}, \\
& \vdots \\
\hat{A}\ket{n}  & = A_{1n}\ket{1} + A_{2n}\ket{2} +\dots+A_{nn}\ket{n}.    
\end{align}
$$
This can be written compactly as
$$
\hat{A}\ket{i} =\sum_{j=1}^{n} A_{ji}\ket{j} ,\text{ for } j=1,2,\dots,n.
$$
(Note the indices are swapped from the system of equations before.)

The $n^{2}$ complex numbers $A_{ij}$ can be written in the form of an $n\times n$ matrix $A$:
$$
A=\begin{pmatrix}
A_{11} & A_{12} & \dots & A_{1n} \\
A_{21} & A_{22} & \dots & A_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
A_{n1} & A_{n2} & \dots & A_{nn}
\end{pmatrix}= \underbrace{ (A_{ij}) }_{ \begin{align}
i  & \text{ is row}  \\
j  & \text{ is column}
\end{align}  } .
$$

> [!tip] A Note on Notation
> $\hat{A}$ notates the linear operator, whereas $A$ denotes the matrix representation of $\hat{A}$ in a basis $\{ \ket{i} \}$. 


> [!warning] Column and Row Meanings of Matrix Representations
> The columns of a matrix representation of linear operators are $\hat{A}\ket{1},\hat{A}\ket{2},\dots,\hat{A}\ket{n}$, proceeding left to right. Similarly the rows of the matrix are $\ket{1},\ket{2},\dots,\ket{n}$, proceeding top to bottom. To find the matrix representation of a basis vector, we therefore sum down the respective column using the matrix components as coefficients of the row corresponding basis vectors.

We can also represent the equation $\hat{A}\ket{a}=\ket{b}$ in a basis as
$$
\begin{align}
\ket{a}  & = \sum_{j=1}^{n} \alpha_{j}\ket{j} , \\
\hat{A}\ket{a}  & = \hat{A}\left( \sum_{j=1}^{n} \alpha_{j}\ket{j}  \right), \\
 & = \sum_{j=1}^{n} \alpha_{j}\hat{A}\ket{j} , \\
 & = \sum_{j=1}^{n} \alpha_{j} \left( \sum_{i=1}^{n} A_{ij}\ket{i}  \right), \\
 & = \sum_{i=1}^{n} \underbrace{ \left( \sum_{j=1}^{n} A_{ij} \right) }_{ \beta_{i} }\ket{i}, \\
 & = \sum_{i=1}^{n} \beta_{i}\ket{i} =\ket{b}. 
\end{align}
$$
So we can write the vector $\ket{b}$ in terms of a column vector of its components
$$
\begin{pmatrix}
\beta_{1} \\
\beta_{2} \\
\vdots \\
\beta_{n}
\end{pmatrix} = \begin{pmatrix}
A_{11} & A_{12} & \dots & A_{1n} \\
A_{21} & A_{22} & \dots & A_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
A_{n1} & A_{n2} & \dots & A_{nn}
\end{pmatrix} \begin{pmatrix}
\alpha_{1} \\
\alpha_{2} \\
\vdots \\
\alpha_{n}
\end{pmatrix},
$$
or,
$$
\vec{\beta}=A\vec{\alpha}.
$$

> [!warning] Insert how to find matrix representation of linear operator in a non orthonormal basis.


#### Product of Linear Operators
Let $\hat{A}$ and $\hat{B}$ be two linear operators mapping in the vector space $V$. Their product is $\hat{C}=\hat{A}\hat{B}$, and we can represent this as a matrix. At this point we introduce [[CCS Physics Series/Tensor Notation|Einstein index notation]], noting that in the expression $\alpha_{i}\ket{i}$ the index $i$ is still considered a dummy index and summation is still implied.
$$
\begin{align}
\hat{C}\ket{j} & = \hat{A}(\hat{B}\ket{j}), \\
 & = \hat{A}\left( B_{kj}\ket{k}  \right), \\
 & =  B_{kj}\hat{A}\ket{k}  \\
 & =  B_{kj}\left(  A_{ik}\ket{i}  \right), \\
 & = \underbrace{ \left( A_{ik}B_{kj} \right) }_{ C_{ij} }\ket{i} , \\
 & =  C_{ij}\ket{i} .
\end{align}
$$
In matrix form:
$$
C=AB.
$$
In other words,

> [!tip] Matrix Representation of Operator Products
> The product of two operators is represented in a given basis by the matrix product of the corresponding matrices.
#### Operations on Matrices

> [!example] Transpose of a Matrix
> If $A$ is an $n\times m$ matrix (meaning $n$ rows and $m$ columns) with matrix elements $A_{ij}$, then the ***transposition*** of the matrix $A$ is $A^{T}$, the $m\times n$ matrix ($m$ rows, $n$ columns) with matrix elements
>$$
(A^{T})_{ij}=A_{ji},$$
>where the rows and columns are exchanged. 

The transposition of a matrix satisfies the following properties:
1. $(A^{T})^{T}=A$.
2. $(A+B)^{T}=A^{T}+B^{T}$.
3. $(ABC\dots)^{T}=\dots C^{T}B^{T}A^{T}$. 


> [!example] Adjoint of a Matrix
> If $A$ is an $n\times m$ matrix with matrix elements $A_{ij}$, then the ***adjoint*** of the matrix $A$ is $A^{\dagger}$, the $m\times n$ matrix with matrix elements 
> $$
(A^{\dagger})_{ij}=A_{ji}^{*}=(A^{T})^{*}_{ij}. $$
>The adjoint of a matrix is therefore the conjugate transpose. 

^a655b3



#### Special Matrices

> [!example] The Identity Matrix
> The ***unit/identity operator*** $\hat{I}$ is represented in any basis by the identity matrix.
> $$
> I=\begin{pmatrix}
> 1 & 0 & \dots & 0 \\
> 0 & 1 & \dots & 0 \\
> \vdots & \vdots & \ddots & 0 \\
> 0 & 0 & 0 & 1
> \end{pmatrix}=\delta_{ij},$$
> which for any square matrix $A$ satisfies the relation $IA=AI=A$. 

^85a5f8


> [!example] Diagonal Matrices
> A ***diagonal matrix*** is given by
> $$
> D=\begin{pmatrix}
> d_{1} & 0 & \dots & 0 \\
> 0 & d_{2} & \dots & 0 \\
> \vdots & \vdots & \ddots & 0 \\
> 0 & 0 & 0 & d_{n}
> \end{pmatrix}=d_{i}\delta_{ij}.$$

^f2a33e



> [!example] Unitary Matrices
> A ***unitary matrix*** $U$ is an $n\times n$ matrix which satisfies the following statement: 
> $$
> U^{-1}=U^{\dagger}.$$
> This means that $U^{\dagger}U=UU^{\dagger}=I$. 

^3c28cf



> [!tip] Rotations
> Rotations are a common example of a unitary matrix. Similarly, all unitary matrices have lots of nice properties.

> [!example] Hermitian Matrices
> A ***hermitian matrix*** $A$ is an $n\times n$ matrix which satisfies the following statement:
> $$
> A^{\dagger}=A.
> $$
> In terms of matrix elements, this implies that
> $$
> (A^{\dagger})_{ij}:=A_{ji}^{*}=A_{ij}.
> $$
> In particular, this means that $A^{*}_{ii}=A_{ii}$ (no sum) and so the diagonal elements of the matrix must be real.

^e3315e

> [!tip] Hermitian matrices also have nice properties
> I fully don't know why this is included in the class notes, as no further properties are mentioned.


> [!tip] Relation to Linear Operators
> Recall that $n\times n$ matrices are special cases of linear operators, and so unitary and hermitian matrices correspond to [[Linear Operators#^56f9c5|unitary]] and [[Linear Operators#^63db04|hermitian operators]]. The converse is [[Change of Basis#^3ddbac|not usually true]] for non-orthonormal bases.



#### Diagonalization of Hermitian Matrices
A Hermitian matrix is diagonal in its eigenbasis with eigenvalues on the diagonal. This means that if $\ket{i},\ket{j}$ are the eigenvectors of a Hermitian matrix $H$:
$$
\braket{ i | H | j } = \braket{ i | U^{\dagger}HU | j } = \text{diagonal matrix,}
$$
where $U$ is a unitary matrix built out of the eigenvectors of $H$. 

> [!tip] Diagonalization of Hermitian Matrices
> For every Hermitian matrix we can find a unitary matrix built out of its eigenvectors such that $U^{\dagger}HU$ is diagonal.

^27d513

### Orthonormal Bases
See first [[Orthonormality]]. 
#### Bra and Ket Vectors
Let $V$ be a complex linear vector space with an inner product. Let $\{ \ket{e_{i}} \}$ be an orthonormal basis of $V$ (that is, $\braket{ e_{i} | e_{j} }=\delta_{ij}$). 
Then any $\ket{a}\in V$ can be written
$$
\ket{a} = \alpha_{m}\ket{e_{m}} ,\text{ (summation implied) where }\alpha_{m}=\braket{ e_{m} | a } .
$$
Taking the adjoint of this vector, we have
$$
\begin{align}
\ket{a} ^{\dagger} & = (\alpha_{m}\ket{e_{m}}) ^{\dagger}, \\
\bra{a}  & = \alpha_{m}^{*} \bra{e_{m}} . 
\end{align}
$$
This tells us $\{ \bra{e_{i}} \}$ is a basis of the dual vector space $V^{*}$ of bra vectors $\bra{a}$. Revisiting the representation of bra and ket vectors in an orthonormal basis, let $\ket{a} = \alpha_{j}\ket{e_{j}}$ and $\ket{b} = \beta_{i}\ket{e_{i}}$. The inner product of these are rather easy to compute thanks to the orthonormal basis.
$$
\begin{align}
\braket{ b | a } &  = (\beta_{i}^{*}\bra{e_{i}} )(\alpha_{j}\ket{e_{j}} ), \\
 & = \beta_{i}^{*}\alpha_{j}\braket{ e_{i} | e_{j} } , \\
 & = \beta_{i}^{*}\alpha_{j}\delta_{ij}, \\
 & = \beta^{*}_{i}\alpha_{i}, \\
 & = \begin{pmatrix}
\beta_{1}^{*} & \dots & \beta_{n}^{*}
\end{pmatrix} \begin{pmatrix}
\alpha_{1} \\
\vdots \\
\alpha_{n}
\end{pmatrix}.
\end{align}
$$
> [!tip] Dot Product Equivalence
> Note the equivalence between the inner product and the dot product of the component vectors in the orthonormal basis. This is specific to the basis being orthonormal, which gives us $\braket{ e_{i} | e_{j} }=\delta_{ij}$ in the sum. Without an orthonormal basis this equivalence wouldn't be present.

For any basis, whether orthonormal or not, we arrange the components $\alpha_{i}$ representing $\ket{a}$ into a column vector.
$$
\vec{\alpha}=\begin{pmatrix}
\alpha_{1} \\
\vdots \\
\alpha_{n}
\end{pmatrix}.
$$
We can arrange the components $\alpha_{i}^{*}$ which represent the corresponding bra vector $\bra{a}$.
$$
\vec{\alpha}^{\dagger}=\begin{pmatrix}
\alpha_{1}^{*} & \dots & \alpha_{n}^{*}
\end{pmatrix}.
$$
If we view $\vec{\alpha}$ as an $n\times 1$ matrix, then $\vec{\alpha}^{\dagger}$ is the [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^a655b3|adjoint]] of this matrix, and is a $1\times n$ matrix (a row vector).

#### Linear Operators
Since $\{ \ket{e_{i}} \}$ is a basis of $V$, every general property we derived before applies here as well. Particularly, the matrix $A$ representing a linear operator $\hat{A}$ in this basis is obtained from the action of $\hat{A}$ on elements of the basis. 
$$
\hat{A}\ket{e_{j}} = A_{ij}\ket{e_{i}}. 
$$
The fact that the basis $\{ \ket{e_{i}} \}$ is orthonormal makes it easy to find the matrix elements $A_{ij}$. Taking the inner product of this $\ket{e_{k}}$:
$$
\braket{ e_{k} | \hat{A} | e_{j} } = \bra{e_{k}} (A_{ij}\ket{e_{i}} )=A_{ij}\braket{ e_{k} | e_{i} } = A_{kj}.
$$
So $A_{ij}=\braket{ e_{i}|\hat{A} | e_{j} }$ for all $i,j=1,2,\dots,n$. 

We can also derive this same result from the [[Orthonormality#^aef684|completeness relation]], which is always available when we consider an orthonormal basis of a linear vector space. We can write
$$
\begin{align}
\hat{A}\ket{e_{j}}  & = \hat{I}\hat{A}\ket{e_{j}} , \\
 & = (\ket{e_{i}} \braket{ e_{i}} )\hat{A}\ket{e_{j}} \tag{summation implied}, \\
 & = \ket{e_{i}} \braket{ e_{i}  | \hat{A}  | e_{j} } , \\
 & = A_{ij}\ket{e_{i}} .\tag{definition of matrix element $A_{ij}$}
\end{align}
$$
This implies that $A_{ij}=\braket{ e_{i} | \hat{A} | e_{j} }$. 

> [!tip] Finding the Matrix of a Linear Operator in an Orthonormal Basis
> In order to obtain the matrix elements $A_{ij}$ of the matrix $A$ which represents the linear operator $\hat{A}$ in the orthonormal basis $\{ \ket{e_{i}} \}$, we only need to act with $\hat{A}$ on $\ket{e_{j}}$ and take the inner product of that with $\ket{e_{i}}$. In the more general case, $\hat{A}\ket{e_{j}}$ need not be expanded in the basis $\{ \ket{e_{i}} \}$ to get the matrix elements. 

^d4361a

#### Matrices
Let $\{ \ket{e_{i}} \}$ be an orthonormal basis of the vector space $V$ with an inner product. In this orthonormal basis, both operators $\hat{A}$ and $\hat{A}^{\dagger}$ are represented by matrices. Denote these by $A$ and $B$, respectively. 
$$
\begin{align}
A & = (A_{ij}),  A_{ij}=\braket{ e_{i} | \hat{A} | e_{j} } . \\
B & = (B_{ij}),  B_{ij}=\braket{ e_{i} | \hat{A}^{\dagger} | e_{j} } .
\end{align}
$$
Note that $B_{ij}=\braket{ e_{i} | \hat{A}^{\dagger} | e_{j} }=\braket{ e_{j} | \hat{A} | e_{i} }^{*}=A_{ji}^{*}$ (by the [[Linear Operators#^9a9d53|adjoint property]]). So we can see that the matrix $B$ is the adjoint of $A$, just as the the operator $\hat{A}^{\dagger}$ is the adjoint of $\hat{A}$.

> [!tip] Non-orthonormal Bases
> When we replace $\{ \ket{e_{i}} \}$ with a basis which isn't orthonormal, we can still represent both $\hat{A}$ and $\hat{A}^{\dagger}$ by matrices. However, in this case the relationship between matrices isn't so simple.

If $\hat{A}$ is a [[Linear Operators#^63db04|Hermitian operator]] ($\hat{A}=\hat{A}^{\dagger}$), then it's matrix representation in an orthonormal basis is also [[#^e3315e|Hermitian]]. That is, $B_{ij}=A^{*}_{ji}=A_{ij}$. 
Similarly, if $\hat{A}$ is a [[Linear Operators#^56f9c5|unitary operator]] ($\hat{A}^{-1}=\hat{A}^{\dagger}$), then it's matrix representation in an orthonormal basis in also [[#^3c28cf|unitary]]. That is, $A^{-1}_{ij}=A^{*}_{ji}$.
