# Computational Mathematics -- Lecture 5 quiz with solutions

### Question 1

The data points $(0.5, 0.5)$, $(2, 0.4)$, $(4, 0.3)$, $(5, 0.1)$, $(7, 0.9)$, $(9, 0.8)$ are joined by straight lines (piecewise-linear interpolation). What is the value of this interpolant at $x = 6.5$?

- **(A)** $0.9$
- **(B)** $0.7$
- **(C)** $0.5$
- **(D)** $0.3$

> **Answer: (B).**
>
> $x = 6.5$ lies in the subinterval $[5, 7]$, between $(5, 0.1)$ and $(7, 0.9)$. On it the interpolant is $P_1(x) = 0.1 + \dfrac{0.9-0.1}{7-5}(x-5)$, so $P_1(6.5) = 0.1 + 0.4\times1.5 = 0.7$. The nearest data value is $0.9$; starting from the wrong end gives $0.3$; and the average $0.5$ is the value at the midpoint $x = 6$, not at $x = 6.5$.

---

### Question 2

The quadratic $P_2(x) = a_0 + a_1x + a_2x^2$ is to interpolate the data points $(1, 2)$, $(2, 3)$, $(3, 6)$. Which augmented matrix is the linear system for the unknowns $(a_0, a_1, a_2)$, in that order?

- **(A)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 2 & 4 & 8 & 3\\ 3 & 9 & 27 & 6\end{array}\right)$
- **(B)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 1 & 2 & 3 & 3\\ 1 & 4 & 9 & 6\end{array}\right)$
- **(C)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 1 & 2 & 4 & 3\\ 1 & 3 & 9 & 6\end{array}\right)$
- **(D)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 4 & 2 & 1 & 3\\ 9 & 3 & 1 & 6\end{array}\right)$

> **Answer: (C).**
>
> Each data point gives one equation $P_2(x_i) = a_0 + a_1x_i + a_2x_i^2 = y_i$, so row $i$ of the matrix is $(1, x_i, x_i^2)$ with right-hand side $y_i$: $(1, 1, 1 \mid 2)$, $(1, 2, 4 \mid 3)$, $(1, 3, 9 \mid 6)$. Decreasing powers give the system for the reversed unknowns $(a_2, a_1, a_0)$; the transposed matrix does not correspond to the equations $P_2(x_i) = y_i$; and starting at $x_i^1$ describes $a_0x + a_1x^2 + a_2x^3$.

---

### Question 3

For the nodes $x_0 = 0$, $x_1 = 2$, $x_2 = 3$, what is the value of the Lagrange basis polynomial $\ell_0(x)$ at $x = 1$?

- **(A)** $1/3$
- **(B)** $2$
- **(C)** $1$
- **(D)** $-1/3$

> **Answer: (A).**
>
> $\ell_0(x) = \dfrac{(x-x_1)(x-x_2)}{(x_0-x_1)(x_0-x_2)} = \dfrac{(x-2)(x-3)}{(0-2)(0-3)}$, so $\ell_0(1) = \dfrac{(-1)(-2)}{(-2)(-3)} = \dfrac{2}{6} = \dfrac13$. Leaving out the denominator gives $2$, a sign slip in one factor gives $-1/3$, and $\ell_0$ equals $1$ only at its own node $x_0$ (it is $0$ at $x_1$ and $x_2$), not at other points.

---

### Question 4

Let $L(x)$ be the quadratic polynomial that interpolates the data points $(0, 1)$, $(1, 3)$, $(3, 2)$. What is $L(2)$?

- **(A)** $8/3$
- **(B)** $5/2$
- **(C)** $10/3$
- **(D)** $4$

> **Answer: (C).**
>
> With nodes $0, 1, 3$: $\ell_0(2) = \dfrac{(2-1)(2-3)}{(0-1)(0-3)} = -\dfrac13$, $\ell_1(2) = \dfrac{(2-0)(2-3)}{(1-0)(1-3)} = 1$, $\ell_2(2) = \dfrac{(2-0)(2-1)}{(3-0)(3-1)} = \dfrac13$. So $L(2) = 1\times(-\tfrac13) + 3\times1 + 2\times\tfrac13 = \tfrac{10}{3}$. Straight-line interpolation between $(1,3)$ and $(3,2)$ gives $5/2$; the sign slip in $\ell_0$ gives $4$; mismatching values and basis polynomials gives $8/3$.

---


### Question 5

The straight line $P(x) = 1 + x$ is proposed as a fit to the data points $(0, 1)$, $(1, 4)$, $(2, 2)$. What is the least-squares error $E$ of this fit, i.e. the sum of the squared residuals?

- **(A)** $1$
- **(B)** $5$
- **(C)** $3$
- **(D)** $9$

> **Answer: (B).**
>
> $E = \sum_i \big(P(x_i) - y_i\big)^2$. The fitted values are $P(0) = 1$, $P(1) = 2$, $P(2) = 3$, so the residuals are $0$, $-2$, $1$ and $E = 0 + 4 + 1 = 5$. Summing the absolute residuals without squaring gives $3$. Squaring a sum instead of summing squares gives $(0-2+1)^2 = 1$ with signed residuals, where a large negative and a positive residual partly cancel, or $(0+2+1)^2 = 9$ with absolute ones.

---

### Question 6

The straight line $y = a_0 + a_1x$ is fitted by least squares to the data points $(0, 2)$, $(1, 3)$, $(2, 5)$, $(3, 6)$. What are the coefficients $(a_0, a_1)$?

- **(A)** $(a_0, a_1) = (2,\ 1)$
- **(B)** $(a_0, a_1) = (7/5,\ 19/10)$
- **(C)** $(a_0, a_1) = (2,\ 4/3)$
- **(D)** $(a_0, a_1) = (19/10,\ 7/5)$

> **Answer: (D).**
>
> Minimising $E = \sum_i (a_0 + a_1x_i - y_i)^2$ gives the normal equations $n a_0 + (\sum x_i) a_1 = \sum y_i$ and $(\sum x_i) a_0 + (\sum x_i^2) a_1 = \sum x_iy_i$. Here $n = 4$, $\sum x_i = 6$, $\sum x_i^2 = 14$, $\sum y_i = 16$, $\sum x_iy_i = 31$: $4a_0 + 6a_1 = 16$ and $6a_0 + 14a_1 = 31$. So $a_1 = (4\times31 - 6\times16)/(4\times14 - 6^2) = 28/20 = 7/5$ and $a_0 = (16 - 6\times7/5)/4 = 19/10$. Swapping gives $(7/5, 19/10)$; the lines through the end points or the first two points ($(2, 4/3)$ and $(2, 1)$) interpolate two points but do not minimise $E$.

---


### Question 7

Estimate $\int_0^2 x^2\,dx$ with the midpoint rule on $n = 2$ equal subintervals.

- **(A)** $3$
- **(B)** $5$
- **(C)** $8/3$
- **(D)** $5/2$

> **Answer: (D).**
>
> With $f(x) = x^2$, the two subintervals are $[0,1]$ and $[1,2]$, of width $1$, with midpoints $1/2$ and $3/2$. The midpoint rule gives $I_M = 1\times f(1/2) + 1\times f(3/2) = 1/4 + 9/4 = 5/2$. The exact value $8/3$ is what the rule approximates, not its result (the midpoint error here is $1/6$). The trapezoidal rule on the same subintervals gives $3$, and using the right end point of each subinterval instead of its midpoint gives $5$.

---

### Question 8

A quantity is measured at five equally-spaced points, giving $y_0,\dots,y_4 = 1, 4, 2, 7, 5$ with spacing $h=1$ (so $n=2$ Simpson subintervals). Using Simpson's rule, estimate $\int_{x_0}^{x_4} y\,dx$.

- **(A)** $12$
- **(B)** $16$
- **(C)** $54$
- **(D)** $18$

> **Answer: (D).**
>
> Simpson's rule with $n=2$ subintervals (5 samples) can be written as $\frac{h}{3}(y_0+y_4+4(y_1+y_3)+2y_2)=\frac{1}{3}(1+5+4(4+7)+2(2))=\frac{1}{3}(6+44+4)=\frac{1}{3}(54)=18$. The answer $12$ swaps the odd/even weighting; $54$ omits the $h/3$ factor; $16$ is the trapezoidal estimate on the same data, not Simpson's.

---

### Question 9

What is the degree of precision of Simpson's rule, i.e. the largest $M$ such that it integrates every polynomial of degree at most $M$ exactly?

- **(A)** $4$
- **(B)** $3$
- **(C)** $2$

> **Answer: (B).**
>
> Simpson's rule integrates the quadratic that interpolates $f$ at $a$, $c = (a+b)/2$ and $b$, so it is exact for quadratics. It is also exact for cubics: $(x - c)^3$ is odd about the midpoint, so both its integral over $[a,b]$ and Simpson's weighted sum $\tfrac{b-a}{6}\big(f(a) + 4f(c) + f(b)\big)$ vanish, and any cubic is a quadratic plus a multiple of $(x-c)^3$. It is not exact for $x^4$. So the degree of precision is $3$, not the degree $2$ of its construction; $4$ is the convergence order of the composite rule, a different quantity.

