# Computational Mathematics -- Lecture 5 quiz

### Question 1

The data points $(0.5, 0.5)$, $(2, 0.4)$, $(4, 0.3)$, $(5, 0.1)$, $(7, 0.9)$, $(9, 0.8)$ are joined by straight lines (piecewise-linear interpolation). What is the value of this interpolant at $x = 6.5$?

- **(A)** $0.9$
- **(B)** $0.7$
- **(C)** $0.5$
- **(D)** $0.3$

---

### Question 2

The quadratic $P_2(x) = a_0 + a_1x + a_2x^2$ is to interpolate the data points $(1, 2)$, $(2, 3)$, $(3, 6)$. Which augmented matrix is the linear system for the unknowns $(a_0, a_1, a_2)$, in that order?

- **(A)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 2 & 4 & 8 & 3\\ 3 & 9 & 27 & 6\end{array}\right)$
- **(B)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 1 & 2 & 3 & 3\\ 1 & 4 & 9 & 6\end{array}\right)$
- **(C)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 1 & 2 & 4 & 3\\ 1 & 3 & 9 & 6\end{array}\right)$
- **(D)** $\left(\begin{array}{ccc|c} 1 & 1 & 1 & 2\\ 4 & 2 & 1 & 3\\ 9 & 3 & 1 & 6\end{array}\right)$

Hint: Take a look at the "Fitting three data points" section of the lecture notes.

---

### Question 3

For the nodes $x_0 = 0$, $x_1 = 2$, $x_2 = 3$, what is the value of the Lagrange basis polynomial $\ell_0(x)$ at $x = 1$?

- **(A)** $1/3$
- **(B)** $2$
- **(C)** $1$
- **(D)** $-1/3$

Hint: Think about the quadratic function that is one at $x_0$ and zero at $x_1$ and $x_2$.

---

### Question 4

Let $L(x)$ be the quadratic polynomial that interpolates the data points $(0, 1)$, $(1, 3)$, $(3, 2)$. What is $L(2)$?

- **(A)** $8/3$
- **(B)** $5/2$
- **(C)** $10/3$
- **(D)** $4$

Hint: Form the three quadratic Lagrange basis functions, form the Lagrange interpolating poly, and evaluate it at $x=2$.

---

### Question 5

The straight line $P(x) = 1 + x$ is proposed as a fit to the data points $(0, 1)$, $(1, 4)$, $(2, 2)$. What is the least-squares error $E$ of this fit, i.e. the sum of the squared residuals?

- **(A)** $1$
- **(B)** $5$
- **(C)** $3$
- **(D)** $9$

---

### Question 6

The straight line $y = a_0 + a_1x$ is fitted by least squares to the data points $(0, 2)$, $(1, 3)$, $(2, 5)$, $(3, 6)$. What are the coefficients $(a_0, a_1)$?

- **(A)** $(a_0, a_1) = (2,\ 1)$
- **(B)** $(a_0, a_1) = (7/5,\ 19/10)$
- **(C)** $(a_0, a_1) = (2,\ 4/3)$
- **(D)** $(a_0, a_1) = (19/10,\ 7/5)$

Hint: Suggest you start by sketching the problem. Then write out the error we're minimising. It takes the form here $E = \left( (a_0 + a_1\cdot 0) - 2 \right)^2 + \left( (a_0 + a_1\cdot 1)-3 \right)^2 + \left( (a_0 + a_1\cdot 2)-5 \right)^2 + \left( (a_0 + a_1\cdot 3)-6 \right)^2$.

We want to find the values of $a_0$ and $a_1$ that minimises $E$, so differentiate $E$ (partially) with respect to $a_0$ and w.r.t. $a_1$, set these two things equal to zero (that's what we get at a minimum),
and solve these two relations for $a_0$ and $a_1$.

Note you should find the two equations $n a_0 + (\sum x_i) a_1 = \sum y_i$ and $(\sum x_i) a_0 + (\sum x_i^2) a_1 = \sum x_iy_i$.

---

### Question 7

Estimate $\int_0^2 x^2\,dx$ with the midpoint rule on $n = 2$ equal subintervals.

- **(A)** $3$
- **(B)** $5$
- **(C)** $8/3$
- **(D)** $5/2$

Hint: You're asked for the approximation value, you can also easily work out the true integral but that's not what you're asked for.

---

### Question 8

A quantity is measured at five equally-spaced points, giving $y_0,\dots,y_4 = 1, 4, 2, 7, 5$ with spacing $h=1$ (so $n=2$ Simpson subintervals). Using Simpson's rule, estimate $\int_{x_0}^{x_4} y\,dx$.

- **(A)** $12$
- **(B)** $16$
- **(C)** $54$
- **(D)** $18$

---

### Question 9

What is the degree of precision of Simpson's rule, i.e. the largest $M$ such that it integrates every polynomial of degree at most $M$ exactly?

- **(A)** $4$
- **(B)** $3$
- **(C)** $2$

