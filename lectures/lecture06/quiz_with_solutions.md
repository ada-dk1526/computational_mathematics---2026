# Computational Mathematics -- Lecture 6 quiz solutions


### Question 1

What is the exact solution of the relaxation problem $\dfrac{dy}{dt} = \dfrac{20 - y}{25}$, $y(0) = 5$?

- **(A)** $y(t) = 5 + \frac{3}{5}t$
- **(B)** $y(t) = 20 - 15e^{t/25}$
- **(C)** $y(t) = 20 - 15e^{-t/25}$
- **(D)** $y(t) = 5e^{-t/25}$

> **Answer: (C).**
>
> This is $y' = K(y_r - y)$ with $K = 1/25$ and $y_r = 20$, whose solution is $y = y_r + (y_0 - y_r)e^{-Kt} = 20 + (5 - 20)e^{-t/25} = 20 - 15e^{-t/25}$. Check: $y' = \frac{15}{25}e^{-t/25}$ and $\frac{20 - y}{25} = \frac{15}{25}e^{-t/25}$; $y(0) = 5$; and $y \to 20$. All four options satisfy $y(0) = 5$, but $20 - 15e^{t/25}$ grows away from $20$, $5e^{-t/25}$ decays to $0$, and $5 + \frac35 t$ keeps the initial slope $3/5$ for ever. The slope of the true solution, $\frac{20 - y}{25}$, shrinks as $y$ approaches $20$.

---

### Question 2

For the ODE $dy/dt = -3y$ with $y(0) = 2$, perform one forward-Euler step with $\Delta t = 0.1$ to find $y_1$.

- **(A)** $2.6$
- **(B)** $-4$
- **(C)** $1.94$
- **(D)** $1.4$

> **Answer: (D).**
>
> $y_1 = y_0 + \Delta t\, f(t_0,y_0) = 2 + 0.1\times(-3\times2) = 2 - 0.6 = 1.4$. The $2.6$ option flips the sign of the rate; the $1.94$ option mis-scales the step contribution; the $-4$ option omits the $\Delta t$ factor entirely.

---

### Question 3

The ODE $y' = -2y$, $y(0) = 1$, is solved with the leapfrog scheme and $\Delta t = 0.2$. Because leapfrog is not self-starting, the first step is taken with forward Euler, giving $y_1 = 0.6$. What is $y_2$?

- **(A)** $0.36$
- **(B)** $0.2$
- **(C)** $0.76$
- **(D)** $0.52$

> **Answer: (D).**
>
> Leapfrog comes from the central difference $\frac{y_{n+1}-y_{n-1}}{2\Delta t} = f(t_n, y_n)$, so $y_{n+1} = y_{n-1} + 2\Delta t\,f(t_n, y_n)$. With $n = 1$: $y_2 = y_0 + 2\times0.2\times(-2\times0.6) = 1 - 0.48 = 0.52$. A second forward Euler step gives $0.36$; using $\Delta t$ instead of $2\Delta t$ gives $0.76$; and evaluating $f$ at $y_0$ instead of the middle level $y_1$ gives $0.2$.

---

### Question 4

Backward Euler with $\Delta t = 1$ is applied to $y' = \dfrac{10 - y}{2}$, $y(0) = 2$. What is $y_1$?

- **(A)** $14$
- **(B)** $26/5$
- **(C)** $14/3$
- **(D)** $6$

> **Answer: (C).**
>
> Backward Euler evaluates the right-hand side at the new level: $y_1 = y_0 + \Delta t\,\frac{10 - y_1}{2} = 2 + 5 - \frac{y_1}{2}$. So $\frac32 y_1 = 7$ and $y_1 = 14/3$. Evaluating at the old level gives the forward Euler value $6$; the trapezoidal step $y_1 = 2 + \frac12\big(4 + \frac{10 - y_1}{2}\big)$ gives $26/5$; and dividing $7$ by $1 - \frac12$ instead of $1 + \frac12$ gives $14$.

---


### Question 5

The damped oscillator $2\ddot{x} + 4\dot{x} + 8x = 0$ is written as a first-order system for the state $(x, v)$, where $v = \dot{x}$: $\dfrac{d}{dt}\begin{pmatrix}x\\ v\end{pmatrix} = A\begin{pmatrix}x\\ v\end{pmatrix}$. What is $A$?

- **(A)** $\begin{pmatrix}0 & 1\\ -4 & -2\end{pmatrix}$
- **(B)** $\begin{pmatrix}0 & 1\\ -8 & -4\end{pmatrix}$
- **(C)** $\begin{pmatrix}0 & 1\\ 4 & 2\end{pmatrix}$
- **(D)** $\begin{pmatrix}0 & 1\\ -2 & -4\end{pmatrix}$

> **Answer: (A).**
>
> The first row is $\dot{x} = v = 0\cdot x + 1\cdot v$. Solving the ODE for $\ddot{x}$: $\dot{v} = \ddot{x} = -\frac{8x + 4v}{2} = -4x - 2v$, so the second row is $(-4, -2)$ and $A = \begin{pmatrix}0 & 1\\ -4 & -2\end{pmatrix}$. Swapping the stiffness and damping entries gives $(-2, -4)$; not dividing by $2$ gives $(-8, -4)$; and losing the sign when moving the terms across gives $(4, 2)$.

---

### Question 6

The trapezoidal scheme $\dfrac{y_{n+1}-y_n}{\Delta t} = \frac12\big(f(t_n,y_n) + f(t_{n+1},y_{n+1})\big)$ is applied to $y' = \lambda y$ with $\lambda\Delta t = -3$. What is its amplification factor $\sigma$, defined by $y_{n+1} = \sigma\,y_n$?

- **(A)** $-5$
- **(B)** $-1/5$
- **(C)** $1/4$
- **(D)** $-2$

> **Answer: (B).**
>
> With $f = \lambda y$: $y_{n+1} - \frac{\lambda\Delta t}{2}y_{n+1} = y_n + \frac{\lambda\Delta t}{2}y_n$, so $\sigma = \frac{1 + \lambda\Delta t/2}{1 - \lambda\Delta t/2} = \frac{1 - 1.5}{1 + 1.5} = -\frac15$. Since $|\sigma| < 1$ the scheme is stable here (as for every $\lambda\Delta t$ with negative real part), but $\sigma < 0$: the numerical solution alternates in sign. The inverted ratio gives $-5$, the forward Euler factor $1 - 3 = -2$, and the backward Euler factor $1/(1+3) = 1/4$.

---

### Question 7

Forward Euler is applied to the relaxation problem $y' = K(y_r - y)$ with $K = 0.2$ and $y(0) \neq y_r$. What is the largest time step $\Delta t$ for which the numerical solution approaches $y_r$ monotonically, without overshooting it?

- **(A)** $5$
- **(B)** $0.2$
- **(C)** $10$

> **Answer: (A).**
>
> Subtracting $y_r$ from the update $y_{n+1} = y_n + \Delta t\,K(y_r - y_n)$ gives $y_{n+1} - y_r = (1 - K\Delta t)(y_n - y_r)$. The distance to $y_r$ keeps its sign (no overshoot) iff $1 - K\Delta t \ge 0$, i.e. $\Delta t \le 1/K = 5$. For $5 < \Delta t < 10 = 2/K$ the factor lies in $(-1, 0)$: stable but alternating about $y_r$; for $\Delta t > 10$ it is unstable. $0.2$ is the rate $K$, not a time.

---

### Question 8

Forward Euler is applied to the system $\boldsymbol{y}' = A\boldsymbol{y}$ with $A = \begin{pmatrix}-2 & 1\\ 1 & -2\end{pmatrix}$. It is stable exactly for $0 < \Delta t < \Delta t_c$. What is $\Delta t_c$?

- **(A)** $1$
- **(B)** $2$
- **(C)** $1/3$
- **(D)** $2/3$

> **Answer: (D).**
>
> The eigenvalues of $A$ solve $(-2-\lambda)^2 - 1 = 0$: $\lambda = -1$ and $\lambda = -3$. Diagonalising decouples the system into $z_i' = \lambda_i z_i$, and forward Euler is stable iff $|1 + \lambda_i\Delta t| < 1$ for both, i.e. $\Delta t < 2$ and $\Delta t < 2/3$. The fastest mode ($\lambda = -3$) sets $\Delta t_c = 2/3$. The slow mode alone would allow $\Delta t < 2$; $1/3$ is the monotonicity limit of the fast mode; and the diagonal entries of $A$ are not its eigenvalues.

---

### Question 9

Consider the IVP $\dfrac{dy}{dt} = y^2$, $y(0) = \tfrac{1}{2}$. Using one step of the RK2-Heun method with $\Delta t = 0.1$, find the exact decimal value of $y_1$.

- **(A)** $0.526281250$
- **(B)** $0.525000000$
- **(C)** $0.502628125$
- **(D)** $0.526265625$

> **Answer: (A).**
>
> With $f(t,y)=y^2$: $k_1=f(t_0,y_0)=\left(\tfrac12\right)^2=0.25$. $k_2=f(t_0+\Delta t,\,y_0+\Delta t\,k_1)=f(0.1,\,0.5+0.1(0.25))=f(0.1,0.525)=0.525^2=0.275625$. $y_1=y_0+\Delta t\,\dfrac{k_1+k_2}{2}=0.5+0.1\left(\dfrac{0.25+0.275625}{2}\right)=0.52628125$.

---

### Question 10

Classical RK4 is a fourth-order method: its global error at a fixed time is $\mathcal{O}(\Delta t^4)$. The error it commits in a single step, starting from exact data (its local error), is $\mathcal{O}(\Delta t^p)$. What is $p$?

- **(A)** $3$
- **(B)** $5$
- **(C)** $4$

> **Answer: (B).**
>
> The local error is $\Delta t\,\tau$, where the local truncation error $\tau$ of a fourth-order method is $\mathcal{O}(\Delta t^4)$; so the local error is $\mathcal{O}(\Delta t^5)$. Check: over a fixed time $T$ about $T/\Delta t$ local errors of size $\mathcal{O}(\Delta t^5)$ accumulate (for a stable method) into a global error $\mathcal{O}(\Delta t^4)$. So the local error exponent (5) is one higher than the global error exponent (4), not equal to it and not one lower.

---
