# Computational Mathematics -- Lecture 4 quiz


### Question 1

A code returns $240$ for a quantity whose exact value is $250$. What is the percentage error of the code's result?

- **(A)** $4\%$
- **(B)** $0.04\%$
- **(C)** $4.17\%$
- **(D)** $10\%$

---

### Question 2

Compute the $\ell_2$ (Euclidean) norm of the vector $\mathbf{v} = (3, -4, 12)$.

- **(A)** $19$
- **(B)** $5$
- **(C)** $13$
- **(D)** $169$

---

### Question 3

The errors of a time-stepping scheme at four time levels are $\boldsymbol{e} = (3,\ -1,\ 1,\ 1)^T$. What is the RMS (root-mean-square) error?

- **(A)** $2\sqrt{3}$
- **(B)** $3/2$
- **(C)** $\sqrt{3}$
- **(D)** $3$

---

### Question 4

A second-order time-stepping scheme is run to a fixed end time $T$; its (global) error at every time level is about $C\Delta t^2$. In a convergence study, the error is measured by the plain (unnormalised) two-norm of the vector of errors at all time levels. What slope will the log-log convergence plot show as $\Delta t\to0$?

- **(A)** $3/2$
- **(B)** $5/2$
- **(C)** $2$
- **(D)** $1$

Hint: Remember that as we refine the time step size the number of steps we do up to a fixed end time is
going to increase: $n\approx T/\Delta t$. Think about what happens if we include all of these in our error calculation for each $\Delta t$ value considered in our convergence study.

---

### Question 5

To verify a forward Euler code we need the exact solution of $\dot{y} = y + t^2$, $y(0) = 1$. Which of these functions is it?

- **(A)** $y(t) = e^{t} + t^3/3$
- **(B)** $y(t) = -e^{t} + t^2 + 2t + 2$
- **(C)** $y(t) = e^{t} - t^2 - 2t - 2$
- **(D)** $y(t) = 3e^{t} - t^2 - 2t - 2$

---

### Question 6

A numerical scheme has an error of $0.008$ at step size $h_1=0.1$, when halved to $h_2=0.05$ the error is $0.001$. Estimate the scheme's order of convergence $p$.

- **(A)** $1/3$
- **(B)** $3$
- **(C)** $1$
- **(D)** $4$

Hint: Start from the assumption that 
error $E(h)\approx Ch^p$ for some constant $C$ and order $p$

---

### Question 7

A code solves $\dot{y} = y + S(t)$ for a given source term $S(t)$. To verify it with the method of manufactured solutions we choose $y_{\text{mms}}(t) = t^2 + e^{2t}$. Which source term $S(t)$ makes $y_{\text{mms}}$ an exact solution?

- **(A)** $S(t) = t^2 + 2t + 3e^{2t}$
- **(B)** $S(t) = 2t + 2e^{2t}$
- **(C)** $S(t) = t^2 - 2t - e^{2t}$
- **(D)** $S(t) = 2t - t^2 + e^{2t}$

---

### Question 8

What is $\|A\|_\infty$, the maximum absolute row sum norm, of $A = \begin{pmatrix}2 & -5\\ 3 & 1\end{pmatrix}$?

- **(A)** $6$
- **(B)** $4$
- **(C)** $7$
- **(D)** $11$

---

### Question 9

What is the condition number $\textrm{cond}_2(A) = \|A\|_2\,\|A^{-1}\|_2$ of $A = \begin{pmatrix}3 & 0\\ 4 & 5\end{pmatrix}$ in the two-norm?

- **(A)** $9$
- **(B)** $3$
- **(C)** $5/3$
- **(D)** $10/3$

---

### Question 10

A matrix $A$ has condition number $\textrm{cond}(A) = 5000$. The right-hand side $\boldsymbol{b}$ of $A\boldsymbol{x} = \boldsymbol{b}$ is known only to a relative error of $10^{-6}$ (with $A$ exact). What is the largest relative error $\|\delta\boldsymbol{x}\|/\|\boldsymbol{x}\|$ that the condition-number bound allows in the solution?

- **(A)** $10^{-6}$
- **(B)** $5\times10^{3}$
- **(C)** $2\times10^{-10}$
- **(D)** $5\times10^{-3}$

---

### Question 11

The system $A\boldsymbol{x} = \boldsymbol{b}$ with $A = \begin{pmatrix}1 & 1\\ 1 & 1.01\end{pmatrix}$ and $\boldsymbol{b} = (2,\ 2.01)^T$ has the solution $\boldsymbol{x} = (1,\ 1)^T$. The second entry of $\boldsymbol{b}$ is now changed by $0.01$, to $\boldsymbol{b} = (2,\ 2.02)^T$. What is the relative change $\|\delta\boldsymbol{x}\|_2/\|\boldsymbol{x}\|_2$ in the solution?

- **(A)** $1$
- **(B)** $\sqrt{2}/2$
- **(C)** $\sqrt{2}$
- **(D)** $0.01$

---
