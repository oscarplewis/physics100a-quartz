---
tags:
  - Physics100A
  - 100ANotes
---
---
### Solving the Spherical Heat Diffusion Equation

Consider the heat diffusion equation
$$
\nabla^{2}u=\frac{1}{\alpha^{2}} \frac{ \partial u }{ \partial t } ,
$$
^f9324c

for the temperature $u(x,y,z,t)$ inside a sphere of radius $R$. 
![[Screenshot 2024-05-31 at 16.02.58.png|200]]

Assume that the temperature distribution is some prescribed function independent of time $t$ at the surface. That is,
$$
u(\vec{r},t)=u_{0}(\vec{r})\text{ for }\lVert \vec{r} \rVert =R.
$$
We want to compute the temperature in the *steady state*, which is the limiting distribution as $t\to \infty$. In this case the temperature will no longer vary with time, so the right hand side of the diffusion equation [[#^f9324c]] will vanish. Thus the steady state temperature is $u(\vec{r})$ which will satisfy Laplace's equation.
$$
\nabla^{2}u=0\tag{steady state}.
$$
### Solving Laplace's Equation

We want to find the solution of Laplace's equation inside a sphere of radius $R$, subject to the boundary condition that it equals a prescribed function $u(\vec{r})=u_{0}(\vec{r})$ for $\lVert \vec{r} \rVert=R$. In order to solve this, we observe that the equation is spherically symmetric, suggesting that we can try separation of variables in spherical coordinates, defined
$$
\begin{align}
x & = r\sin\theta \cos \phi, \\
y & =r\sin\theta \sin \phi, \\
z & =r\cos\theta,
\end{align}
$$
for $0\leq r<\infty,0\leq\theta\leq \pi,0\leq \phi\leq 2\pi$. In spherical coordinates we have
$$
\frac{1}{r^{2}} \frac{ \partial  }{ \partial r } \left[ r^{2}\frac{ \partial u }{ \partial r }  \right]+\frac{1}{r^{2}\sin\theta} \frac{ \partial  }{ \partial \theta } \left[ \sin\theta \frac{ \partial u }{ \partial \theta }  \right] +\frac{1}{r^{2}\sin\theta} \frac{ \partial^{2} u }{ \partial \phi^{2} }=0.
$$
This is Laplace's equation in spherical coordinates. Using separation of variables, we substitute in $u(r,\theta,\phi)=R(r)\Theta(\theta)\Phi(\phi)$ and multiply by $\frac{r^{2}\sin ^{2}\theta}{R\Theta \Phi}$.
$$
\frac{\sin^{2}\theta}{R} \frac{d}{dr}\left[ r^{2} \frac{dR}{dr} \right] +\frac{\sin\theta}{\Theta} \frac{d}{d\theta}\left[ \sin\theta\frac{ d\Theta}{d\theta} \right] =-\frac{1}{\Phi} \frac{d^{2}\Phi}{d\phi^{2}}.
$$
Both sides here must be equal to a constant. We let:
$$
\begin{align}
 \hspace{2px} -\frac{1}{\Phi} \frac{d^{2}\Phi}{d\phi^{2}} & =m^{2}, \\
 \hspace{2px} \frac{\sin ^{2}\theta}{R} \frac{d}{dr}\left[ r^{2} \frac{dR}{dr} \right] + \frac{\sin\theta}{\Theta} \frac{d}{d\theta}\left[ \sin\theta\frac{ d\Theta}{d\theta} \right]  & =m^{2}.
\end{align}
$$
^6f864c

First we discuss [[#^6f864c|Eqn(2-1)]]. By construction, spherical coordinates imply that $\phi$ is periodic on $2\pi$. So:
$$
\Phi(\phi)=\Phi(\phi+2\pi),\hspace{2px}\Phi'(\phi)=\Phi'(\phi+2\pi).
$$
So $\Phi(\phi)$ must be a periodic function with period $2\pi$. Therefore [[#^6f864c|Eqn(2-1)]] is the Sturm-Liouville eigenvalue problem for the operator $\hat{L}_{\phi}=\frac{d^{2}}{d\phi^{2}}$ acting on the vector space of periodic functions $\Phi(\phi)$. Solving this problem ([[Active Learning Master List#Active Learning 1|this active learning]]), we have
$$
\begin{align}
\text{eigenvalues} & : \lambda_{m}=-m^{2},m\in \mathbb{Z}. \\
\text{eigenvectors} & : \Phi_{m}(\phi)=e^{ im\phi }\text{ (not normalized)}.
\end{align}
$$
For any of these values of $m$, we now solve [[#^6f864c|Eqn(2-2)]] by separating the variables and dividing by $\sin ^{2}\theta$. We then get two equations again:
$$
\begin{align}
\frac{1}{\Theta \sin\theta} \frac{d}{d\theta}\left[ \frac{\sin\theta d\Theta}{d\theta} \right] -\frac{m^{2}}{\sin ^{2}\theta} & =\lambda, \\
\frac{1}{R} \frac{d}{dr}\left[ r^{2} \frac{dR}{dr} \right]  & =-\lambda.
\end{align}
$$
^56bb47

First we focus on [[#^56bb47|Eqn(3-1)]]. We've already solved this equation! Let $x=\cos\theta$. Then we can rewrite this in terms of $x$:
$$
(1-x^{2}) \frac{d^{2}\Theta}{dx^{2}}-2x \frac{d\Theta}{dx}-\frac{m^{2}}{1-x^{2}}\Theta=\lambda\Theta.
$$
This is the [[Associated Legendre Polynomials|associated Legendre equation]], which has solutions:
$$
\begin{align}
\text{eigenvalues} & : \lambda=-l(l+1),\hspace{2px}l=\left| m \right| ,\left| m \right| +1,\dots, \\
\text{eigenvectors} & : \Theta(x)=P_{l}^{m}(\cos\theta),
\end{align}
$$
^0ddeea

for $l\in\mathbb{Z}^{+}_{0},m\in\mathbb{Z}$ and $-l\leq m\leq l$. 

> [!NOTE] Note!
> The boundary condition requiring that $\Theta(x)$ be finite for $x=\pm 1$ just represents conditions on solutions in the directions $\theta=0,\pi$ in spherical coordinates.

Finally we consider [[#^56bb47|Eqn(3-2)]] for any of the possible values $\lambda=-l(l+1)$ restricted by [[#^0ddeea]]. 
$$
\frac{d}{dr}\left[ r^{2} \frac{dR}{dr} \right] =l(l+1)R.
$$
We've also encountered this equation before. We apply product rule, finding
$$
r^{2} \frac{d^{2}R}{dr^{2}}+2r \frac{dR}{dr}=l(l+1)R,
$$
which has an elementary solution. Let $R(r)=r^{\xi}$. Substituting and solving (see [[this active learning]]) we have $R(r)=Ar^{l}+Br^{-l-1}$. Putting all of this together, we have
$$
\begin{align}
u_{lm}(r,\theta,\phi) & =\left[ A_{lm}r^{l}+B_{lm}r^{-l-1} \right] P_{l}^{m}(\cos\theta)e^{ im\phi }, \text{for }l=0,1,2,\dots,-l\leq m\leq l.
\end{align}
$$
^e57784

This is a solution to Laplace's equation in spherical coordinates.

### Spherical Harmonics

Instead of representing the solutions as products of the associated Legendre polynomials, it's often convenient to use a set of orthonormal functions called ***spherical harmonics***.

> [!example] Spherical Harmonics
> ***Spherical harmonics*** is a basis of [[Linear Independence & Basis#^12b0fb|orthonormal]] polynomials defined by
> $$
> Y_{lm}(\theta,\phi)=(-1)^{m} \sqrt{[](Linear%20Independence%20&%20Basis.md#^12b0fb)_{l}^{m}(\cos\theta) \frac{e^{ i m\phi }}{\sqrt{ 2\pi }},
> $$
> where $l=0,1,2,\dots$ and $-l\leq m\leq l$ for $m\in\mathbb{Z}$. Using the definition of the associated Legendre functions for $m<0$, we can also write:
> $$
> Y_{lm}(\theta,\phi)=\begin{cases}
> (-1)^{m} \sqrt{ \frac{(l-m)!}{(l+m)!} \frac{(2l+1)}{2}  } P_{l}^{m}(\cos\theta) \frac{e^{ i m\phi }}{\sqrt{ 2\pi }}, & m\geq 0, \\
> \sqrt{ \frac{(l-\left| m \right| )!}{(l+\left| m \right| )!} \frac{(2l+1)}{2} }\hspace{2px}P_{l}^{m}(\cos\theta) \frac{e^{ i m\phi }}{\sqrt{ 2\pi }}, & m<0.
> \end{cases}
> $$
> 


> [!tip] Properties of Spherical Harmonics
> $$
\begin{align}
(i) &\hspace{10px}  Y_{lm}^{*}(\theta,\phi)=(-1)^{m}Y_{l,-m}(\theta,\phi). \\
(ii)  &\hspace{10px} \int_{0}^{2\pi}  \, \hspace{0.5mm} d\phi \underbrace{ \int_{0}^{\pi} \sin\theta \, \hspace{0.5mm} d\theta  }_{ \int_{-1}^{1}  \, \hspace{0.5mm} dx  }\hspace{5px}Y^{*}_{l'm'} (\theta,\phi)Y_{lm}(\theta,\phi)=\delta_{l'l}\delta_{m'm}. \\
(iii)  &\hspace{10px} \text{Any suitably well behaved function $f(\theta,\phi)$ which depends}\\&\hspace{10px} \text{only on the angles $\theta,\phi$ can be expanded as a linear}\\
&\hspace{10px} \text{combination of the spherical harmonics.}\\
&\hspace{10px} \ket{f}  = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} a_{lm} \ket{lm}.
\end{align}$$

Note that Property $(iii)$ states that if we define the following inner product for any two functions that depend only on angles $\theta,\phi$, $f_{1}$ and $f_{2}$, with
$$
\braket{ f_{1} | f_{2} } = \int_{0}^{2\pi}  \, \hspace{0.5mm} d\phi \int_{0}^{\pi} \sin\theta \, \hspace{0.5mm} d\theta f^{*}_{1}(\theta,\phi)f_{2}(\theta,\phi),  
$$
then the spherical harmonics are orthonormal with respect to this inner product. That is, we can rewrite property $(ii)$ as
$$
\braket{ l'm' | lm } = \delta_{l'l}\delta_{m'm}.\tag{$ii$}
$$
We can now obtain the coefficients $a_{lm}$ in property $(iii)$ in the orthonormal basis $\{ Y_{lm}(\theta,\phi) \}$. 
$$
a_{l'm'}=\braket{ l'm' | f } = \int_{0}^{2\pi}  \, \hspace{0.5mm} d\phi \int_{0}^{\pi} \sin\theta \, \hspace{0.5mm} d\theta Y^{*}_{l'm'}(\theta,\phi)f(\theta,\phi). 
$$

> [!note] Note!
> When $m=0$, the associated Legendre function $P_{l}^{m}(\cos\theta)$ becomes the corresponding Legendre function $P_{l}(\cos\theta)$. In these cases, $Y_{l,0}$ is simply $1/\sqrt{ 2\pi }$ times the normalized Legendre polynomial.
> $$
Y_{l,m=0}=\frac{1}{\sqrt{ 2\pi }}\rho_{l}(\cos\theta).$$
### Back to Laplace

Returning to Laplace's equation, we can now write [[#^e57784]] in terms of spherical harmonics.
$$
u(r,\theta,\phi)=\sum_{l=0}^{\infty} \sum_{m=-l}^{l} \left[ \alpha_{lm}r^{l}+\frac{\beta_{lm}}{r^{l+1}} \right] Y_{l}^{m}(\theta,\phi),
$$
for any arbitrary constants $a_{lm}$ and $\beta_{lm}$. We can use properties of the orthonormal basis $\{ Y_{lm} \}$ to find the values of the coefficients for any boundary conditions.

### Examples

![[Lecture Nineteen.pdf]]










