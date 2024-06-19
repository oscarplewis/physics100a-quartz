---
tags:
  - Physics100A
  - 100ANotes
---
---
### General Solution to the Sturm-Liouville Problem

#### Statement of the Problem

> [!question] The Sturm-Liouville Problem
> Let:
> - $f(x)$ be a smooth function on $a\leq x\leq b$, for $a,b\in [-\infty,\infty]$. 
> - $\hat{L}$ be a [[Linear Operators#^9dd697|linear operator]] such that
> $$
> \hat{L}f(x)=\alpha(x) \frac{d^{2}f}{dx^{2}}+\beta(x) \frac{df}{dx}+\gamma(x)f(x),
> $$
> for $\alpha(x)\neq 0,\beta(x),\gamma(x)$ all real valued for $a\leq x\leq b$.  
> - An [[Inner Products#^572aff|inner product]] be defined
> $$
> \braket{ f | g } = \int_{a}^{b} f^{*}(x)g(x)w(x) \, \hspace{0.5mm} dx ,
> $$
> for a real valued weight function $w(x)>0$ for all $a\leq x\leq b$. 
> - The square [[Inner Products#^db8742|norms]] $\braket{ f | f }$, $\braket{ f' | f' }$, $\braket{ f'' | f'' },\braket{ g | g },\braket{ g' | g' },\braket{ g'' | g'' }$ are all finite valued.
> 
> The goal of the Sturm-Liouville problem is to find a weight function $w(x)$ and boundary conditions on the function $f(x)$ at $x=a,b$ such that $\hat{L}^{\dagger}=\hat{L}$ (i.e. $\hat{L}$ is [[Linear Operators#^63db04|Hermitian]]) with respect to the inner product.

^364905

#### Placing Constraints on $w(x)$ and the Boundaries (i.e. Integration by Parts)

Explicitly, this means we must choose $w(x)$ and appropriate boundary conditions such that:
$$
\begin{align}
\braket{ f | \hat{L} | g }  & = \braket{ g | \hat{L} | f } ^{*}, \\
\int_{a}^{b} f^{*}(x)(\hat{L}g)(x)w(x) \, \hspace{0.5mm} dx  & = \int_{a}^{b} (\hat{L}f)^{*}(x)g(x)w(x) \, \hspace{0.5mm} dx .
\end{align}
$$
In order to find these things, we integrate by parts, a lengthy albeit straightforward process.
$$
\begin{align}
\braket{ f | \hat{L} | g }  & = \int_{a}^{b} w(x)f^{*}(x)\left[ \alpha(x) \frac{d^{2}}{dx^{2}}+\beta(x)\frac{ d  }{ d x } +\gamma(x) \right] g(x) \, \hspace{0.5mm} dx , \\
 & = \int_{a}^{b} w(x)f^{*}(x)\alpha(x)g''(x) \, \hspace{0.5mm} dx \tag{1-A} \\
 &\hspace{20px} + \int_{a}^{b} w(x)f^{*}(x)\beta(x)g'(x) \, \hspace{0.5mm} dx \tag{1-B} \\
 &\hspace{20px} + \int_{a}^{b} w(x)f^{*}(x)\gamma(x)g(x) \, \hspace{0.5mm} dx \tag{1-C},
\end{align}
$$
and,
$$
\begin{align}
\braket{ g | \hat{L} | f } ^{*} & = \int_{a}^{b} w(x)g(x)\left[ \alpha(x) \frac{d^{2}}{dx^{2}}+\beta(x)\frac{d}{dx} +\gamma(x) \right] f^{*}(x) \, \hspace{0.5mm} dx , \\
 & = \int_{a}^{b} w(x)\alpha(x)f''^{*}(x)g(x) \, \hspace{0.5mm} dx  \tag{2-A}\\
 & \hspace{20px}+ \int_{a}^{b} w(x)\beta(x)f'^{*}(x)g(x) \, \hspace{0.5mm} dx  \tag{2-B}\\
 &\hspace{20px} + \int_{a}^{b} w(x)\gamma(x)f^{*}(x)g(x) \, \hspace{0.5mm} dx .\tag{2-C}
\end{align}
$$


Note that Term (1-C) is already equal to Term (2-C). The other terms, however, we must integrate by parts on. For Term (1-A):
$$
\begin{align}
\int_{a}^{b} w(x)\alpha(x)f^{*}(x)g''(x) \, \hspace{0.5mm} dx  & = \left[ w(x)\alpha(x)f^{*}(x) \right]g'(x)\biggr |_{a}^{b} -\int_{a}^{b} \left[ w(x)\alpha(x)f^{*}(x) \right]'g'(x)  \, \hspace{0.5mm} dx , \\
 & = w(x)\alpha(x)f^{*}(x)g'(x)\biggr |_{a}^{b}-\int_{a}^{b} \left[ w(x)\alpha(x) \right]' f^{*}(x)g'(x) \, \hspace{0.5mm} dx  \\
 &\hspace{20px} - \int_{a}^{b} w(x)\alpha(x)f'^{*}(x) \, \hspace{0.5mm} dx .
\end{align}
$$
For Term (1-B):
$$
\begin{align}
\int_{a}^{b} w(x)f^{*}(x)\beta(x)g'(x) \, \hspace{0.5mm} dx  & = \left[ w(x)\beta(x)f^{*}(x) \right] g(x)\biggr |_{a}^{b}-\int_{a}^{b} \left[ w(x)\beta(x)f^{*}(x) \right]'\hspace{2px}g(x) \, \hspace{0.5mm} dx, \\
&  = w(x)\beta(x)f^{*}(x)g(x)\biggr |_{a}^{b}-\int_{a}^{b} \left[ w(x)\beta(x) \right]' f^{*}(x)g(x) \, \hspace{0.5mm} dx \\
 &\hspace{20px} - \int_{a}^{b} w(x)\beta(x)f'^{*}(x)g(x) \, \hspace{0.5mm} dx .
\end{align}
$$
Putting it all together, we have:
$$
\begin{align}
\braket{ f | \hat{L} | g } & = \left[ (w\alpha f^{*})g'+(w\beta f^{*})g \right] \biggr |_{a}^{b}+\int_{a}^{b} \biggr [\left( w\alpha \right)'f^{*}g'+w\alpha f'^{*}g' +(w\beta)'f^{*}g+w\beta f'^{*}g +w\gamma f^{*}g \biggr ]  \, \hspace{0.5mm} dx .
\end{align}
$$

> [!warning] sign error? :((( should be negative :<

We can repeat the same integration by parts process for Term (2-A) and Term (2-B), yielding
$$
\braket{ g | \hat{L} | f }^{*}=\left[ (w\alpha g)f'^{*}+w\beta gf^{*} \right] \biggr |_{a}^{b}-\int_{a}^{b} \biggr [  (w\alpha)'gf'^{*}+w\alpha f'^{*}g'+(w\beta)'gf^{*}+w\beta g'f^{*} + w\gamma gf^{*}  \biggr ] \, \hspace{0.5mm} dx .
$$
Combining these, we have
$$
\begin{align}
\braket{ f | \hat{L} | g } -\braket{ g | \hat{L} | f } ^{*} & = -\int_{a}^{b} \left[ (w\alpha)'(f^{*}g'-gf'^{*})+(w\alpha)(\cancelto{ 0 }{ f'^{*}g'-g'f'^{*} } ) \right]  \, \hspace{0.5mm} dx  \\
 &\hspace{20px} - \int_{a}^{b} \left[ (w\beta)'(\cancelto{ 0 }{ f^{*}g-gf^{*} } ) (w\beta)(f'^{*}g-g'f^{*}) \right]  \, \hspace{0.5mm} dx  \\
 &\hspace{20px} - \int_{a}^{b} w\gamma(\cancelto{ 0 }{ f^{*}g-gf^{*} } ) \, \hspace{0.5mm} dx \\
 &\hspace{20px} + \biggr [  w\alpha(f^{*}g'-gf'^{*})+w\beta(\cancelto{ 0 }{ f^{*}g-gf^{*} } ) \biggr ]\biggr |_{a}^{b}.
\end{align}
$$
Therefore,
$$
\begin{align}
\braket{ f | \hat{L} | g } -\braket{ g | \hat{L} | f } ^{*} & = \biggr [ w\alpha(f^{*}g'-gf'^{*}) \biggr ] \biggr |_{a}^{b}-\int_{a}^{b} \left [ (w\alpha)'-w\beta \right ](f^{*}g'-gf'^{*}) \, \hspace{0.5mm} dx.
\end{align}
$$
^0f216e

$\hat{L}$ is Hermitian if this quantity vanishes. This will happen if both of the following conditions are true:
1. $(w\alpha)'-w\beta=0$ for all $a\leq x\leq b$. (A constraint on the weight function.)
2. $w\alpha(f^{*}g'-gf'^{*})\biggr|_{a}^{b}=0$. (A constraint on the boundary conditions.)


> [!tip] Choosing These Constraints
> The second constraint is rather obvious looking at [[#^0f216e]]. The first constraint is less so. We note that $f(x)$ and $g(x)$ are arbitrary functions, and the only way the integral vanishes if its integrand is zero for any choice of $f$ and $g$. This means that the factor with the weight function must be the one which consistently vanishes, and so we arrive at the first constraint.

#### Constraint of the Weight Function

The weight function $w(x)$ satisfies
$$
(w\alpha)'=w\beta=\frac{\beta}{\alpha}(w\alpha).
$$
This implies:
$$
\frac{(w\alpha)'}{(w\alpha)}=\frac{\beta}{\alpha}.
$$
This is a simple first order differential equation, so we can integrate to obtain the solution.
$$
\begin{align}
\ln(w\alpha) & =\int^{x} \frac{\beta}{\alpha} \, dx' +\ln C', \\
w(x)  & = \frac{C'}{\alpha(x)}\exp\left( \int_{}^{x} \frac{\beta(x')}{\alpha(x')} \, \hspace{0.5mm} dx'  \right).
\end{align}
$$
Note that $w(x)\neq 0$ for $a\leq x\leq b$ and we specified $\alpha(x)\neq 0$. We also want $w(x)>0$, so either $\alpha(x)<0$ or $\alpha(x)>0$ throughout the interval.
$$
\begin{align}
\text{If }  & \alpha(x)>0,\text{ choose } C'>0, \\
\text{If }  & \alpha(x)<0,\text{choose }C'<0.
\end{align}
$$
Without loss of generality, we choose $\alpha(x)>0$ and $C'=1$ from now henceforth (this is possible because we can always multiply the equation by some scale factor, such that the constant is 1). Then we have,
$$
w(x)=\frac{1}{\alpha(x)}\exp \left( \int_{}^{x} \frac{\beta(x')}{\alpha(x')} \, \hspace{0.5mm} dx'  \right) .
$$

^50152a

#### Constraint of the Boundary Conditions

The boundary conditions for the problem must satisfy,
$$
\left[ w\alpha(f^{*}g'-gf'^{*}) \right] \biggr |_{a}^{b}=0.
$$
^737d4d

These are the most general conditions, and any more specificity we add will lose some solutions. We pick boundary conditions, which in turn determine the vector space of functions $f(x),g(x),u(x)\in V$ on which the operator $\hat{L}$ will act. 

We will consider four common examples which have boundary conditions consistent with [[#^737d4d]]. 
$$
\begin{align}
\text{I.} & \text{ Dirichlet conditions: } u(a)=u(b)=0. \\
\text{II.} & \text{ von Neumann conditions: } u'(a)=u'(b)=0. \\
\text{III.} & \text{ General unmixed conditions: } A\hspace{2px}u(a)-\tilde{A}\hspace{2px}u'(a)=B\hspace{2px}u(b)-\tilde{B}u'(b). \\
\text{IV.}  & \text{ Periodic conditions: }u(a)=u(b),\hspace{2px}u'(a)=u'(b).
\end{align}
$$

^40d5d0

> [!warning] In part III, the notes have $u(x)$ when it should be $u(a)$ as above.

#### Eigenfunctions of $\hat{L}$

We may consider any of the four vector spaces of functions $u(x) \in V$ with $V=V_{I},V_{II},V_{III},$ or $V_{IV}$ satisfying:
- The corresponding boundary conditions I, II, III, or IV. 
- $\braket{ u | u }=\int_{a}^{b} u^{*}(x)u(x)w(x) \, \hspace{0.5mm} dx<\infty$, $\braket{ u' | u' }<\infty$, $\braket{ u'' | u'' }<\infty$, for $w(x)$ which satisfies [[#^50152a]].(Here the weight function generalizes the notion of being square integrable.)

These choices guarantee that when acting on any one of these vector spaces the linear operator $\hat{L}:V \to V$ is [[Linear Operators#^63db04|Hermitian]]. From the [[Eigenvectors and Eigenvalues#^7d228b|spectral theorem for hermitian operators]], the vector space $V$ under consideration has an orthonormal basis $\{ \ket{u_{n}} \}$ which consists of eigenfunctions of the Hermitian linear operator $\hat{L}$. Explicitly, the eigenfunction equation then reads:
$$
\hat{L}\ket{u_{n}} =\hat{L}\hspace{2px}u_{n}(x)=\alpha(x)u''(x)+\beta(x)u'(x)+\gamma(x)u(x)=\lambda_{n}u_{n}(x)=\lambda_{n}\ket{u_{n}} .
$$

^d8bfc9


We need to find solutions $u_{n}(x)$ of this differential equation which satisfy the boundary conditions and which have finite norm $\braket{ u_{n} | u_{n} }<\infty$. 

We can rewrite [[#^d8bfc9]] in an equivalent form which may be easier to solve, multiplying by the weight function.
$$
\begin{align}
w(x)\hat{L}\hspace{2px}u_{n}(x) & = \lambda_{n}w(x)u_{n}(x).
\end{align}
$$
We can rewrite the left hand side, using the fact that $(w\alpha)'-w\beta=0$:
$$
\begin{align}
w(x)\hat{L}\hspace{2px}u_{n}(x) & = w(x)\alpha(x)u_{n}''(x)+w(x)\beta(x)u_{n}'(x)+w(x)\gamma(x)u_{n}(x), \\
 & = \frac{d}{dx} \biggr ( w(x)\alpha(x)u_{n}'(x) \biggr ) +\gamma(x)w(x)u_{n}(x).
\end{align}
$$
So we arrive at:
$$
\frac{d}{dx} \biggr [  w(x)\alpha(x) \frac{du_{n}}{dx} \biggr ]+\biggr [ \gamma(x)-\lambda_{n} \biggr ]w(x)u_{n}(x)=0.
$$

^092f18

> [!tip] Equation Equivalency
> Any solution $u_{n}(x)$ of the Sturm-Liouville problem as stated in [[#^d8bfc9]] is also a solution of [[#^092f18]], and vice versa.

#### Summary

> [!summary] Summary
> We begin with a [[#^364905|series of statements of the problem]], and examine the consequences of the statements. We end with [[#^d8bfc9]] and [[#^092f18]] for specified boundary conditions. A differential equation of the form of [[#^d8bfc9]] for functions $u_{n}(x)$ satisfying boundary conditions according to [[#^737d4d]] and with weight function as prescribed in [[#^50152a]] is called a ***Sturm-Liouville problem***.
> $$
\begin{align}
\hat{L}\ket{u_{n}} &  =\lambda_{n}\ket{u_{n}} , \\
w(x) & =\frac{1}{\alpha(x)}\exp \left[ \int_{}^{x} \frac{\beta(\omega)}{\alpha(\omega)} \, \hspace{0.5mm} d\omega  \right],\\
0 & = w(x)\alpha(x)\left[ f^{*}(x) \frac{dg(x)}{dx}-\frac{df^{*}(x)}{dx}g(x) \right] \biggr |_{a}^{b}
\end{align}$$
> The operator $\hat{L}$ is a [[Linear Operators#^63db04|Hermitian operator]] on the [[Linear Vector Spaces#^1175c0|vector space]] $V$ of functions satisfying the boundary conditions and with finite [[Inner Products#^db8742|norm]] (as prescribed). Hence all properties of Hermitian operators apply to $\hat{L}:V \to V$. 
> 1. [[Eigenvectors and Eigenvalues#^56e47a|Eigenvectors]] belonging to different eigenvalues are [[Linear Independence & Basis#^167287|orthogonal]].
> 2. All eigenvalues are real.
> 3. The eigenvectors form an [[Linear Independence & Basis#^12b0fb|orthonormal basis]] of the vector space $V$. 
> 4. The eigenvectors and eigenvalues can be used to solve the homogenous equation $\hat{L}\ket{y}-w\ket{y}=\ket{g}$, with the solution $\ket{y}=\hat{G}\ket{g}$ for $\hat{G}=\sum_{n=1}^{\infty} \frac{\ket{u_{n}}\bra{u_{n}}}{\lambda_{n}-w}$. That is, $y(x)=\sum_{n=1}^{\infty} \frac{u_{n}(x)}{\lambda_{n}-w}\int_{a}^{b} u_{n}^{*}(x)g(x)w(x) \, \hspace{0.5mm} dx$. In words, they can be used when applying [[Eigenvectors and Eigenvalues#^09b206|Green's function]].

Sturm-Liouville problems are methods to solve second order differential equations. First we construct a space for which the differential operator is Hermitian, we then solve the eigenvalue problem, and finally we can use Green's function to solve the second order equation.

### The Dirichlet Conditions

We will now consider an example of a Sturm-Liouville problem. Consider the vector space $V$ of functions $u(x)$ which are smooth on the interval $1\leq x\leq e$ which satisfy the Dirichlet boundary conditions of $u(1)=u(e)=0$, with the standard weighted inner product for function spaces. Let $\hat{L}$ be the differential operator
$$
\hat{L}\hspace{2px}u(x) = x^{2} \frac{d^{2}u}{dx^{2}}+x \frac{du}{dx} ,
$$
acting on functions in $V$. 


> [!example] The Sturm-Liouville Problem
> Find the eigenfunctions $u_{n}(x)$ and eigenvalues $\lambda_{n}$ of $\hat{L}$.

#### Overview

The method of solution will take us through the following steps.
1. Find the most general solution of the homogenous differential equation
$$
\hat{L}\hspace{2px}u(x)-\lambda_{n}u(x)=0,
$$
irrespective of the boundary conditions.
2. Impose the Dirichlet boundary conditions on the general solution found in Step 1.

#### Step 1

This differential equation becomes easier to solve when written in the form of [[#^092f18]], for which we need to find the weight function. Recall [[#^50152a]], and note that it applies because $\alpha(x)=x^{2}>0$. Here, $\alpha(x)=x^{2}$, $\beta(x)=x$, and $\gamma(x) =0$. So:
$$
w(x)=\frac{1}{x^{2}}\exp\left( \int_{}^{x} \frac{x'}{(x')^{2}} \, \hspace{0.5mm} dx' \right)=\frac{1}{x}.
$$
Returning to [[#^092f18]], we can write:
$$
\frac{d}{dx} \left[ x \frac{du}{dx}  \right] -\lambda\frac{ 1}{x}u(x)=0,
$$
which simplifies to
$$
x \frac{d^{2}u}{dx^{2}}+\frac{du}{dx}-\frac{\lambda}{x}u=0.
$$
This is a second order homogenous ordinary differential equation, which has two linearly independent solutions for a given $\lambda$. A good ansatz for this is $u(x)=x^{\xi}$ to see if there is any balance with powers. Substituting this in (for $\xi \in\mathbb{C}$), we have:
$$
\begin{align}
\xi^{2}x^{\xi-1}-\lambda x^{\xi-1} & =0, \\
\xi^{2}=\lambda.
\end{align}
$$
Thus when $\lambda \neq 0$, then $u_{+}(x)=x^{\sqrt{ \lambda }}$ and $u_{-}(x)=x^{-\sqrt{ \lambda }}$ are the two linearly independent solutions. The most general solution to this equation then is
$$
u(x)=Ax^{\sqrt{ \lambda }}+Bx^{-\sqrt{ \lambda }},
$$
for $A,B\in\mathbb{C}$.

#### Step 2

We then seek to impose the chosen boundary conditions $u(1)=u(e)=0$ on this solution. Substituting in $x=1$, we find:
$$
u(1)=0=A+B\implies A=-B.
$$
This places our first constraint on the arbitrary constants. We can then write our general solution in the following form:
$$
u(x)=A(x^{\sqrt{ \lambda }}-x^{-\sqrt{ \lambda }}).
$$
^8f5585

Next we substitute in $x=e$. 
$$
u(e)=0=A(e^{\sqrt{ \lambda }}-e^{ -\sqrt{ \lambda } }).
$$
We cannot have $A=0$ because that solution is trivial, so instead we must place constraints on $\lambda$. Recall the definition of $\sinh\theta=\frac{1}{2}(e^{ \theta }-e^{ -\theta })$. So we can write:
$$
\sinh \sqrt{ \lambda }=0.
$$
This only has solutions where $\lambda=-\left| \lambda \right|<0$ (that is, $\lambda$ is a negative real number). In this case,
$$
e^{ \sqrt{ \lambda } }-e^{ -\sqrt{ \lambda } }=e^{ i\sqrt{ \lambda } }-e^{ -i\sqrt{ \left| \lambda \right|  } }=2i\sin(\sqrt{ \left| \lambda \right|  })=0.
$$
This is a restatement of the boundary condition. So:
$$
\sqrt{ \left| \lambda \right|  }=n\pi,
$$
for nonnegative integer $n$. 

> [!note] Proof of Solution
> Solutions of $\sinh(z)=\frac{1}{2}(e^{ z }-e^{ -z })=0$ take the form $z=x+iy$ for $x,y\in\mathbb{R}$. This means that $0=e^{ z }-e^{ -z }\implies e^{ x }e^{ iy }=e^{ -x }e^{ -iy }$. Taking the modulus of both sides of this equation gives:
> $$
\begin{align}
|e^{ x }e^{ iy }| & = |e^{ -x }e^{ -iy }|.
\end{align}$$
>We know that $|e^{ x }|=e^{ x }$, a real number, and $|e^{ iy }|=1$. So this equation becomes:
> $$
\begin{align}
e^{ x } & =e^{ -x }, \\
e^{ 2x } & = 1, \\
2x &  =\ln 1=0.
\end{align}$$
>This means that $x=0 \implies z=iy$, a pure imaginary number. So we have:
> $$
e^{ iy }-e^{ -iy }=2i\sin(y)=0,$$
>which has solutions $y=\pi n$ for nonegative integer $n$ as above. Therefore the equation $\sinh(z)=0$ has solutions $z=i\pi n$.

From above, we have
$$
\sqrt{ \left| \lambda \right|  }=\pi n,
$$
with $\lambda \in\mathbb{R}_{<0}$ (a negative real). This becomes:
$$
\lambda_{n}=-\left| \lambda \right| =-\pi^{2}n^{2},
$$
for integer $n>0$. These are the eigenvalues of the linear operator $\hat{L}$. The eigenvectors then take the form of [[#^8f5585]] for $\sqrt{ \lambda }=i\pi n$. 
$$
u_{n}(x)=A\left[ x^{i\pi n}-x^{-i\pi n} \right],
$$
for $n=1,2,3,\dots.$ Note that when $n=0$, $u_{0}(x)=0$, but the null vector [[Eigenvectors and Eigenvalues#^56e47a|by definition]] cannot be an eigenvector. So we exclude $n=0$.

#### Conclusion

> [!summary] Conclusion
> Let $V$ be a vector space of functions $u(x)$ which are smooth on the interval $1\leq x\leq e$ and which satisfy the Dirichlet boundary conditions $u(1)=u(e)=0$. Let $\hat{L}$ be a linear operator defined:
> $$
> \hat{L}=x^{2} \frac{d^{2}}{dx^{2}}+x\frac{d}{dx} ,$$
> such that $\hat{L}:V\to V$. We define the inner product on elements of $V$ to be:
> $$
> \braket{ f | g } = \int_{1}^{e} f^{*}(x)g(x) \frac{1}{x} \, \hspace{0.5mm} dx ,$$
> for which all $u(x)\in V$ have finite norm, and the linear operator $\hat{L}$ is Hermitian with
> $$
> \begin{align}
> \text{eigenvalues: }&\lambda_{n}=-\pi^{2}n^{2},\hspace{2px}n=1,2,3,\dots, \\
> \text{eigenvectors: }& u_{n}(x)= A_{n}\left[ x^{i\pi n}-x^{-i\pi n} \right] =2iA_{n}\sin(\pi n\ln(x)).
> \end{align}$$
> Note that the functions $u_{n}(x)\in V$, satisfying the Dirichlet boundary conditions, and so also satisfying the more general constraints on boundary conditions for the Sturm-Liouville problem. Since $\hat{L}$ is Hermitian, by the spectral theorem we know that the set of eigenfunctions $\{ u_{n}(x) \}$ can be normalized by a suitable choice of the constant $A_{n}$ to become an orthonormal basis of $V$. This also allows us to construct Green's function to solve inhomogenous equations of the form $\hat{L}\hspace{2px}u(x)-\lambda\hspace{2px}u(x)=g(x)$. 

