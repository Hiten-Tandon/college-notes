Asymptotes are lines which touch a given curve, at infinity.
They're basically tangents to a curve at infinity.
There are two kinds of Asymptotes, 
1. [[Parallel Asymptotes|Parallel Asymptotes]]
2. [[Engg. Mathematics/Oblique Asymptotes|Oblique Asymptotes]]

To calculate asymptotes, 
1. Put x = 1 and y = m in the highest degree term of the equation, say &Phi;<sub>n</sub>(m)
2. Solve the following to get the slopes $$m\ \epsilon\ \{x\ |\ x\ \ \epsilon\ R\ and \ \phi_n(x) = 0\}$$
3. Then use the following to get c<sub>i</sub> $$\forall \ i \ \epsilon\ \{1\ldots n\}\ \exists\ c_i = \frac{\phi_{n-1}(m_i)}{\phi_n'(m_i)}$$
4. If you get same equation say N number of times, use the roots(c<sub>i</sub>) of the following equation to adjust the lines. $$\sum_{i=0}^{N}{\frac{c^i}{i!}\frac{d^i\phi_{n - N + i}(m)}{dm^i}} = 0$$
Now you have the asymptotic lines as $$y_i = m_ix + c_i$$
Note: 
- if m &varepsilon; {-&infin;, 0, &infin;}, the asymptote is a parallel asymptote
	- x-parallel or horizontal if m is 0
	- y-parallel or vertical if m is &pm;&infin; 	
 - If m or c is an Imaginary number, the asymptote doesn't exist.

For Example, let's take the equation $$(x + y)^2(3x + 2y) + 2x^2 - 3y^2 + 7y -10 = 0$$
Here, the highest order of the equation is 3. So, we take all the order 3 terms of the equation, and set x = 1, y = m
$$ \phi_3(m) = (m + 1)^2(2m + 3)$$
Then set &Phi;<sub>3</sub>(m) = 0
$$\phi_3(m) = (m + 1)^2(2m + 3) = 0$$
Solving this, we get, three values for m
$$ m \epsilon \{-1, -1, -1\frac{1}{2}\}$$
First we'll calculate c for the different term by the formula
$$c_i = -\frac{\phi_2(m)}{\phi_3'(m)}$$
where, 
$$\phi_2(m) = 2 - 3m^2 [substitute\ x\ for\ 1\ and\ y\ for\ m]$$
and, $$\phi_3(m) = (m + 1)^2(2m + 3)$$
$$\implies \phi_3'(m) = \frac{d}{dm}((m + 1)^2(2m + 3)) $$
$$or,\ \phi_3'(m) = 2(m+1)(2m+3) + 2(m + 1)^2$$
$$or,\ \phi_3'(m) = 6m^2 + 14m + 8$$
$$\implies c = -\frac{2 - 3m^2}{6m^2 + 14m + 8} $$
$$\implies c = \frac{3m^2 - 2}{6m^2+14m+8}$$
putting in the only unique value of m (i.e. -1.5), in the formula for c, we get
$$\implies c_1 = \frac{3(-1\frac{1}{2})^2 - 2}{6(-1\frac{1}{2})^2+14(-1\frac{1}{2}) + 8}$$
$$\implies c_1 = \frac{3(2\frac{1}{4}) - 2}{6(2\frac{1}{4}) + 14(-1\frac{1}{2}) + 8} $$
$$\implies c_1 = \frac{6\frac{3}{4} - 2}{13\frac{1}{2} - 21 + 10}$$
$$\implies c_1 = \frac{4\frac{3}{4}}{2\frac{1}{2}}$$
$$\implies c_1 = 1\frac{9}{10}$$
Thus, we can write our first asymptote's equation to be
$$y_1 = -\frac{3x}{2} + 1\frac{9}{10}$$
Now, let's calculate the constants for the asymptote's equations, to do so we need to put
$$\sum_{i = 0}^{N}{\frac{c^i}{i!}\frac{d^i\phi_{n-N+i}(m)}{dm^i}} = 0$$
here, N = 2, n = 3 and m = -1, therefore, the above statement can be re-written as follows:
$$\phi_1(-1) + c(\phi_2'(-1)) + \frac{c^2}{2}(\phi_3''(-1)) = 0$$
$$\phi_1(-1) = 7(-1) = -7$$
$$\phi_2'(m) = \frac{d}{dm}(2 - 3m^2) = -6m$$
$$\implies \phi_2'(-1) = -6(-1) = 6$$
Now,
$$\phi_3''(m) = \frac{d}{dm}(\phi_3'(m))$$
which we already have from when we calculated it for the c<sub>1</sub> calculation.
$$\implies \phi_3''(m) = \frac{d}{dm}(6m^2 + 14m +8) = (12m + 14)$$
$$\implies\phi_3''(-1)= 14 - 12 = 2$$
Putting these values in the initial equation, we get:
$$\frac{c^2}{2}(2) + 6c -7 = 0$$
$$\implies c^2 + 6c -7 = 0$$
which can be simply factorized into,
$$(c - 1)(c + 7) = 0$$
thus, we get:
$$c_2 = -7, c_3 = 1$$
Giving us the equations of asymptotes 2 and 3 as follows:
$$y_2 = -x - 7$$
$$y_3 = -x + 1$$
Thus, we get the three asymptotes for the equations as follows:
$$y_1 = -\frac{3x}{2} + 1\frac{9}{10}$$
$$y_2 = -x-7$$$$y_3 = -x + 1$$
<!--Nice :)-->