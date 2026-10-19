# Computational Mathematics -- Lecture 2 quiz solutions

$\newcommand{\ii}{\mathrm{i}}\newcommand{\dd}{\mathrm{d}}\newcommand{\rr}{\mathbb{R}}\newcommand{\cc}{\mathbb{C}}$

### Question 1

Let $A = \begin{pmatrix}1&2\\3&4\end{pmatrix}$ and $\mathbf{x} = \begin{pmatrix}1\\1\end{pmatrix}$. Compute $A\mathbf{x}$.

- **(A)** $\begin{pmatrix}3\\7\end{pmatrix}$
- **(B)** $\begin{pmatrix}2\\12\end{pmatrix}$
- **(C)** $\begin{pmatrix}1\\4\end{pmatrix}$
- **(D)** $\begin{pmatrix}4\\6\end{pmatrix}$

> **Answer: (A).**
>
> $A$ is $2\times 2$ and $\mathbf{x}$ is $2\times 1$, so the product is conformable. Row 1: $1(1)+2(1)=3$. Row 2: $3(1)+4(1)=7$, giving $\begin{pmatrix}3\\7\end{pmatrix}$.

---

### Question 2

Solve the linear system $3x + 2y = 7$, $\;x - y = -1$.

- **(A)** $(x,y) = (-5,\ -10)$
- **(B)** $(x,y) = (-1,\ -2)$
- **(C)** $(x,y) = (1,\ 2)$
- **(D)** $(x,y) = (2,\ 1)$

> **Answer: (C).**
>
> From the second equation $x = y - 1$. Substituting into the first: $3(y-1) + 2y = 7 \Rightarrow 5y = 10 \Rightarrow y = 2$, and then $x = 1$. Check: $3 + 4 = 7$ and $1 - 2 = -1$. Equivalently, with $A = \begin{pmatrix}3&2\\1&-1\end{pmatrix}$, $\det A = 3(-1) - 2(1) = -5$ and $\boldsymbol{x} = A^{-1}\boldsymbol{b} = \frac{1}{-5}\begin{pmatrix}-1&-2\\-1&3\end{pmatrix}\begin{pmatrix}7\\-1\end{pmatrix} = \frac{1}{-5}\begin{pmatrix}-5\\-10\end{pmatrix} = \begin{pmatrix}1\\2\end{pmatrix}$. $(2,1)$ has the components swapped; $(-5,-10)$ is $\operatorname{adj}(A)\boldsymbol{b}$ without the factor $1/\det A$; $(-1,-2)$ divides by $+5$ instead of $-5$.

---

### Question 3

Let $A$ and $B$ be invertible $2\times 2$ matrices with $A^{-1} = \begin{pmatrix}1&2\\0&1\end{pmatrix}$ and $B^{-1} = \begin{pmatrix}2&1\\1&1\end{pmatrix}$. What is $(AB)^{-1}$?

- **(A)** $\begin{pmatrix}2&2\\0&1\end{pmatrix}$
- **(B)** $\begin{pmatrix}2&5\\1&3\end{pmatrix}$
- **(C)** $\begin{pmatrix}4&3\\1&1\end{pmatrix}$
- **(D)** $\begin{pmatrix}3&-5\\-1&2\end{pmatrix}$

> **Answer: (B).**
>
> $(AB)^{-1} = B^{-1}A^{-1}$, because $(AB)(B^{-1}A^{-1}) = A(BB^{-1})A^{-1} = AA^{-1} = I$. So $(AB)^{-1} = \begin{pmatrix}2&1\\1&1\end{pmatrix}\begin{pmatrix}1&2\\0&1\end{pmatrix} = \begin{pmatrix}2\cdot1+1\cdot0 & 2\cdot2+1\cdot1\\ 1\cdot1+1\cdot0 & 1\cdot2+1\cdot1\end{pmatrix} = \begin{pmatrix}2&5\\1&3\end{pmatrix}$, and there is no need to find $A$ or $B$. $\begin{pmatrix}4&3\\1&1\end{pmatrix} = A^{-1}B^{-1}$ keeps the original order, which is wrong because matrix multiplication does not commute. $\begin{pmatrix}3&-5\\-1&2\end{pmatrix}$ is the inverse of $\begin{pmatrix}2&5\\1&3\end{pmatrix}$, i.e. $AB$ itself. $\begin{pmatrix}2&2\\0&1\end{pmatrix}$ is the entry-by-entry product, not the matrix product.

---

### Question 4

Compute $\det(A)$ for $A = \begin{pmatrix}1&2&3\\0&1&4\\5&6&0\end{pmatrix}$.

- **(A)** $16$
- **(B)** $-79$
- **(C)** $49$
- **(D)** $1$

> **Answer: (D).**
>
> Cofactor expansion along the first row uses the alternating sign pattern $+,-,+$: $\det(A) = (+1)M_{11} - (+2)M_{12} + (+3)M_{13}$, where $M_{11}=1\cdot0-4\cdot6=-24$, $M_{12}=0\cdot0-4\cdot5=-20$, $M_{13}=0\cdot6-1\cdot5=-5$. So $\det(A) = 1(-24) - 2(-20) + 3(-5) = -24+40-15 = 1$.

---

### Question 5

$A$ and $B$ are $3\times 3$ matrices with $\det(A) = 2$ and $\det(B) = -3$. What is $\det\left(2A^TB^{-1}\right)$?

- **(A)** $\tfrac{16}{3}$
- **(B)** $-\tfrac{16}{3}$
- **(C)** $-48$
- **(D)** $-\tfrac{4}{3}$

> **Answer: (B).**
>
> Use $\det(MN) = \det(M)\det(N)$, $\det(\alpha M) = \alpha^n\det(M)$ with $n = 3$, $\det(A^T) = \det(A)$, and $\det(B^{-1}) = 1/\det(B)$ (because $\det(B^{-1})\det(B) = \det(B^{-1}B) = \det(I) = 1$): $\det(2A^TB^{-1}) = 2^3\det(A^T)\det(B^{-1}) = 8\times 2\times\left(-\tfrac{1}{3}\right) = -\tfrac{16}{3}$. Using $2$ instead of $2^3$ gives $-\tfrac{4}{3}$; using $\det(B^{-1}) = -3$ gives $-48$; dropping the sign gives $\tfrac{16}{3}$.

---

### Question 6

What is the rank of $A = \begin{pmatrix}1&3&0&1\\3&9&1&4\\4&12&1&5\\-1&-3&-1&-2\end{pmatrix}$?

- **(A)** $2$
- **(B)** $3$
- **(C)** $1$
- **(D)** $4$

> **Answer: (A).**
>
> Row reduce: $R_2 - 3R_1 = (0,0,1,1)$, $R_3 - 4R_1 = (0,0,1,1)$ and $R_4 + R_1 = (0,0,-1,-1)$; then $R_3 - R_2 = \boldsymbol{0}$ and $R_4 + R_2 = \boldsymbol{0}$. The row echelon form $\begin{pmatrix}1&3&0&1\\0&0&1&1\\0&0&0&0\\0&0&0&0\end{pmatrix}$ has two non-zero rows, so $\text{rank}(A) = 2$. (Row 3 = row 1 + row 2 and row 4 = $2\times$ row 1 $-$ row 2. Column 2 = $3\times$ column 1 and column 4 = column 1 + column 3, so there are also exactly two independent columns.) The rank is not 1 because columns 1 and 3 are not parallel.

---

### Question 7

Let $A = \begin{pmatrix}1&2&-1\\2&4&-2\\1&3&1\end{pmatrix}$. Which of the following vectors is a non-zero vector in the null space of $A$, i.e. a non-zero solution of $A\boldsymbol{x} = \boldsymbol{0}$?

- **(A)** $(-5,\ 2,\ 1)^T$
- **(B)** $(5,\ -2,\ 1)^T$
- **(C)** $(-2,\ 1,\ 0)^T$
- **(D)** $(1,\ 2,\ -1)^T$

> **Answer: (B).**
>
> Row reduce $A$: $R_2 - 2R_1$ is a zero row and $R_3 - R_1 = (0,1,2)$, giving the reduced row echelon form $\begin{pmatrix}1&0&-5\\0&1&2\\0&0&0\end{pmatrix}$. So $x - 5z = 0$ and $y + 2z = 0$: $x = 5z$, $y = -2z$, and $z = 1$ gives $(5,-2,1)^T$. Check: $A(5,-2,1)^T = (5-4-1,\ 10-8-2,\ 5-6+1)^T = \boldsymbol{0}$. ($\text{rank}(A) = 2$, so the null space has dimension $3 - 2 = 1$, and every non-zero multiple of this vector spans it.) For the others, $A(-5,2,1)^T = (-2,-4,2)^T$, $A(1,2,-1)^T = (6,12,6)^T$ and $A(-2,1,0)^T = (0,0,1)^T$, none of them zero.

---

### Question 8

A matrix $A$ has 5 columns and rank 3. What is the dimension of its null space?

- **(A)** $2$
- **(B)** $4$
- **(C)** $5$
- **(D)** $3$

> **Answer: (A).**
>
> By the rank-nullity theorem, $\text{rank}(A) + \dim(\text{null}(A)) = n$, where $n=5$ is the number of columns. So $\dim(\text{null}(A)) = 5 - 3 = 2$.

---

### Question 9

Let $A=\begin{pmatrix}1&2\\2&4\end{pmatrix}$ and $\mathbf{b}=\begin{pmatrix}3\\7\end{pmatrix}$. Classify the solvability of $A\mathbf{x}=\mathbf{b}$.

- **(A)** Infinitely many solutions
- **(B)** No solution
- **(C)** Unique solution

> **Answer: (B).**
>
> Row 2 of $A$ is exactly twice row 1, since $(2,4)=2\cdot(1,2)$, so the two equations $x_1+2x_2=b_1$ and $2x_1+4x_2=b_2$ are the same equation up to scaling. This linear dependence rules out a unique solution: the system is either inconsistent (no solution) or has infinitely many solutions, depending on whether $\mathbf{b}$ respects that same 2:1 ratio. Here $b_1=3$ and $b_2=7$, but $2\cdot b_1=6\neq7=b_2$, so $\mathbf{b}$ does not satisfy the required ratio: there is no solution.

---

### Question 10

A linear transformation $T$ of the plane maps $\boldsymbol{i} = (1,0)^T$ to $(2,1)^T$ and $\boldsymbol{j} = (0,1)^T$ to $(-1,3)^T$. What is $T(\boldsymbol{p})$ for $\boldsymbol{p} = (3,2)^T$?

- **(A)** $(1,\ 11)^T$
- **(B)** $(1,\ 4)^T$
- **(C)** $(8,\ 3)^T$
- **(D)** $(4,\ 9)^T$

> **Answer: (D).**
>
> $\boldsymbol{p} = 3\boldsymbol{i} + 2\boldsymbol{j}$, so by linearity $T(\boldsymbol{p}) = 3T(\boldsymbol{i}) + 2T(\boldsymbol{j}) = 3(2,1)^T + 2(-1,3)^T = (6-2,\ 3+6)^T = (4,9)^T$. Equivalently, the matrix of $T$ has the images of the basis vectors as its **columns**, $A = \begin{pmatrix}2&-1\\1&3\end{pmatrix}$, and $A\boldsymbol{p} = (4, 9)^T$. Putting the images in the rows gives $(8,3)^T$; swapping the weights gives $(1,11)^T$; $(1,4)^T$ is just $T(\boldsymbol{i}) + T(\boldsymbol{j}) = T((1,1)^T)$.

---

### Question 11

The triangle with vertices $(0,0)$, $(2,0)$ and $(0,3)$ is mapped by the linear transformation $\boldsymbol{x} \mapsto A\boldsymbol{x}$ with $A = \begin{pmatrix}1&2\\3&4\end{pmatrix}$. What is the area of the image of the triangle?

- **(A)** $12$
- **(B)** $2$
- **(C)** $6$
- **(D)** $30$

> **Answer: (C).**
>
> The triangle has area $\tfrac{1}{2}\times 2\times 3 = 3$. A linear map scales every area by $\lvert\det A\rvert$, and $\det A = 1\cdot4 - 2\cdot3 = -2$, so the image has area $\lvert -2\rvert\times 3 = 6$ (the negative sign only means that the orientation of the triangle is reversed). Check directly: the vertices map to $(0,0)$, $(2,6)$ and $(6,12)$, and the area of that triangle is $\tfrac{1}{2}\lvert 2\cdot12 - 6\cdot6\rvert = \tfrac{1}{2}\lvert 24-36\rvert = 6$. $2$ is only the scale factor; $30$ uses $ad+bc$; $12$ forgets the $\tfrac{1}{2}$ in the triangle's area.

---

### Question 12

What is the orthogonal projection of $\boldsymbol{u} = (3,1)^T$ onto the line through the origin in the direction of $\boldsymbol{v} = (1,1)^T$?

- **(A)** $(0.4,\ 0.4)^T$
- **(B)** $(4,\ 4)^T$
- **(C)** $(1,\ 1)^T$
- **(D)** $(2,\ 2)^T$

> **Answer: (D).**
>
> The projection is $c\,\boldsymbol{v}$, with the residual $\boldsymbol{u} - c\boldsymbol{v}$ orthogonal to $\boldsymbol{v}$: $(\boldsymbol{u} - c\boldsymbol{v})\cdot\boldsymbol{v} = 0 \Rightarrow c = \dfrac{\boldsymbol{u}\cdot\boldsymbol{v}}{\boldsymbol{v}\cdot\boldsymbol{v}} = \dfrac{4}{2} = 2$, so the projection is $(2,2)^T$. Check: the residual $(3,1)^T - (2,2)^T = (1,-1)^T$ is orthogonal to $(1,1)^T$. With the unit vector $\hat{\boldsymbol{v}} = \boldsymbol{v}/\sqrt{2}$ this is the homework's formula $(\boldsymbol{u}\cdot\hat{\boldsymbol{v}})\hat{\boldsymbol{v}} = \hat{\boldsymbol{v}}\hat{\boldsymbol{v}}^T\boldsymbol{u}$. $(4,4)^T$ forgets to normalise $\boldsymbol{v}$, $(1,1)^T$ is just $\boldsymbol{v}$ (the direction, not the projection), and $(0.4,0.4)^T$ divides by $\boldsymbol{u}\cdot\boldsymbol{u}$ instead of $\boldsymbol{v}\cdot\boldsymbol{v}$.

---
