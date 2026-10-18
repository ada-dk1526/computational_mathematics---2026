# Computational Mathematics -- Lecture 1 quiz solutions

$\newcommand{\ii}{\mathrm{i}}\newcommand{\dd}{\mathrm{d}}\newcommand{\rr}{\mathbb{R}}\newcommand{\cc}{\mathbb{C}}$

### Question 1

Consider the course's (Euler-derived) form of the logistic map, $x_{n+1} = x_n + r\,x_n(1-x_n)$, with $r = 2.5$. Which of the following is exactly the set of its fixed points?

- **(A)** $\{0,\ 1.4\}$
- **(B)** $\{1\}$
- **(C)** $\{0,\ 0.6\}$
- **(D)** $\{0,\ 1\}$

> **Answer: (D).**
>
> A fixed point satisfies $x_{n+1} = x_n$: $x + r x(1-x) = x \iff r x(1-x) = 0 \iff x = 0$ or $x = 1$ (for this form, whatever the value of $r>0$). So the answer is D. Where did the other list of incorrect candidate solutions come from?... $\{0, 1.4\}$ are the roots of the right-hand side $x(1+r-rx)$, i.e. the endpoints of the plotting interval $[0, (1+r)/r]$ used in the notes; they are not fixed points. $0.6 = 1 - 1/r$ is the non-trivial fixed point of the *classical* form $r x(1-x)$. Dividing through by $x$ loses $x = 0$: a population of zero stays at zero, so it is a (trivial, unstable) fixed point.

---

### Question 2

The course's (Euler-derived) logistic map $x_{n+1} = x_n + r\,x_n(1-x_n)$ is iterated with $r = 1.6$ starting from $x_0 = 0.3$. What is the long-term behaviour of $x_n$?

- **(A)** It converges to $x=1$, alternately overshooting and undershooting it
- **(B)** It stays bounded but never settles to a single value
- **(C)** It converges to $x=1$ monotonically, never overshooting it
- **(D)** It blows up: the iterates grow in magnitude without bound

> **Answer: (A).**
>
> Near the fixed point $x = 1$ write $x_n = 1 + \varepsilon_n$; linearising, $\varepsilon_{n+1} \approx (1-r)\,\varepsilon_n = -0.6\,\varepsilon_n$. The distance from $x = 1$ shrinks by a factor $0.6$ each generation and changes sign, so $x_n$ converges to $1$ while overshooting alternately above and below it (e.g. $0.3 \to 0.636 \to 1.006 \to 0.996 \to \ldots$), as for $r = 1.9$ in the notes. Monotone convergence needs $0 < r \le 1$; the iterates only fail to settle for $r > 2$ and blow up for $r > 3$ (the classical-form thresholds are one higher: $2, 3, 4$). The nonlinear term $-r x_n^2$ caps the growth, so the linear picture $(1+r)x_n$ only holds while $x_n$ is small.

---

### Question 3

The Taylor series of $f(x) = \ln x$ about $x_0 = 1$ is truncated after the $(x - x_0)^3$ term. What approximation does it give for $\ln(1.2)$, to 5 decimal places?

- **(A)** $0.18267$
- **(B)** $0.17733$
- **(C)** $0.17600$
- **(D)** $0.18227$

> **Answer: (A).**
>
> $f(1) = 0$; $f'(x) = 1/x$, $f'(1) = 1$; $f''(x) = -1/x^2$, $f''(1) = -1$; $f'''(x) = 2/x^3$, $f'''(1) = 2$. With $h = x - x_0 = 0.2$: $T_3 = h - \dfrac{h^2}{2!} + \dfrac{2h^3}{3!} = 0.2 - 0.02 + 0.002667 = 0.182667 \approx 0.18267$ (the exact value is $\ln 1.2 = 0.18232$). Dropping the factorials gives $0.2 - 0.04 + 0.016 = 0.176$. Also keeping the $h^4$ term ($f''''(1) = -6$, so $-h^4/4 = -0.0004$) gives $0.18227$, which is closer to $\ln 1.2$ but is not the approximation asked for. A wrong sign on the cubic term gives $0.2 - 0.02 - 0.002667 = 0.17733$.

---

### Question 4

The Taylor series of $f(x) = \sin x$ about $x_0 = 0$ is truncated after the first-order term, giving the linearisation $\sin h \approx h$. What is the largest $p$ for which the truncation error satisfies $\sin h - h = \mathcal{O}(h^{p})$ as $h \to 0$?

- **(A)** $2$
- **(B)** $3$
- **(C)** $1$

> **Answer: (B).**
>
> $\sin h = h - \dfrac{h^3}{3!} + \dfrac{h^5}{5!} - \ldots$: the $h^2$ coefficient is $f''(0)/2! = -\sin(0)/2 = 0$. The first neglected *non-zero* term is $-h^3/6$, so $\sin h - h = \mathcal{O}(h^3)$ and no higher power works, since $(\sin h - h)/h^3 \to -1/6 \neq 0$ (it is of course also $\mathcal{O}(h^2)$, but that bound is not sharp). Halving $h$ reduces the error in this lienarisation (linear approximation) by about a factor of 8.

---

### Question 5

The error of a numerical method with step size $\Delta t$ behaves like $E(\Delta t) = 10^{-5}\,\Delta t + 10^{5}\,\Delta t^{2} + \Delta t^{3}$. What is the largest $p$ for which $E(\Delta t) = \mathcal{O}(\Delta t^{p})$ in the limit $\Delta t \to 0$?

- **(A)** $3$
- **(B)** $1$
- **(C)** $2$

> **Answer: (B).**
>
> As $\Delta t \to 0$ the *lowest* power dominates, whatever the coefficients: once $\Delta t < 10^{-10}$ the $10^{-5}\Delta t$ term is the largest, so $E = \mathcal{O}(\Delta t)$ and halving $\Delta t$ eventually only halves the error. For larger $\Delta t$ the $10^{5}\Delta t^{2}$ term dominates and the error *looks* second order; we are simply not yet in the asymptotic limit. In the opposite limit $\Delta t \to \infty$ the *highest* power dominates instead, and $E = \mathcal{O}(\Delta t^{3})$.

---

### Question 6

Consider the initial value problem $y' = t - 3y$. Using the forward-Euler (explicit Euler) update obtained by truncating the Taylor expansion of $y(t+\Delta t)$ after the first-order term, write the update for $y_{n+1}$ in terms of $y_n$, $t_n$ and $\Delta t$.

- **(A)** $y_n - \Delta t\,(t_n - 3y_n)$
- **(B)** $y_n + \Delta t\,((t_n + \Delta t) - 3y_n)$
- **(C)** $y_n + \Delta t\,t_n - 3y_n$
- **(D)** $y_n + \Delta t\,(t_n - 3y_n)$

> **Answer: (D).**
>
> Taylor-expanding $y(t+\Delta t) = y(t) + \Delta t\,y'(t) + O(\Delta t^2)$ and truncating after the first-order term gives $y_{n+1} \approx y_n + \Delta t\,y'_n$. Substituting $y'_n = t_n - 3y_n$ gives $y_{n+1} = y_n + \Delta t\,(t_n - 3y_n)$.

---

### Question 7

Apply one step of the forward Euler method to $y' = y + t^3$ with $y(1) = 2$ and step size $\Delta t = 0.1$. What is the resulting approximation to $y(1.1)$?

- **(A)** $2.3$
- **(B)** $2.33$
- **(C)** $1.7$
- **(D)** $2.3331$

> **Answer: (A).**
>
> Forward Euler: $y_{n+1} = y_n + \Delta t\,f(t_n, y_n)$ with $f(t, y) = y + t^3$. At $(t_n, y_n) = (1, 2)$, $f = 2 + 1 = 3$, so $y_{n+1} = 2 + 0.1 \times 3 = 2.3$. $2.33$ adds the second-order Taylor term $\tfrac{\Delta t^2}{2}y''$ - exactly the term forward Euler drops. $2.3331$ uses the slope at the *end* of the step, but forward Euler uses the slope at the known starting point. $1.7$ has the sign of the increment wrong.

---

### Question 8

The logistic ODE $\dfrac{dx}{dt} = \alpha\,x(1-x)$ with $\alpha = 0.8$ is solved with forward Euler using $\Delta t = 1.5$. If $x_n = 0.5$, what is $x_{n+1}$?

- **(A)** $0.7$
- **(B)** $0.8$
- **(C)** $0.3$
- **(D)** $0.2$

> **Answer: (B).**
>
> Forward Euler gives $x_{n+1} = x_n + \Delta t\,\alpha\,x_n(1-x_n)$ - the course's form of the logistic map with $r = \alpha\Delta t = 0.8 \times 1.5 = 1.2$. So $x_{n+1} = 0.5 + 1.2 \times 0.5 \times 0.5 = 0.8$. Using $r = \alpha$ ignores the time step (giving $0.7$); the classical form omits the $x_n$ carried over from the previous step (giving $0.3$).

---

### Question 9

The logistic ODE $\dfrac{dx}{dt} = \alpha\,x(1-x)$ (with $\alpha = 1.25$ and $x(0) = 0.1$) has an exact solution that tends to $x = 1$. Suppose we solve it approximately with forward Euler using $\Delta t = 2$. What does the numerical solution do at long times?


- **(A)** It blows up: the iterates grow in magnitude without bound
- **(B)** It converges to $x=1$ monotonically, like the exact solution
- **(C)** It converges to $x=1$, alternately overshooting and undershooting it
- **(D)** It stays bounded but never settles to a single value

> **Answer: (D).**
>
> Forward Euler turns the ODE into the logistic map $x_{n+1} = x_n + r x_n(1-x_n)$ with $r = \alpha\Delta t = 1.25\times2 = 2.5$. Since $2 < r < 3$ the fixed point $x = 1$ is unstable ($|1 - r| = 1.5 > 1$), but the iterates remain bounded, so the numerical solution never settles - here it ends up cycling between four values ($\approx 1.225, 0.536, 1.158, 0.701$). This is a purely numerical artefact: the exact solution does nothing of the sort. Smaller $\Delta t$ (with $\alpha\Delta t < 2$) restores convergence.

---

### Question 10

Forward Euler is applied to the logistic ODE $\dfrac{dx}{dt} = \alpha\,x(1-x)$ with $\alpha = 0.4$ and $0 < x_0 < 1$. What is the largest time step $\Delta t$ for which the numerical solution still converges to the steady state $x = 1$ (oscillations about $x = 1$ allowed)?

- **(A)** $0.8$
- **(B)** $2.5$
- **(C)** $5$
- **(D)** $7.5$

> **Answer: (C).**
>
> Forward Euler gives the logistic map $x_{n+1} = x_n + r x_n(1-x_n)$ with $r = \alpha\Delta t$. Near $x = 1$ the distance from the fixed point is multiplied by $1 - r$ each step, so the solution converges while $|1 - r| < 1$, i.e. up to $r = \alpha\Delta t = 2$ (at exactly $2$ it still converges, but only extremely slowly). Hence $\Delta t \le 2/\alpha = 2/0.4 = 5$. Up to $\Delta t = 2.5$ ($r\le1$) the approach is monotone; between $5$ and $7.5$ the solution is bounded but never settles; beyond $7.5$ ($r > 3$) it blows up. The threshold depends on the physical parameter $\alpha$.

---

### Question 11

A time-stepping scheme gives errors $e_1 = 8.0\times10^{-3}$ with $\Delta t_1 = 0.1$ and $e_2 = 2.0\times10^{-3}$ with $\Delta t_2 = 0.05$, both in the asymptotic regime. What is the observed order of convergence $p$ (the slope of error against $\Delta t$ on a log-log plot)?

- **(A)** $1$
- **(B)** $0.5$
- **(C)** $2$
- **(D)** $4$

> **Answer: (C).**
>
> If $e \approx C\Delta t^{p}$ then $\ln e \approx \ln C + p\ln\Delta t$, a straight line of slope $p$ on a log-log plot, and $p = \dfrac{\ln(e_1/e_2)}{\ln(\Delta t_1/\Delta t_2)} = \dfrac{\ln 4}{\ln 2} = 2$. Halving $\Delta t$ quartered the error, so this is a second-order scheme (forward Euler would only halve it). $4$ is the error ratio, not the order, and $0.5$ has the ratio upside down.

---

### Question 12

With forward Euler (a first-order method), the error at $t = 5$ is $3.0\times10^{-3}$ when $\Delta t = 0.1$. Assuming we are in the asymptotic regime, what error do you expect at $t = 5$ with $\Delta t = 0.025$?

- **(A)** $1.5\times10^{-3}$
- **(B)** $1.875\times10^{-4}$
- **(C)** $7.5\times10^{-4}$

> **Answer: (C).**
>
> For a first-order method the error at a fixed time behaves like $C\Delta t$, so dividing $\Delta t$ by $4$ divides the error by $4$: $3.0\times10^{-3}/4 = 7.5\times10^{-4}$. Each step makes an $\mathcal{O}(\Delta t^2)$ error, but reaching $t = 5$ takes $5/\Delta t$ steps, so the accumulated error is $\mathcal{O}(\Delta t)$ - scaling by $16$ confuses the two.

---
