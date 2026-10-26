# Computational Mathematics -- Lecture 7 quiz

### Question 1

Derive the standard 2-point backward-difference formula for $f'(x)$ using $f(x-h)$ and $f(x)$, i.e. find $(c_{-1},c_0)$ such that $f'(x)\approx\dfrac{1}{h}\big(c_{-1}f(x-h)+c_0f(x)\big)$.

- **(A)** $\left(-\dfrac12,\ \dfrac12\right)$
- **(B)** $(1,\ -1)$
- **(C)** $(1,\ 1)$
- **(D)** $(-1,\ 1)$

Hint: Start from a Taylor series expansion of $f(x-h)$ about location $x$ and rearrange.

---

### Question 2

The central difference $\dfrac{f(x+h) - f(x-h)}{2h}$ approximates $f'(x)$. Taking the truncation error as this approximation minus the true value $f'(x)$, what is its leading term?

- **(A)** $-\dfrac{h}{2}f''(x)$
- **(B)** $\dfrac{h}{2}f''(x)$
- **(C)** $\dfrac{h^2}{6}f'''(x)$
- **(D)** $-\dfrac{h^2}{6}f'''(x)$

Hint: Start from a Taylor series expansions of $f(x+h)$ and  $f(x+h)$ about location $x$.

---

### Question 3

A function takes the values $f(x-h) = 1$, $f(x) = 3$ and $f(x+h) = 7$, with $h = 0.5$. What does the three-point central difference formula give for $f''(x)$?

- **(A)** $6$
- **(B)** $2$
- **(C)** $4$
- **(D)** $8$

---

### Question 4

The five-point central stencil $f''(x) \approx \dfrac{-f(x+2h) + 16f(x+h) - 30f(x) + 16f(x-h) - f(x-2h)}{12h^2}$ approximates the second derivative. What is its order of accuracy?

- **(A)** $2$
- **(B)** $4$
- **(C)** $3$

Hint: Think about this problem without bothering to form all four Taylor series expansions ... with this many points (5) combined, how many terms can you cancel in the representation of $f''(x)$?

---

### Question 5

The steady problem $\kappa c'' - Uc' = 0$ on $[0, 1]$, with $c(0) = 0$ and $c(1) = c_E$, is discretised with central differences on the ghost-node mesh with $N = 2$ interior nodes ($\Delta x = 0.5$, unknowns $c_0, c_1, c_2, c_3$), with $\kappa = 0.5$ and $U = 1$. The boundary rows are $\tfrac12(c_0 + c_1) = 0$ and $\tfrac12(c_2 + c_3) = c_E$. What is the matrix $A$ of the system $A\boldsymbol{c} = \boldsymbol{b}$?

- **(A)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 3 & -4 & 1 & 0\\ 0 & 3 & -4 & 1\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$
- **(B)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 0 & -4 & 4 & 0\\ 0 & 0 & -4 & 4\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$
- **(C)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 4 & -4 & 0 & 0\\ 0 & 4 & -4 & 0\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$
- **(D)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 1 & -4 & 3 & 0\\ 0 & 1 & -4 & 3\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$

Hint: Recall that the interior nodes satisfy the discretisation $\kappa\frac{c_{i+1} - 2c_i + c_{i-1}}{\Delta x^2} - U\frac{c_{i+1} - c_{i-1}}{2\Delta x} = 0$

---

### Question 6

The steady problem $\kappa c'' - Uc' = 0$ on $[0, 1]$ with $c(0) = 0$, $c(1) = 1$, $\kappa = 0.25$ and $U = 0.5$ is discretised with central differences on the ghost-node mesh with $N = 2$ interior nodes, $x_1 = 0.25$ and $x_2 = 0.75$ ($\Delta x = 0.5$). The boundary conditions are $\tfrac12(c_0 + c_1) = 0$ and $\tfrac12(c_2 + c_3) = 1$. What value does the scheme give for $c_2$?

- **(A)** $4/13$
- **(B)** $7/16$
- **(C)** $3/4$
- **(D)** $15/16$

---

### Question 7

The steady advection-diffusion equation with $U = 2$ and $\kappa = 0.01$ is to be solved on a uniform mesh with $\Delta x = 0.02$. Which discretisation of the advection term should be used on this mesh, and why?

- **(A)** Central, because its second-order accuracy outweighs upwind's numerical diffusion on this mesh
- **(B)** Central, because the cell Peclet number is below 2
- **(C)** Upwind, because the cell Peclet number exceeds 2

---

### Question 8

The advection term of the steady advection-diffusion equation with $U = 1$ and $\kappa = 0.005$ is discretised with first-order upwinding on a mesh with $\Delta x = 0.02$. What is the ratio $\kappa_{\text{num}}/\kappa$ of the numerical diffusivity that upwinding introduces to the physical diffusivity?

- **(A)** $2$
- **(B)** $0.5$
- **(C)** $0.01$
- **(D)** $4$

Hint: Refer to the notes section *Analysis of the upwind scheme*

---

### Question 9

The advection-diffusion equation $c_t + Uc_x = \kappa c_{xx}$ with $\kappa = 0.1$ and $U = 1$ is solved with FTCS (forward Euler in time, central differences in space), $\Delta x = 0.1$ and $\Delta t = 0.01$. At some time level, $c_{i-1} = 1$, $c_i = 2$ and $c_{i+1} = 4$. What is $c_i$ at the next time level?

- **(A)** $1.95$
- **(B)** $1.8$
- **(C)** $2.25$
- **(D)** $1.85$

---

### Question 10

On a periodic domain with $N = 4$ nodes $x_0, x_1, x_2, x_3$ (node $x_3$ is the left neighbour of $x_0$), the central difference $\frac{c_{i+1} - c_{i-1}}{2\Delta x}$ is written as $\frac{1}{\Delta x}D_x\boldsymbol{c}$. What is the matrix $D_x$?

- **(A)** $\begin{pmatrix}0 & -\tfrac12 & 0 & \tfrac12\\ \tfrac12 & 0 & -\tfrac12 & 0\\ 0 & \tfrac12 & 0 & -\tfrac12\\ -\tfrac12 & 0 & \tfrac12 & 0\end{pmatrix}$
- **(B)** $\begin{pmatrix}0 & \tfrac12 & 0 & 0\\ -\tfrac12 & 0 & \tfrac12 & 0\\ 0 & -\tfrac12 & 0 & \tfrac12\\ 0 & 0 & -\tfrac12 & 0\end{pmatrix}$
- **(C)** $\begin{pmatrix}0 & \tfrac12 & 0 & -\tfrac12\\ -\tfrac12 & 0 & \tfrac12 & 0\\ 0 & -\tfrac12 & 0 & \tfrac12\\ \tfrac12 & 0 & -\tfrac12 & 0\end{pmatrix}$
- **(D)** $\begin{pmatrix}0 & \tfrac12 & 0 & \tfrac12\\ -\tfrac12 & 0 & \tfrac12 & 0\\ 0 & -\tfrac12 & 0 & \tfrac12\\ -\tfrac12 & 0 & -\tfrac12 & 0\end{pmatrix}$

---

### Question 11

An explicit finite-difference scheme (forward differencing in time, central differencing in space) is used for the 1-D advection-diffusion equation with $U=1$, $\kappa=1$, $\Delta x=0.5$, $\Delta t=0.2$. Classify the discretization.

- **(A)** Unstable -- the Courant-number bound $C<1$ is violated
- **(B)** Stable -- the diffusion number $\kappa\Delta t/\Delta x = 0.4 < \tfrac12$
- **(C)** Stable -- the Courant number $C<1$ and cell Peclet number $Pe_c<2$ bounds are satisfied
- **(D)** Unstable -- the diffusion number bound $r < \tfrac12$ is violated

---

### Question 12

The advection-diffusion equation with $U = 0.5$ and $\kappa = 0.02$ is solved with FTCS (forward Euler in time, central differences in space) on a mesh with $\Delta x = 0.02$. What is the largest time step $\Delta t$ that the Courant-number and diffusion-number bounds allow?

- **(A)** $0.04$
- **(B)** $0.01$
- **(C)** $0.02$

---
