# Computational Mathematics -- Lecture 7 quiz with solutions

### Question 1

Derive the standard 2-point backward-difference formula for $f'(x)$ using $f(x-h)$ and $f(x)$, i.e. find $(c_{-1},c_0)$ such that $f'(x)\approx\dfrac{1}{h}\big(c_{-1}f(x-h)+c_0f(x)\big)$.

- **(A)** $\left(-\dfrac12,\ \dfrac12\right)$
- **(B)** $(1,\ -1)$
- **(C)** $(1,\ 1)$
- **(D)** $(-1,\ 1)$

> **Answer: (D).**
>
> Taylor-expanding $f(x-h)$ about $x$: $f(x-h)=f(x)-hf'(x)+O(h^2)$. Rearranging: $hf'(x)=f(x)-f(x-h)+O(h^2)$, so $f'(x)\approx\dfrac{f(x)-f(x-h)}{h}=\dfrac{1}{h}\big((-1)f(x-h)+(1)f(x)\big)$, giving $(c_{-1},c_0)=(-1,1)$.

---

### Question 2

The central difference $\dfrac{f(x+h) - f(x-h)}{2h}$ approximates $f'(x)$. Taking the truncation error as this approximation minus the true value $f'(x)$, what is its leading term?

- **(A)** $-\dfrac{h}{2}f''(x)$
- **(B)** $\dfrac{h}{2}f''(x)$
- **(C)** $\dfrac{h^2}{6}f'''(x)$
- **(D)** $-\dfrac{h^2}{6}f'''(x)$

> **Answer: (C).**
>
> By Taylor's theorem, $f(x\pm h) = f(x) \pm hf'(x) + \frac{h^2}{2}f''(x) \pm \frac{h^3}{6}f'''(x) + \dots$. Subtracting, $f(x+h) - f(x-h) = 2hf'(x) + \frac{h^3}{3}f'''(x) + \dots$, and dividing by $2h$ gives $f'(x) + \frac{h^2}{6}f'''(x) + \mathcal{O}(h^4)$. So the leading error term is $\frac{h^2}{6}f'''(x)$: second order. The opposite sign convention gives $-\frac{h^2}{6}f'''(x)$. The one-sided differences are only first order: $+\frac{h}{2}f''(x)$ is the forward difference's term and $-\frac{h}{2}f''(x)$ the backward difference's. Their $f''$ terms cancel in the central difference, which is why it is second order.

---

### Question 3

A function takes the values $f(x-h) = 1$, $f(x) = 3$ and $f(x+h) = 7$, with $h = 0.5$. What does the three-point central difference formula give for $f''(x)$?

- **(A)** $6$
- **(B)** $2$
- **(C)** $4$
- **(D)** $8$

> **Answer: (D).**
>
> The three-point formula is $f''(x) \approx \dfrac{f(x+h) - 2f(x) + f(x-h)}{h^2} = \dfrac{7 - 6 + 1}{0.25} = 8$. Dividing by $h$ instead of $h^2$ gives $4$, and dividing by $(2h)^2$ gives $2$. The value $6 = \frac{7-1}{2\times0.5}$ is the central approximation of the first derivative.

---

### Question 4

The five-point central stencil $f''(x) \approx \dfrac{-f(x+2h) + 16f(x+h) - 30f(x) + 16f(x-h) - f(x-2h)}{12h^2}$ approximates the second derivative. What is its order of accuracy?

- **(A)** $2$
- **(B)** $4$
- **(C)** $3$

> **Answer: (B).**
>
> Five points can match the Taylor terms up to $f''''$, which alone would suggest order $5 - 2 = 3$. But the stencil is symmetric, so the odd-derivative terms ($f'''$, $f^{(5)}$) cancel automatically; the first term that survives involves $f^{(6)}$, with an $h^4$ factor after dividing by $h^2$. So the approximation is fourth order. The three-point formula is second order.

---

### Question 5

The steady problem $\kappa c'' - Uc' = 0$ on $[0, 1]$, with $c(0) = 0$ and $c(1) = c_E$, is discretised with central differences on the ghost-node mesh with $N = 2$ interior nodes ($\Delta x = 0.5$, unknowns $c_0, c_1, c_2, c_3$), with $\kappa = 0.5$ and $U = 1$. The boundary rows are $\tfrac12(c_0 + c_1) = 0$ and $\tfrac12(c_2 + c_3) = c_E$. What is the matrix $A$ of the system $A\boldsymbol{c} = \boldsymbol{b}$?

- **(A)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 3 & -4 & 1 & 0\\ 0 & 3 & -4 & 1\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$
- **(B)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 0 & -4 & 4 & 0\\ 0 & 0 & -4 & 4\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$
- **(C)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 4 & -4 & 0 & 0\\ 0 & 4 & -4 & 0\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$
- **(D)** $\begin{pmatrix}\tfrac12 & \tfrac12 & 0 & 0\\ 1 & -4 & 3 & 0\\ 0 & 1 & -4 & 3\\ 0 & 0 & \tfrac12 & \tfrac12\end{pmatrix}$

> **Answer: (A).**
>
> At an interior node, $\kappa\frac{c_{i+1} - 2c_i + c_{i-1}}{\Delta x^2} - U\frac{c_{i+1} - c_{i-1}}{2\Delta x} = 0$ gives the coefficients $\frac{\kappa}{\Delta x^2} + \frac{U}{2\Delta x} = 2 + 1 = 3$ on $c_{i-1}$, $-\frac{2\kappa}{\Delta x^2} = -4$ on $c_i$ and $\frac{\kappa}{\Delta x^2} - \frac{U}{2\Delta x} = 2 - 1 = 1$ on $c_{i+1}$. The first and last rows are the ghost-node boundary conditions $(\tfrac12, \tfrac12)$. Flipping the advection sign swaps the 3 and the 1. Dividing the advection difference by $\Delta x$ instead of $2\Delta x$ gives $2 \pm 2$, i.e. 4 and 0, on the neighbours. The remaining option makes both mistakes.

---

### Question 6

The steady problem $\kappa c'' - Uc' = 0$ on $[0, 1]$ with $c(0) = 0$, $c(1) = 1$, $\kappa = 0.25$ and $U = 0.5$ is discretised with central differences on the ghost-node mesh with $N = 2$ interior nodes, $x_1 = 0.25$ and $x_2 = 0.75$ ($\Delta x = 0.5$). The boundary conditions are $\tfrac12(c_0 + c_1) = 0$ and $\tfrac12(c_2 + c_3) = 1$. What value does the scheme give for $c_2$?

- **(A)** $4/13$
- **(B)** $7/16$
- **(C)** $3/4$
- **(D)** $15/16$

> **Answer: (B).**
>
> With $\frac{\kappa}{\Delta x^2} = 1$ and $\frac{U}{2\Delta x} = \tfrac12$, the interior rows are $\tfrac32c_{i-1} - 2c_i + \tfrac12c_{i+1} = 0$. The boundary rows give $c_0 = -c_1$ and $c_3 = 2 - c_2$. Row 1: $-\tfrac32c_1 - 2c_1 + \tfrac12c_2 = 0$, so $c_2 = 7c_1$. Row 2: $\tfrac32c_1 - 2c_2 + \tfrac12(2 - c_2) = 0$, so $\tfrac32c_1 - \tfrac52c_2 = -1$. Substituting, $\tfrac32c_1 - \tfrac{35}{2}c_1 = -1$, so $c_1 = \tfrac1{16}$ and $c_2 = \tfrac7{16}$. (The exact solution at $x = 0.75$ is $\frac{e^{1.5} - 1}{e^2 - 1} \approx 0.54$: two nodes are a very coarse mesh.) Ignoring advection gives $c_2 = 3/4$; flipping its sign gives $15/16$; and setting the ghost values directly gives $4/13$.

---

### Question 7

The steady advection-diffusion equation with $U = 2$ and $\kappa = 0.01$ is to be solved on a uniform mesh with $\Delta x = 0.02$. Which discretisation of the advection term should be used on this mesh, and why?

- **(A)** Central, because its second-order accuracy outweighs upwind's numerical diffusion on this mesh
- **(B)** Central, because the cell Peclet number is below 2
- **(C)** Upwind, because the cell Peclet number exceeds 2

> **Answer: (C).**
>
> The cell Peclet number is $Pe_c = U\Delta x/\kappa = 2\times0.02/0.01 = 4 > 2$. With central advection the coefficient of $c_{i+1}$, $\frac{\kappa}{\Delta x^2}(1 - Pe_c/2)$, is then negative, so the discrete solution can oscillate (wiggles, negative concentrations). Upwinding avoids this, at the price of first-order accuracy and numerical diffusion; refining the mesh until $Pe_c < 2$ would also work. Central's second order only helps once the mesh resolves the solution.

---

### Question 8

The advection term of the steady advection-diffusion equation with $U = 1$ and $\kappa = 0.005$ is discretised with first-order upwinding on a mesh with $\Delta x = 0.02$. What is the ratio $\kappa_{\text{num}}/\kappa$ of the numerical diffusivity that upwinding introduces to the physical diffusivity?

- **(A)** $2$
- **(B)** $0.5$
- **(C)** $0.01$
- **(D)** $4$

> **Answer: (A).**
>
> From the Taylor series, $U\frac{c_i - c_{i-1}}{\Delta x} = Uc'(x_i) - \frac{U\Delta x}{2}c''(x_i) + \mathcal{O}(\Delta x^2)$, so upwinding adds a diffusion term with $\kappa_{\text{num}} = U\Delta x/2 = 0.01$. Its ratio to the physical diffusivity is $\kappa_{\text{num}}/\kappa = 0.01/0.005 = 2 = Pe_c/2$: the scheme has three times the true diffusion in total, so the solution will be far too smooth. Dropping the $\tfrac12$ gives $Pe_c = 4$; $0.5$ is the inverted ratio; $0.01$ is $\kappa_{\text{num}}$, not the ratio.

---

### Question 9

The advection-diffusion equation $c_t + Uc_x = \kappa c_{xx}$ with $\kappa = 0.1$ and $U = 1$ is solved with FTCS (forward Euler in time, central differences in space), $\Delta x = 0.1$ and $\Delta t = 0.01$. At some time level, $c_{i-1} = 1$, $c_i = 2$ and $c_{i+1} = 4$. What is $c_i$ at the next time level?

- **(A)** $1.95$
- **(B)** $1.8$
- **(C)** $2.25$
- **(D)** $1.85$

> **Answer: (A).**
>
> The semi-discrete equation is $\frac{dc_i}{dt} = \kappa\frac{c_{i+1} - 2c_i + c_{i-1}}{\Delta x^2} - U\frac{c_{i+1} - c_{i-1}}{2\Delta x}$. Here the diffusion term is $0.1\times\frac{4 - 4 + 1}{0.01} = 10$ and the advection term is $1\times\frac{4 - 1}{0.2} = 15$. So forward Euler gives $c_i^{n+1} = c_i^{n} + 0.01\times(10 - 15)$, with $c_i^{n}=2$ = $c_i^{n}=1.95$. Adding the advection term gives $2.25$; dividing it by $\Delta x$ instead of $2\Delta x$ gives $1.8$; and dropping diffusion gives $1.85$.

---

### Question 10

On a periodic domain with $N = 4$ nodes $x_0, x_1, x_2, x_3$ (node $x_3$ is the left neighbour of $x_0$), the central difference $\frac{c_{i+1} - c_{i-1}}{2\Delta x}$ is written as $\frac{1}{\Delta x}D_x\boldsymbol{c}$. What is the matrix $D_x$?

- **(A)** $\begin{pmatrix}0 & -\tfrac12 & 0 & \tfrac12\\ \tfrac12 & 0 & -\tfrac12 & 0\\ 0 & \tfrac12 & 0 & -\tfrac12\\ -\tfrac12 & 0 & \tfrac12 & 0\end{pmatrix}$
- **(B)** $\begin{pmatrix}0 & \tfrac12 & 0 & 0\\ -\tfrac12 & 0 & \tfrac12 & 0\\ 0 & -\tfrac12 & 0 & \tfrac12\\ 0 & 0 & -\tfrac12 & 0\end{pmatrix}$
- **(C)** $\begin{pmatrix}0 & \tfrac12 & 0 & -\tfrac12\\ -\tfrac12 & 0 & \tfrac12 & 0\\ 0 & -\tfrac12 & 0 & \tfrac12\\ \tfrac12 & 0 & -\tfrac12 & 0\end{pmatrix}$
- **(D)** $\begin{pmatrix}0 & \tfrac12 & 0 & \tfrac12\\ -\tfrac12 & 0 & \tfrac12 & 0\\ 0 & -\tfrac12 & 0 & \tfrac12\\ -\tfrac12 & 0 & -\tfrac12 & 0\end{pmatrix}$

> **Answer: (C).**
>
> Row $i$ has $-\tfrac12$ in column $i-1$ and $+\tfrac12$ in column $i+1$, with indices taken modulo 4. Row 0 needs its left neighbour $c_{-1} = c_3$, which gives $-\tfrac12$ in column 3. Row 3 needs its right neighbour $c_4 = c_0$, which gives $+\tfrac12$ in column 0. Without these corner entries the matrix is not periodic; with their signs swapped the neighbours are the wrong way round; and the negated matrix computes the difference in the opposite direction, $\frac{c_{i-1} - c_{i+1}}{2\Delta x}$.

---

### Question 11

An explicit finite-difference scheme (forward differencing in time, central differencing in space) is used for the 1-D advection-diffusion equation with $U=1$, $\kappa=1$, $\Delta x=0.5$, $\Delta t=0.2$. Classify the discretization.

- **(A)** Unstable -- the Courant-number bound $C<1$ is violated
- **(B)** Stable -- the diffusion number $\kappa\Delta t/\Delta x = 0.4 < \tfrac12$
- **(C)** Stable -- the Courant number $C<1$ and cell Peclet number $Pe_c<2$ bounds are satisfied
- **(D)** Unstable -- the diffusion number bound $r < \tfrac12$ is violated

> **Answer: (D).**
>
> Three conditions must all hold for stability: cell Peclet number $Pe_c=U\Delta x/\kappa=(1)(0.5)/1=0.5$, which satisfies $Pe_c<2$. Courant number $C=U\Delta t/\Delta x=(1)(0.2)/0.5=0.4$, which satisfies $C<1$. Diffusion number $r=\kappa\Delta t/\Delta x^2=(1)(0.2)/(0.5)^2=0.8$, which violates the bound $r<\tfrac12$. Since all three bounds must hold simultaneously and the diffusion-number bound fails, the discretization is unstable.

---

### Question 12

The advection-diffusion equation with $U = 0.5$ and $\kappa = 0.02$ is solved with FTCS (forward Euler in time, central differences in space) on a mesh with $\Delta x = 0.02$. What is the largest time step $\Delta t$ that the Courant-number and diffusion-number bounds allow?

- **(A)** $0.04$
- **(B)** $0.01$
- **(C)** $0.02$

> **Answer: (B).**
>
> The cell Peclet number is $Pe_c = U\Delta x/\kappa = 0.5$, below 2, so only the time-step bounds matter. The Courant number $C = U\Delta t/\Delta x < 1$ needs $\Delta t < \Delta x/U = 0.04$. The diffusion number $r = \kappa\Delta t/\Delta x^2 < \tfrac12$ needs $\Delta t < \Delta x^2/(2\kappa) = 0.0004/0.04 = 0.01$. Both must hold, so the smaller one, $0.01$, is the limit: here diffusion, not advection, sets the time step. (Since $C/r = Pe_c$, the diffusion bound is the tighter one whenever $Pe_c < 2$.)

---
