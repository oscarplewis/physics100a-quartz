---
tags:
  - Physics100A
  - 100ANotes
---
---
### The Legendre Equation

> [!example] Legendre's Differential Equation
> ***Legendre's differential equation*** is:
> $$
> (1-x^{2}) y''-2xy' -\lambda y=0.
> $$
^576ebd

We are seeking solutions $y(x)$ to this differential equation on the interval $-1\leq x\leq x$. We can write this in the following manner:
$$
\begin{align}
\hat{L}y & =0, \\
\hat{L} & = (1-x^{2}) \frac{d^{2}}{dx^{2}}-2x\frac{d}{dx} .
\end{align}
$$
And so this becomes an eigenvalue/Sturm-Liouville problem for the differential operator $\hat{L}$. We then define the weight function for the inner product to be:
$$
w(x)=1.
$$
So we define our inner product as
$$
\braket{ f | g } = \int_{-1}^{1} f^{*}(x)g(x) \, \hspace{0.5mm} dx ,
$$
for which the linear operator $\hat{L}$ is Hermitian. We also must specify the boundary conditions which determines the space of functions on which $\hat{L}$ acts. The most general condition is:
$$
\left[ w\alpha(f^{*}g'-gf'^{*}) \right] \biggr |_{a}^{b}=(1-x^{2})(f^{*}g'-gf'^{*})\biggr |_{-1}^{1}=0.
$$
This is actually universally true for this operator, since $(1-x^{2})=0$ for $x=\pm {1}$. So, [[Active Learning Master List#Legendre Boundary Conditions|the boundary condition constraints are satisfied]] *for all functions $f$ such that $f$ and $f'$ are both finite at $x=\pm 1$*.

> [!summary] Legendre Equation
> The differential operator
> $$
> \hat{L}=(1-x^{2}) \frac{d^{2}y}{dx^{2}}-2x\frac{dy}{dx},
> $$
> is Hermitian with the inner product
> $$
> \braket{ y_{1} | y_{2} } = \int_{-1}^{1} y_{1}^{*}(x)y_{2}(x) \, \hspace{0.5mm} dx ,
> $$
> acting on the vector space of $V$ of functions $y(x)$ which are smooth on the interval $-1\leq x\leq 1$ and which are finite and have finite first derivatives at the endpoints $x=\pm 1$. The ***Legendre equation*** is the eigenvalue equation
> $$
> \hat{L}\hspace{2px}y(x)=\lambda\hspace{2px}y(x),
> $$
> in $V$. 

^e942b4

### Solving the Legendre Equation

To solve this, we take two steps.

> [!summary] Solving the Sturm-Liouville Problem
> The solution to the eigenvalue problem is broken up into two steps.
> 1. Find the general solution to the ODE irrespective of boundary conditions.
> 2. Impose boundary conditions which determines the allowed eigenvalues and associated eigenvectors.

#### Step 1

We can use the [[Power Series Method#^ca8439|power series method]] to solve this differential equation. First let's write Legendre's equation in the following form.
$$
y''(x)+f_{1}(x)y'(x)+f_{0}(x)y(x)=0,
$$
^156908

for $f_{1}(x)=-\frac{2x}{1-x^{2}}$ and $f_{0}(x)=-\frac{\lambda}{1-x^{2}}$. 

First let's discuss the general case, for undetermined $f_{1}(x)$ and $f_{0}(x)$.

> [!example] Ordinary Points
> The point $x_{0}$ is an ***ordinary point*** of the differential equation if $f_{1}(x)$ and $f_{2}(x)$ can both be expanded in a Taylor series about $x_{0}$.

Let's first discuss this generally. We can use the power series method to find the solution $y(x)$ near any of the ordinary points. Let's use $x_{0}=0$. If $f_{1}$ and $f_{0}$ have a Taylor series expansion around $x_{0}=0$, then the expansion of the general solution is likewise power series around $x_{0}=0$. In other words, if $x_{0}$ is an ordinary point for $f_{1}$ and $f_{0}$ then it is an ordinary point for $y$. We can then proceed to solve for the coefficients of $y$.

Returning to the specific case of the Legendre equation, let $y(x)=\sum_{n=0}^{\infty}a_{n}x^{n}$. Substituting this into [[#^156908]], we have:
$$
\sum_{n=2}^{\infty} n(n-1)a_{n}x^{n-2}+f_{1}(x)\sum_{n=1}^{\infty} na_{n}x^{n-1}+f_{0}(x)\sum_{n=0}^{\infty} a_{n}x^{n}=0.
$$
Recall that $f_{1}(x)=-\frac{2x}{1-x^{2}}$ and $f_{0}(x)=-\frac{\lambda}{1-x^{2}}$. If we substitute these in and multiply through by $1-x^{2}$, we have
$$
\sum_{n=2}^{\infty} n(n-1)a_{n}x^{n-2}-\sum_{n=2}^{\infty} n(n-1)a_{n}x^{n}-2\sum_{n=1}^{\infty} na_{n}x^{n}-\lambda \sum_{n=0}^{\infty} a_{n}x^{n}=0.
$$
We can make an index substitution here. In the first term we take $n\to n+2$, in the second term we note that the $n=0$ and $n=1$ terms vanish, and in the third we note that the $n=0$ term vanishes. We then get:
$$
\sum_{n=0}^{\infty} \biggr [ (n+2)(n+1)a_{n+2}+(-n(n+1)-\lambda)a_{n} \biggr ]x^{n}=0.
$$
This equation must be satisfied for all $-1\leq x\leq 1$, so the coefficients for all $n$ must vanish (because the monomials $x^{n}$ are linearly independent). So:
$$
(n+2)(n+1)a_{n+2}-\left[ n(n+1)+\lambda \right] a_{n}=0,
$$
for all $n=0,1,2,\dots.$ We choose to parameterize the eigenvalue $\lambda$ by 
$$
-\lambda=l(l+1).
$$
Substituting this in, we rearrange the coefficient formula to get:
$$
a_{n+2}=\frac{(n+l+1)(n-l)}{(n+1)(n+2)}a_{n}.
$$
^e31861

This is called a ***recursion relation***. We can calculate the first few values of this, finding in the end that the most general solution is the following.
$$
\begin{align}
y(x) & = y_{\mathrm{even}}(x)+y_{\mathrm{odd}}(x), \\
& = a_{0}\left[ 1-\frac{l(l+1)}{2!}x^{2}+\frac{(l-2)(l)(l+1)(l+3)}{4!}x^{4}-\dots \right]  \\
 & \hspace{0.5in} + a_{1}\left[ x-\frac{(l-1)(l+2)}{3!}x^{3}+\frac{(l-3)(l-1)(l+2)(l+4)}{5!}x^{5}-\dots \right] .
\end{align}
$$
^8096b2

We must check for which values of $x$ the series converges. We find the "radius of convergence" by the [[Basics of Series Expansions#^bac49d|ratio test]], for each particular odd and even series, [[Active Learning Master List#Convergence of Legendre Power Series Solutions|here]].
#### Step 2

Now we proceed to step two, finding solutions in the form of [[#^8096b2]] which are finite and have finite derivatives at $x=\pm 1$. 

The convergence at $x=\pm 1$ is more subtle. We can use Gauss's Test (see e.g. [Arfkin & Weber](https://msashigri.wordpress.com/wp-content/uploads/2016/11/methods-of-mathemacial-for-physicists.pdf)) which states that the even and odd series in [[#^8096b2]] are divergent at $x=\pm 1$ unless they terminate (have a a finite number of terms).

> [!tip] Crucial Point
> The boundary condition requires that the functions and their derivatives are finite at $x= \pm 1$. For the even and odd series, this will only happen if the series terminates by Gauss's test. We will see below that this restricts the eigenvalues to a discrete set of values. In other words, the eigenvalues are ***quantized***.

Recall the recursion relation, [[#^e31861]]:
$$
a_{n+2}=\frac{(n+l+1)(n-l)}{(n+1)(n+2)}a_{n}.
$$
If $n$ is even, then we start with $a_{0}\in \mathbb{C}$, and let $n=0,2,4,\dots$. The recursion relation gives us all the even coefficients. If $n$ is odd, then we start with $a_{1}\in \mathbb{C}$ and let $n=1,3,5,\dots$. The recursion relation gives us all the odd coefficients. 

The eigenvalue is $\lambda=-l(l+1)$. The termination of the series puts restrictions on $l$, such that somewhere along the line there will be some $N$ such that $a_{n}=0$ for $n>N$. 

**(A)** Consider $l\in 2\mathbb{Z}_{\geq 0}$. Then we substitute $n=l$ into the recursion relation and find:
$$
a_{l+2}=\frac{(2l+1)(l-l)}{(l+1)(l+2)}a_{l}=0,
$$
and consequently $a_{l+4},a_{l+6},\dots=0$. 
$$
y_{\mathrm{even}}(x)=a_{0}+a_{2}x^{2}+\dots+a_{l}x^{l}.
$$
That is, the even series is a polynomial of degree $l$. Thus the even series terminates. However, the odd series does not, so in order for $y(x)$ to terminate the all the odd coefficients must vanish. That is, we set $a_{1}=0$ to satisfy the boundary conditions, and we're left with
$$
y(x)=a_{0}+a_{2}x^{2}+\dots+a_{l}x^{l}.
$$

**(B)** Now consider $l\in (2\mathbb{Z}+1)_{\geq 0}$. In this case, the odd series terminates but the even does not, so we set $a_{0}=0$ to satisfy the boundary conditions, and
$$
y(x)=a_{1}x+a_{3}x^{3}+\dots+a_{l}x^{l}.
$$

**(C)** Now consider $l\in \mathbb{Z}_{<0}$. In the recursion relation, the term $(n+l+1)$ can be zero if $l<0$, which can cause termination of the series. Let $\bar{l}=-l-1$ (equivalently, $l=-\bar{l}-1$). Explicitly,
$$
\begin{align}
l & =-1,-2,-3,-4,\dots =\text{integers }<0, \\
\bar{l} & =0,1,2,3,\dots=\text{integers }\geq 0.
\end{align}
$$
This reduces the case where $l$ is a negative integer to the cases we just discussed (A and B_ where $l$ is a nonnegative integer. Upon $l\to \bar{l}$, the recursion relation becomes
$$
a_{n+2}=\frac{(n-\bar{l})(n+\bar{l}+1)}{(n+1)(n+2)}a_{n}.
$$
So the recursion relation looks the same if we replace $l\geq0$ with $l<0$ ($\bar{l}\geq 0$). Hence we obtain
$$
\begin{align}
y_{\mathrm{even}}(x) & =a_{0}+a_{2}x^{2}+\dots+a_{\bar{l}}x^{\bar{l}}=a_{0}+a_{2}x^{2}+\dots+a_{-l-1}x^{-l-1}\hspace{2px}(\text{for even }\bar{l}), \\
y_{\mathrm{odd}}(x) & = a_{1}x+a_{3}x^{3}+\dots+a_{\bar{l}}x^{\bar{l}}=a_{1}x+a_{3}x^{3}+\dots+a_{-l-1}x^{-l-1}\hspace{2px}(\text{for odd }\bar{l}).
\end{align}
$$

^14e01b

This completes our discussion of integer $l$.

**(D)** When $l$ is not an integer, then neither the even nor the odd series converges, so the boundary conditions are not satisfied for non-integer $l$, and there exists no solution to Legendre's equation for these eigenvalues (the only solution is the trivial case, which by definition cannot be an eigenvector).
### Conclusion and Ramifications

> [!summary] Conclusion
> The [[#^e942b4|Legendre differential operator]]
> $$
> \hat{L}=(1-x^{2}) \frac{d^{2}}{dx^{2}}-2x\frac{d}{dx} ,\hspace{20px}-1\leq x\leq 1,
> $$
> is Hermitian with respect to the inner product
> $$
> \braket{ f | g } = \int_{-1}^{1} f^{*}(x)g(x) \, \hspace{0.5mm} dx ,
> $$
> for the vector space $V$ of finite smooth functions with finite first derivatives on the interval $-1\leq x\leq 1$. The [[Eigenvectors and Eigenvalues#^9df0a3|spectrum]] of $\hat{L}$ is
> $$
> \lambda=-l(l+1),\hspace{20px}l=0,1,2,\dots,
> $$
> and the eigenfunctions are $y_{\mathrm{even}}(x)$ or $y_{\mathrm{odd}}(x)$ from [[#^14e01b]] depending on whether $l$ is even or odd, are are an even or odd polynomial of degree $l$. 

If we choose the arbitrary constants $a_{0}$ and $a_{1}$ in such a way that
$$
y_{\mathrm{even}}(1)=1,\hspace{2px}y_{\mathrm{odd}}(1)=1,
$$
then the solutions are the Legendre polynomials. 
$$
P_{l}(x)=\begin{cases}
y^{\mathrm{even}}_{l}(x), & l=0,2,4,\dots, \\
y^{\mathrm{odd}}_{l}(x), & l=1,3,4,\dots,
\end{cases}
$$
such that $P_{l}(1)=1$ (the normalization factor). As discussed above, negative values of $l$ merely duplicate the positive and zero indexed functions. The first few are:
$$
\begin{align}
l=0,-1 & : P_{0}(x)=P_{-1}(x)=1, \\
l=1,-2 & : P_{1}(x)=P_{-2}(x)=x, \\
l=2,-3 & : P_{2}(x)=P_{-3}(x)=\frac{1}{2}(3x^{2}-1), \\
l=3,-4 & : P_{3}(x)=P_{-4}(x)=\frac{1}{2}(5x^{3}-3x), \\
 &\hspace{5px}\vdots
\end{align}
$$

> [!tip] An Interesting Thing
> Note that we got these before using Gram-Schmidt procedure to construct orthogonal polynomials from the nonorthogonal basis of monomials $\{ 1,x,x^{2},\dots \}$ simply by specifying the weight function ($w(x)=1$) and the interval ($-1\leq x\leq 1$). Instead, we automatically know that these are orthogonal by the [[Eigenvectors and Eigenvalues#^7d228b|spectral theorem for Hermitian operators]].

In summary (again):
$$
\hat{L}P_{l}(x)=\lambda_{l}P_{l}(x)=-l(l+1)P_{l}(x),
$$
with the inner product
$$
\braket{ P_{l} | P_{m} } =\int_{-1}^{1} P_{l}^{*}(x)P_{m}(x) \, \hspace{0.5mm} dx =0 \text{ for }l\neq m.
$$
We will show [[#Normalization Factor of Legendre Polynomials|later]] that
$$
\braket{ P_{l} | P_{l} } =\int_{-1}^{1} P_{l}^{*}(x)P_{l}(x) \, \hspace{0.5mm} dx =\frac{2}{2l+1}.
$$
This allows us to generalize a form of the normalized Legendre polynomials $\rho_{l}(x)$:
$$
\rho_{l}(x)=\sqrt{ \frac{2l+1}{2} }P_{l}(x),
$$
such that $\braket{ \rho_{l} |\rho_{m}  }=\delta_{lm}$. 

> [!tip] ON Basis!
> We now have an orthonormal basis of eigenvectors of the [[#^e942b4|Legendre differential operator]] on the vector space of functions $y(x)$ on the interval $-1\leq x\leq 1$ which are at least twice differentiable and are finite at the endpoints $x=\pm 1$ and have finite derivatives there.

We can then do all the things we can do with an orthonormal basis. The completeness relation:
$$
\hat{I}=\sum_{n=0}^{\infty} \ket{\rho_{n}} \bra{\rho_{n}}.
$$
Spectral decomposition:
$$
\hat{L}=-\sum_{l=0}^{\infty} l(l+1)\ket{\rho_{l}} \bra{\rho_{l}} .
$$
Expansion of other functions in the vector space:
$$
\ket{y} = \sum_{l=0}^{\infty} \braket{ \rho_{l} | y } \ket{\rho_{l}} .
$$
Green's function:
$$
y(x)=\sum_{l=0}^{\infty} \frac{\rho_{l}(x)}{-l(l+1)-\gamma}\int_{-1}^{1} \rho_{l}^{*}(t)g(t) \, \hspace{0.5mm} dt 
$$

> [!example] Legendre Series
> A series expansion of the solution $y(x)$ obtained from Green's function is called a ***Legendre series***.

### Rodrigues' Formula

This is a compact way to find all Legendre polynomials in closed form.

> [!example] Leibniz's Rule of Products
> Let $f_{1}$ and $f_{2}$ be functions of $x$. Then the $n$-th derivative of $f_{1}\cdot f_{2}$ is given by:
> $$
> \frac{d^{n}}{dx^{n}}\left[ f_{1}(x)f_{2}(x) \right] = \sum_{m=0}^{n} \begin{pmatrix}
> n \\
> m
> \end{pmatrix} \frac{d^{m}f_{1}}{dx^{m}} \frac{d^{n-m}f_{2}}{dx^{n-m}}.$$
^75178c

We can use this to find solutions to [[#^e942b4|Legendre's equation]] for $\lambda=-l(l+1)$. 

> [!claim]
> Let $g(x)=(x^{2}-1)^{l}$. Then $\psi_{l}(x)= \frac{d^{l}g(x)}{dx^{l}}$ satisfies Legendre's differential equation.
^692ddb

`\begin{proof}`First differentiate $g(x)$ with respect to $x$.
$$
\frac{dg(x)}{dx}=l(x^{2}-1)^{l-1}(2x),
$$
by definition of $g(x)$. Now we multiply this by $x^{2}-1$:
$$
(x^{2}-1) \frac{dg}{dx}=2lx\hspace{2px}g(x).
$$
We differentiate both sides of this $n=l+1$ times using Leibniz's rule. Note that all derivatives greater than third order vanish.
$$
\frac{d^{l+1}}{dx^{l+1}}\left[ (x^{2}-1) \frac{dg}{dx} \right] =(x^{2}-1) \frac{d^{l+2}g(x)}{dx^{l+2}}+(l+1)(2x) \frac{d^{l+1}g(x)}{dx^{l+1}}+l(l+1) \frac{d^{l}g(x)}{dx^{l}}.
$$
Differentiating the right hand side similarly, noting that all derivatives greater than first order vanish, we have:
$$
\frac{d^{l+1}}{dx^{l+1}}\left[ 2lx\hspace{2px}g(x) \right] = 2lx \frac{d^{l+1}g(x)}{dx^{l+1}} + 2l(l+1) \frac{d^{l}g}{dx^{l}}.
$$
We can equate the left and right hand sides of the equation, and combining like orders of derivatives, we obtain:
$$
(x^{2}-1)\left( \frac{d^{l}g}{dx^{l}} \right)''+2x\left( \frac{d^{l}g}{dx^{l}} \right)'-l(l+1)\left( \frac{d^{l}g}{dx^{l}} \right) =0.
$$
This is [[#^576ebd|Legendre's equation]] with a factor of $-1$. We thus conclude that the functions $\psi_{l}(x)=\frac{d^{l}g}{dx^{l}}$ with $g(x)=(x^{2}-1)^{l}$ satisfy Legendre's equation.`\end{proof}`


> [!claim] Rodrigues' Formula
> The functions $\psi_{l}(x)=\frac{d^{l}}{dx^{l}}(x^{2}-1)^{l}$ from [[#^692ddb]] are proportional to the Legendre polynomials $P_{l}(x)=\kappa_{l} \frac{d^{l}}{dx^{l}}(x^{2}-1)^{l}$, where $\kappa_{l}=\frac{1}{2^{l}\hspace{2px}l!}$. 
^claim2

Note that with this choice of $\kappa_{l}$ then the Legendre polynomials satisfy the normalization condition $P_{l}(1)=1$. 

`\begin{proof}[Proof of [[#^claim2]].]`We can see that
$$
\psi_{l}(x)=\frac{d^{l}}{dx^{l}}\left[ \underbrace{ (x^{2}-1)(x^{2}-1)\dots(x^{2}-1) }_{ l\text{ times} }  \right] ,
$$
is clearly a polynomial of degree $l$ (since the bracketed term is a polynomial of degree $2l$, which is then differentiated $l$ times). We established earlier that Legendre's equation has *precisely one* solution (up to an overall multiplicative constant) for every $l=0,1,2,\dots$ which is of the form of a polynomial of degree $l$. Further we know from [[#^692ddb]] that $\psi_{l}(x)$ is a solution of the Legendre equation. Hence $P_{l}(x)=\kappa_{l}\psi_{l}(x)$, for some constant $\kappa_{l}$, the choice of which comes from the normalization at $x=1$. `\end{proof}`

> [!example] Rodrigues' Formula
> The equations
> $$
P_{l}(x)=\frac{1}{2^{l}\hspace{2px}l!} \frac{d^{l}}{dx^{l}}\left[ (x^{2}-1)^{l} \right] ,$$
>are called Rodrigues' formula. This yields an explicit formula for all of the Legendre polynomials.

^981879

### Generating Function for Legendre Polynomials

All Legendre polynomials and many of their properties can be compactly expressed in terms of a [[Generating Functions#^ab3c81|generating function]]. It is a function of two variables for Legendre polynomials.
$$
\Phi(x,h)=(1-2xh+h^{2})^{-1/2},\hspace{2px}\text{for }\left| x \right| \leq 1\text{ and }\left| h \right| \leq 1.
$$

> [!claim]
> The series expansion of the generating function $\Phi(x,h)$ is
> $$
> \Phi(x,h)=P_{0}(x)+hP_{1}(x)+h^{2}P_{2}(x)+\dots,
> $$
> where $P_{l}(x)$ is the $l$-th Legendre polynomial with normalization $P_{l}(1)=1$. 

`\begin{proof}`Let $y=2xh-h^{2}$. Then we can write $\Phi(x,h)=(1-y)^{-1/2}$. We can recall the generalized binomial series, which states that for some complex number $z$:
$$
(1-z)^{s}=\sum_{n=0}^{\infty} \frac{s(s-1)\dots(s-n+1)}{n!}z^{n},
$$
which converges for $\left| z \right|<1$. We can use this to expand $\Phi$ in powers of $h$:
$$
\phi(x,h)=\sum_{l=0}^{\infty} h^{l}a_{l}(x).
$$
^someequation

We know from the binomial theorem that $a_{l}(x)$ is a polynomial. Since the solution to Legendre's equation is unique, that means that if $a_{l}(1)=1$ then it is implied that $a_{l}(x)=P_{l}(x)$ if indeed $a_{l}(x)$ is a solution to Legendre's equation.
$$
\begin{align}
\Phi(1,h)=(1-2h+h^{2})^{-1/2}=\frac{1}{1-h}=\sum_{l=0}^{\infty} h^{l}.
\end{align}
$$
This matches [[#^someequation]] for $a_{l}(1)=1$. We then can make the rather simple calculation showing that $\Phi(x,h)$ satisfies:
$$
(1-x^{2})\frac{ \partial^{2} \Phi }{ \partial x^{2} } -2x\frac{ \partial \Phi }{ \partial x } +h\frac{ \partial^{2} (h\Phi) }{ \partial h^{2} } =0.
$$
Substituting in [[#^someequation]], we have
$$
(1-x^{2})\left[ \sum_{l=0}^{\infty} h^{l}a_{l}''(x) \right]-2x\left[ \sum_{l=0}^{\infty} h^{l}a_{l}'(x) \right] +\underbrace{ h\left[ \sum_{l=0}^{\infty} \frac{ \partial^{2}  }{ \partial h^{2} } (h^{l+1}a_{l}(x)) \right] }_{ \chi }  =0.
$$
The expression $\chi$ above is 
$$
\chi=h\sum_{l=0}^{\infty} l(l+1)h^{l-1}a_{l}(x)=\sum_{l=0}^{\infty} l(l+1)h^{l}a_{l}(x).
$$
Combining the coefficients of like powers, we have
$$
(1-x^{2})a_{l}''(x)-2xa_{l}(x)+l(l+1)a_{l}(x)=0,
$$
which is Legendre's equation. Therefore $a_{l}(x)$ is a solution to Legendre's equation, and $a_{l}(x)=P_{l}(x)$.`\end{proof}`

This means that $\Phi$ is a generating function for the Legendre polynomials.


> [!example] Legendre Generating Function
> The generating function for the Legendre polynomials is
> $$
\Phi(x,h)=(1-2xh+h^{2})^{-1/2}=\sum_{l=0}^{\infty} P_{l}(x)\hspace{2px}h^{l}.$$

### Recurrence Relations for Legendre Polynomials

From the generating function we can derive a recurrence relation (a relation between two different Legendre polynomials; essentially a generalization of trig identities). If we differentiate the left hand side of the generating function with respect to $h$, we have
$$
(1-2xh+h^{2})\frac{ \partial \Phi }{ \partial h } =(x-h)\Phi.
$$
Inserting the expression for $\Phi$ in terms of the Legendre polynomials:
$$
(1-2xh+h^{2})\sum_{l=1}^{\infty} lh^{l-1}P_{l}(x)=\sum_{l=0}^{\infty} (x-h)h^{l}P_{l}(x).
$$
This is going to get rather nasty rather quickly. We can move both terms to the right hand side as follows:
$$
\sum_{l=1}^{\infty} \biggr [ \underbrace{ lh^{l-1}P_{l} }_{ \mathrm{A} } -\underbrace{ 2xlh^{l}P_{l} }_{ \mathrm{B} } +\underbrace{ lh^{l+1}P_{l} }_{ \mathrm{C} }  \biggr ]-\sum_{l=0}^{\infty} \biggr [ \underbrace{ xh^{l}P_{l} }_{ \mathrm{D} } -\underbrace{ h^{l+1}P_{l} }_{ \mathrm{E} }  \biggr ]=0.
$$
We can now do a few things:
- We make the substitution $l'=l-1$ in term A, and group it by itself to create term A'. 
- We note that if we extend the series to $l=0$, then term B is unchanged. We can then group it with term D to create term B'. 
- We note that if we extend the series to $l=0$, then term C is unchanged. We can then group it with term E to create term C'.

Combining all of these, we have:
$$
\underbrace{ \sum_{l'=0}^{\infty} (l'+1)h^{l'}P_{l'+1} }_{ \mathrm{A'} } -\underbrace{ \sum_{l=0}^{\infty} x(2l+1)h^{l}P_{l} }_{ \mathrm{B'} } +\underbrace{ \sum_{l=0}^{\infty} (l+1)h^{l+1}P_{l} }_{ \mathrm{C'} } =0.
$$
Let's do a few more things.
- We can pull out the $l'=0$ term from term A' and the $l=0$ term from term B', combining them to create term A''. 
- We can make the index substitution $l'\to l$ on the terms $l>0$ from term A', creating term B''.
- We can take the terms $l>0$ from term B', creating term C''. 
- Finally, from term C' we make the substitution $l'=l+1$ and then rebrand the index $l'\to l$, creating term D''.

Combining all of these, we have
$$
\underbrace{ h^{0}(P_{1}-xP_{0}) }_{ \mathrm{A''} } -\sum_{l=1}^{\infty} \biggr [ \underbrace{ (l+1)P_{l+1} }_{ \mathrm{B''} } -\underbrace{ x(2l+1)h^{l}P_{l} }_{ \mathrm{C''} } +\underbrace{ lP_{l-1} }_{ \mathrm{D''} }  \biggr ]h^{l}=0.
$$
The power $h^{l}$ are linearly independent, so this requires that all the coefficients vanish.
$$
\begin{align}
l=0 & : P_{1}-xP_{0}=0, \\
l\geq 1 & : (l+1)P_{l+1}-x(2l+1)P_{l}+lP_{l-1}=0.
\end{align}
$$
If we make the substitution $l\to l-1$ in the second equation, we have:
$$
l\geq 2: lP_{l}-x(2l-1)P_{l-1}+(l-1)P_{l-2}=0.
$$
This is a recursion relation for Legendre polynomials, letting us get $P_{l}$ from $P_{l-1}$ and $P_{l-2}$. It also functions as a useful identity, similar to trigonometric identities.

Here are also a bunch of useful recursion relations.

> [!tip] Useful Legendre Recurrence Relations
> 1. $lP_{l}=(2l-1)xP_{l-1}-(l-1)P_{l-2}$.
> 2. $xP_{l}'-P_{l-1}'=lP_{l}$.
> 3. $P_{l}'-xP_{l-1}'=lP_{l-1}$.
> 4. $(1-x^{2})P_{l}'=lP_{l-1}-lxP_{l}$.
> 5. $(2l+1)P_{l}=P_{l+1}'-P_{l-1}'$.
> 6. $(1-x^{2})P_{l-1}'=lxP_{l-1}-lP_{l}$.
^recursion

### Explicit Expression for $P_{l}(0)$ at from the Generating Function

On one hand, $\Phi(x,h)=\sum_{l=0}^{\infty}h^{l}P_{l}(x)$ (series expansion). One the other hand, $\Phi(x,h)=(1-2xh+h^{2})^{-1/2}$ (definition). Equating these at $x=0$ gives:
$$
\begin{align}
\Phi(0,h)=\sum_{l=0}^{\infty} h^{l}P_{l}(0) & =(1+h^{2})^{-1/2}, \\
 & = \sum_{n=0}^{\infty} \frac{\left( -\frac{1}{2} \right)\left( -\frac{3}{2} \right)\left( -\frac{5}{2} \right)\dots\left( -\frac{1}{2}-n+1 \right)}{n!}h^{2n}.
\end{align}
$$
More explicitly, the $n$-th term in the right-hand side series is
$$
\frac{(-1)^{2n/2}(2n-1)!!}{2^{2n/2}\left( \frac{2n}{2} \right)!}.
$$
Hence we conclude:
$$
P_{l}(0)=\begin{cases}
0, & l=\mathrm{odd,} \\
\frac{(-1)^{l/2}(l-1)!!}{2^{l/2}\left( \frac{l}{2} \right)!},& l=\mathrm{even.}
\end{cases}
$$

### Geometric Interpretation of the Legendre Generating Function

> [!warning] This is very important in certain physics problems.
> 

Consider two vectors $\vec{r}$ and $\vec{r}'$ in $\mathbb{R}^{3}$. Consider:
$$
\frac{1}{\left| \vec{r}-\vec{r}' \right| }=\frac{1}{\sqrt{ r^{2}+r'^{2}-2rr'\cos\theta }}=\frac{1}{r} \frac{1}{\sqrt{ 1-2\left( \frac{r'}{r} \right)\cos\theta+\left( \frac{r'}{r} \right)^{2}  }}.
$$
This problem comes up a lot in $\frac{1}{R}$ potentials, as this is the reciprocal of the distance between two objects. Let $h=\frac{r'}{r}<1$, $x=\cos\theta$. Then we can write this using the generating function for Legendre polynomials.
$$
\frac{1}{\left| \vec{r}-\vec{r}' \right| }=\frac{1}{r\sqrt{ 1-2xh+h^{2} }}=\frac{1}{r}\Phi(x,h),\hspace{2px}\text{ for }x=\cos\theta,h=\frac{r'}{r}(r'<r).
$$
![[Screenshot 2024-05-17 at 14.23.37.png|200]]

This then becomes
$$
\frac{1}{\left| \vec{r}-\vec{r}' \right| }=\sum_{l-0}^{\infty} \frac{(r')^{l}}{r^{l+1}}P_{l}(\cos\theta).
$$
When $r<r'$ we can repeat this calculation with $r$ and $r'$ exchanged.
$$
\frac{1}{\left| \vec{r}'-\vec{r} \right| }=\sum_{l=0}^{\infty} \frac{r^{l}}{(r')^{l+1}}P_{l}(\cos\theta).
$$
### Normalization Factor of Legendre Polynomials

Our aim for this section is to evaluate $\braket{ P_{l} | P_{l} }=\int_{-1}^{1} \left| P_{l}(x) \right|^{2} \, \hspace{0.5mm} dx$. We begin with the [[#^recursion|second recursion relation]], which can be derived from the generating function and the equation
$$
(x-h)\frac{ \partial \Phi }{ \partial x } =h\frac{ \partial \Phi }{ \partial h } .
$$
This relation is
$$
lP_{l}(x)=xP_{l}'(x)-P_{l-1}'(x).
$$
Multiplying both sides by $P_{l}(x)$ and integrating, we have
$$
l\int_{-1}^{1} P_{l}(x)^{2} \, \hspace{0.5mm} dx = \int_{-1}^{1} xP_{l}(x)P_{l}'(x) \, \hspace{0.5mm} dx -\int_{-1}^{1} P_{l}(x)P_{l-1}'(x) \, \hspace{0.5mm} dx .
$$
The last term is zero because we know that the equations $P_{l}(x)$ and $P_{l-1}'(x)$ are orthogonal. So, using integration by parts, we can find
$$
l\int_{-1}^{1} P_{l}(x)^{2} \, \hspace{0.5mm} dx = 1-\frac{1}{2}\int_{-1}^{1} P_{l}(x)^{2} \, \hspace{0.5mm} dx ,
$$
which implies
$$
\braket{ P_{l} | P_{l} } \int_{-1}^{1} P_{l}(x)^{2} \, \hspace{0.5mm} dx =\frac{2}{2l+1}.
$$
### Misc. Properties
The following is given as Equation (7.6) in Boas, and is a property of the Legendre polynomials.
$$
\int_{-1}^{1} P_{l}(x)\cdot (\text{any polynomial of degree $<l$}) \, \hspace{0.5mm} dx =0.
$$