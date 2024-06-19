- [ ] ---
tags:
  - Physics100A
  - 100ANotes
---
---
Notes taken from *Mathematical Methods in the Physical Sciences*, Chapter 7, by Mary L. Boas.
### Simple Harmonic Motion and Wave Motion
Let particle $P$ move at a constant speed around a circle of radius $A$. At the same time, let particle $Q$ move up and down along the straight line segment $RS$ in such a way that the $y$-coordinates of $P$ and $Q$ are always equal. 
![[IMG_93C1A4A08C33-1.jpeg|300]]

If $\omega$ is the angular velocity of $P$ in radians per second, and $\theta=0\text{ }@ \text{ }t=0$, then at a later time $t$
$$
\theta=\omega t.
$$
The $y$ coordinate of $Q$ is
$$
y=A\sin\theta=A\sin\omega t.
$$
The back and forth motion of the point $Q$ is called ***simple harmonic motion***. By definition an object is executing simple harmonic motion if its displacement from equilibrium can be written as a sinusoidal function such as $A\sin\omega t$, $A\cos\omega t$, $A\sin(\omega t+\phi)$, etc. Many physical systems obey this sort of motion, such as pendulums, tuning forks, etc.

The $x$ and $y$ coordinates of particle $P$ are
$$
x=A\cos\omega t,\hspace{0.5 in} y=A\sin \omega t.
$$
We can graph $x$ and $y$ as a function of $t$.
![[Screenshot 2024-04-10 at 19.50.14.png|400]]
Here the number $A$ is called the ***amplitude*** of the oscillation, and physically it represents the maximum displacement of $Q$ from the equilibrium position. The ***period*** of the oscillation is the time it takes to complete one oscillation, which is $T=2\pi/\omega$. 
Differentiating $y$ gives
$$
\frac{dy}{dt}=A\omega \cos\omega t,
$$
the velocity of the point $Q$. The maximum value of $dy/dt$, $A\omega$, is called the ***velocity amplitude*** of the oscillation.

If we think of $P$ as a point $z=x+iy$ in the complex plane, we can replace these equations by a single equation
$$
z=Ae^{ i\omega t }.
$$
We often use an equation of this form to describe the motion of $Q$ as well, understanding that the actual position of the point is the imaginary component (or, given different starting conditions, the real component).

All of these equations are periodic functions.

> [!example] Periodic Function
> A function $f(x)$ is called ***periodic*** if it satisfies the equation
> $$
f(x+p)=f(x),$$
for all values of $x$. The value $p$ is called the period of the function.

^44d6dd

### Introducing the Fourier Series
#### Applications of the Fourier Series
A good use for the Fourier series, which will be introduced momentarily, is sound waves in music. If you strike a key on a piano, the resulting sound you hear is not only one frequency. Rather you get a primary wave with one frequency (called the fundamental) and a number of secondary waves with different frequencies (called overtones). The overtone frequencies, specifically, are integer multiples of the fundamental frequency. The combination of waves with all these frequencies is a rather complicated periodic function with the period of the fundamental. We can use a Fourier series, an infinite series of sines and cosines, to express this superposition of the fundamental and its overtones. Expanding a function in a Fourier series then amounts to breaking it down into its various harmonics, in a process which is sometimes called harmonic analysis.

The Fourier series can, in general, be used to represent any periodic function. Some simple waves which we can use this technique for are below.
![[Screenshot 2024-04-10 at 20.05.26.png|400]]

There are applications to other fields, obviously. Radio waves, visible light, and x-rays are all waves, as are water waves and earthquake waves. Fourier analysis can apply to all of these.

#### Preliminary Work
According to Mary L. Boas, [PhD in physics, MIT graduate](http://www.legacy.com/obituaries/seattletimes/obituary.aspx?n=mary-elizabeth-layne-boas&pid=139866372), and [longtime supporter of female physics students](https://web.archive.org/web/20120428055447/http://www.phys.washington.edu/awards.htm),

> [!quote] Boas p. 347
> The concept of the average value of a function is often useful.

Boas hath spoken. We shall endeavor to define this "average value".

To find the average of a set of numbers, we simply sum them and divide by the number of numbers.
$$
\text{average}=\frac{\sum_{i=1}^{n} a_{i}}{n}.
$$
We look for a similar form for a continuous variable. For a function $f(x)$ on the interval $(a,b)$, we can average a number of values of $f(x)$:
$$
\text{average}\approx \frac{f(x_{1})+f(x_{2})+\dots+f(x_{n})}{n}.
$$
As the number of points $n$ increases, this will become a better and better approximation. If we let all the points $x_{i}$ be a constant distance $\Delta x$ apart, such that $\Delta x=\frac{b-a}{n}$, then we multiply the numerator and denominator of this equation by $\Delta x$:
$$
\text{average}\approx \frac{[f(x_{1})+f(x_{2})+\dots+f(x_{n})]\Delta x}{n\Delta x}.
$$
The denominator by definition is $b-a$. As $\Delta x\to 0$, the numerator approaches an integral, so we have:

> [!example] Average Value of a Function Over an Interval
> The average value of a function $f(x)$ over an interval $(a,b)$ is 
> $$
\langle f(x) \rangle = \frac{1}{b-a}\int_{a}^{b} f(x) \, \hspace{0.5mm} dx .$$

^542d64



It can further be shown that

> [!tip] Average Values of Square Trig Functions
> $$
\begin{align}
\langle \sin ^{2}nx \rangle_{T}  & = \frac{1}{2\pi}\int_{-\pi}^{\pi} \sin ^{2}nx \, \hspace{0.5mm} dx = \frac{1}{2}, \\
\langle \cos ^{2}nx \rangle_{T}  & = \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos ^{2}nx \, \hspace{0.5mm} dx = \frac{1}{2}.
\end{align}$$
>These are the average values of these functions over one period, $T$.




#### Fourier Coefficients

We want to expand a given periodic function $f(x)$ in terms of an infinite series of sines and cosines. (This is the entire aim of the Fourier series.) 

> [!warning] Assumption of the Period
> In this derivation, we simply our job by assuming that the period of the function $f(x)$ is $2\pi$. This isn't necessary, but it simplifies the problem a bit since both sine and cosine have periods of $2\pi$, and we can generalize later.

We can then write
$$
f(x)=\frac{a_{0}}{2}+a_{1}\cos x+a_{2}\cos 2x+a_{3}\cos 3x+\dots+b_{1}\sin x+b_{2}\sin 2x+ b_{3}\sin 3x +\dots,
$$

^a104b8

and from here derive formulas for the coefficients $a_{n},b_{n}$. Overlook the $\frac{1}{2}$ in the first term for the moment, it's addition will become clear later.

First we define these useful integrals.

> [!tip] Useful Trig Integrals
> Over an interval $I=(-\pi,\pi)$, we have 
> $$
\begin{align}
 & \langle \sin mx\cos nx \rangle_{I}   = \frac{1}{2\pi}\int_{-\pi}^{\pi} \sin mx\cos nx \, \hspace{0.5mm} dx = 0. \\
& \langle \sin mx\sin nx \rangle_{I}  = \frac{1}{2\pi}\int_{-\pi}^{\pi} \sin mx\sin nx \, \hspace{0.5mm} dx = \begin{cases}
0, & m\neq n, \\
\frac{1}{2}, & m=n\neq 0, \\
0, & m=n=0.
\end{cases} \\
& \langle \cos mx\cos nx \rangle _{I}   = \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos mx\cos nx \, \hspace{0.5mm} dx = \begin{cases}
0, & m\neq n, \\
\frac{1}{2}, & m=n\neq 0, \\
1, & m=n=0.
\end{cases}
\end{align}$$

^7295e6

Proving these could very well be a useful exercise.

To find the coefficient $a_{n}$ and $b_{n}$, we find the average value of $f(x)$ over the interval $I$. 
$$
\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x) \, \hspace{0.5mm} dx = \frac{a_{0}}{2} \frac{1}{2\pi}\int_{-\pi}^{\pi}  \, \hspace{0.5mm} dx +a_{1} \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos x \, \hspace{0.5mm} dx +\dots+b_{1} \frac{1}{2\pi}\int_{-\pi}^{\pi} \sin x \, \hspace{0.5mm} dx +\dots.
$$
By the [[#^7295e6|Useful Trig Integrals]] above, all integrals on the right hand side vanish except the first ($m\neq n$). So
$$
\begin{align}
\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x) \, \hspace{0.5mm} dx  & = \frac{a_{0}}{2} \frac{1}{2\pi}\int_{-\pi}^{\pi}  \, \hspace{0.5mm} dx , \\
a_{0} & = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x) \, \hspace{0.5mm} dx .
\end{align}
$$
Since we're given $f(x)$ as a function to be expanded, we can find $a_{0}$ by evaluating the integral.

One down, infinitely many to go!

To find $a_{1}$, we multiply both sides of the equation by $\cos x$ and repeat the process.
$$
\begin{align}
\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)\cos x \, \hspace{0.5mm} dx =  \frac{a_{0}}{2} \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos x \, \hspace{0.5mm} dx &+a_{1} \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos ^{2}x \, \hspace{0.5mm} dx +a_{2} \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos 2x \cos x \, \hspace{0.5mm} dx \\ & +\dots+b_{1} \frac{1}{2\pi}\int_{-\pi}^{\pi} \sin x\cos x \, \hspace{0.5mm} dx + \dots.
\end{align}
$$
This time all terms on the right are zero except the $a_{1}$ term, and we have
$$
\begin{align}
\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)\cos x \, \hspace{0.5mm} dx  & =a_{1} \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos ^{2}x \, \hspace{0.5mm} dx = \frac{a_{1}}{2}, \\
a_{1} & = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\cos x \, \hspace{0.5mm} dx .
\end{align}
$$
Two down, infinitely many to go!

We can now write down a general formula for $a_{n}$. We multiply both sides of the $f(x)$ expansion by $\cos nx$ and find the average value of $f(x)$. All terms then vanish except the $a_{n}$ term, and we have
$$
\begin{align}
\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)\cos nx \, \hspace{0.5mm} dx  & =a_{n} \frac{1}{2\pi}\int_{-\pi}^{\pi} \cos ^{2}nx \, \hspace{0.5mm} dx = \frac{a_{n}}{2},
\end{align}
$$

> [!example] Cosine Coefficients in a Fourier Series
> $$
a_{n} = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\cos nx \, \hspace{0.5mm} dx .$$
^1f66de


> [!tip] The One-Half Explained
> Note that this formula includes the constant term $n=0$, but only because we included the $\frac{1}{2}$ in the original expansion.

We can similarly derive an equation for $b_{n}$.

> [!example] Sine Coefficients in a Fourier Series
> $$
b_{n}=\frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\sin nx \, \hspace{0.5mm} dx .$$
^6dc4e7



> [!warning] We're going to use these formulas a lot. Memorize them.

#### Example: The Square Wave
![[Screenshot 2024-04-10 at 20.51.00.png|600]]

Let $f(x)=\begin{cases}0,& -\pi<x<0, \\ 1, & 0<x<\pi \end{cases}$, and let $f(x)$ be continued periodically with period $2\pi$ outside the interval $(-\pi,\pi)$. 
We can find $a_{n}$ and $b_{n}$ using the formulas above.
$$
\begin{align}
a_{n}  & = \frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\cos nx \, \hspace{0.5mm} dx = \frac{1}{\pi}\left[ \int_{-\pi}^{0} 0\cdot \cos nx \, \hspace{0.5mm} dx + \int_{0}^{\pi} 1\cdot \cos nx \, \hspace{0.5mm} dx  \right], \\
& = \frac{1}{\pi}\int_{0}^{\pi} \cos nx \, \hspace{0.5mm} dx = \begin{cases}
0, & n\neq 0, \\
1, & n=0.
\end{cases}
\end{align}
$$



$$
\begin{align}
b_{n} & =\frac{1}{\pi}\int_{-\pi}^{\pi} f(x)\sin nx \, \hspace{0.5mm} dx = \frac{1}{\pi}\left[ \int_{-\pi}^{0} 0\cdot \sin nx \, \hspace{0.5mm} dx +\int_{0}^{\pi} 1\cdot \sin nx \, \hspace{0.5mm} dx  \right], \\
 & = \frac{1}{\pi}\int_{0}^{\pi} \sin nx \, \hspace{0.5mm} dx = \begin{cases}
0, & \text{for even } n, \\
\frac{2}{n\pi}, & \text{for odd } n.
\end{cases}
\end{align}
$$



Putting these coefficients all together, we have
$$
f(x)=\frac{1}{2} + \frac{2}{\pi}\left( \sin x+\frac{1}{3}\sin 3x+\frac{1}{5}\sin 5x +\dots \right) .
$$

We can expand this result to some other cases using [[Basics of Series Expansions#Expanding Functions in Power Series|series techniques]] (the manipulations of series to find other series is consistent for Fourier series as well as for power series). 

For example, consider the function $g(x)=\begin{cases}-1,& -\pi<x<0, \\ 1, & 0<x<\pi\end{cases}$. We can simplify this by noting that $g(x)=2f(x)-1$, where $f(x)$ is our square wave from above. Applying the same manipulations to the series of $f(x)$, we have
$$
g(x)=\frac{4}{\pi}\left( \sin x+\frac{1}{3}\sin 3x+\frac{1}{5}\sin 5x + \dots \right) .
$$

### Dirichlet Conditions
Now we have a series, but there are still some questions that we ought to get answered. Does it converge, and if so, does it converge to the values of $f(x)$? You will find, if you try, that for most values of $x$ the series does not respond to any of the [[Basics of Series Expansions#Divergence and Convergence Tests|tests for convergence already discussed]]. What is the sum of the series at $x=0$ where $f(x)$ jumps from 0 to 1? You can see from the Fourier series that the sum at $x=0$ is 1, but what does this have to do with $f(x)$?

Most of these questions are answered for most practical purposes by Dirichlet's theorem.


> [!example] Dirichlet's Theorem
> If a [[#^44d6dd|periodic function]] $f(x)$ satisfies the following ***Dirichlet conditions***:
> 1. The period of $f(x)$ is $2\pi$.
> 2. $f(x)$ is single valued on the interval $(-\pi,\pi)$.
> 3. $f(x)$ has a finite number of extremum values on the interval $(-\pi,\pi)$. 
> 4. $f(x)$ has a finite number of discontinuities on the interval $(-\pi,\pi)$. 
> 5. The integral $\int_{-\pi}^{\pi} |f(x)| \, \hspace{0.5mm} dx$ converges to a finite value.
> 
> Then the [[#^c9f528|Fourier series]] converges to $f(x)$ at all points where $f(x)$ is continuous. At jump discontinuities, the Fourier series converges to the midpoint of the jump.
^f11c7f


Most functions in applied work match this description. A notable exemption is $f(x)=1/x$, which fails condition 5. On the other hand, $f(x)=1/\sqrt{ |x| }$ does satisfy the Dirichlet conditions. 


> [!tip] Applying the Dirichlet Conditions
> This is useful because instead of needing to check the convergence of the Fourier series for each function we can instead check the function itself against the Dirichlet conditions beforehand. If they check out, then we know that the Fourier series will converge before we find it.


> [!warning] The Converse of Dirichlet's Theorem
> Note that the converse of Dirichlet's theorem is not true. If a function fails to satisfy Dirichlet's conditions, then it still *may* be expandable in a Fourier series. However, such functions are rarely met with in practice.


### The Complex Fourier Series

We can express real sines and cosines can be expressed in terms of complex exponentials by the formulas
$$
\sin nx=\frac{e^{ inx }-e^{ -inx }}{2i},\hspace{0.5in}\cos nx=\frac{e^{ inx }+e^{ -inx }}{2}.
$$
Substituting these equations into the trigonometric Fourier series, we can find a series in terms of $e^{ inx }$ and $e^{ -inx }$. Alternatively, we could simply do it directly.
$$
f(x)=c_{0}+c_{1}e^{ ix }+c_{-1}e^{ -ix }+c_{2}e^{ 2ix }+c_{-2}e^{ -2ix }+\dots=\sum_{n=-\infty}^{n=\infty} c_{n}e^{ inx }.
$$
We then use a similar method to find the coefficients.
$$
c_{n}=\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)e^{ -inx } \, \hspace{0.5mm} dx .
$$
### Other Intervals and Periods
The functions $\sin nx$, $\cos nx$, and $e^{ inx }$ have period $2\pi$. Previously we've been using the interval $(-\pi,\pi)$, but any interval can work so long as we adjust the bounds of integration, and the equations for coefficients $a_{n},b_{n},c_{n}$ we found previously would remain the same. 

We can change the period by recalling that a function $\sin\omega t$ has period $2\pi/\omega$. For a period of $2l$, the function becomes $\sin(\frac{n\pi x}{l})$. Our coefficients are then
$$
\begin{align}
a_{n} & = \frac{1}{l}\int_{-l}^{l} f(x)\cos\left( \frac{n\pi x}{l} \right) \, \hspace{0.5mm} dx , \\
b_{n} & = \frac{1}{l}\int_{-l}^{l} f(x)\sin\left( \frac{n\pi x}{l} \right) \, \hspace{0.5mm} dx , \\
c_{n} & = \frac{1}{2l}\int_{-l}^{l} f(x)e^{ -in\pi x/l } \, \hspace{0.5mm} dx .
\end{align}
$$
The Dirichlet theorem needs $\pi$ replaced by $l$ in order to apply here.

### Even and Odd Functions


> [!example] Even and Odd Functions
> A function $f(x)$ is called ***even*** if $f(-x)=f(x)$.
> It is called ***odd*** if $f(-x)=-f(x)$. 

^e413f4

If $f(x)$ is odd, then $\int_{-l}^{l} f(x) \, \hspace{0.5mm} dx=0$. If it is even, however, $\int_{-l}^{l} f(x) \, \hspace{0.5mm} dx=2\int_{0}^{l} f(x) \, \hspace{0.5mm} dx$. The formulas for coefficients simplify in these cases.

If $f(x)$ is odd, $\begin{cases}b_{n}=\frac{2}{l}\int_{0}^{l} f(x)\sin \frac{\pi nx}{l} \, \hspace{0.5mm} dx,\\ a_{n}=0.  \end{cases}$ Odd functions can therefore be expanded in a sine series.
If $f(x)$ is even, $\begin{cases}a_{n}=\frac{2}{l}\int_{0}^{l} f(x)\cos \frac{n\pi x}{l} \, \hspace{0.5mm} dx,\\ b_{n}=0.\end{cases}$ Even functions can therefore be expanded in a cosine series. 

### Parseval's Theorem
We begin with the equation  
$$
f(x)=\frac{a_{0}}{2}+\sum_{n=1}^{\infty} a_{n}\cos nx+\sum_{n=1}^{\infty} b_{n}\sin nx.
$$
We square $f(x)$ and then average the square over $(-\pi,\pi)$. 
$$
\langle f^{2}(x) \rangle = \frac{1}{2\pi}\int_{-\pi}^{\pi} f^{2}(x) \, \hspace{0.5mm} dx .
$$
To avoid writing out a large number of terms from squaring the Fourier series, we consider the types of terms. Using the fact that $\langle \sin ^{2}nx \rangle=\langle \cos ^{2}nx \rangle=\frac{1}{2}$, we have
$$
\begin{align}
\left\langle  a_{0}^{2}/4 \right\rangle  & = a_{0}^{2}/4, \\
\langle a_{n} ^{2}\cos ^{2}nx \rangle  & = a_{n}^{2}/2, \\
\langle b_{n}^{2}\sin ^{2}nx \rangle  & = b_{n}^{2}/2.
\end{align}
$$
All other terms vanish. So then we have
$$
\langle f^{2}(x) \rangle = \left( \frac{a_{0}}{2} \right)^{2}+\frac{1}{2}\sum_{n=1}^{\infty} a_{n}^{2}+\frac{1}{2}\sum_{n=1}^{\infty} b_{n}^{2}.
$$
This is one form of ***Parseval's theorem***. It is unchanged if the interval is $2l$ instead of $2\pi$. If we write $f(x)$ as a complex exponential Fourier series and allow for the function to be complex valued, then we find
$$
|f(x)|^{2}=\sum_{n=-\infty}^{\infty} |c_{n}|^{2}.
$$
This is also called the ***completeness relation***. 

> [!example] Implication of Parseval's Theorem for Fourier Series
> For a [[#^c9f528|Fourier series]] representation of $f(x)$, with $a_{n}$ being the cosine coefficients, $b_{n}$ being the sine coefficients, and $c_{n}$ being the exponential coefficients, then ***Parseval's theorem*** implies:
>$$
\begin{align}
\langle f(x)^{2} \rangle  & = \left( \frac{a_{0}}{2} \right)^{2}+\frac{1}{2}\sum_{n=1}^{\infty} (a_{n}^{2}+b_{n}^{2})=\sum_{n=-\infty}^{\infty} \left| c_{n} \right| ^{2}.
\end{align}$$
>This is also called the ***completeness relation*** for Fourier series.


### Fourier Transforms

Up until now we've been expanding periodic functions with the Fourier series. What if we can represent a function which isn't periodic using something similar? And can we extend the Fourier series to cover a case where $n$ is a continuous variable rather than discrete?

In these cases, we can extend the Fourier series to the Fourier integral. We recall the complex Fourier series formulas:
$$
\begin{align}
f(x) & = \sum_{n=-\infty}^{\infty} c_{n}e^{ in\pi x/l }, \\
c_{n} & = \frac{1}{2l}\int_{-l}^{l} f(x)e^{ -in\pi x/l } \, \hspace{0.5mm} dx .
\end{align}
$$
The period of $f(x)$ is $2l$ and the frequencies of the terms in the series are $\frac{n}{2l}$. For a continuous range of frequencies, we now define



> [!example] The Fourier Transform 
>$$
\begin{align}
f(x) & =\int_{-\infty}^{\infty} g(\alpha)e^{ i\alpha x } \, \hspace{0.5mm} d\alpha, \\
g(\alpha) & = \frac{1}{2\pi}\int_{-\infty}^{\infty} f(x)e^{ -i\alpha x } \, \hspace{0.5mm} dx .
\end{align}$$
^0eb83e



Here, $g(\alpha)$ corresponds to $c_{n}$, $\alpha$ corresponds to $n$, and $\int_{-\infty}^{\infty}$ corresponds to $\sum_{-\infty}^{\infty}$. The functions $f(x)$ and $g(\alpha)$ are called a pair of *Fourier transforms*. Usually $g(\alpha)$ is called the Fourier transform of $f(x)$, and $f(x)$ is called the inverse Fourier transform of $g(\alpha)$, though it's rather common to call them both Fourier transforms as the integrals only differ in form in the sign of the exponent.


> [!example] The Fourier Integral Theorem
> If a function $f(x)$ satisfies the [[#^f11c7f|Dirichlet conditions]] on every finite interval, and if $\int_{-\infty}^{\infty} |f(x)| \, \hspace{0.5mm} dx$ is finite, then the [[Fourier Series and Transforms#^0eb83e|Fourier transform]] statements are true.

^a48613

#### Plausibility
What follows is an explanation of the plausibility of the definition of the Fourier transform, rather than a comprehensive mathematical proof.

It might seem reasonable for a non-periodic function by letting the period $(-l,l)$ increase to $(-\infty,\infty)$. Let's try to do this. If we call $\frac{n\pi}{l}=\alpha_{n}$ and $\alpha_{n+1}-\alpha_{n}=\frac{\pi}{l}=\Delta\alpha$, then $\frac{1}{2l}=\frac{\Delta a}{2\pi}$ and we can rewrite the complex Fourier series as
$$
\begin{align}
f(x) & = \sum_{-\infty}^{\infty} c_{n}e^{ \alpha_{n}x }, \\
c_{n} & = \frac{1}{2l}\int_{-l}^{l} f(x)e^{ -i\alpha_{n}x } \, \hspace{0.5mm} dx = \frac{\alpha}{2\pi}\int_{-l}^{l} f(u)e^{ -i\alpha_{n}u } \, \hspace{0.5mm} du .
\end{align}
$$
Substituting the coefficients into the series expansion, we have
$$
\begin{align}
f(x) & = \sum_{-\infty}^{\infty} \left[ \frac{\Delta\alpha}{2\pi}\int_{-l}^{l} f(u)e^{ -i\alpha_{n}u } \, \hspace{0.5mm} du  \right] e^{ i\alpha_{n}u }, \\
 & = \sum_{-\infty}^{\infty} \frac{\Delta\alpha}{2\pi}\int_{-l}^{l} f(u)e^{ i\alpha_{n}(x-u) } \, \hspace{0.5mm} du = \frac{1}{2\pi}\sum_{-\infty}^{\infty} F(\alpha_{n})\Delta\alpha,
\end{align}
$$
where 
$$
F(\alpha_{n})=\int_{-l}^{l} f(u)e^{ i\alpha_{n}(x-u) } \, \hspace{0.5mm} du.
$$
The summation looks rather like the formula for the sum whose limit is an integral as $\Delta\alpha\to 0$. If we let $l$ tend to infinity (letting the period tending to infinity), then $\Delta\alpha=\frac{\pi}{l}\to 0$, and the sum becomes an integral. We now get
$$
F(\alpha)=\int_{-\infty}^{\infty} f(u)e^{ i\alpha(x-u) } \, \hspace{0.5mm} du .
$$
Substituting this into the expansion of $f(x)$, we now have
$$
f(x)=\frac{1}{2\pi}\int_{-\infty}^{\infty} e^{ i\alpha x } \, \hspace{0.5mm} dx \int_{-\infty}^{\infty} f(u)e^{ -i\alpha u } \, \hspace{0.5mm} du .
$$
If we define $g(\alpha)$ by
$$
g(\alpha)=\frac{1}{2\pi}\int_{-\infty}^{\infty} f(x)e^{ -i\alpha x } \, \hspace{0.5mm} dx = \frac{1}{2\pi}\int_{-\infty}^{\infty} f(u)e^{ -i\alpha u } \, \hspace{0.5mm} du,
$$
then we have
$$
f(x)=\int_{-\infty}^{\infty} g(\alpha)e^{ i\alpha x } \, \hspace{0.5mm} d\alpha. 
$$
These equations are the same as the defined Fourier transforms. Note that the actual requirement for the factor of $\frac{1}{2\pi}$ is that the product of the constants multiplying the two integrals for $f(x)$ and $g(\alpha)$ should be $\frac{1}{2\pi}$.

#### Example: Fourier Transform of the Gaussian
This section is taken from the Shankar *Basic Training in Mathematics* book, Chapter 9. 

Take the [Gaussian function](https://en.wikipedia.org/wiki/Gaussian_function) $f(x)=e^{ -x^{2} }$. The Fourier transform of this is
$$
\begin{align}
g(\alpha) & = \int_{-\infty}^{\infty} e^{-x^{2}} e^{ -i\alpha x } \, \hspace{0.5mm} dx , \\
 & = e^{ -\alpha^{2}/4 }\int_{-\infty-i\alpha/2}^{\infty-i\alpha/2} e^{-z^{2}}  \, \hspace{0.5mm} dz, 
\end{align}
$$
for $z=x-\frac{i\alpha}{2}$. We recall that this integral equals $\sqrt{ \pi }$, so
$$
g(\alpha)= \sqrt{ \pi }e^{ -\alpha^{2}/4 },
$$
is the Fourier transform of the Gaussian. Note that it also is a Gaussian function.


#### Even and Odd Functions
If $f(x)$ is odd, then $g(\alpha)$ is likewise odd (proof on Boas pg 381). Following from this, we have the Fourier sine transforms.

> [!example] Fourier Sine Transforms
> We define $f_{s}(x)$ and $g_{s}(\alpha)$, a pair of ***Fourier sine transforms*** representing [[#^e413f4|odd functions]], by the equations
> $$
\begin{align}
f_{s}(x) & = \sqrt{ \frac{2}{\pi} }\int_{0}^{\infty} g_{s}(x)\sin\alpha x \, \hspace{0.5mm} d\alpha, \\
g_{s}(x)  & = \sqrt{ \frac{2}{\pi} }\int_{0}^{\infty} f_{s}(x)\sin\alpha x \, \hspace{0.5mm} dx .
\end{align}$$

Even functions are discussed in a similar manner, and so we arrive at the Fourier cosine transforms.


> [!example] Fourier Cosine Transforms
> We define $f_{c}(x)$ and $g_{c}(\alpha)$, a pair of ***Fourier cosine transforms*** representing [[#^e413f4|even functions]], by the equations
> $$
\begin{align}
f_{c}(x) & = \sqrt{ \frac{2}{\pi} }\int_{0}^{\infty} g_{c}(x)\cos\alpha x \, \hspace{0.5mm} d\alpha, \\
g_{c}(x)  & = \sqrt{ \frac{2}{\pi} }\int_{0}^{\infty} f_{c}(x)\cos\alpha x \, \hspace{0.5mm} dx .
\end{align}$$

#### Parseval's Theorem for Fourier Integrals

> [!example] Implication of Parseval's Theorem for Fourier Integrals
> $$
\int_{-\infty}^{\infty} |g(\alpha)|^{2} \, \hspace{0.5mm} d\alpha=\frac{1}{2\pi}\int_{-\infty}^{\infty} |f(x)|^{2} \, \hspace{0.5mm} dx . $$

### Summary

> [!example] The Fourier Series
> The Fourier series is a method of expanding [[#^44d6dd|periodic functions]] using an infinite series of sines and cosines. Given a function $f(x)$ with period $2l$ (periodic on any interval of that width), we can expand it as follows:
> $$
> \begin{align}
> f(x) & =\frac{a_{0}}{2}+\sum_{n=1}^{\infty} \left( a_{n}\cos \left( \frac{\pi nx}{l} \right)+b_{n}\sin \left( \frac{\pi nx}{l} \right) \right), \\
> a_{n} & = \frac{1}{l}\int_{-l}^{l} f(x)\cos\left( \frac{\pi nx}{l} \right) \, \hspace{0.5mm} dx , \\
> b_{n} & = \frac{1}{l}\int_{-l}^{l} f(x)\sin\left( \frac{\pi nx}{l} \right) \, \hspace{0.5mm} dx .
> \end{align}$$
> For a complex valued $f(x)$, we can also expand this function as follows:
> $$
> \begin{align}
> f(x) & = \sum_{n=-\infty}^{n=\infty} c_{n}e^{ inx }, \\
> c_{n} & = \frac{1}{2l}\int_{-l}^{l} f(x)e^{ -i\pi nx/l } \, \hspace{0.5mm} dx .
> \end{align}$$
> The complex Fourier series is equivalent to the trigonometric Fourier series by Euler's formula.
^c9f528


