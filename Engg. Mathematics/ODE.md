General ODE:
$$\sum_{i = 0}^{n}{a_i \cdot \frac{d^i}{dx^i} y} = \phi(x)$$
Let $f$ be a function such that
$$\left( f \cdot \frac{d}{dx} \right) y = \sum_{i = 0}^{n}{a_i \cdot \frac{d^i}{dx^i}y}$$
Then, applying the inverse of the composed function on both sides of the equation:
$$y = \left( f \cdot \frac{d}{dx} \right)^{-1}(\phi(x))$$
$$\implies y = \int{f^{-1} (\phi(x)) dx}$$

$\because$ it is not possible to calculate inverse of $f$ generally we can calculate it experimentally

Assuming $y = \exp(mx)$

$$\exp(mx) = \int{f^{-1} (\phi(x)) dx}$$
