# Computational Mathematics -- Lecture 3 quiz

### Question 1

The point $\boldsymbol{p} = (3,4)^T$ (in standard coordinates) is to be described using the new basis vectors $\boldsymbol{b}_1 = (2,3)^T$ and $\boldsymbol{b}_2 = (1,2)^T$. What are its coordinates $(p_1', p_2')$ with respect to the new basis, i.e. the numbers with $\boldsymbol{p} = p_1'\boldsymbol{b}_1 + p_2'\boldsymbol{b}_2$?

- **(A)** $(p_1', p_2') = (18,\ 11)$
- **(B)** $(p_1', p_2') = (10,\ 17)$
- **(C)** $(p_1', p_2') = (2,\ -1)$
- **(D)** $(p_1', p_2') = (-6,\ 5)$


Hint: Here you want to use the result from lectures that $\boldsymbol{p} = A_b\boldsymbol{p}'$ where $\boldsymbol{p}' = A_b^{-1}\boldsymbol{p}$.

You can also use the results that for 
$$A = 
\begin{pmatrix}
    a & b\\
    c & d
\end{pmatrix}, \quad
A^{-1} = \frac{1}{ad-bc}
\begin{pmatrix}
    d & -b\\
    -c & a
\end{pmatrix}$$


---

### Question 2

Find the eigenvalues of $A = \begin{pmatrix}4&1\\2&3\end{pmatrix}$ via its characteristic polynomial.

- **(A)** $\{5, -2\}$
- **(B)** $\{5, 2\}$
- **(C)** $\{-5, -2\}$
- **(D)** $\{-5, 2\}$

Hint: Here you want to solve (the quadratic) $\det(A-\lambda I)=0$ for $\lambda$.

---

### Question 3

The matrix $A=\begin{pmatrix}5&4\\1&2\end{pmatrix}$ has eigenvalues $\lambda=1$ and $\lambda=6$. Find the unit-length eigenvector corresponding to $\lambda=1$.

- **(A)** $\left(\dfrac{\sqrt2}{2},\ -\dfrac{\sqrt2}{2}\right)$
- **(B)** $\left(\dfrac{\sqrt2}{2},\ \dfrac{\sqrt2}{2}\right)$
- **(C)** $\left(\dfrac{4\sqrt{17}}{17},\ \dfrac{\sqrt{17}}{17}\right)$
- **(D)** $\left(-\dfrac{\sqrt{17}}{17},\ \dfrac{4\sqrt{17}}{17}\right)$

Hint: Here you want to start from $(A-\lambda I)\mathbf v=0$. For the given values of $\lambda$ find $\mathbf v$ and make sure it has unit length.

---

### Question 4

For $A = \begin{pmatrix}2&1&0\\0&2&0\\0&0&3\end{pmatrix}$, what are the algebraic and the geometric multiplicity of the eigenvalue $\lambda = 2$?

- **(A)** algebraic 2, geometric 2
- **(B)** algebraic 1, geometric 1
- **(C)** algebraic 2, geometric 1

Hint: Here, as the matrix is upper triangular, the characteristic polynomial just involves the diagonal terms: $\det(A-\lambda I) = (2-\lambda)^2(3-\lambda)$. Following this look at the section of the lecture "
4.3  Repeated eigenvalues - algebraic \& geometric multiplicity". You will need to think about how many linearly independent eigenvectors you can find.

---

### Question 5

The matrix $Q = \begin{pmatrix}3/5 & -4/5\\ 4/5 & 3/5\end{pmatrix}$ is orthogonal. What is $Q^{-1}$?

- **(A)** $\begin{pmatrix}3/5 & 4/5\\ -4/5 & 3/5\end{pmatrix}$
- **(B)** $\begin{pmatrix}-3/5 & -4/5\\ 4/5 & -3/5\end{pmatrix}$
- **(C)** $\begin{pmatrix}3/5 & -4/5\\ 4/5 & 3/5\end{pmatrix}$
- **(D)** $\begin{pmatrix}5/3 & -5/4\\ 5/4 & 5/3\end{pmatrix}$

Hint: What does the fact that $Q$ is orthogonal mean about its inverse?

---


### Question 6

$A = \begin{pmatrix}1&2\\2&1\end{pmatrix}$ has eigenvalues $3$ and $-1$ with eigenvectors $(1,1)^T$ and $(1,-1)^T$. Using $A^N = P\Lambda^NP^{-1}$, what is $A^4$?

- **(A)** $\begin{pmatrix}40&41\\41&40\end{pmatrix}$
- **(B)** $\begin{pmatrix}1&16\\16&1\end{pmatrix}$
- **(C)** $\begin{pmatrix}41&40\\40&41\end{pmatrix}$
- **(D)** $\begin{pmatrix}81&0\\0&1\end{pmatrix}$

Hint: See section "2.2  Powers of matrices " from the supplementary notebook.

---

### Question 7

Solve $\dot{\boldsymbol{x}} = A\boldsymbol{x}$ with $A = \begin{pmatrix}2&1\\1&2\end{pmatrix}$ and $\boldsymbol{x}(0) = (1,0)^T$.

- **(A)** $\boldsymbol{x}(t) = \tfrac12\big(e^{t}+e^{3t},\ e^{t}-e^{3t}\big)^T$
- **(B)** $\boldsymbol{x}(t) = e^{2t}\big(\cos t,\ \sin t\big)^T$
- **(C)** $\boldsymbol{x}(t) = \tfrac12\big(e^{3t}+e^{-t},\ e^{3t}-e^{-t}\big)^T$
- **(D)** $\boldsymbol{x}(t) = \tfrac12\big(e^{3t}+e^{t},\ e^{3t}-e^{t}\big)^T$

Hint: See section "2.3  Using linear algebra to solve systems of ODEs" of the supplementary notebook.

---


### Question 8

What are the singular values of $A = \begin{pmatrix}5&4\\-4&-5\end{pmatrix}$?

- **(A)** $81$ and $1$
- **(B)** $9$ and $1$
- **(C)** $3$ and $3$

Hint: See section "7  Singular Value Decomposition (SVD)" -- the singular values are the square roots of the eigenvalues of $A^TA$. See also exercise "1.5  When does the SVD agree with the eigen-decomposition?"

---
