---
tags:
  - Physics100A
  - 100ANotes
---
---
In function spaces, the [[Eigenvectors and Eigenvalues#^9df0a3|spectrum]] of a linear operator can have discrete (bound states) and/or continuous (scattering states) parts.

For instance, consider the Hamiltonian (that is, the energy function). This operator is such that $\hat{H}\ket{\psi_{i}}=\lambda_{i}\ket{\psi_{i}}$ with the ground state (the smallest $\lambda_{i}$, notated $\lambda_{0}$) is in the discrete part of the spectrum, and all other eigenvalues are $\lambda_{i}>\lambda_{0}$, then the operator is said to have a *gap*: you must supply nonzero energy to move to the next eigenstate (the next allowed eigenvalue). If a spectrum is continuous (*gapless*), then an "excitation" costs infinitesimal energy.

### Completeness of Infinite Dimensional Spaces
In infinite dimensional spaces (function spaces), given a basis, you can expand any function, but it is not necessarily the case that the limit of every infinite sum is in the space. For instance, the function $f(x)=\begin{cases}1,x>0,\\0,x<0\end{cases}$ can be expanded with a Fourier series just like every other function in $C$, but $f(x)\not\in C$. An incomplete function space does not contain all the limit points, whereas a complete function space does contain the limit points.

> [!example] Completeness of Vector Spaces
> Let $V$ be an infinite dimensional vector space (a function space). Given a basis $\{ \ket{i} \}$, you can expand any element $\ket{f}\in V$ as an infinite series of the form
> $$
> \ket{f} =\sum_{i=1}^{\infty} f_{i}\ket{i} .$$
> By definition of the basis $\{ \ket{i} \}$, every element of $V$ can be expanded in this form. The vector space $V$ is called ***complete*** if every infinite series of this form for $f_{i}\in\mathbb{F}$ converges to an element in $V$. If there exists some infinite series of this form which converge to an element not in the vector space, then $V$ is called ***incomplete.*** 

^7b2155

### $L^{2}_{W(x)}[a,b]$ and $C$
Recall $L^{2}_{W(x)}[a,b]$, the space of all square integrable functions with a weight function $W(x)$ applied. A function $f(x)$ is an element of this space if and only if it satisfies
$$
\int_{a}^{b} \left| f(x) \right| ^{2}W(x) \, \hspace{0.5mm} dx <\infty.
$$
Consider the set of functions which are continuous and finite on $[a,b]$. These form a linear vector space called $C< L^{2}_{W(x)}[a,b]$ (where the symbol $<$ denotes a subspace). For example, the following functions are elements of $C$,
![[Screenshot 2024-04-30 at 23.03.49.png|400]]
whereas this function is not:
![[Screenshot 2024-04-30 at 23.04.24.png|100]]
Note that $h(x)\in L^{2}_{W(x)}[a,b]\hspace{2px}/ C$ (the symbol "$/$" denotes a set difference, and this could also be interpreted to mean that $h$ is in the first set and not in the second). 

> [!example] Weierstrauss Theorem
> Let the function $f(x)$ be continuous on the closed finite interval $[a,b]$ (i.e. $f(x)\in C$). Then there exists a sequence of polynomials $p_{n}(x)$ of degree $n$, such that
> $$
> \lim_{ n \to \infty } p_{n}(x)=f(x).
> $$
> More precisely, for any $\varepsilon>0$, there exists an $n$ and polynomials $p_{n}(x)$ of degree $n$ such that
> $$
> \left| f(x)-p_{n}(x) \right| <\varepsilon\hspace{2px}\forall\hspace{2px}x \in[a,b].
> $$
> Note that $\varepsilon$ is independent of $x$, implying that $f(x)$ is uniformly approximated by $p_{n}(x)$. Similarly, this implies that the functions $\{ 1,x,x^{2},\dots \}$ form a basis of $C$.

> [!note]- Proof of Weierstrauss Theorem
> This proof is taken verbatim from Dennery & Krzywicki pp.200-201.
> ![[Screenshot 2024-04-30 at 23.15.30.png|400]]![[Screenshot 2024-04-30 at 23.15.55.png|400]]

Given a weight function $W(x)$ and a specified interval $[a,b]$ we can construct a set of orthogonal polynomials using the Gram-Schmidt method. For instance, the weight function $W(x)=1$ produces the Legendre polynomials, and the weight function $W(x)=e^{ -x^{2} }$ produces the Hermite polynomials.

> [!tip] Physicists are Lazy
> The weight function may be selected so that the basis vectors are eigenfunctions of a Sturm-Liouville Operator.
> $$
> \begin{align}
> \hat{L} & =\alpha(x) \frac{d^{2}}{dx^{2}}+\beta(x) \frac{d}{dx} +\gamma(x), \\
> W(x) & = \frac{1}{\alpha(x)}\exp\left( \int_{}^{x} \frac{\beta(x')}{\alpha(x')} \, \hspace{0.5mm} dx' \right).
> \end{align}$$

By the Weierstrauss Theorem, $\{ 1,x,x^{2},\dots \}$ is a basis of $C$, implying that every function which is continuous on a definite interval can be expanded:
$$
f(x)=\sum_{i=1}^{\infty} f_{i}c_{i}(x),
$$
where $c_{i}(x)$ is the appropriate orthogonal polynomial. The converse is not true. That is, not every infinite series of this form converges to a continuous function. 

> [!tip] Incompleteness of Continuity
> $C$ is an [[#^7b2155|incomplete]] vector space.

| **Example**   | **Complete**        | **Incomplete** |
| ------------- | ------------------- | -------------- |
| Numbers       | $\mathbb{R}$        | $\mathbb{Q}$   |
| Vector spaces | $L^{2}_{W(x)}[a,b]$ | $C$            |


> [!example] Reisz-Fisher Theorem
> The linear vector space $L^{2}_{W(x)}[a,b]$ is complete.

![[Screenshot 2024-05-01 at 08.11.01.png|400]]

In the same way that we think of a vector (ket) as a sequence of components (coefficients of basis vectors),
$$
\vec{\alpha}=\begin{pmatrix}
\alpha_{1} \\
\vdots \\
\alpha_{n}
\end{pmatrix},\hspace{20px}\ket{a} =\sum_{i=1}^{n} \alpha_{i}\ket{i} ,
$$
in an $n$ dimensional space, we can think of a vector (function) as an infinite sequence of complex numbers ($f_{1},f_{2},\dots$), e.g. Fourier coefficients, in a general sense, such that
$$
\sum_{i=1}^{\infty} \left| f_{i} \right| ^{2}<\infty.
$$
(This is some general convergence criterion.) $L^{2}_{W(x)}[a,b]$ is the vector space spanned by such functions. 


> [!example] Hilbert Space
> A complete, infinite dimensional inner product space is called a ***Hilbert space***.

### First Order Linear ODE Review

Suppose you want a solution $y(x)$ for a linear, first order, inhomogeneous ODE.
$$
\frac{ d y(x) }{ d x }+p(x)y(x)=g(x).
$$

^abbe9a

There is a general method to obtain the solution which involves the integrating factor. First consider the homogeneous equation
$$
\frac{dy(x)}{dx}+p(x)y(x)=0.
$$
The method of the integrating factor takes an ODE of this form and multiplies both sides by a factor
$$
\eta(x)=\exp \left[ \int_{}^{x} p(x') \, \hspace{0.5mm} dx'  +C \right] ,
$$
for some constant $C$. We can then recognize the left hand side as the evaluation of the product rule, and we can reverse it:
$$
\frac{d}{dx}  \left[ \eta(x)y(x) \right]  = 0.
$$
Integrating with respect to $x$, we find
$$
y(x)=\frac{A}{\eta(x)}=A\exp \left[ -\int_{}^{x} p(x') \, \hspace{0.5mm} dx' + C  \right] .
$$
Letting $I=\int_{}^{x} p(x') \, \hspace{0.5mm} dx'$, we can write
$$
y(x)e^{ I }=A.
$$
Differentiating the left hand side, we find
$$
\begin{align}
\frac{d}{dx} (y(x)e^{ I }) & =e^{ I } \frac{dy}{dx}+ye^{ I } \frac{dI}{dx}, \\
 & = e^{ I }\left( \frac{dy}{dx}+p(x)y(x) \right) .
\end{align}
$$
Substituting in [[#^abbe9a]], we have
$$
\frac{d}{dx} (y(x)e^{ I })=e^{ I }g(x).
$$
Since $e^{ I }$ and $g(x)$ are both functions of $x$, we can integrate both sides, yielding
$$
y(x)=e^{ -I }\int_{}^{x} g(x'')e^{ I(x'') } \, \hspace{0.5mm} dx'' + Ce^{ -I },
$$
where $I=\int_{}^{x} p(x') \, \hspace{0.5mm} dx'$. Note that there is one arbitrary constant $C$ here, which may be set by boundary conditions. The term $Ce^{ -I }$ solves the homogenous equation.

We write:
$$
y(x)=y_{p}(x)+y_{c}(x),
$$
the general solution with $y_{p}(x)=e^{ -I }\int_{}^{x} g(x'')e^{ I(x'') } \, \hspace{0.5mm} dx''$ being the particular solution to the inhomogeneous equation and $y_{c}(x)=Ce^{ -I(x) }$ being the characteristic solution of the homogeneous equation.

All possible solutions $y(x)$ can be found by varying $C$. A first order linear ODE has one constant which can be used to satisfy one initial or boundary condition.

### Second Order Linear ODEs

Consider the second order linear ordinary differential equation
$$
F\left( x,y(x),\frac{dy}{dx},\frac{d^{2}y}{dx^{2}} \right)=0,
$$
for some arbitrary linear function $F$. We can rearrange this as
$$
\frac{d^{2}y}{dx^{2}}=f\left( x,y(x),\frac{dy}{dx} \right),
$$
again for some arbitrary linear function $f$. Roughly speaking, two integrations are required here, so we expect two arbitrary constants in the general solution. The constants can be used to satisfy two initial or boundary conditions. For our case, we write:
$$
\alpha(x) \frac{d^{2}y(x)}{dx^{2}}+\beta(x)\frac{dy(x)}{dx}+\gamma(x)y(x)=g(x).
$$
We are developing a method to solve this using properties of the differential operator
$$
\hat{L}=\alpha(x) \frac{d^{2}}{dx^{2}}+\beta(x)\frac{d}{dx} +\gamma(x),
$$
and Green's Function.

#### Review: Homogeneous Second Order Linear ODEs

Dividing out $\alpha(x)$, we have
$$
\hat{L}y(x)=\frac{d^{2}y}{dx^{2}}+p(x)\frac{ d y }{ d x } + q(x)y(x)=0.
$$
The functions $y_{1}(x)$ and $y_{2}(x)$ satisfy this equation, with
$$
\det \begin{pmatrix}
y_{1} & y_{2} \\
y_{1}' & y_{2}'
\end{pmatrix}\neq 0,
$$
the Wronskian. (This condition is required for the linear independence of the functions.) Then the general solution is $c_{1}y_{1}(x)+c_{2}y_{2}(x)$. 

#### Back to Inhomogeneous Equations

We have
$$
\hat{L}y(x)=\frac{d^{2}y}{dx^{2}}+p(x) \frac{dy}{dx}+q(x)y=g(x).
$$
In previous classes we learned how to find a particular solution $y_{p}(x)$ which satisfies this equation, writing the general solution
$$
y(x)=y_{p}(x)+c_{1}y_{1}(x)+c_{2}y_{2}(x),
$$
and using initial/boundary conditions to set $c_{1}$ and $c_{2}$. In this class we develop a more general technique called the Sturm-Liouville Problem that involves finding eigenfunctions and eigenvalues of $\hat{L}$:
$$
\hat{L}\ket{\phi_{n}} =\lambda_{n}\ket{\phi_{n}} .
$$
We want to define an inner product such that $\hat{L}$ is Hermitian to make this problem significantly easier. This is where the weight function comes in, choosing it such that
$$
\braket{ \phi_{n} | \phi_{m} } =\delta_{nm}\tag{$\{ \ket{\phi_{n}}  \}$ is an orthonormal basis}.
$$
We can then rewrite the inhomogeneous equation as
$$
\hat{L}\ket{y} -\gamma \ket{y}=\ket{g} ,
$$
for $\gamma=0$, $\ket{g}\leftrightarrow g(x)$, and $\hat{L}$ is Hermitian. Once we have it in this form we can apply [[Eigenvectors and Eigenvalues#^09b206|Green's function]], finding:
$$
\ket{y} =\hat{G}\ket{g} =\sum_{n=1}^{\infty} \frac{\ket{\phi_{n}} \braket{ \phi_{n} | g } }{\lambda_{n}-\gamma}.
$$
If we expand the inhomogeneous term $\ket{g}$ in the orthonormal basis $\{ \ket{\phi_{n}} \}$, the coefficients in the expansion of $\ket{y}$ are especially easy to calculate.

> [!tip] Key Concept
> If you solve the eigenvalue/eigenvector problem for $\hat{L}$, you can write down the solution to the inhomogeneous equation using Green's function.

