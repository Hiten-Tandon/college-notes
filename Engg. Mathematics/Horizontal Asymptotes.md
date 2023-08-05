Horizontal Asymptotes are [[Parallel Asymptotes]]
To find horizontal asymptotes of a curve, we can either use the method discussed earlier, or a shortcut.

Let's derive the shortcut.
So let's say, we have a polynomial of n<sup>th</sup> degree let's call it p(x, y), now let's say, p(x, y) = k, hence, p(x, y) - k = 0  
Now, we want to find the vertical asymptote to this polynomial is.

The qualification of a vertical asymptote is that, it will meet the curve at x = &infin; thus, let's put a limit on our polynomial.

$$\lim_{x\rightarrow\infty} p(x, y) - k = 0$$
Now, we know that, as limit tends to infinity, only the highest order term of the said variable is considered, and rest of the equation is ignored. Let's name this term, t(x), thus we get the equation
$$\lim_{x\rightarrow\infty}t(x) = 0$$
Let's say that the order of t(x) in terms of x is n, then we know that t(x) can be re-written as x<sup>n</sup>(C) where C is the coefficient of the term.
this means the limit can now be rewritten as:
$$\lim_{x\rightarrow\infty}Cx^n = 0$$
Thus, from this, we get two plausible solutions of this, 
$$\lim_{x\rightarrow\infty}C = 0,\ \lim_{x\rightarrow\infty}x^n = 0$$
However, since x is tending to &infin; it can't be zero, hence we get 
$$\lim_{x\rightarrow\infty}C = 0$$
Now, since the equation has no x, the limit can be dropped and we get:
$$C = 0$$
This is an important result as we can essentially find all the horizontal asymptotes to any curve.


For ex: Let's say we have the following equation
$$3x^2y +2xy - 4y = 0$$
To obtain it's horizontal asymptote, set, $$3y = 0$$
Thus the horizontal asymptote of the curve is the x-axis.

Let's take another example: $$3x^2y + 2x^2 - 5xy + 3y - 7 = 0$$
Here the highest power of x is 2, hence we put it's coefficient to 0
$$3y + 2 = 0$$
or, $$y = -\frac{2}{3}$$
Let's take yet another example: $$-4x^2 + x^2y^2 + 2xy - y^2 + 3y = 0$$
The highest power of x is 2, hence we put it's coefficient to 0
$$y^2 - 4 = 0$$
$$y^2 = 4$$
or, $$y = \pm 2 $$
i.e. This equation has two horizontal asymptotes, $$y = 2$$ and $$y = -2$$