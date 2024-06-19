---
tags:
  - 100ANotes
  - Physics100A
---
---
### The Associated Legendre Equation

> [!example] Associated Legendre Equation
> The ***associated Legendre equation*** is
> $$
> (1-x^{2})y''-2xy'+\left[ l(l+1)-\frac{m^{2}}{1-x^{2}} \right]y=0,\tag{1}$$
> for $m\in\mathbb{Z}$ and $-1\leq x\leq 1$. 
^d82212

> [!tip] It's Not as Bad as It Seems
> The equation only depends on $m^{2}$, so we are free to only consider nonnegative values of $m$. That is, $m\in\mathbb{Z}_{\geq 0}$.

Note that for $m=0$ [[#^d82212|Eqn(1)]] becomes [[Legendre Polynomials#^576ebd|Legendre's equation]]. The solution to this equation will be related to the Legendre polynomials. To see this, consider
$$
y(x)=(1-x^{2})^{m/2}u(x).
$$
Substituting this into [[#^d82212|Eqn(1)]] and using $y'=\frac{m}{2}(-2x)(1-x^{2})^{(m/2)-1}u+(1-x^{2})^{m/2}u'$, and so one, we have (after some algebra):
$$
(1-x^{2})u''-2(m+1)xu'+[l(l+1)-m(m+1)]u=0.
$$
^eqn2

We can view this as a Sturm-Liouville problem. For every value of $m$, we seek the eigenvalues $\lambda$ and eigenvectors $u(x)$. We know that the weight function will be
$$
w(x)=\frac{1}{1-x^{2}}\exp\left( \int_{}^{x} -\frac{2(m+1)\omega}{1-\omega^{2}} \, \hspace{0.5mm} d\omega  \right)=m+1,
$$
on the vector space $V$ of functions $u(x)$ which are finite and have finite derivatives at $x=\pm 1$ (which [[Active Learning Master List#Legendre Boundary Conditions|we know satisfies the restrictions on boundary conditions]]). We can then solve the Sturm-Liouville problem.

> [!summary] Solving the Sturm-Liouville Problem
> The solution to the eigenvalue problem is broken up into two steps.
> 1. Find the general solution to the ODE irrespective of boundary conditions.
> 2. Impose boundary conditions which determines the allowed eigenvalues and associated eigenvectors.

The method to solve this is completely analogous to our treatment of the Legendre equation, so the only thing we need be concerned about is the result.

> [!summary] Eigenvalues of Associated Legendre Differential Operator
> For every value of $m\in\mathbb{Z}_{\geq 0}$ (note that for each $m$ we have a different operator, eigenvalues, and eigenvectors), the eigenvalues of the operator $\hat{L}=(1-x^{2}) \frac{d^{2}}{dx^{2}}-2(m+1)x\frac{d}{dx}$ are of the form
> $$
> \begin{align}
> \lambda & =-\left[ l(l+1)-m(m+1) \right] , \\
> l & = m,m+1,m+2,\dots,
> \end{align}$$
> and for each such eigenvalue (with specified $(l,m)$) there is *one and only one* eigenvector which satisfies the boundary condition (finite and with finite derivatives at $x=\pm 1$).

The derivation of the eigenfunctions again comes down to Gauss's test for convergence of the series. We can obtain these polynomials from Legendre polynomials in the process below.

> [!claim]
> The polynomial $u(x)=\frac{d^{m}}{dx^{m}}P_{l}(x)$, where $P_{l}(x)$ is the $l$-th Legendre polynomial, is a solution of [[#^eqn2]].

`\begin{proof}`We begin with [[#^eqn2]] for $m=0$, which is [[Legendre Polynomials#^576ebd|Legendre's equation]], so the claim is correct for $m=0$. Next we differentiate [[#^eqn2]], finding
$$
-2xu''+(1-x^{2})u'''-2(m+1)u'-2(m+1)xu''+[l(l+1)-m(m+1)]u'=0.
$$
We can rewrite this as
$$
(1-x^{2})(u')''-2[(m+1)+1]x(u')'+[l(l+1)-(m+1)(m+2)](u')=0,
$$
which is the same as [[#^eqn2]] with $m$ replaced by $(m+1)$. We can repeat this process, showing that [[#^eqn2]] has the solutions
$$
\begin{align}
m=0 & \to P_{l}(x), \\
m=1 & \to \frac{d}{dx} P_{l}(x), \\
m=2 & \to \frac{d^{2}}{dx^{2}}P_{l}(x), \\
 & \vdots
\end{align}
$$
Therefore $u(x)=\frac{d^{m}}{dx^{m}}P_{l}(x)$ is a solution of [[#^eqn2]].`\end{proof}`

Going back to the original [[#^d82212|Eqn(1)]], we have that
$$
y(x)=P_{l}^{m}(x)=(1-x^{2})^{m/2} \frac{d^{m}}{dx^{m}}P_{l}(x),
$$
is a solution of the [[#^d82212|associated Legendre equation]]. (Note that the functions $u(x)$ are polynomials but $y(x)$ mayn't be.) Also note that $\frac{d^{m}}{dx^{m}}P_{l}(x)=0$ for $m>l$, because $P_{l}(x)$ is a polynomial of degree $l$. So we have the condition that $0\leq m\leq l$, for $m\in\mathbb{Z}$. 

> [!example] Rodrigues' Formula for Associated Legendre Polynomials
> [[Legendre Polynomials#^981879|Rodrigues' formula]] for the Legendre polynomials gives this explicit expression for the associated Legendre functions:
> [](Legendre%20Polynomials.md#^981879){dx^{(l+m)}}\left[ (x^{2}-1)^{l} \right] ,\hspace{5px}0\leq m\leq l.$$
^47ca52

This formula also makes sense for negative values of $m$. Let $m=-\left| m \right|=-l,-l+1,-l+2,\dots,-1$. Then we have
$$
P^{-\left| m \right| }_{l}(x)=\frac{1}{2^{l}\hspace{2px}l!}(1-x^{2})^{-\left| m \right| /2} \frac{d^{(l-\left| m \right| )}}{dx^{(l-\left| m \right| )}}[(x^{2}-1)^{l}].
$$
It can be shown that these functions $P_{l}^{-\left| m \right|}$ are also solutions of the associated Legendre equation, and are proportional to the functions $P_{l}^{\left| m \right|}(x)$:
$$
P_{l}^{-\left| m \right| }(x)=(-1)^{m} \frac{(l-\left| m \right| )!}{(l+\left| m \right| )!}P_{l}^{\left| m \right| }(x).
$$
Therefore [[#^47ca52|this formula]] provides a solution of the associated Legendre equation for $-l\leq m\leq l,m\in\mathbb{Z}$. 

### Normalization Factor

The normalization is given by Boas 12.10 Problem 10.
$$
\begin{align}
\int_{-1}^{1} [P_{l}^{m}(x)]^{2} \, \hspace{0.5mm} dx  & =\frac{(l+m)!}{(l-m)!} \frac{2}{(2l+1)}, \\
-l\leq m\leq l, &\hspace{5px}m\in \mathbb{Z}, \\
l & = 0,1,2,\dots
\end{align}
$$
### Summary

> [!summary] Summary
> For every value of $m\in\mathbb{Z}$, the associated Legendre equation is an eigenvalue problem for the Hermitian differential operator (with respect to the ordinary inner product with weight function $w(x)=1$):
> $$
> \begin{align}
> \hat{L} & =(1-x^{2}) \frac{d^{2}}{dx^{2}}-2x\frac{d}{dx} -\frac{m^{2}}{1-x^{2}}, \\
> \hat{L}\hspace{2px}y(x) & = \lambda\hspace{2px}y(x).
> \end{align}
> $$
> The eigenvalues of $\hat{L}$ are
> $$
> \begin{align}
> \lambda & =\lambda_{l} = -l(l+1), \\
> l & =\left| m \right| ,  \left| m \right| +1,\left| m \right| +2,\dots
> \end{align}
> $$
> The (not normalized) eigenfunction corresponding to the eigenvalue $-l(l+1)$ is
> $$
> P^{m}_{l}(x),
> $$
> the [[#^47ca52|associated Legendre function]], with 
> $$
> \hat{L}\hspace{2px}P_{l}^{m}(x)=-l(l+1)\hspace{2px}P_{l}^{m}(x).
> $$
> Because $\hat{L}$ is Hermitian under these conditions, we know that these are orthogonal.
> $$
> \braket{ P_{l}^{m} | P_{l'}^{m} } = \frac{(l+m)!}{(l-m)!} \frac{2}{(2l+1)}\delta_{l,l'}.
> $$
> 