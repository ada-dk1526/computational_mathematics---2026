# Computational Mathematics -- Lecture 1 quiz

$\newcommand{\ii}{\mathrm{i}}\newcommand{\dd}{\mathrm{d}}\newcommand{\rr}{\mathbb{R}}\newcommand{\cc}{\mathbb{C}}$

### Question 1

Consider the course's (Euler-derived) form of the logistic map, $x_{n+1} = x_n + r\,x_n(1-x_n)$, with $r = 2.5$. Which of the following is exactly the set of its fixed points?

- **(A)** $\{0,\ 1.4\}$
- **(B)** $\{1\}$
- **(C)** $\{0,\ 0.6\}$
- **(D)** $\{0,\ 1\}$


Hint: Recall that to be a fixed point we need $x_{n+1} = x_n$. But we also have the relationship $x_{n+1} = x_n + r\,x_n(1-x_n)$. Combining, at a fixed point it must be the case that $x_{n} = x_n + r\,x_n(1-x_n)$. Simplify and solve this for possible $x_n$ values that satisay the definition of being a fixed point.  Further insight: this is a quadratic equation so we might be expecting up to two real solutions.

---

### Question 2

The course's (Euler-derived) logistic map $x_{n+1} = x_n + r\,x_n(1-x_n)$ is iterated with $r = 1.6$ starting from $x_0 = 0.3$. What is the long-term behaviour of $x_n$?

- **(A)** It converges to $x=1$, alternately overshooting and undershooting it
- **(B)** It stays bounded but never settles to a single value
- **(C)** It converges to $x=1$ monotonically, never overshooting it
- **(D)** It blows up: the iterates grow in magnitude without bound

Hint: You could evaluate the map starting from 0.3 and see what happens. An alternative is to consider a linearisation about the fixed point $x=1$. What this means is write $x_n = 1 + \varepsilon_n$ where $\varepsilon_n$ is a *small* difference between $x$ and the fixed point (and so $\varepsilon_n^2$ and higher powers are *very small* and can be ignored in our analysis. Substituting into our logistic map yields $1 + \varepsilon_{n+1} = 1 + \varepsilon_n + r\,(1 + \varepsilon_n)(1-(1 + \varepsilon_n))$, simplifying and dropping terms you should find $\varepsilon_{n+1} = (1-r)\varepsilon_n)$. Given our value of $r$, what does this relationshop between the differences to the fixed point imply about the behaviour of $x$?

---

### Question 3

The Taylor series of $f(x) = \ln x$ about $x_0 = 1$ is truncated after the $(x - x_0)^3$ term. What approximation does it give for $\ln(1.2)$, to 5 decimal places?

- **(A)** $0.18267$
- **(B)** $0.17733$
- **(C)** $0.17600$
- **(D)** $0.18227$

Hint: Make use of the Taylor series expansion in the form 
$$f(x) = f(x_0) + (x - x_0) f'(x_0) + \frac{(x - x_0)^2}{2!} f''(x_0) + \frac{(x - x_0)^3}{3!} f'''(x_0) + \ldots$$
and recall that the derivative of $ln x$ is $1/x$, and so the second derivative is $-1/x^2$ and so on. 

---

### Question 4

The Taylor series of $f(x) = \sin x$ about $x_0 = 0$ is truncated after the first-order term, giving the linearisation $\sin h \approx h$. What is the largest $p$ for which the truncation error satisfies $\sin h - h = \mathcal{O}(h^{p})$ as $h \to 0$?

- **(A)** $2$
- **(B)** $3$
- **(C)** $1$

Hint: Here you might consider Taylor series expansion in the form
$$ f(x_0+h)  = f(x_0) + hf'(x_0) + \frac{h^2}{2!}f''(x_0) + \frac{h^3}{3!}f'''(x_0) + \ldots $$

---

### Question 5

The error of a numerical method with step size $\Delta t$ behaves like $E(\Delta t) = 10^{-5}\,\Delta t + 10^{5}\,\Delta t^{2} + \Delta t^{3}$. What is the largest $p$ for which $E(\Delta t) = \mathcal{O}(\Delta t^{p})$ in the limit $\Delta t \to 0$?

- **(A)** $3$
- **(B)** $1$
- **(C)** $2$

Hint: Notice that in the limit that $\Delta t$ gets small, $\Delta t^2$ gets very small and $\Delta t^3$ gets very very small. But, the multiplier $10^{5}$ is 10 orders of magnitude larger than $10^{-5}$, that's a big differnce in scaling of the first two terms making up $E$. So assuming we are in a regime (i.e. a range of values) with $\Delta t$ sufficiently small, is
$E\approx 10^{-5}\,\Delta t$ or $E\approx 10^{5}\,\Delta t^2$ or $E\approx 10^{-5}\,\Delta t^3$?

---

### Question 6

Consider the initial value problem $y' = t - 3y$. Using the forward-Euler (explicit Euler) update obtained by truncating the Taylor expansion of $y(t+\Delta t)$ after the first-order term, write the update for $y_{n+1}$ in terms of $y_n$, $t_n$ and $\Delta t$.

- **(A)** $y_n - \Delta t\,(t_n - 3y_n)$
- **(B)** $y_n + \Delta t\,((t_n + \Delta t) - 3y_n)$
- **(C)** $y_n + \Delta t\,t_n - 3y_n$
- **(D)** $y_n + \Delta t\,(t_n - 3y_n)$

Hint: Recall that forward Euler takes the form

$$ y(t+\Delta t) = y(t) + \Delta t \, y'(t) = y(t) + \Delta t f(t,y(t)) \iff
y_{n+1} = y_n + \Delta t \, f(t_n,y_n)$$

What is $f(t_n,y_n)$ in this case?

---

### Question 7

Apply one step of the forward Euler method to $y' = y + t^3$ with $y(1) = 2$ and step size $\Delta t = 0.1$. What is the resulting approximation to $y(1.1)$?

- **(A)** $2.3$
- **(B)** $2.33$
- **(C)** $1.7$
- **(D)** $2.3331$

---

### Question 8

The logistic ODE $\dfrac{dx}{dt} = \alpha\,x(1-x)$ with $\alpha = 0.8$ is solved with forward Euler using $\Delta t = 1.5$. If $x_n = 0.5$, what is $x_{n+1}$?

- **(A)** $0.7$
- **(B)** $0.8$
- **(C)** $0.3$
- **(D)** $0.2$

---

### Question 9

The logistic ODE $\dfrac{dx}{dt} = \alpha\,x(1-x)$ (with $\alpha = 1.25$ and $x(0) = 0.1$) has an exact solution that tends to $x = 1$. Suppose we solve it approximately with forward Euler using $\Delta t = 2$. What does the numerical solution do at long times?

- **(A)** It blows up: the iterates grow in magnitude without bound
- **(B)** It converges to $x=1$ monotonically, like the exact solution
- **(C)** It converges to $x=1$, alternately overshooting and undershooting it
- **(D)** It stays bounded but never settles to a single value

---

### Question 10

Forward Euler is applied to the logistic ODE $\dfrac{dx}{dt} = \alpha\,x(1-x)$ with $\alpha = 0.4$ and $0 < x_0 < 1$. What is the largest time step $\Delta t$ for which the numerical solution still converges to the steady state $x = 1$ (oscillations about $x = 1$ allowed)?

- **(A)** $0.8$
- **(B)** $2.5$
- **(C)** $5$
- **(D)** $7.5$

---

### Question 11

A time-stepping scheme gives errors $e_1 = 8.0\times10^{-3}$ with $\Delta t_1 = 0.1$ and $e_2 = 2.0\times10^{-3}$ with $\Delta t_2 = 0.05$, both in the asymptotic regime. What is the observed order of convergence $p$ (the slope of error against $\Delta t$ on a log-log plot)?

- **(A)** $1$
- **(B)** $0.5$
- **(C)** $2$
- **(D)** $4$

---

### Question 12

With forward Euler (a first-order method), the error at $t = 5$ is $3.0\times10^{-3}$ when $\Delta t = 0.1$. Assuming we are in the asymptotic regime, what error do you expect at $t = 5$ with $\Delta t = 0.025$?

- **(A)** $1.5\times10^{-3}$
- **(B)** $1.875\times10^{-4}$
- **(C)** $7.5\times10^{-4}$

---
