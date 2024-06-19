---
tags:
  - Physics100A
  - 100ANotes
---
---
Note that the following statements all employ [[Tensor Notation|Einstein index notation]].


$A=[A_{ij}]$. $A^{T}=[(A^{T})_{ij}]=[A_{ji}]$. 
$B=[B_{ij}]$. $B^{T}=[(B^{T})_{ij}]=[B_{ji}]$. 
$AB=[(AB)_{ij}]=[A_{ik}B_{kj}]$.
$BA=[(BA)_{ij}]=[B_{ik}A_{kj}]$.
$(AB)^{T}=B^{T}A^{T}=[(B^{T}A^{T})_{ij}]=[(B^{T})_{ik}(A^{T})_{kj}]=[B_{ki}A_{jk}]=[A_{jk}B_{ki}]$. 
$(BA)^{T}=A^{T}B^{T}=[(A^{T}B^{T})_{ij}]=[(A^{T})_{ik}(B^{T})_{kj}]=[A_{ki}B_{jk}]=[B_{jk}A_{ki}]$. 
$AB=BA \implies A_{ik}B_{kj}=B_{ik}A_{kj}$.
$(AB)^{\dagger}=B^{\dagger}A^{\dagger}=[(B^{\dagger}A^{\dagger})_{ij}]=[(B^{\dagger})_{ik}(A^{\dagger})_{kj}]=[B_{ki}^{*}A_{jk}^{*}]=[A_{jk}^{*}B_{ki}^{*}]$. 

> [!tip] Transposing Matrices
> Therefore to take the transpose of a product of matrices, simply swap the outer indices and leave the dummy indices alone.

The inverse of a matrix $A$ is some matrix $A^{-1}$, such that
$$
A_{ik}A^{-1}_{kj}=A^{-1}_{ik}A_{kj}=0 \hspace{5px}\forall\hspace{5px} i,j.
$$
