# Computational Mathematics -- Lecture 2 quiz

$\newcommand{\ii}{\mathrm{i}}\newcommand{\dd}{\mathrm{d}}\newcommand{\rr}{\mathbb{R}}\newcommand{\cc}{\mathbb{C}}$

### Question 1

Let $A = \begin{pmatrix}1&2\\3&4\end{pmatrix}$ and $\mathbf{x} = \begin{pmatrix}1\\1\end{pmatrix}$. Compute $A\mathbf{x}$.

- **(A)** $\begin{pmatrix}3\\7\end{pmatrix}$
- **(B)** $\begin{pmatrix}2\\12\end{pmatrix}$
- **(C)** $\begin{pmatrix}1\\4\end{pmatrix}$
- **(D)** $\begin{pmatrix}4\\6\end{pmatrix}$

---

### Question 2

Solve the linear system $3x + 2y = 7$, $\;x - y = -1$.

- **(A)** $(x,y) = (-5,\ -10)$
- **(B)** $(x,y) = (-1,\ -2)$
- **(C)** $(x,y) = (1,\ 2)$
- **(D)** $(x,y) = (2,\ 1)$

---

### Question 3

Let $A$ and $B$ be invertible $2\times 2$ matrices with $A^{-1} = \begin{pmatrix}1&2\\0&1\end{pmatrix}$ and $B^{-1} = \begin{pmatrix}2&1\\1&1\end{pmatrix}$. What is $(AB)^{-1}$?

- **(A)** $\begin{pmatrix}2&2\\0&1\end{pmatrix}$
- **(B)** $\begin{pmatrix}2&5\\1&3\end{pmatrix}$
- **(C)** $\begin{pmatrix}4&3\\1&1\end{pmatrix}$
- **(D)** $\begin{pmatrix}3&-5\\-1&2\end{pmatrix}$

Hint: Recall that $(AB)^{-1}=B^{-1}A^{-1}$

---

### Question 4

Compute $\det(A)$ for $A = \begin{pmatrix}1&2&3\\0&1&4\\5&6&0\end{pmatrix}$.

- **(A)** $16$
- **(B)** $-79$
- **(C)** $49$
- **(D)** $1$

Hint: You can use a cofactor expansion.

---

### Question 5

$A$ and $B$ are $3\times 3$ matrices with $\det(A) = 2$ and $\det(B) = -3$. What is $\det\left(2A^TB^{-1}\right)$?
- **(A)** $\tfrac{16}{3}$
- **(B)** $-\tfrac{16}{3}$
- **(C)** $-48$
- **(D)** $-\tfrac{4}{3}$

Hint: Recall the properties $|AB|=|A||B|$, $|A^T|=|A|$, $|\alpha A|=\alpha^n|A|$, $|A^{-1}|=1/|A|$

---

### Question 6

What is the rank of $A = \begin{pmatrix}1&3&0&1\\3&9&1&4\\4&12&1&5\\-1&-3&-1&-2\end{pmatrix}$?

- **(A)** $2$
- **(B)** $3$
- **(C)** $1$
- **(D)** $4$

Hint: Use row reduction operations. See Exercise 2.

---

### Question 7

Let $A = \begin{pmatrix}1&2&-1\\2&4&-2\\1&3&1\end{pmatrix}$. Which of the following vectors is a non-zero vector in the null space of $A$, i.e. a non-zero solution of $A\boldsymbol{x} = \boldsymbol{0}$?

- **(A)** $(-5,\ 2,\ 1)^T$
- **(B)** $(5,\ -2,\ 1)^T$
- **(C)** $(-2,\ 1,\ 0)^T$
- **(D)** $(1,\ 2,\ -1)^T$

Hint: Use row reduction operations. See Exercise 2.

---

### Question 8

A matrix $A$ has 5 columns and rank 3. What is the dimension of its null space?

- **(A)** $2$
- **(B)** $4$
- **(C)** $5$
- **(D)** $3$

Hint: Recall the rank-nullity hypothesis.

---

### Question 9

Let $A=\begin{pmatrix}1&2\\2&4\end{pmatrix}$ and $\mathbf{b}=\begin{pmatrix}3\\7\end{pmatrix}$. Classify the solvability of $A\mathbf{x}=\mathbf{b}$.

- **(A)** Infinitely many solutions
- **(B)** No solution
- **(C)** Unique solution

Hint: See exercise 3.

---

### Question 10

A linear transformation $T$ of the plane maps $\boldsymbol{i} = (1,0)^T$ to $(2,1)^T$ and $\boldsymbol{j} = (0,1)^T$ to $(-1,3)^T$. What is $T(\boldsymbol{p})$ for $\boldsymbol{p} = (3,2)^T$?

- **(A)** $(1,\ 11)^T$
- **(B)** $(1,\ 4)^T$
- **(C)** $(8,\ 3)^T$
- **(D)** $(4,\ 9)^T$

---

### Question 11

The triangle with vertices $(0,0)$, $(2,0)$ and $(0,3)$ is mapped by the linear transformation $\boldsymbol{x} \mapsto A\boldsymbol{x}$ with $A = \begin{pmatrix}1&2\\3&4\end{pmatrix}$. What is the area of the image of the triangle?

- **(A)** $12$
- **(B)** $2$
- **(C)** $6$
- **(D)** $30$

---

### Question 12

What is the orthogonal projection of $\boldsymbol{u} = (3,1)^T$ onto the line through the origin in the direction of $\boldsymbol{v} = (1,1)^T$?

- **(A)** $(0.4,\ 0.4)^T$
- **(B)** $(4,\ 4)^T$
- **(C)** $(1,\ 1)^T$
- **(D)** $(2,\ 2)^T$

Hint: See exercise 4.

---
