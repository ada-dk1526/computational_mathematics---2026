# Computational Mathematics -- Lecture 3 quiz solutions


### Question 1

The point $\boldsymbol{p} = (3,4)^T$ (in standard coordinates) is to be described using the new basis vectors $\boldsymbol{b}_1 = (2,3)^T$ and $\boldsymbol{b}_2 = (1,2)^T$. What are its coordinates $(p_1', p_2')$ with respect to the new basis, i.e. the numbers with $\boldsymbol{p} = p_1'\boldsymbol{b}_1 + p_2'\boldsymbol{b}_2$?

- **(A)** $(p_1', p_2') = (18,\ 11)$
- **(B)** $(p_1', p_2') = (10,\ 17)$
- **(C)** $(p_1', p_2') = (2,\ -1)$
- **(D)** $(p_1', p_2') = (-6,\ 5)$

> **Answer: (C).**
>
> With the new basis vectors as the columns of $A_b = \begin{pmatrix}2&1\\3&2\end{pmatrix}$, $\boldsymbol{p} = A_b\boldsymbol{p}'$, so $\boldsymbol{p}' = A_b^{-1}\boldsymbol{p}$. Here $\det A_b = 4-3 = 1$ and $A_b^{-1} = \begin{pmatrix}2&-1\\-3&2\end{pmatrix}$, so $(p_1', p_2') = (6-4,\ -9+8) = (2,-1)$. Check: $2(2,3)^T - (1,2)^T = (3,4)^T$. $(10,17)$ is $A_b\boldsymbol{p}$, which moves the point instead of re-expressing it; $(-6,5)$ uses the basis vectors as rows; $(18,11)$ is $A_b^T\boldsymbol{p}$, but $A_b^{-1} = A_b^T$ only for an orthogonal matrix, and these basis vectors are not orthonormal.

---

### Question 2

Find the eigenvalues of $A = \begin{pmatrix}4&1\\2&3\end{pmatrix}$ via its characteristic polynomial.

- **(A)** $\{5, -2\}$
- **(B)** $\{5, 2\}$
- **(C)** $\{-5, -2\}$
- **(D)** $\{-5, 2\}$

> **Answer: (B).**
>
> $\det(A-\lambda I) = (4-\lambda)(3-\lambda)-2 = \lambda^2-7\lambda+10=(\lambda-5)(\lambda-2)$, giving $\lambda=5,2$.

---

### Question 3

The matrix $A=\begin{pmatrix}5&4\\1&2\end{pmatrix}$ has eigenvalues $\lambda=1$ and $\lambda=6$. Find the unit-length eigenvector corresponding to $\lambda=1$.

- **(A)** $\left(\dfrac{\sqrt2}{2},\ -\dfrac{\sqrt2}{2}\right)$
- **(B)** $\left(\dfrac{\sqrt2}{2},\ \dfrac{\sqrt2}{2}\right)$
- **(C)** $\left(\dfrac{4\sqrt{17}}{17},\ \dfrac{\sqrt{17}}{17}\right)$
- **(D)** $\left(-\dfrac{\sqrt{17}}{17},\ \dfrac{4\sqrt{17}}{17}\right)$

> **Answer: (A).**
>
> For $\lambda=1$: $A-I=\begin{pmatrix}4&4\\1&1\end{pmatrix}$, so $(A-I)\mathbf v=0$ gives $4v_1+4v_2=0$, i.e. $v_1=-v_2$. Taking $v_1=1$ gives the direction $(1,-1)$, which normalises to $\left(\tfrac{\sqrt2}{2},-\tfrac{\sqrt2}{2}\right)$. The eigenvector for $\lambda=6$ instead solves $\begin{pmatrix}-1&4\\1&-4\end{pmatrix}\mathbf v=0$, giving direction $(4,1)$, normalised to $\left(\tfrac{4\sqrt{17}}{17},\tfrac{\sqrt{17}}{17}\right)$ -- the wrong eigenvalue's vector, not this one.

---

### Question 4

For $A = \begin{pmatrix}2&1&0\\0&2&0\\0&0&3\end{pmatrix}$, what are the algebraic and the geometric multiplicity of the eigenvalue $\lambda = 2$?

- **(A)** algebraic 2, geometric 2
- **(B)** algebraic 1, geometric 1
- **(C)** algebraic 2, geometric 1

> **Answer: (C).**
>
> $A$ is upper triangular, so $\det(A-\lambda I) = (2-\lambda)^2(3-\lambda)$: $\lambda=2$ is a double root, algebraic multiplicity 2. The geometric multiplicity is $\dim\,\text{null}(A-2I)$: $A-2I = \begin{pmatrix}0&1&0\\0&0&0\\0&0&1\end{pmatrix}$ has rank 2, so its null space has dimension $3-2 = 1$ (spanned by $(1,0,0)^T$): geometric multiplicity 1. The two multiplicities need not be equal - here there is only one independent eigenvector for $\lambda=2$, so $A$ is not diagonalisable.

---

### Question 5

The matrix $Q = \begin{pmatrix}3/5 & -4/5\\ 4/5 & 3/5\end{pmatrix}$ is orthogonal. What is $Q^{-1}$?

- **(A)** $\begin{pmatrix}3/5 & 4/5\\ -4/5 & 3/5\end{pmatrix}$
- **(B)** $\begin{pmatrix}-3/5 & -4/5\\ 4/5 & -3/5\end{pmatrix}$
- **(C)** $\begin{pmatrix}3/5 & -4/5\\ 4/5 & 3/5\end{pmatrix}$
- **(D)** $\begin{pmatrix}5/3 & -5/4\\ 5/4 & 5/3\end{pmatrix}$

> **Answer: (A).**
>
> For an orthogonal matrix $Q^TQ = I$, so $Q^{-1} = Q^T$: just swap rows and columns, $Q^{-1} = \begin{pmatrix}3/5 & 4/5\\ -4/5 & 3/5\end{pmatrix}$. Check: $QQ^T = \begin{pmatrix}9/25+16/25 & 12/25-12/25\\ 12/25-12/25 & 16/25+9/25\end{pmatrix} = I$. ($Q$ is the rotation by $\theta$ with $\cos\theta=3/5$, $\sin\theta=4/5$; its inverse rotates back by $-\theta$.) $Q$ itself is not its own inverse since $Q^2\neq I$; negating the diagonal instead of the off-diagonal entries gives $-Q^T$, and $Q(-Q^T) = -I$; the entry-wise reciprocals do not give $I$ at all.

---

### Question 6

$A = \begin{pmatrix}1&2\\2&1\end{pmatrix}$ has eigenvalues $3$ and $-1$ with eigenvectors $(1,1)^T$ and $(1,-1)^T$. Using $A^N = P\Lambda^NP^{-1}$, what is $A^4$?

- **(A)** $\begin{pmatrix}40&41\\41&40\end{pmatrix}$
- **(B)** $\begin{pmatrix}1&16\\16&1\end{pmatrix}$
- **(C)** $\begin{pmatrix}41&40\\40&41\end{pmatrix}$
- **(D)** $\begin{pmatrix}81&0\\0&1\end{pmatrix}$

> **Answer: (C).**
>
> With $P = \begin{pmatrix}1&1\\1&-1\end{pmatrix}$, $\Lambda = \text{diag}(3,-1)$ and $P^{-1} = \tfrac12\begin{pmatrix}1&1\\1&-1\end{pmatrix}$: $A^4 = P\,\text{diag}(3^4, (-1)^4)\,P^{-1} = \tfrac12\begin{pmatrix}1&1\\1&-1\end{pmatrix}\begin{pmatrix}81&0\\0&1\end{pmatrix}\begin{pmatrix}1&1\\1&-1\end{pmatrix} = \tfrac12\begin{pmatrix}82&80\\80&82\end{pmatrix} = \begin{pmatrix}41&40\\40&41\end{pmatrix}$. (Check: $A^2 = \begin{pmatrix}5&4\\4&5\end{pmatrix}$ and $(A^2)^2 = \begin{pmatrix}41&40\\40&41\end{pmatrix}$.) Entry-wise powers are not matrix powers; $\Lambda^4$ is $A^4$ in eigenvector coordinates only; $(-1)^4 = +1$.

---

### Question 7

Solve $\dot{\boldsymbol{x}} = A\boldsymbol{x}$ with $A = \begin{pmatrix}2&1\\1&2\end{pmatrix}$ and $\boldsymbol{x}(0) = (1,0)^T$.

- **(A)** $\boldsymbol{x}(t) = \tfrac12\big(e^{t}+e^{3t},\ e^{t}-e^{3t}\big)^T$
- **(B)** $\boldsymbol{x}(t) = e^{2t}\big(\cos t,\ \sin t\big)^T$
- **(C)** $\boldsymbol{x}(t) = \tfrac12\big(e^{3t}+e^{-t},\ e^{3t}-e^{-t}\big)^T$
- **(D)** $\boldsymbol{x}(t) = \tfrac12\big(e^{3t}+e^{t},\ e^{3t}-e^{t}\big)^T$

> **Answer: (D).**
>
> $\det(A-\lambda I) = (2-\lambda)^2 - 1 = 0$ gives $\lambda_1 = 3$ with $\boldsymbol{v}_1 = (1,1)^T$ and $\lambda_2 = 1$ with $\boldsymbol{v}_2 = (1,-1)^T$. So $\boldsymbol{x}(t) = c_1e^{3t}\boldsymbol{v}_1 + c_2e^{t}\boldsymbol{v}_2$, and $\boldsymbol{x}(0) = c_1\boldsymbol{v}_1 + c_2\boldsymbol{v}_2 = (1,0)^T$ gives $c_1 = c_2 = \tfrac12$: $\boldsymbol{x}(t) = \tfrac12\big(e^{3t}+e^{t},\ e^{3t}-e^{t}\big)^T$. Check: $\dot x_1 = \tfrac12(3e^{3t}+e^t) = 2x_1 + x_2$. All four options satisfy $\boldsymbol{x}(0) = (1,0)^T$, so the initial condition alone cannot decide: in the second option the eigenvectors are paired with the wrong exponentials ($\dot x_2 \neq x_1 + 2x_2$); the third uses $\lambda_2 = -1$; the fourth comes from complex eigenvalues $2\pm i$, but a real symmetric matrix has real eigenvalues, so there is no oscillation.


---

### Question 8

What are the singular values of $A = \begin{pmatrix}5&4\\-4&-5\end{pmatrix}$?

- **(A)** $81$ and $1$
- **(B)** $9$ and $1$
- **(C)** $3$ and $3$

> **Answer: (B).**
>
> The singular values are the square roots of the eigenvalues of $A^TA = \begin{pmatrix}5&-4\\4&-5\end{pmatrix}\begin{pmatrix}5&4\\-4&-5\end{pmatrix} = \begin{pmatrix}41&40\\40&41\end{pmatrix}$, whose eigenvalues are $41\pm40$, i.e. $81$ and $1$. So $\sigma_1 = 9$, $\sigma_2 = 1$. (Check: $\sigma_1\sigma_2 = 9 = |\det A|$.) The eigenvalues of $A$ itself are $\pm3$ (from $\lambda^2 - 9 = 0$), but $A$ is not symmetric, so its singular values are not $|\lambda_i|$: $A$ stretches one unit direction by a factor 9 and leaves the length of the orthogonal one unchanged (factor 1).

---
