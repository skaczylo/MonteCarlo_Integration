# MonteCarlo_Integration
In this notebook, the approximate calculation of a definite integral of a positive function over an interval $[a, b]$ is performed using the Monte Carlo method.

The main objective is to bound the graph of the function within a rectangle $[a, b] \times [0, M]$. To do this, we divide the interval $$[a, b]$$ uniformly into subintervals $[x_i, x_{i+1}]$, where $a < x_1 < \dots < x_n < b$. For each $x_i$, we compute $f(x_i)$ and take the maximum $M$ among all of them, i.e.,

$$ M = \max \{ f(x_i) \}. $$

This way, we can obtain an approximate maximum of the function $f$ over $[a, b]$.

Once we have the rectangle $[a, b] \times [0, M]$, we generate `num_points`
 random points inside it and check for each point whether it falls under the area formed by the graph and the $X$-axis.

Finally, the integral is approximated as:


 $$ I \approx \frac{N_{\text{below}}}{N_{\text{total}}} \cdot (b - a) \cdot M $$


In this notebook, two implementations of this Monte Carlo method are provided: one using traditional programming methods (loops, conditionals, etc.), and another using `NumPy vectorized functions`. The execution times of both implementations are compared to evaluate the efficiency gains from using NumPy.

