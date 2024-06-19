---
tags:
  - Physics100A
  - 100ANotes
---
---
### Infinitely Dimensional Vectors
In all preceding discussion the dimensionality of the space was unspecified but presumed to be finite. Now let's change that.

Consider a function $f(x)$ defined in some interval $x \in [a,b]$. A good example is where $f(x,t)$ is the displacement of a string clamped at $x=0$ and $x=L$. Say we want to communicate to a person far away the string's displacement at some given time $t$. One simple way is to divide the interval $[0,L]$ into some number of equal parts, such as 20, at the 19 points $x=L/20,2L/20$, etc. We then transmit the displacement at these points to our friend, who can reconstruct an approximate picture of the string. If we wish to be more accurate, we can simply take a larger number of $n$ points. If we notate $f_{n}(x)$ as the discrete function approximation of $f(x)$ coinciding with $n$ points and vanishing between the points, we can interpret the ordered $n$-tuple $\{ f_{n}(x_{1}),f_{n}(x_{2}),\dots,f_{n}(x_{n}) \}$ as components of a vector $\ket{f_{n}}$ in the vector space $V^{n}$ over $\mathbb{R}$. 
$$
\ket{f_{n}} =\begin{pmatrix}
f_{n}(x_{1}) \\
f_{n}(x_{2}) \\
\vdots \\
f_{n}(x_{n})
\end{pmatrix}.
$$
The basis vectors here are 
$$
\ket{x_{i}} =\begin{pmatrix}
0 \\
0 \\
\vdots \\
1 \\ 
0 \\
\vdots \\
0
\end{pmatrix} \leftarrow \text{i-th place.}
$$
These basis vectors correspond to the discrete function which is unity at $x_{i}$ and zero everywhere else, and satisfy
$$
\begin{align}
\braket{ x_{i} | x_{j} }  & =\delta_{ij}, \tag{orthogonality}\\
\sum_{i=1}^{n} \ket{x_{i}} \bra{x_{i}}  & = \hat{I}.\tag{completeness}
\end{align}
$$
We can imagine a space containing $n$ mutually perpendicular axes, one for each point $x_{i}$. Along each axis is a unit vector $\ket{x_{i}}$. The function $f_{n}(x)$ is therefore represented as
$$
\ket{f_{n}} =\sum_{i=1}^{n} f_{n}(x_{i})\ket{x_{i}} .
$$
We can see then that the set of all vectors representing discrete functions which vanish at $x=0,L$ and which are specified at $n$ points in between form a vector space (which we called $V^{n}$). 
We can then define an inner product in this space:
$$
\braket{ f_{n} | g_{n} } =\sum_{i=1}^{n} f_{n}(x_{i})g_{n}(x_{i}).
$$
The most detailed we can get about describing the string's displacement is if we specify its value at every point on the interval $[0,L]$. In this case $f_{\infty}(x)\equiv f(x)$ is specified by an ordered infinity of numbers, a value $f(x)$ corresponding to every value $x \in [0,L]$. Each function $f(x)$ is now represented by a ket $\ket{f_{\infty}}$ in an infinite-dimensional vector space, and vice versa. 

Vector addition and scalar multiplication are defined the same. The inner product, however, will change. If we take the limit as $n\to \infty$, we see that
$$
\braket{ f_{n} | g_{n} } =\sum_{i=1}^{\infty} f_{n}(x_{i})g_{n}(x_{i}),
$$
will diverge for practically any function. We then need to redefine the inner product for finite $n$ such that as $n\to \infty$ a smooth limit is obtained. The natural choice for this example of the string of length $L$ is 
$$
\braket{ f_{n} | g_{n} } =\sum_{i=1}^{n} f_{n}(x_{i})g_{n}(x_{i})\left( \frac{L}{n+1} \right) .
$$
If we let $n\to \infty$, we now see that (by the standard definition of the integral)
$$
\begin{align}
\braket{ f | g }  & =\int_{0}^{L} f(x)g(x) \, \hspace{0.5mm} dx , \\
\braket{ f | f }  & = \int_{0}^{L} f^{2}(x) \, \hspace{0.5mm} dx .
\end{align}
$$
To generalize this to include complex functions, we can say 
$$
\braket{ f | g } =\int_{0}^{L} f^{*}(x)g(x) \, \hspace{0.5mm} dx .
$$
We previously defined the basis as $\ket{x_{i}}$, so here each point $x$ will have a basis vector $\ket{x}$. Orthogonality requires that
$$
\braket{ x | x' } =0,\hspace{5px}x\neq x'.
$$
However, if $x=x'$, we don't require that $\braket{ x | x }=1$ in the infinite dimensional case. We can deduce the correct normalization by beginning with the natural generalization of the completeness relation:
$$
\int_{a}^{b} \ket{x'} \bra{x'}  \, \hspace{0.5mm} dx'=\hat{I}. 
$$
Left-multiplying both sides by the basis bra $\bra{x}$ and right-multiplying both sides by the arbitrary ket $\ket{f}$, we arrive at
$$
\int_{a}^{b} \braket{ x | x' } \braket{ x' | f }  \, \hspace{0.5mm} dx' = \braket{ x | f } .
$$
By definition, $\braket{ x | f }$ (the projection of $\ket{f}$ along the basis $\ket{x}$) is just $f(x)$, and likewise $\braket{ x' | f}=f(x')$. We let the inner product $\braket{ x | x' }=\delta(x,x')$, which is some unknown function. Since this function vanishes if $x=x'$, we can restrict the integral to an infinitesimal region near $x=x'$:
$$
\int_{x-\varepsilon}^{x+\varepsilon} \delta(x,x')f(x') \, \hspace{0.5mm} dx'=f(x).
$$
In this infinitesimal region, $f(x')\approx f(x)$, so
$$
\begin{align}
f(x)\int_{x-\varepsilon}^{x+\varepsilon} \delta(x,x') \, \hspace{0.5mm} dx'  & =f(x), \\
\int_{x-\varepsilon}^{x+\varepsilon} \delta(x,x') \, \hspace{0.5mm} dx' & = 1.
\end{align}
$$
The function $\delta(x,x')$ only depends on the difference $x-x'$ and it cannot be finite at $x=x'$. So we can write
$$
\int_{a}^{b} \delta(x-x') \, \hspace{0.5mm} dx'=1,\text{ for }a<x<b, 
$$
where $\delta(x)$ is the [[Dirac delta function]]. This gives us the correct normalization.
$$
\braket{ x | x' } = \delta(x-x').
$$
(Shankar QM pg 60-63 has more on Dirac delta functions for the intellectually curious, but it is largely tangential to the subject matter of the course at this time.)

To summarize: 
- An infinite dimensional vector $\ket{a}=\begin{pmatrix}a_{1}\\a_{2}\\a_{3}\\\vdots\end{pmatrix}$ can be described by an infinite number of basis vectors $\ket{x}$, which satisfy orthogonality $\braket{ x | x' }=\delta(x-x')$ and completeness $\int_{a}^{b} \ket{x} \bra{x} \, \hspace{0.5mm} dx=\hat{I}$. 
- These vectors are elements of an infinitely dimensional vector space defined by the basis $\{ \ket{x} \}$.

### Linear Operators in Infinite Dimensions

