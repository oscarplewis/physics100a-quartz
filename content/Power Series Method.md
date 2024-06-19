---
tags:
  - Physics100A
  - 100ANotes
---
---
Notes taken mostly from *Mathematical Methods in the Physical Sciences*, Chapter 12.1, by Mary L. Boas.

> [!example] The Power Series Method
> Given a linear differential equation whose coefficients depend on the variable, a useful thing to do is to assume an infinite series solution. We then substitute the power series ansatz into the differential equation and solve for the coefficients to find the general solution.

^ca8439

### A Simple Example

We can illustrate the method of series solutions by solving the following differential equation, which can also be solved using elementary methods.
$$
y'=2xy.
$$
We assume a solution of the form
$$
y=\sum_{n=0}^{\infty} a_{n}x^{n}.
$$
Differentiating this term by term, we find:
$$
y'=a_{1}+2a_{2}x+3a_{3}x^{2}+\dots = \sum_{n=1}^{\infty} na_{n}x^{n-1}
$$
If we substitute these into the differential equation and change the indices a bit, we have:
$$
\sum_{n=0}^{\infty} (n+1)a_{n+1}x^{n}=\sum_{n=1}^{\infty} 2a_{n-1}x^{n}
$$
We can separate this out term by term and modify the indices, solving for the coefficients:
$$
\begin{align}
a_{0} & =a_{0}, \\
a_{1} & = 0, \\
a_{n} & =\frac{2a_{n-2}}{n}.
\end{align}
$$
We notice then that all odd coefficients will be zero, and can reformulate this:
$$
a_{n}=\begin{cases}
0, & \text{for odd }n, \\
\frac{2^{n/2}}{n!!}a_{0}, & \text{for even }n.
\end{cases}
$$
So we substitute this back into our assume form of the solution, finding
$$
y(x) = \sum_{n=0}^{\infty} \frac{a_{0}}{n!}x^{2n}.
$$
We recognize this as the series expansion of $a_{0}e^{ x^{2} }$, which is a solution of the differential equation by elementary methods.

> [!tip] Do we always get a closed form expression?
> No, we can't always expect that our series solution can be represented by elementary functions. In simple cases we may recognize solutions, but more generally it is best to leave it in the form of a power series with determined coefficients.

Every other usage of the the power series method will follow this general form: assuming a power series form of solution, substituting into the differential equation, and then solving for the coefficients, placing constraints on them as needed.