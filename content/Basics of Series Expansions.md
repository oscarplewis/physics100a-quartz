---
tags:
  - Physics100A
  - 100ANotes
---
---
Notes taken mostly from *Mathematical Methods in the Physical Sciences*, Chapter 1, by Mary L. Boas. 
### Geometric Series
A geometric series multiplies each term by some fixed number to get the next term.
$$
\begin{align}
 & \text{Recursive:} & a_{n+1}=ra_{n}, \\
 & \text{Explicit:} & a_{n}=r^{n}a_{0},
\end{align}
$$
For finite $n$, the sum of the series is
$$
S_{n}=\frac{a_{0}(1-r^{n})}{1-r}
$$

If $n\to \infty$, then this is an infinite geometric series, and the sum is
$$
S=\lim_{ n \to \infty } S_{n}=\frac{a_{0}}{1-r}
$$
If $S$ exists, then the series is convergent.

### Infinite Series
Generally an infinite series has the form
$$
a_{1}+a_{2}+a_{3}+\dots+a_{n}+\dots
$$
We define a partial sum as
$$
S_{n}=a_{1}+a_{2}+a_{3}+\dots a_{n}
$$

> [!tip] Convergence Condition for Partial Sums
> If the partial sums converge to a limit $S$ ($\lim_{ n \to \infty }S_{n}=S$) then the series converges. $S$ is called the sum of the series. If the partial sums do not converge, then neither does the series.

The difference $R_{n}=S-S_{n}$ is called the remainder after $n$ terms. Note that $\lim_{ n \to \infty }R_{n}=0$. 

We are very interested in whether an infinite series diverges or converges.

### Divergence and Convergence Tests

>[!note] Preliminary Test for Divergence
>If the terms of an infinite series do not tend to zero (i.e. $\lim_{ n \to \infty }a_{n}\neq 0$) then the series diverges. If they do tend to zero, further testing is necessary.

^f6ad6f


> [!NOTE] Limit Comparison Test
> Let $\sum_{k=1}^{\infty}a_{k}$ and $\sum_{k=1}^{\infty}b_{k}$ be series and let $p=\lim_{ k \to \infty } \frac{a_{k}}{b_{k}}$. If $p$ is finite and positive, then either both series converge or both diverge.

^e39ef4

 

>[!note] Comparison Test for Convergence
>Say $m_{1}+m_{2}+m_{3}+\dots$ is a series which you know converges, and the series you're testing is $a_{1}+a_{2}+a_{3}+\dots$. Then if $|a_{n}|\leq m_{n}$ for all $n>N$ (for some positive integer $N$), the series is absolutely convergent. It can be shown that if a series absolutely converges ($\sum |a_{n}|=\text{finite}$) then the series also converges ($\sum a_{n}=\text{finite}$).

^a7134c

>[!note] Comparison Test for Divergence
>Say $d_{1}+d_{2}+d_{3}+\dots$ is a series which you know diverges, and the series you're testing is $a_{1}+a_{2}+a_{3}+\dots$. Then if $|a_{n}|\geq d_{n}$ for all $n>N$ (for some positive integer $N$), the series is absolutely divergent ($\sum |a_{n}|=\text{undefined}$).

^510bf1



>[!note] Integral Test for Convergence
>For a series $a_{1}+a_{2}+a_{3}+\dots$, if $0<a_{n+1}\leq a_{n}$ for $n>N$, and a function $f(x)$ which is continuous on $[1,\infty)$ such that $f(n)=a_{n}$ for all $n>N$, then $\sum^{\infty}a_{n}$ converges if $\int^{\infty} f(x) \, dx$ is finite and diverges if the integral is infinite. (The integral is only to be evaluated at the upper limit; the lower limit is unnecessary.)

^22a0fd



> [!NOTE] Power Test for Convergence
> The series $\sum_{k=1}^{\infty} \frac{1}{k^{p}}$ converges if $p>1$ and diverges if $p\leq 1$. 
> This can be shown from the [[Basics of Series Expansions#^22a0fd|integral test]]. 

^fb8b51


>[!note] Ratio Test of Convergence
>Let the ratio between two terms of the series be $$ \rho_{n}=\left| \frac{a_{n+1}}{a_{n}} \right|, $$ and let $\rho=\lim_{ n \to \infty }\rho_n$. Then if
> $$
\begin{cases}
\rho<1, & \text{the series converges;} \\
\rho=1, & \text{the test is inconclusive;} \\
\rho>1, & \text{the series diverges.}
\end{cases} $$

^bac49d

> [!note] Root Test of Convergence
> If $\sum_{k=1}^{\infty}a_{k}$ is a series of positive terms, let $p=\lim_{ k \to \infty }\sqrt[k]{ a_{k} }$. 
> $$
> \text{If }\begin{cases}
> p<1, & \text{the series converges.} \\
> p>1, & \text{the series diverges.} \\
> p=1, & \text{the test is inconclusive.}
> \end{cases}
> $$
> 

^73ab17


>[!note] Special Comparison Test
>If $\sum_{n=1}^{\infty}b_{n}$ is a convergent series of positive terms and $a_{n}\geq 0$ and $a_{n}/b_{n}$ tends to a finite limit, then $\sum_{n=1}^{\infty}a_{n}$ converges. 
If $\sum_{n=1}^{\infty}d_{n}$ is a divergent series of positive terms and $a_{n}\geq 0$ and $a_{n}/d_{n}$ tends to a limit greater than zero (or to $+\infty$), then $\sum_{n=1}^{\infty}a_{n}$ diverges.


All of these tests are presented here without proof. If a proof is desired, the internet may prove a useful tool.

### Alternating Series

An alternating series is a series whose terms are alternately positive and negative. For example:
$$
1-\frac{1}{2}+\frac{1}{3}-\frac{1}{4}+\dots
$$
We want to know two things mainly given an alternating series: does it converge? does it absolutely converge?

>[!note] Convergence Test for Alternating Series
>An alternating series converges if the absolutely value of the terms decreases steadily to zero. That is, if $|a_{n+1}|\leq|a_{n}|$ and $\lim_{ n \to \infty }a_{n}=0$. 

See [[Alternating Series]] for more information and examples.


### Conditional Convergence
If a series does not absolutely converge but converges in some cases, it is conditionally convergent. Conditionally convergent series are always alternating series, and their positive terms individually and their negative terms individually will form two divergent series. 

These series will converge if their terms are ordered in a specific fashion, and diverge if they are ordered in other fashions.

### Useful Properties of Series
1. The convergence or divergence of a series is not affected by multiplying every term of the series by the same nonzero constant. Neither is it affected by changing a finite number of terms (such as omitting the first few terms).
2. Two convergent series may be added or subtracted term by term. The resulting series is convergent and the sum is obtained by adding/subtracting the sums of the two given series.
3. The terms of an absolutely convergent series may be rearranged in any order without affecting either the convergence or the sum. This is not true of conditionally convergent series.

### Power Series and Intervals of Convergence

A power series takes the form
$$
\sum_{n=0}^{\infty} a_{n}x^{n}=a_{0}+a_{1}x+a_{2}x^{2}+a_{3}x^{3}+\dots
$$
or
$$
\sum_{n=0}^{\infty} a_{n}(x-a)^{n}=a_{0}+a_{1}(x-a)+a_{2}(x-a)^{2}+a_{3}(x-a)^{3}+\dots
$$
Whether or not a power series converges depends on the value of $x$. We can often do this with the ratio test. We end up with the ratio being the absolute value of some function of $x$, and we know a series converges if the ratio is less than one. Comparing these allows us to find the intervals of convergence of the power series.

### Theorems of Power Series
1. A power series may be differentiated or integrated term by term; the resulting series converges to the derivative or integral of the function represented by the original series within the same interval of convergence as the original series (that is, not necessarily at the endpoints of the interval).
2. Two power series may be added, subtracted, or multiplied; the resultant series converges at least in the common interval of convergence. You may divide two series if the denominator series is not zero at x = 0, or if it is and the zero is canceled by the numerator (as, for example, in $(\sin x)/x$). The resulting series will have some interval of convergence (which can be found by the ratio test or more simply by complex variable theory).
3. One series may be substituted in another provided that the values of the substituted series are in the interval of convergence of the other series.
4. 1The power series of a function is unique, that is, there is just one power series of the form $\sum_{n=0}^{\infty}a_{n}x^{n}$ which converges to a given function.

### Expanding Functions in Power Series

If we have a function $f(x)$, one way to find a power series representing it is to assume first that there exists such a series, and then to find the coefficients by repeatedly differentiating $f(x)$. For instance:
$$
\begin{align}
f(x) & = a_{0}+a_{1}x+a_{2}x^{2}+\dots+a_{n}x^{n}+\dots \\
f'(x)  & = a_{1}+2a_{2}x+3a_{3}x^{2}+\dots+na_{n}x^{n}+\dots
\end{align}
$$
and so on. Then we can solve for $a_{n}$. 
A power series found this way is called a Taylor series about the origin (finding it about a point $x=a$ can also be done by substituting $x\to(x-a)$ in the above expressions).
Generally, the Taylor series takes the form
$$
f(x)=\sum_{n=0}^{\infty} \frac{(x-a)^{n}}{n!}f^{(n)}(a)
$$
This is a rather clunky method, however. We know that power series representations of functions are unique, so we can find it with *any* method, not just this one.


>[!note] Multiplying a Series by a Polynomial or by Another Series
>To find the series of a product of functions, we can multiply the two series together. For $f(x)=\sum a_{n}x^{n}$ and $g(x)=\sum b_{n}x^{n}$, then $f(x)g(x)=\left( \sum a_{n}x^{n} \right)\left( \sum b_{n}x^{n} \right)$. 
>If one of the functions is a polynomial, then it is itself a power series, so you can just multiply the polynomial by the series of the other function.


>[!note] Dividing a Series by a Polynomial or by Another Series
>To find the series of a quotient of functions, we can divide the two series. For $f(x)=\sum a_{n}x^{n}$ and $g(x)=\sum b_{n}x^{n}$,  then $\frac{f(x)}{g(x)}=\frac{\sum a_{n}x^{n}}{\sum b_{n}x^{n}}$.
>If one of the functions is a polynomial, then it is itself a power series, so you can just divide the series by the polynomial or vice versa.


>[!note] Binomial Series
>The generalized binomial theorem is
> $$
(1+x)^{p}=\sum_{n=0}^{\infty} \frac{\left( \prod_{k=0}^{n-1} (p-k) \right)^{[n\neq0]}}{n!} x^{n} $$
>(where $[n\neq 0]$ denotes an [[#Endnote|Iverson bracket]]) or, in less complicated notation,
>$$
(1+x)^{p}=1+px+\frac{p(p-1)}{2!}x^{2}+\frac{p(p-1)(p-2)}{3!}x^{3}+\dots $$
^5b5e7c

>[!note] Substitution of a Polynomial or Series for the Variable in Another Series
>To find the series of a function of composition, we can substitute the series for one into the series for another. For $f(x)=\sum a_{n}x^{n}$ and $g(x)=\sum b_{n}x^{n}$,  then $f(g(x))=\sum a_{n}\left( \sum b_{n}x^{n} \right)^{n}$. 
>


>[!note] Use a Computer


### Error of Approximation
If $S=\sum_{n=1}^{\infty}a_{n}$ is an alternating series with $|a_{n+1}|<|a_{n}|$, and $\lim_{ n \to \infty }a_{n}=0$ (that is, it converges), then the error for an $n$-th order approximation is $\left|S-(a_{1}+a_{2}+\dots+a_{n})\right|\leq|a_{n+1}|$. 


If $S=\sum_{n=0}^{\infty}a_{n}x^{n}$ converges for $|x|<1$ and if $|a_{n+1}|<|a_n|\mathrm{~for~}n>N$, then $\left|S-\sum_{n=0}^Na_nx^n\right|<|a_{N+1}x^{N+1}|\div(1-|x|).$






### Endnote
>[!info] The Iverson Bracket
>The Iverson Bracket is a function defined for a conditional proposition $P$ as $$
[P]\equiv \begin{cases}
1, & \text{if }P\text{ is true;} \\
0, & \text{otherwise.}
\end{cases} $$

So in the generalized binomial theorem [[#^5b5e7c |above]], $[n\neq 0]$ is zero for $n=0$ and one everywhere else.  
^4aa0d7










