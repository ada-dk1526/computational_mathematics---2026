# Computational Mathematics -- Lecture 6 quiz

### Question 1

What is the exact solution of the relaxation problem $\dfrac{dy}{dt} = \dfrac{20 - y}{25}$, $y(0) = 5$?

- **(A)** $y(t) = 5 + \frac{3}{5}t$
- **(B)** $y(t) = 20 - 15e^{t/25}$
- **(C)** $y(t) = 20 - 15e^{-t/25}$
- **(D)** $y(t) = 5e^{-t/25}$

---

### Question 2

For the ODE $dy/dt = -3y$ with $y(0) = 2$, perform one forward-Euler step with $\Delta t = 0.1$ to find $y_1$.

- **(A)** $2.6$
- **(B)** $-4$
- **(C)** $1.94$
- **(D)** $1.4$

---

### Question 3

The ODE $y' = -2y$, $y(0) = 1$, is solved with the leapfrog scheme and $\Delta t = 0.2$. Because leapfrog is not self-starting, the first step is taken with forward Euler, giving $y_1 = 0.6$. What is $y_2$?

- **(A)** $0.36$
- **(B)** $0.2$
- **(C)** $0.76$
- **(D)** $0.52$

---

### Question 4

Backward Euler with $\Delta t = 1$ is applied to $y' = \dfrac{10 - y}{2}$, $y(0) = 2$. What is $y_1$?

- **(A)** $14$
- **(B)** $26/5$
- **(C)** $14/3$
- **(D)** $6$

Hint: Form the BE update:  $y_1 = y_0 + \Delta t\,\frac{10 - y_1}{2}$, rearrange to solve for $y_1$.

---

### Question 5

The damped oscillator $2\ddot{x} + 4\dot{x} + 8x = 0$ is written as a first-order system for the state $(x, v)$, where $v = \dot{x}$: $\dfrac{d}{dt}\begin{pmatrix}x\\ v\end{pmatrix} = A\begin{pmatrix}x\\ v\end{pmatrix}$. What is $A$?

- **(A)** $\begin{pmatrix}0 & 1\\ -4 & -2\end{pmatrix}$
- **(B)** $\begin{pmatrix}0 & 1\\ -8 & -4\end{pmatrix}$
- **(C)** $\begin{pmatrix}0 & 1\\ 4 & 2\end{pmatrix}$
- **(D)** $\begin{pmatrix}0 & 1\\ -2 & -4\end{pmatrix}$

---

### Question 6

The trapezoidal scheme $\dfrac{y_{n+1}-y_n}{\Delta t} = \frac12\big(f(t_n,y_n) + f(t_{n+1},y_{n+1})\big)$ is applied to $y' = \lambda y$ with $\lambda\Delta t = -3$. What is its amplification factor $\sigma$, defined by $y_{n+1} = \sigma\,y_n$?

- **(A)** $-5$
- **(B)** $-1/5$
- **(C)** $1/4$
- **(D)** $-2$

Hint: The trap scheme for this ODE can be written $y_{n+1} - \frac{\lambda\Delta t}{2}y_{n+1} = y_n + \frac{\lambda\Delta t}{2}y_n$. Plug in the given value for $\lambda\Delta t$ and rearrange.

---

### Question 7

Forward Euler is applied to the relaxation problem $y' = K(y_r - y)$ with $K = 0.2$ and $y(0) \neq y_r$. What is the largest time step $\Delta t$ for which the numerical solution approaches $y_r$ monotonically, without overshooting it?

- **(A)** $5$
- **(B)** $0.2$
- **(C)** $10$

Hint: The FE update for this problem takes the form $y_{n+1} = y_n + \Delta t\,K(y_r - y_n)$. 
The question is essentially asking us about the sign of $y-y_r$ and whether the sign changes (non-monotonicity) or not. From the FE update, substrating $y_r$ from both sides, 
we can see $y_{n+1} - y_r = (1 - K\Delta t)(y_n - y_r)$.
What property of the multiplier $(1 - K\Delta t)$ means that $y_{n+1} - y_r$ is not a different sign to $y_{n1} - y_r$?

---

### Question 8

Forward Euler is applied to the system $\boldsymbol{y}' = A\boldsymbol{y}$ with $A = \begin{pmatrix}-2 & 1\\ 1 & -2\end{pmatrix}$. It is stable exactly for $0 < \Delta t < \Delta t_c$. What is $\Delta t_c$?

- **(A)** $1$
- **(B)** $2$
- **(C)** $1/3$
- **(D)** $2/3$

Hint: Find the two eigenvalues of $A$ and ask that $|1 + \lambda_i\Delta t| < 1$ for both. Which gives the stictest bound on $\Delta t$.

---

### Question 9

Consider the IVP $\dfrac{dy}{dt} = y^2$, $y(0) = \tfrac{1}{2}$. Using one step of the RK2-Heun method with $\Delta t = 0.1$, find the exact decimal value of $y_1$.

- **(A)** $0.526281250$
- **(B)** $0.525000000$
- **(C)** $0.502628125$
- **(D)** $0.526265625$

---

### Question 10

Classical RK4 is a fourth-order method: its global error at a fixed time is $\mathcal{O}(\Delta t^4)$. The error it commits in a single step, starting from exact data (its local error), is $\mathcal{O}(\Delta t^p)$. What is $p$?

- **(A)** $3$
- **(B)** $5$
- **(C)** $4$

---
