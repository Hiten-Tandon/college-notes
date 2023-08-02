Asymptotes are lines which touch a given curve, at infinity.
They're basically tangents to a curve at infinity.
There are two kinds of Asymptotes, 
1. [[Parallel Asymptotes|Parallel Asymptotes]]
2. [[Engg. Mathematics/Oblique Asymptotes|Oblique Asymptotes]]

To calculate asymptotes, 
1. Put x = 1 and y = m in the highest degree term of the equation, say &Phi;<sub>n</sub>(m)
2. Solve the following to get the slopes $$m\ \epsilon\ \{x\ |\ x\ \ \epsilon\ R\ and \ \phi_n(x) = 0\}$$
3. Then use the following to get c<sub>i</sub> $$\forall \ i \ \epsilon\ \{1\ldots n\}\ \exists\ c_i = \frac{\phi_{n-1}(m_i)}{\phi_n'(m_i)}$$
4. If you get same equation say N number of times, use the following equation to adjust the lines. $$\sum_{i=0}^{N}{\frac{c^i}{i!}\frac{d^i\phi_{n - N + i}(m)}{dx^i}} = 0$$
Now you have the asymptotic lines as $$y_i = m_ix + c_i$$
Note: 
- if m &varepsilon; {-&infin;, 0, &infin;}, the asymptote is a parallel asymptote
	- x-parallel or horizontal if m is 0
	- y-parallel or vertical if m is &pm;&infin; 	
 - If m or c is an Imaginary number, the asymptote doesn't exist.
