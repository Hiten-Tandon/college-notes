Vertical Asymptotes are [[Parallel Asymptotes]]
To find vertical asymptotes of a curve we can either use the method discussed earlier, or we can use a shortcut.

Let's derive the shortcut.

So let's say, we have a polynomial of n<sup>th</sup> degree let's call it p(x, y), now let's say, p(x, y) = k, hence, p(x, y) - k = 0  
Now, we want to find the vertical asymptote to this polynomial is.

The qualification of a vertical asymptote is that, it will meet the curve at y = &infin; thus, let's put a limit on our polynomial.

$$\lim_{y\rightarrow\infty} p(x, y) - k = 0$$
Now, we know that, as limit tends to infinity, only the highest order term of the said variable is considered, and rest of the equation is ignored. Let's name this term, t(y), thus we get the equation
$$\lim_{y\rightarrow\infty}t(y) = 0$$
Let's say that the order of t(y) in terms of y is n, then we know that t(y) can be re-written as y<sup>n</sup>(C) where C is the coefficient of the term.
this means the limit can now be rewritten as:
$$\lim_{y\rightarrow\infty}Cy^n = 0$$
Thus, from this, we get two plausible solutions of this, 
$$\lim_{y\rightarrow\infty}C = 0,\ \lim_{y\rightarrow\infty}y^n = 0$$
However, since y is tending to &infin; it can't be zero, hence we get 
$$\lim_{y\rightarrow\infty}C = 0$$
Now, since the equation has no y, the limit can be dropped and we get:
$$C = 0$$
This is an important result as we can essentially find all the vertical asymptotes to any curve.

For example let's say we have an equation: 
$$3x^2y +xy - 4y = 0$$
The highest power of y in equation is 1, hence we set it's coefficient to 0.
$$3x^2 + x -4 = 0$$
This can be easily factorized to 
$$(3x + 4)(x - 1) = 0$$
i.e. $$ x = 1\ or,\ -1\frac{1}{3}$$
Thus this equation has two vertical asymptotes, $$x_1 = 1$$ and $$x_2 = -1\frac{1}{3}$$