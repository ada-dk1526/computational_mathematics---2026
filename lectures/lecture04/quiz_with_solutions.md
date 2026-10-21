# Computational Mathematics -- Lecture 4 quiz with solutions


### Question 1

A code returns $240$ for a quantity whose exact value is $250$. What is the percentage error of the code's result?

- **(A)** $4\%$
- **(B)** $0.04\%$
- **(C)** $4.17\%$
- **(D)** $10\%$

> **Answer: (A).**
>
> The percentage error is $e_{\%} = 100\,|x - x_{\text{approx}}|/|x|$ with $x$ the exact value: $100\times|250-240|/250 = 100\times10/250 = 4\%$. The absolute error is $10$ (not a percentage), the relative error is $0.04$ (that is, $4\%$, not $0.04\%$), and the error is always measured relative to the exact value, not the approximation ($10/240$ would give $4.17\%$).

---

### Question 2

Compute the $\ell_2$ (Euclidean) norm of the vector $\mathbf{v} = (3, -4, 12)$.

- **(A)** $19$
- **(B)** $5$
- **(C)** $13$
- **(D)** $169$

> **Answer: (C).**
>
> $\|\mathbf{v}\|_2=\sqrt{3^2+(-4)^2+12^2}=\sqrt{9+16+144}=\sqrt{169}=13$. The value $19$ is instead the $\ell_1$ norm $|3|+|-4|+|12|$.

---

### Question 3

The errors of a time-stepping scheme at four time levels are $\boldsymbol{e} = (3,\ -1,\ 1,\ 1)^T$. What is the RMS (root-mean-square) error?

- **(A)** $2\sqrt{3}$
- **(B)** $3/2$
- **(C)** $\sqrt{3}$
- **(D)** $3$

> **Answer: (C).**
>
> $e_{\text{RMS}} = \big(\frac1n\sum_i e_i^2\big)^{1/2} = \big((9+1+1+1)/4\big)^{1/2} = \sqrt{3}$, i.e. $\|\boldsymbol{e}\|_2/\sqrt{n}$ with $n = 4$. The plain two-norm $\sqrt{12} = 2\sqrt3$ grows with the number of entries, which is why the normalised (averaged) version is used to compare error vectors of different lengths. $3/2$ is the mean absolute error, and $3$ is the mean squared error (which here happens to equal the max-norm too).

---

### Question 4

A second-order time-stepping scheme is run to a fixed end time $T$; its (global) error at every time level is about $C\Delta t^2$. In a convergence study, the error is measured by the plain (unnormalised) two-norm of the vector of errors at all time levels. What slope will the log-log convergence plot show as $\Delta t\to0$?

- **(A)** $3/2$
- **(B)** $5/2$
- **(C)** $2$
- **(D)** $1$

> **Answer: (A).**
>
> With a fixed end time there are $n\approx T/\Delta t$ time levels, each with an error of about $C\Delta t^2$, so $\|\boldsymbol{e}\|_2 = \big(\sum_i e_i^2\big)^{1/2} \approx \big(n\,C^2\Delta t^4\big)^{1/2} \propto \Delta t^{-1/2}\,\Delta t^{2} = \Delta t^{3/2}$. The plot shows slope $3/2$, although the scheme is second order: the growing number of terms in the sum costs half an order (for the one-norm it would cost a whole order). The max-norm, or the RMS error $\|\boldsymbol{e}\|_2/\sqrt{n}$, would show the true slope $2$.

---

### Question 5

To verify a forward Euler code we need the exact solution of $\dot{y} = y + t^2$, $y(0) = 1$. Which of these functions is it?

- **(A)** $y(t) = e^{t} + t^3/3$
- **(B)** $y(t) = -e^{t} + t^2 + 2t + 2$
- **(C)** $y(t) = e^{t} - t^2 - 2t - 2$
- **(D)** $y(t) = 3e^{t} - t^2 - 2t - 2$

> **Answer: (D).**
>
> Check by substitution. For $y = 3e^t - t^2 - 2t - 2$: $\dot y = 3e^t - 2t - 2$ and $y + t^2 = 3e^t - 2t - 2$, so the ODE holds, and $y(0) = 3 - 2 = 1$. (SymPy's dsolve, given the initial condition, returns the same function.) The second option also has $y(0) = 1$, but $\dot y = -e^t + 2t + 2 \ne y + t^2 = -e^t + 2t^2 + 2t + 2$. The third has $y(0) = 1$, but $\dot y = e^t + t^2 \ne y + t^2$: the terms of a linear ODE cannot be integrated separately. The fourth satisfies the ODE but gives $y(0) = -1$.

---

### Question 6

A numerical scheme has an error of $0.008$ at step size $h_1=0.1$, when halved to $h_2=0.05$ the error is $0.001$. Estimate the scheme's order of convergence $p$.

- **(A)** $1/3$
- **(B)** $3$
- **(C)** $1$
- **(D)** $4$

> **Answer: (B).**
>
> We know from typical Taylor series based error analysis that a numerical scheme's error typically scales as a power of the step size, $E(h)\approx Ch^p$ for some constant $C$ and order $p$ -- this is the standard error-scaling assumption behind the course's log-log convergence plots. Taking the ratio at two step sizes cancels the unknown constant $C$: $\text{error}_1/\text{error}_2 = (h_1/h_2)^p$, so $p = \ln(\text{error}_1/\text{error}_2) / \ln(h_1/h_2)$. Here $\ln(0.008/0.001)/\ln(0.1/0.05) = \ln 8/\ln 2 = 3$.

---

### Question 7

A code solves $\dot{y} = y + S(t)$ for a given source term $S(t)$. To verify it with the method of manufactured solutions we choose $y_{\text{mms}}(t) = t^2 + e^{2t}$. Which source term $S(t)$ makes $y_{\text{mms}}$ an exact solution?

- **(A)** $S(t) = t^2 + 2t + 3e^{2t}$
- **(B)** $S(t) = 2t + 2e^{2t}$
- **(C)** $S(t) = t^2 - 2t - e^{2t}$
- **(D)** $S(t) = 2t - t^2 + e^{2t}$

> **Answer: (D).**
>
> $y_{\text{mms}}$ must satisfy $\dot{y}_{\text{mms}} = y_{\text{mms}} + S(t)$, so $S$ is the residual $S = \dot{y}_{\text{mms}} - y_{\text{mms}} = (2t + 2e^{2t}) - (t^2 + e^{2t}) = 2t - t^2 + e^{2t}$. Check: $y_{\text{mms}} + S = t^2 + e^{2t} + 2t - t^2 + e^{2t} = 2t + 2e^{2t} = \dot{y}_{\text{mms}}$. Using $\dot{y}_{\text{mms}}$ alone ignores the $y$ term the code adds; $t^2 - 2t - e^{2t}$ has the opposite sign; and adding $y_{\text{mms}}$ to $\dot{y}_{\text{mms}}$ double counts it.


---

### Question 8

What is $\|A\|_\infty$, the maximum absolute row sum norm, of $A = \begin{pmatrix}2 & -5\\ 3 & 1\end{pmatrix}$?

- **(A)** $6$
- **(B)** $4$
- **(C)** $7$
- **(D)** $11$

> **Answer: (C).**
>
> $\|A\|_\infty = \max_i \sum_j |A_{ij}|$: the row sums of absolute values are $|2|+|-5| = 7$ and $|3|+|1| = 4$, so $\|A\|_\infty = 7$. (This is the matrix norm induced by the vector max-norm.) The maximum absolute column sum, $6$, is $\|A\|_1$; forgetting the absolute values gives $4$; and $11$ treats the matrix as a vector of four entries.

---

### Question 9

What is the condition number $\textrm{cond}_2(A) = \|A\|_2\,\|A^{-1}\|_2$ of $A = \begin{pmatrix}3 & 0\\ 4 & 5\end{pmatrix}$ in the two-norm?

- **(A)** $9$
- **(B)** $3$
- **(C)** $5/3$
- **(D)** $10/3$

> **Answer: (B).**
>
> In the two-norm, $\textrm{cond}_2(A) = \sigma_{\max}/\sigma_{\min}$, the ratio of the largest to the smallest singular value. $A^TA = \begin{pmatrix}25 & 20\\ 20 & 25\end{pmatrix}$ has eigenvalues $45$ and $5$, so $\sigma_{\max} = \sqrt{45}$, $\sigma_{\min} = \sqrt{5}$ and $\textrm{cond}_2(A) = \sqrt{45/5} = 3$. The eigenvalues of $A$ itself ($3$ and $5$) do not give it, because $A$ is not symmetric; $9$ forgets the square roots; $10/3$ uses the Frobenius norm instead of the two-norm.

---

### Question 10

A matrix $A$ has condition number $\textrm{cond}(A) = 5000$. The right-hand side $\boldsymbol{b}$ of $A\boldsymbol{x} = \boldsymbol{b}$ is known only to a relative error of $10^{-6}$ (with $A$ exact). What is the largest relative error $\|\delta\boldsymbol{x}\|/\|\boldsymbol{x}\|$ that the condition-number bound allows in the solution?

- **(A)** $10^{-6}$
- **(B)** $5\times10^{3}$
- **(C)** $2\times10^{-10}$
- **(D)** $5\times10^{-3}$

> **Answer: (D).**
>
> From $A\boldsymbol{x}=\boldsymbol{b}$ and $A(\boldsymbol{x}+\delta\boldsymbol{x}) = \boldsymbol{b}+\delta\boldsymbol{b}$: $\delta\boldsymbol{x} = A^{-1}\delta\boldsymbol{b}$, so $\|\delta\boldsymbol{x}\|\le\|A^{-1}\|\|\delta\boldsymbol{b}\|$, and $\|\boldsymbol{b}\|\le\|A\|\|\boldsymbol{x}\|$. Together, $\|\delta\boldsymbol{x}\|/\|\boldsymbol{x}\| \le \textrm{cond}(A)\,\|\delta\boldsymbol{b}\|/\|\boldsymbol{b}\| = 5000\times10^{-6} = 5\times10^{-3}$. The condition number amplifies the relative error of the data; it does not divide it, it is not itself the error, and the solution's relative error can be much larger than the data's.

---

### Question 11

The system $A\boldsymbol{x} = \boldsymbol{b}$ with $A = \begin{pmatrix}1 & 1\\ 1 & 1.01\end{pmatrix}$ and $\boldsymbol{b} = (2,\ 2.01)^T$ has the solution $\boldsymbol{x} = (1,\ 1)^T$. The second entry of $\boldsymbol{b}$ is now changed by $0.01$, to $\boldsymbol{b} = (2,\ 2.02)^T$. What is the relative change $\|\delta\boldsymbol{x}\|_2/\|\boldsymbol{x}\|_2$ in the solution?

- **(A)** $1$
- **(B)** $\sqrt{2}/2$
- **(C)** $\sqrt{2}$
- **(D)** $0.01$

> **Answer: (A).**
>
> Solve with the new right-hand side: $x_1 + x_2 = 2$ and $x_1 + 1.01x_2 = 2.02$ give $0.01x_2 = 0.02$, so $\boldsymbol{x}' = (0,\ 2)^T$ and $\delta\boldsymbol{x} = (-1,\ 1)^T$. Then $\|\delta\boldsymbol{x}\|_2/\|\boldsymbol{x}\|_2 = \sqrt2/\sqrt2 = 1$: a $100\%$ change in the solution from a change of about $0.35\%$ in $\boldsymbol{b}$ ($0.01/\|(2,\ 2.01)^T\|_2$). The matrix is nearly singular (ill-conditioned), so the solve amplifies relative errors enormously. $\sqrt2$ is the absolute change; $\sqrt2/2$ measures it against the new solution instead of the original.

---
