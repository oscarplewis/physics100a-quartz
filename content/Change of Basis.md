---
tags:
  - Physics100A
  - 100ANotes
---
---
### General Properties of Change of Basis

Let $V$ be a linear vector space of $n$-th dimension (an inner product is not necessary, as there is no notion of basis orthonormality at this point). We will consider two bases of $V$: the "old basis", $\{ \ket{i} \}$, and the "new basis", $\{ \ket{i'} \}$. 

Any ket $\ket{i'}$ of the new basis can be expressed in terms of the old basis. This defines an $n\times n$ matrix $R$:
$$
\ket{i'} = \sum_{j=1}^{n} R_{ji}\ket{j} .
$$
Explicitly in terms of the elements:
$$
\begin{align}
\ket{1'}  & = R_{11}\ket{1}+R_{21}\ket{2}+\dots+R_{n1}\ket{n}, \\
\ket{2'}  & = R_{12}\ket{1} +R_{22}\ket{2}+\dots+R_{n2}\ket{n}, \\
 & \vdots \\
\ket{n'}  & = R_{1n}\ket{1} +R_{2n}\ket{2} +\dots+R_{nn}\ket{n} .   
\end{align}
$$
The $n\times n$ matrix $R$ with matrix elements $R_{ij}$ ($i$ is row, $j$ is column) is the matrix representation of the linear operator $\hat{R}$ defined by
$$
\hat{R}\ket{i} =\ket{i'} .
$$
(That is, $R$ is the matrix representation of $\hat{R}$ in the old basis $\{ \ket{i} \}$.) 


> [!tip] $R$ In the Old Basis
> This is because $\ket{1}=\begin{pmatrix}1\\0\\ \vdots\end{pmatrix}$  in the old basis, and $\hat{R}\ket{1},\hat{R}\ket{2},\dots,\hat{R}\ket{n}$ is 
> $$
R=\begin{pmatrix}
R_{11} & R_{12} & \dots R_{1n} \\
R_{21} & R_{22} & \dots & R_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
R_{n1} & R_{n2} & \dots & R_{nn}
\end{pmatrix}.$$
>(Here each column is $\hat{R}\ket{j}$, and each row $\ket{i}$.) Therefore in the old basis:
> $$
\hat{R}\ket{1} \leftrightarrow \begin{pmatrix}
R_{11} & R_{12} & \dots  & R_{1n} \\
R_{21} & R_{22} & \dots & R_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
R_{n1} & R_{n2} & \dots & R_{nn}
\end{pmatrix}\begin{pmatrix}
1 \\
0 \\
\vdots \\
0
\end{pmatrix}=\begin{pmatrix}
R_{11} \\
R_{21} \\
\vdots \\
R_{n1}
\end{pmatrix}.$$
>This coordinate vector can be written as $R_{11}\ket{1}+R_{12}\ket{2}+\dots+R_{n1}\ket{n}$ (in the old basis), which is $\ket{1'}$ by definition.
>Therefore, $\ket{i'}=\hat{R}\ket{i}$ is the general relationship between bases, and $\hat{R}$ is called the ***change of basis operator***.

^9af2b8

Since these are both bases, $\hat{R}$ must be invertible.
$$
\ket{i} =\hat{R}^{-1}\ket{i'} .
$$
We can exchange the roles of each basis in the transformation (from the new basis to the old basis, for instance) and the transformation must still hold. That is, $\hat{R}$ is a bijection (both surjective/onto and injective/one-to-one), because there are $n$ total basis vectors in both bases, and each basis vector $\ket{i}$ in the old basis must map to exactly one basis vector $\ket{i'}$ in the new basis. 

### Representing Vectors in Different Bases

Consider any vector $\ket{a}\in V$. We can represent this vector in either of our two bases:
$$
\ket{a} =\sum_{i=1}^{n} \alpha_{i}\ket{i} =\sum_{i=1}^{n} \alpha_{i}'\ket{i'} .
$$
We want to find the relationship between these components. Consider:
$$
\begin{align}
\ket{a}  & = \sum_{i=1}^{n} \alpha_{i}'\ket{i'} =\sum_{i=1}^{n} \alpha_{i}'\left( \sum_{j=1}^{n} R_{ji}\ket{j}  \right), \\
& = \sum_{j=1}^{n} \left( \sum_{i=1}^{n} R_{ji}\alpha_{i}' \right)\ket{j}\tag{reordering sums} , \\
 \sum_{i=1}^{n} \alpha_{i}\ket{i} & = \sum_{i=1}^{n} \left( \sum_{j=1}^{n} R_{ij}\alpha_{j}' \right)\ket{i}\tag{exchanging indices} .
\end{align}
$$
This tells us that
$$
\sum_{i=1}^{n} \left[ \left( \sum_{j=1}^{n} R_{ij}\alpha_{j}' \right)-\alpha_{i} \right] \ket{i}=0. 
$$
We know that the basis vectors $\{ \ket{i} \}$ are [[Linear Independence & Basis#^12b0fb|linearly independent by definition]]. So, by the [[Linear Independence & Basis#^4d61b3|definition of linear independence]], we can see that each coefficient of $\ket{i}$ is individually equal to zero.
$$
\begin{align}
\left( \sum_{j=1}^{n} R_{ij}\alpha_{j}' \right)-\alpha_{i} & =0, \\
\alpha_{i} & = \sum_{j=1}^{n} R_{ij}\alpha_{j}'.
\end{align}
$$
We can write this more succinctly as
$$
\vec{\alpha}=R\vec{\alpha}',
$$
for $\vec{\alpha}$ being the column vector in the old basis, $R$ being the $n\times n$ matrix representation of the change of basis operator (hereafter the change of basis matrix), and $\vec{\alpha}'$ being the column vector in the new basis. Equivalently:
$$
\vec{\alpha}'=R^{-1}\vec{\alpha}.
$$

^3b5ec6

We previously established that $\hat{R}^{-1}$ exists, so therefore its matrix representation $R^{-1}$ likewise exists.

> [!warning] Contradictory Formulas?
> This formula is to transform the *coordinates* of *one* vector between two different bases. This is in contrast to transforming the old basis vectors to the new basis vectors, both represented as coordinate vectors in *the same basis*. The same matrix and the same inverse matrix is used for both, but the equations are swapped because the usages are different.

### Representing Linear Operators in Different Bases
Let $\hat{A}:V\to V$ be a linear operator. Consider vectors $\ket{a},\ket{b}\in V$, with
$$
\ket{b} =\hat{A}\ket{a} .
$$
In the old basis,
$$
\begin{align}
\ket{a}  & =\sum_{i=1}^{n} \alpha_{i}\ket{i} , \\
\ket{b}  & =\sum_{i=1}^{n} \beta_{i}\ket{i} .
\end{align}
$$
$A$ with components $A_{ij}$ is the matrix representation of $\hat{A}$ in the old basis. Then:
$$
\beta_{i}=\sum_{j=1}^{n} A_{ij}\alpha_{j},
$$
or,
$$
\vec{\beta}=A\vec{\alpha}.
$$
We can now write the same equation in the new basis.
$$
\begin{align}
\ket{a}  & =\sum_{i=1}^{n} \alpha_{i}'\ket{i'} , \\
\ket{b}  & =\sum_{i=1}^{n} \beta_{i}'\ket{i'} .
\end{align}
$$
$A'$ with components $A_{ij}'$ denotes the matrix representation of $\hat{A}$ in the new basis. Then:
$$
\beta_{i}'= \sum_{j=1}^{n} A'_{ij}\alpha_{j},
$$
or,
$$
\vec{\beta}'=A'\vec{\alpha}'.
$$
We can now use the relationship between the components of vectors in the old and new bases:
$$
\begin{align}
\vec{\alpha} & =R\vec{\alpha}', \\
\vec{\beta} & =R \vec{\beta}'.
\end{align}
$$
This means
$$
\beta=A\alpha\implies R\vec{\beta}'=AR\vec{\alpha}'.
$$
Multiplying both sides by $R^{-1}$,
$$
\vec{\beta}'=R^{-1}AR\vec{\alpha}'=A'\vec{\alpha}'.
$$
Therefore,
$$
A'=R^{-1}AR.
$$
To summarize:

> [!example] Change of Basis for a Linear Operator
> Given a [[Linear Operators#^9dd697|linear operator]] $\hat{A}$, with its matrix representation in the basis $\{ \ket{i} \}$ denoted $A$, with components $A_{ij}$, and its matrix representation in the basis $\{ \ket{i'} \}$ denoted $A'$, with components $A_{ij}'$, then these matrices obey the relation:
> $$
A'=R^{-1}AR,$$
>where $R$ is matrix representation of the change of basis operator that satisfies $\ket{i'}=\hat{R}\ket{i}$.

^82646b

> [!tip] Matrices Only
> Note that we only express a statement for matrices here, and do not have an equivalent expression in operator notation. This is because the operator $\hat{A}$ is abstract and is exactly the same regardless of basis: it is only the matrix representation of $\hat{A}$ in a given basis which changes when the basis is changed. That is:
> $$
\begin{align}
\hat{A}' & =\hat{A}, \\
A' & =R^{-1}AR.
\end{align}$$

### Example: Vectors
Consider a two-dimensional vector space $V$. Let $\{ \ket{1},\ket{2} \}$ be the "old basis" of $V$, and $\{ \ket{1'},\ket{2'} \}$ be the "new basis" of $V$, where
$$
\begin{align}
\ket{1'} &  =\ket{1} +\ket{2} , \\
\ket{2'}  & = \ket{1} +i\ket{2} .
\end{align} 
$$
We can write the new basis vectors as coordinate vectors in the old basis:
$$
\begin{align}
\ket{1'}  & \to \begin{pmatrix}
1 \\
1
\end{pmatrix}, \\
\ket{2'}  & \to \begin{pmatrix}
1 \\
i
\end{pmatrix}.
\end{align}
$$
The change of basis matrix $R$ must satisfy:
$$
\begin{align}
\begin{pmatrix}
1 \\
1
\end{pmatrix} & = R\begin{pmatrix}
1 \\
0
\end{pmatrix}, \\
\begin{pmatrix}
1 \\
i
\end{pmatrix} & = R\begin{pmatrix}
0 \\
1
\end{pmatrix}.
\end{align}
$$
(These are all coordinate vectors in the old basis). We see that
$$
R=\begin{pmatrix}
1  & 1\\
1 & i
\end{pmatrix}.
$$
This is the matrix representation in the old basis of the change of basis operator satisfying the equation $\ket{i'}=\hat{R}\ket{i}$. It's inverse is
$$
R^{-1}=\frac{1}{i-1}\begin{pmatrix}
i & -1 \\
-1 & 1
\end{pmatrix}.
$$
Given some vector $\ket{a}=\ket{1}-\ket{2}$, we can represent this in both bases.
$$
\begin{align}
\ket{a}  & = \ket{1} -\ket{2} \to\vec{\alpha}=\begin{pmatrix}
1 \\
-1
\end{pmatrix}.
\end{align}
$$
These are the components of $\ket{a}$ in the old basis $\{ \ket{i} \}$. We know from before that $\vec{\alpha}'=R^{-1}\vec{\alpha}$, so
$$
\begin{align}
\vec{\alpha}' & =\frac{1}{i-1}\begin{pmatrix}
i & -1 \\
-1 & 1
\end{pmatrix}\begin{pmatrix}
1 \\
-1
\end{pmatrix}, \\
 & = \frac{1}{i-1}\begin{pmatrix}
i+1 \\
-2
\end{pmatrix}.
\end{align}
$$
These are the components of $\ket{a}$ in the new basis $\{ \ket{i'} \}$. 
### Example: Linear Operators

We use the same bases as in the previous example.

Consider the linear operator $\hat{A}$ represented in the "old basis" by the matrix
$$
A=\begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix}.
$$
The columns are $\hat{A}\ket{1},\hat{A}\ket{2}$ and the rows are $\ket{1},\ket{2}$. This means that
$$
\begin{align}
\hat{A}\ket{1}  & = 0\ket{1} +i\ket{2}=i\ket{2}, \\
\hat{A}\ket{2}  & = i\ket{1} +0\ket{2} =i\ket{1} .  
\end{align}
$$
We know from before that $A'=R^{-1}AR$, where $R$ is the change of basis matrix. So:
$$
\begin{align}
A' & =\left( \frac{1}{2}+\frac{i}{2} \right)\begin{pmatrix}
-i & 1 \\
1 & -1
\end{pmatrix}\begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix}\begin{pmatrix}
1 & 1 \\
1 & i
\end{pmatrix}, \\
 & = \left( \frac{1}{2}+\frac{i}{2} \right)\begin{pmatrix}
-i & 1 \\
1 & -1
\end{pmatrix}\begin{pmatrix}
-i & 1 \\
i & i
\end{pmatrix}, \\
 & = \left( \frac{1}{2}+\frac{i}{2} \right)\begin{pmatrix}
i-1 & 0 \\
-2i & 1-i
\end{pmatrix}, \\
 & = \begin{pmatrix}
-1 & 0 \\
1-i & 1
\end{pmatrix}.
\end{align}
$$
This is the matrix representation of the operator $\hat{A}$ in the new basis.


### Orthonormal Bases
As always, one of the most interesting and useful cases is changes of [[Linear Independence & Basis#^12b0fb|orthonormal bases]]. See first [[Orthonormality]]. 

Let $V$ be an [[Inner Products#^3cf67b|inner product space]] with an "old basis" $\{ \ket{e_{i}} \}$ and a "new basis" $\{ \ket{e_{i}'} \}$. Both bases are orthonormal. 


> [!example] Unitary Change of Basis
> Let $V$ be an [[Inner Products#^3cf67b|inner product space]] with an orthonormal "old basis" $\{ \ket{e_{i}} \}$ and an orthonormal "new basis" $\{ \ket{e_{i}'} \}$. The change of basis matrix $R$ is [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^3c28cf|unitary]], and satisfies the relation
> $$
> \ket{e_{i}'}=\sum_{j=1}^{n} R_{ji}\ket{e_{j}}.$$
> Further, the linear operator $\hat{R}$ is likewise [[Linear Operators#^56f9c5|unitary]], and satisfies the relation
> $$
> \hat{R}\ket{e_{i}}=\ket{e_{i}'}.$$
> The proof is [[Change of Basis#^645477|here]] and [[Change of Basis#^46ce77|here]].
> 

^eb87a9

> [!note]+ Proof of a Unitary Change of Basis Matrix
> 
> First consider the inner product of $\ket{e_{i}'}$ with $\ket{e_{k}}$. 
> 
> $$
> \braket{ e_{k} | e_{i}' } =\sum_{j=1}^{n} R_{ji}\underbrace{ \braket{ e_{k} | e_{j} } }_{ \delta_{kj} }   =R_{ki},k=1,2,\dots,n.$$
> This shows that the change of basis matrix $R$ is the matrix of inner products between the elements of the old and the new orthonormal bases. That is:
> $$
> R_{ij}=\braket{ e_{i} | e_{j}' } .$$
> The [[Orthonormality#^aef684|completeness relation]] for the old basis is
> $$
> \hat{I}=\sum_{k=1}^{n} \ket{e_{k}} \bra{e_{k}} .$$
> Second, take:
> $$
> \begin{align}
> \braket{ e_{i}' | \hat{I} | e_{j}' }  & = \braket{ e_{i}' | \left( \sum_{k=1}^{n} \ket{e_{k}} \braket{ e_{k}}  \right) | e_{j}'  }, \\
>  \braket{ e_{i}' | e_{j}' } & =  \sum_{k=1}^{n}\underbrace{ \braket{ e_{i}' | e_{k} } }_{ \braket{ e_{k} | e_{i}' } ^{*} }  \braket{ e_{k} | e_{j}' } , \\
> \delta_{ij} & = \sum_{k=1}^{n} R_{ki}^{*}R_{kj}. 
> \end{align}$$
> Recalling that the [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^a655b3|adjoint of a matrix]] is $(R^{\dagger})_{ij}=R^{*}_{ji}$, this yields
> $$
> \begin{align}
> \delta_{ij} & =\sum_{k=1}^{n} (R^{\dagger})_{ik}R_{kj}, \\
> I & = R^{\dagger}R.
> \end{align}$$
> The completeness relation for the new basis is 
> $$
> \hat{I}=\sum_{k=1}^{n} \ket{e_{k}'} \bra{e_{k}'}.$$
> Third, take:
> $$
> \begin{align}
> \braket{ e_{i} | \hat{I} | e_{j} } & = \braket{ e_{i} | \left( \sum_{k=1}^{n} \ket{e_{k}'} \braket{ e_{k}'}  \right) |  e_{j}  }, \\
> \braket{ e_{i} | e_{j} }  & = \sum_{k=1}^{n} \braket{ e_{i} | e_{k}' }   \braket{ e_{k}' | e_{j} } , \\
> \delta_{ij} & = \sum_{k=1}^{n} R_{ik} R_{jk}^{*}.
> \end{align}$$
> So:
> $$
> \begin{align}
> \delta_{ij} & =\sum_{k=1}^{n} R_{ik}R_{jk}^{*}=\sum_{k=1}^{n} R_{ik}(R^{\dagger})_{kj}, \\
> I & = RR^{\dagger}.
> \end{align}$$
> Putting this together, we have $I=RR^{\dagger}=R^{\dagger}R$, which is the condition for a [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^3c28cf|matrix to be unitary]].
> QED.

^645477


> [!tldr]+ Lemma 1
> **Lemma 1:** Let $\{ \ket{e_{i}} \}$ be an orthonormal basis of the [[Inner Products#^3cf67b|inner product space]] $V$. The linear operator $\hat{A}:V\to V$ is a Hermitian operator if the $n\times n$ matrix $A$ which represents $\hat{A}$ in the orthonormal basis $\{ \ket{e_{i}} \}$ is a Hermitian matrix.
> 
> **Proof:** Using the [[Orthonormality#^aef684|completeness relation]], we can write 
> $$
> \hat{I}=\sum_{i=1}^{n} \ket{e_{i}} \bra{e_{i}} .$$
> Then:
> $$
> \begin{align}
> \hat{A}=\hat{I}\hat{A}\hat{I} & =\left( \sum_{i=1}^{n} \ket{e_{i}} \bra{e_{i}}  \right)\hat{A} \left( \sum_{j=1}^{n} \ket{e_{j}} \bra{e_{j}} \right), \\
>  & = \sum_{i,j=1}^{n} \ket{e_{i}} \underbrace{ \braket{ e_{i} | \hat{A} | e_{j} } }_{ A_{ij} }  \bra{e_{j}} , \\
>  & = \sum_{i,j=1}^{n} \ket{e_{i}}A_{ij}\bra{e_{j}}.  
> \end{align}$$
> This is called the [[#^3df49f|decomposition of the operator in an orthonormal basis]]. The matrix $A$ representing $\hat{A}$ in this basis has components $A_{ij}=\braket{ e_{i} | \hat{A} | e_{j} }$. It's relatively simple to compute the adjoint of $\hat{A}$:
> $$
> \hat{A}=\sum_{i,j=1}^{n} A_{ij}\ket{e_{i}} \bra{e_{j}}, $$
> so $\hat{A}^{\dagger}$ is given by
> $$
> \begin{align}
> \hat{A}^{\dagger} & =\left( \sum_{i,j=1}^{n} A_{ij}\ket{e_{i}} \bra{e_{j}}  \right)^{\dagger}, \\
> & = \sum_{i,j=1}^{n} A_{ij}^{*}\underbrace{ (\ket{e_{i}}\bra{e_{j}}  ) }_{ \ket{e_{j}} \bra{e_{i}}  } . 
> \end{align}$$
> 
> > [!warning] Note!
> > We don't switch the order of $i$ and $j$ in the subscripts of $A$. This is because in this expression $A_{ij}$ is a scalar, and the adjoint of a scalar is simply its complex conjugate. 
> > We should be careful to make a distinction between taking the adjoint of the matrix $(A^{\dagger})_{ij}=A_{ji}^{*}$ and taking the adjoint of the scalar elements of the matrix $(A_{ij})^{\dagger}=A^{*}_{ij}$. 
> 
> We now relabel the indices, swapping $i$ and $j$ and also switching the order of summation.
> $$
> \begin{align}
> \hat{A}^{\dagger} & = \sum_{i,j=1}^{n} A^{*}_{ji}\ket{e_{i}}\bra{e_{j}}  
> \end{align}$$
> By definition of the [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^a655b3|matrix adjoint]], $A^{*}_{ji}=(A^{\dagger})_{ij}$. So we have
> $$
> \hat{A}^{\dagger}=\sum_{i,j=1}^{n} (A^{\dagger})_{ij}\ket{e_{i}} \bra{e_{j}} .$$
> Recall the definition of $\hat{A}$:
> $$
\hat{A}=\sum_{i,j=1}^{n} A_{ij}\ket{e_{i}}\bra{e_{j}}.  $$
>So $\hat{A}^{\dagger}=\hat{A}$ if and only if $A_{ij}=(A^{\dagger})_{ij}$. That is, the operator $\hat{A}$ is Hermitian if the matrix representation in an orthonormal basis $A$ is Hermitian.

^a1859b

> [!example] Decomposition of a Linear Operator in an Orthonormal Basis
> Given a [[Linear Operators#^9dd697|linear operator]] ${} \hat{A}:V \to V {}$ and an orthonormal [[Linear Independence & Basis#^12b0fb|basis]] $\{ \ket{e_{i}} \}$ of the [[Inner Products#^3cf67b|inner product space]] $V$, we define the operator's ***decomposition in an orthonormal basis*** as
> $$
> \hat{A}=\sum_{i=1}^{n} \sum_{j=1}^{n} \ket{e_{i}} A_{ij} \bra{e_{j}}, $$
> where $A_{ij}$ are the components of the matrix representation of $\hat{A}$ in the basis $\{ \ket{e_{i}} \}$, given by $A_{ij}=\braket{ e_{i} | \hat{A} | e_{j} }$. 

^3df49f



> [!tldr]+ Lemma 2
> **Lemma 2:** Let $\{ \ket{e_{i}} \}$ be an orthonormal basis of the [[Inner Products#^3cf67b|inner product space]] $V$. The linear operator $\hat{A}:V\to V$ is a unitary operator if the $n\times n$ matrix $A$ which represents $\hat{A}$ in the orthonormal basis $\{ \ket{e_{i}} \}$ is a unitary matrix.
> 
> **Proof:** If the matrix $A$ is unitary, then $A^{\dagger}A=AA^{\dagger}=I$. We use the following expressions from [[#^a1859b|Lemma 1]]:
> $$
> \begin{align}
> \hat{A} & =\sum_{i,j=1}^{n} A_{ij}\ket{e_{i}} \bra{e_{j}}, \\
> \hat{A}^{\dagger}  & = \sum_{i,j=1}^{n} (A^{\dagger})_{ij}\ket{e_{i}}\bra{e_{j}}.  
> \end{align}$$
> Then we see:
> $$
> \begin{align}
> \hat{A}^{\dagger}\hat{A} & =\left( \sum_{i,j=1}^{n} (A^{\dagger})_{ij}\ket{e_{i}}\bra{e_{j}} \right) \left( \sum_{k,l=1}^{n} A_{kl}\ket{e_{k}} \bra{e_{l}} \right) , \\
>  & = \sum_{i,j,k,l=1}^{n} (A^{\dagger})_{ij}A_{kl}\ket{e_{i}}\underbrace{ \braket{ e_{j} | e_{k} } }_{ \delta_{jk} } \bra{e_{l}}  , \\
> & = \sum_{i,j,l=1}^{n} (A^{\dagger})_{ij}A_{jl}\ket{e_{i}}\bra{e_{l}}.  
> \end{align}$$
> We can now swap the order of summation:
> $$
> \hat{A}^{\dagger}\hat{A}=\sum_{i,l,j=1}^{n} (A^{\dagger})_{ij}A_{jl}\ket{e_{i}} \bra{e_{l}} .$$
> Since $A$ is a unitary matrix, 
> $$
> \begin{align}
> A^{\dagger}A & =I, \\
> \sum_{j=1}^{n} (A^{\dagger})_{ij}A_{jl} & = \delta_{il}.
> \end{align}$$
> Substituting this into our expression, we have
> $$
> \begin{align}
> \hat{A}^{\dagger}\hat{A} & = \sum_{i,l=1}^{n} \delta_{il}\ket{e_{i}}\bra{e_{l}}, \\
>  & = \sum_{l=1}^{n}  \ket{e_{i}} \bra{e_{i}}, \\
>  & = \hat{I}, 
> \end{align}$$
> by the [[Orthonormality#^aef684|completeness relation]]. A similar method also proves that $\hat{A}\hat{A}^{\dagger}=\hat{I}$. Therefore the linear operator $\hat{A}$ is unitary if its matrix representation in an orthonormal basis is [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#^3c28cf|unitary]].
> 

^b4c7ca


> [!NOTE]+ Proof of a Unitary Change of Basis Operator
> By [[Change of Basis#^b4c7ca|Lemma 2]], a linear operator is unitary if its matrix representation in an orthonormal basis is unitary. We previously proved that the [[Change of Basis#^645477|change of basis matrix is unitary]]. Therefore, by Lemma 2, the change of basis operator $\hat{R}$ satisfying the relation $\ket{e_{i}'}=\hat{R}\ket{e_{i}}$ is a unitary operator.

^46ce77


> [!tip] Summary
> Consider a Hermitian operator $\hat{H}=\hat{H}^{\dagger}$ and a unitary operator $\hat{U}^{-1}=\hat{U}^{\dagger}$, in an inner product space $V$. 
> The operators $\hat{H}$ and $\hat{V}$ are represented in an orthonormal basis $\{ \ket{e_{i}} \}$ by the matrices $H=H^{\dagger}$ and $U^{-1}=U^{\dagger}$, and are represented in another orthonormal basis $\{ \ket{e_{i}'} \}$ by $H'=R^{-1}HR$ and $U'=R^{-1}UR$, where $R$ is the change of basis matrix from the old basis $\{ \ket{e_{i}} \}$ to the new basis $\{ \ket{e_{i}'} \}$.
> Note that the matrices $H'$ and $U'$ must be Hermitian and unitary matrices, respectively, since they represent the Hermitian operator $\hat{H}$ and unitary operator $\hat{U}$ in an orthonormal basis. 

^61c303

We can check this by recalling that the change of basis matrix $R$ from $\{ \ket{e_{i}} \}$ to $\{ \ket{e_{i}'} \}$ [[Change of Basis#^eb87a9|is unitary]]. To emphasize this:
$$
\begin{align}
(H')^{\dagger} & = (R^{-1}HR)^{\dagger}=(R^{\dagger}HR)^{\dagger}, \tag{$R^{\dagger}=R^{-1}$}\\
& = (HR)^{\dagger}(R^{\dagger})^{\dagger}, \tag{$(AB)^{\dagger}=B^{\dagger}A^{\dagger}$}\\
& = R^{\dagger}H^{\dagger}R,\tag{$(A^{\dagger})^{\dagger}=A$} \\
& = R^{\dagger}HR,\tag{since $H^{\dagger}=H$} \\
& = H'.
\end{align}
$$
So $H'$ is Hermitian. Similarly,
$$
\begin{align}
(V')^{\dagger} & =R^{\dagger}V^{\dagger}R,\tag{as above} \\
& = R^{\dagger}V^{-1}R, \tag{since $V$ is unitary}\\
& = R^{-1}V^{-1}R.\tag{since $R$ is unitary}
\end{align}
$$
So, 
$$
\begin{align}
(V')^{\dagger}V' & =(R^{-1}V^{-1}R)(R^{-1}VR), \\
& = I.
\end{align}
$$
So $V'$ is unitary.


> [!warning] Non-Orthonormal Bases
> In contrast, the matrices representing Hermitian and unitary operators in a basis which is not orthonormal will **not** generally be Hermitian and unitary matrices. 

^3ddbac





