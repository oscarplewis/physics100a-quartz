---
tags:
  - 100ANotes
  - Physics100A
---
---
Behold, the Laplacian.
$$
\begin{align}
\nabla^{2}=\frac{ \partial^{2}  }{ \partial x^{2} } +\frac{ \partial^{2}  }{ \partial y^{2} } +\frac{ \partial^{2}  }{ \partial z^{2} } .
\end{align}
$$
Examples:
1. Laplace's equation: $\nabla^{2}\phi=0$.
2. Poisson's equation: $\nabla^{2}\phi=\rho$.
3. Heat diffusion equation: $\nabla^{2}u=\frac{1}{\alpha^{2}}\frac{ \partial u }{ \partial t }$.
4. Schrödinger's equation: $-\frac{\hbar^{2}}{2m}\nabla^{2}\Psi+V(\vec{r},t)=i\hbar \frac{ \partial \Psi }{ \partial t }$.
5. Wave equation: $\nabla^{2}\Psi=\frac{1}{c^{2}}\frac{ \partial^{2} \Psi }{ \partial t^{2} }$.
6. Helmholtz equation: $\nabla^{2}F+\kappa^{2}F=0$.

### Separation of Variables: The 2D Diffusion Equation

We will demonstrate the process of *separation of variables* for solving the diffusion equation in two dimensions.

![[Screenshot 2024-05-22 at 08.17.03.png|400]]

Consider this system. Let $u(x,y,t)$ be the temperature of the plate at position $(x,y)$ at time $t$. We need to solve the differential equation
$$
\nabla^{2}u=\frac{1}{\alpha^{2}} \frac{ \partial u }{ \partial t } ,
$$
for some real number $\alpha$. This gives us the temperature of the plate given an initial condition $u_{0}(x,y)$ at $t=0$. We further subject $u$ to the boundary conditions $u(a,y,t)=u(x,b,t)=0$. 

Separation of variables means we desire to find a solution of the form
$$
u(x,y,t)=f(x,y)\tau(t),
$$
which is called *separable*. Substituting this into the heat diffusion equation yields
$$
\tau(t)\nabla^{2}f(x,y)=\frac{1}{\alpha^{2}}f(x,y)\frac{ d \tau }{ d t } .
$$
Dividing by $f(x,y)\tau(t)$ gives us
$$
\frac{1}{f}\nabla^{2}f=\frac{1}{\alpha^{2}\tau} \frac{d\tau}{dt}.
$$
Since each side of the equation is dependent on different independent variables, in order for the equation to be true both sides must equal a constant, say $-k^{2}$ (called the *separation constant*, which is negative purely by convention). This allows us to separate these equations:
$$
\begin{align}
\frac{1}{\alpha^{2}\tau} \frac{d\tau}{dt} & =-k^{2}, \\
\frac{1}{f}\left[ \frac{ \partial^{2} f }{ \partial x^{2} } +\frac{ \partial^{2} f }{ \partial y^{2} }  \right]  & = -k^{2}.
\end{align}
$$
^764bf4

[[#^764bf4|Eqn(1-1)]] is easily integrated, and we find
$$
\tau(t)=e^{ -\alpha^{2}k^{2}t }.
$$
^af5acd

Note that there are no boundary conditions for the time component of $u$.

> [!tip] What is $k$?
> Up to this point, $k$ could have been any complex number, mathematically speaking. Physically, though, we expect that the longer we wait the cooler the plate will get at any point $(x,y)$. We can clearly see then from [[#^af5acd]] that if $k$ is a positive real number, then the plate will cool down as time progresses. (If $k$ is imaginary, then $k^{2}<0$ and the plate would heat up over time.) 

Onto [[#^764bf4|Eqn(1-2)]]! The rectangular geometry of the problem (plate and boundary conditions) suggests the independence of $x$ and $y$, so we can try separation of variables in $x$ and $y$.
$$
f(x,y)=\chi(x)\phi(y).
$$
Inserting this into [[#^764bf4|Eqn(1-2)]] and doing some manipulation gives us
$$
\frac{\chi''}{\chi}+\frac{\phi''}{\phi}=-k^{2}.
$$
As before, this is only satisfied if each term equals a constant. So we can break it up into two equations:
$$
\begin{align}
\chi''(x) & =-k_{x}^{2}\chi(x), \\
\phi''(y) & = -k_{y}^{2}\phi(y),
\end{align}
$$
^695fc6

each of which is easily integrable. Note that $k_{x}^{2}+k_{y}^{2}=k^{2}$, where $k_{x}$ and $k_{y}$ will be determined by the boundary conditions. The boundary conditions themselves transfer over rather easily:
$$
\begin{align}
\chi(0) & =\chi(a)=0, \\
\phi(0) & =\phi(b)=0.
\end{align}
$$
^d80d62

> [!tip] Using Separation of Variables
> Essentially the goal of separation of variables is to reduce a multivariable partial differential equation to some number of Sturm-Liouville problems with ordinary differential equations for each independent variable.

Together, [[#^695fc6]] and [[#^d80d62]] represent the simplest [[Sturm-Liouville Problems#^364905|Sturm-Liouville problem]], for the differential operator $\hat{L}_{x}=\frac{d^{2}}{dx^{2}}$ (henceforth we shall solve [[#^695fc6|Eqn(3-1)]] because the solution to [[#^695fc6|Eqn(3-2)]] is identical). We know that $\hat{L}_{x}$ is Hermitian with respect to the usual inner product with weight function $w=1$. We now have the [[Eigenvectors and Eigenvalues#^56e47a|eigenvalue]] problem
$$
\hat{L}_{x}\chi(x)=-k_{x}^{2}\chi(x),\hspace{2px}0\leq x\leq a,
$$
where $\chi(x)$ satisfies [[Sturm-Liouville Problems#^40d5d0|Dirichlet boundary conditions]] at the endpoints. We will omit the solution's derivation here. The eigenvalues are
$$
-k_{x}^{2}=-\left( \frac{\pi}{a} \right)^{2}n^{2},\hspace{2px}n=1,2,3,\dots
$$
and the corresponding normalized eigenvectors are
$$
\chi_{n}(x)=\sqrt{ \frac{2}{a} }\sin\left( \frac{\pi n}{a}x \right),\hspace{2px}n=1,2,3,\dots
$$
Similarly, for $y$:
$$
\begin{align}
-k_{y}^{2} & =-\left( \frac{\pi}{b} \right)^{2}m^{2},\hspace{2px}m=1,2,3,\dots \\
\phi_{n}(x) & = \sqrt{ \frac{2}{b} }\sin\left( \frac{\pi n}{b}y \right),m=1,2,3,\dots
\end{align}
$$
(The boundary conditions have already been applied.) Putting these together, we have
$$
\begin{align}
f_{nm}(x,y) & =\frac{2}{\sqrt{ ab }}\sin\left( \frac{\pi n}{a}x \right)\sin\left( \frac{\pi m}{b}y \right),\hspace{2px}n,m=1,2,3,\dots \\
k^{2} & = \left( \frac{\pi}{a} \right)^{2}n^{2}+\left( \frac{\pi}{b} \right)^{2}m^{2}.
\end{align}
$$
Adding back in the time component, we find:
$$
u_{nm}(x,y,t)=\frac{2}{\sqrt{ ab }}\sin\left( \frac{\pi n}{a}x \right)\sin\left( \frac{\pi m}{b}y \right)e^{ -\alpha^{2}\left[ \left( \frac{\pi}{a} \right)^{2}n^{2}+\left( \frac{\pi}{b} \right)^{2}m^{2} \right] t }.
$$
These are the solutions of the heat diffusion equation for our particular case. Note, however, that any individual $u_{nm}$ will never satisfy any initial temperature distribution $u_{0}(x,y)$ on the plate. BUT, any linear combination of these solutions is also a solution to the PDE *and* allows us to satisfy initial conditions.
$$
u(x,y,t)=\sum_{n=1}^{\infty} \sum_{m=1}^{\infty} c_{nm}u_{nm}(x,y,t),
$$
where $c_{nm}$ is chosen to satisfy the initial conditions.
$$
u_{0}(x,y)=\sum_{n=1}^{\infty} \sum_{m=1}^{\infty} c_{nm}u_{nm}(x,y,0).
$$
^c390d0

This is simply a linear algebra problem, specifically an [[Phys 100A - Methods of Theoretical Physics, Part 1/Notes/Basis Representations of Vector Spaces#Orthonormal Bases|expansion]] in an [[Linear Independence & Basis#^12b0fb|orthonormal basis]] (orthonormal because the eigenvectors were previously normalized). Let $u_{nm}(x,y,0)=\ket{nm}$ and $u_{0}(x,y)=\ket{u_{0}}$. Then [[#^c390d0]] becomes
$$
\ket{u_{0}} =\sum_{n=1}^{\infty} \sum_{m=1}^{\infty} c_{nm}\ket{nm} .
$$
We can let the inner product be 
$$
\braket{ f | g } =\int_{0}^{a} \int_{0}^{b} f^{*}(x,y)g(x,y) \, \hspace{0.5mm} dy  \, \hspace{0.5mm} dx .
$$
Then the vectors $\ket{nm}$ form an orthonormal basis for functions that vanish at the boundary of the rectangle. That is,
$$
\braket{ nm | n'm' } =\delta_{nn'}\delta_{mm'}.
$$
We can now write the completeness relation:
$$
\hat{I}=\sum_{n=1}^{\infty} \sum_{m=1}^{\infty} \ket{nm} \bra{nm},
$$
and compute the coefficients $c_{nm}$.
$$
\braket{ n'm' | u_{0} } =\sum_{n=1}^{\infty}\sum_{m=1}^{\infty}  c_{nm}\braket{ n'm' | nm } =c_{n'm'}
$$
Explicitly,
$$
\begin{align}
c_{nm} & =\int_{0}^{a}  \, \hspace{0.5mm} dx \int_{0}^{b}  \, \hspace{0.5mm} dy \frac{2}{\sqrt{ ab }}\sin\left( \frac{\pi n}{a}x \right)\sin\left( \frac{\pi m}{b} y \right)u_{0}(x,y), \\
u(x,y,t) & =\sum_{n=1}^{\infty} \sum_{m=1}^{\infty} c_{nm}e^{ -\alpha^{2}\left[  \left( \frac{\pi}{a} \right)^{2}n^{2}+\left( \frac{\pi}{b} \right)^{2}m^{2} \right]t  } \frac{2}{\sqrt{ ab }}\sin\left( \frac{\pi nx}{a} \right)\sin\left( \frac{\pi my}{b} \right).
\end{align}
$$
Note that we can write this in a simpler form using our linear algebra notation.
$$
\ket{u} =\sum_{n=1}^{\infty} \sum_{m=1}^{\infty} \braket{ nm | u_{0} } e^{ -\alpha^{2}\left[  \left( \frac{\pi}{a} \right)^{2}n^{2}+\left( \frac{\pi}{b} \right)^{2}m^{2} \right]t }\ket{nm} .
$$
^eqn6

We can simplify this further by recalling:
$$
\nabla^{2}(\chi \phi)=(\hat{L}_{x}+\hat{L}_{y})(\chi \phi)=-\left[  \left( \frac{\pi}{a} \right)^{2}n^{2}+\left( \frac{\pi}{b} \right)^{2}m^{2} \right](\chi \phi).
$$
Recalling that [[Linear Operators#Exponential of an Operator|exponentials of linear operators]] satisfy
$$
e^{ \alpha^{2}t\nabla^{2} }\ket{nm} =e^{ =\alpha^{2}\left[  \left( \frac{\pi}{a} \right)^{2}n^{2}+\left( \frac{\pi}{b} \right)^{2}m^{2} \right]t }\ket{nm} ,
$$
we can rewrite [[#^eqn6]] as 
$$
\begin{align}
\ket{u}  & = \sum_{n=1}^{\infty} \sum_{m=1}^{\infty} \braket{ nm | u_{0} } e^{ \alpha^{2}t\nabla^{2} }\ket{nm} , \\
 & = e^{ \alpha^{2}t\nabla^{2} }\left( \underbrace{ \left[ \sum_{n=1}^{\infty} \sum_{m=1}^{\infty} \ket{nm} \bra{nm}  \right] }_{ \hat{I} }  \ket{u_{0}}  \right), \\
\ket{u}  & = e^{ \alpha^{2}t\nabla^{2} }\ket{u_{0}} .
\end{align}
$$
This provides a very simple way to write the solution, stating that the solution $\ket{u}$ to the problem is obtained by applying the linear operator $e^{ \alpha^{2}t\nabla^{2} }$ to the function $\ket{u_{0}}$, the prescribed initial condition.