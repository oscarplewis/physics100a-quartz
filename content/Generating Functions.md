---
tags:
  - Physics100A
  - 100ANotes
---
---
A generating function is a representation of an infinite sequence as the coefficients of a formal power series. \[Formal means it is considered separately from any notions of convergence.]

> [!tip] Convergence
> Right off the bat we must make this note: the generating function, unlike an *ordinary* series, is not required to converge. In fact, we don't even regard it as a function, and we leave the "variable" indeterminate. 

We can also have multivariate formal power series to encode information about infinite multi-dimensional arrays of numbers, but in this document we will deal primarily with single "variable" generating functions.

> [!example] Generating Functions
> A generating function is a function representation of an infinite sequence as the coefficients of a formal power series. For a sequence $\{ a_{0},a_{1},a_{2},\dots \}$ we can write a power series of the form
> $$
> A(x) = \sum_{k=0}^{\infty} a_{k}x^{k},$$
> which is called the generating function of the sequence. Equivalently, we could write some function which produces the coefficients written in the form of operations on formal power series.

^ab3c81


> [!tip] Expressing Generating Functions
> Oftentimes generating series (in series form) are expressed in closed form (as generating functions), rather than a series, by some expression involving operations defined for formal series.

### Examples


> [!exm]
> Consider the sequence $\{ 1,1,1,1,\dots \}$. Write a generating function for that sequence.
^ee4c09

A generating series (the generating function expressed in series form rather than closed form) for this sequence is
$$
S=1+x+x^{2}+x^{3}+\dots
$$
If we multiply this series by $-x$, and add it then we have:
$$
(1-x)S=1\implies S=\frac{1}{1-x}.
$$
Therefore we see that the generating function for the given sequence is $\frac{1}{1-x}$.

We can then use this function to represent more sequences.

> [!exm]
> Consider the sequence $\{ 1,-1,1,-1,\dots \}$. Write a generating function for that sequence.

If we substitute $x\to-x$ in the series from [[#^ee4c09]] then we get the generating function
$$
\frac{1}{1+x}=1-x+x^{2}-x^{3}+\dots,
$$
which is the generating series for this sequence. Indeed we can continue onwards in this fashion, acquiring a wide variety of sequences by replacing $x$ with various things.

> [!exm]
> Consider the sequence $\{ 3,9,27,81,\dots \}$. Write a generating function for that sequence.

If we make the substitution $x\to3x$ in the series from [[#^ee4c09]] then we have
$$
\frac{1}{1-3x}=1+3x+9x^{2}+27x^{3}+\dots
$$
We can then multiply both sides by $3$ to get the desired sequence.
$$
\frac{3}{1-3x}=3+9x+27x^{2}+81x^{3}+\dots
$$
So this is the generating function for the given sequence.

> [!exm]
> Consider the sequence $\{ 1,0,1,0,\dots \}$. Write a generating function for that sequence.

If we make the substitution $x\to x^{2}$ in the series from [[#^ee4c09]] then we have
$$
\frac{1}{1-x^{2}}=1+x^{2}+x^{4}+x^{6}+\dots
$$
which produces the desired series. Similarly, we can construct the sequence $\{ 0,1,0,1,\dots \}$ by "shifting" the sequence by 1, which we do by multiplying the series by $x$. 
$$
\frac{x}{1-x^{2}}=x+x^{3}+x^{5}+x^{7}+\dots
$$
which produces this second sequence.

> [!exm]
> Consider the sequence $\{ 1,2,3,4,\dots \}$. Write a generating function for that sequence.

To acquire this sequence, we can take the derivative of the series from [[#^ee4c09]]:
$$
\frac{1}{(1-x)^{2}}=1+2x+3x^{2}+4x^{3}+\dots
$$
which produces the desired sequence.

> [!exm]
> Consider the sequence of odd numbers. Write a generating function for this sequence.

^c01e8c

We can take the sequence from [[#^ee4c09]], make the substitution $x\to x^{2}$, and shift it over by one to get:
$$
\frac{x}{1-x^{2}}=x+x^{3}+x^{5}+x^{7}+\dots
$$
We can then differentiate this function:
$$
\frac{1+x^{2}}{(1-x^{2})^{2}} = 1+3x^{2}+5x^{4}+7x^{6}+\dots
$$
This is almost the sequence we want. This is the generating function for $\{ 1,0,3,0,5,0,\dots \}$. We can now make the rather awkward substitution $x^{2}\to x$, finding
$$
\frac{1+x}{(1-x)^{2}}=1+3x+5x^{2}+7x^{3}+\dots
$$
which creates the sequence we desire.

Alternatively, we can represent the generating function for the desired sequence by $A$. 
$$
A=1+3x+5x^{2}+7x^{3}+9x^{4}+\dots
$$
We can shift this over by 1 and subtract:
$$
\begin{align}
A & = 1+3x+5x^{2}+7x^{3}+9x^{4}+\dots \\
-xA & = 0-x-3x^{2}-5x^{3}-7x^{4}-\dots \\
\hline (1-x)A & = 1+2x+2x^{2}+2x^{3}+2x^{4}+\dots
\end{align}
$$
We know that the generating function for this sequence is $1+\frac{2x}{1-x}$, so this means that
$$
(1-x)A=1+\frac{2x}{1-x}\implies A=\frac{1+x}{(1-x)^{2}}.
$$

> [!exm]
> Find the generating function for $1,4,9,16,....$  Take $a_{0}=1$.

We know that every odd is a difference between two squares. Let $A=1+4x+9x^{2}+16x^{3}+\dots$.
$$
\begin{align}
A & = 1+4x+9x^{2}+16x^{3}+25x^{4}+\dots \\
-xA & = 0-x-4x^{2}-9x^{3}-16x^{4}-\dots \\
\hline (1-x)A & = 1+3x+5x^{2}+7x^{3}+9x^{4}+\dots
\end{align}
$$
This is the generating series of odds from the [[#^c01e8c]]. So:
$$
(1-x)A=\frac{1+x}{(1-x)^{2}}\implies A=\frac{1+x}{(1-x)^{3}}.
$$

> [!tip] More
> More on generating functions can be found [here](https://discrete.openmathbooks.org/dmoi2/section-27.html).



