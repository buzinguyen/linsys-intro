# 15. Dynamical systems
```{contents}
:local:
```
We will now formally define dynamical system, i.e, what does it mean to be a dynamical system, what elements are in a dynamical system, and as well some axioms that a dynamical system has to satisfy.

# Definition
A dynamical system $D(U, \Sigma, Y, s, r)$ with:
* $U$: input space. The input function $u(\cdot): T \rightarrow U = \mathbb{R}^{n_i}$, with $n_i$ the dimension of the input.
* $\Sigma$: state space. Function $x(\cdot): T \rightarrow \Sigma: \mathbb{R}^n$.
* $Y$: output space. Output function $y(\cdot): T \rightarrow Y = \mathbb{R}^{n_o}$ with $n_o$ the dimension of the output.
* $s$: state transition function, defines as $s(\cdot, \cdot, \cdot, \cdot): T \times T \times \Sigma \times U \rightarrow \Sigma$. An example is $x(t) = s(t, t_0, x_0, u(\cdot))\Big|_{t_0}^t$
* $r$: read-out map (output map), defines as $r(t, x(t), u(t))\rightarrow y(t)$.
With $T$ be the set of time, it can either be $\mathbb{R}_+$ or $\{nT\}, n \in \mathbb{Z}$.

# Axioms
## State transition axiom
If the inputs are the same over a time interval, and we start at the same state, then the state transition function will give us the same result at the end of that time interval.

$$
\begin{align*}
	u(t) &= \tilde{u}(t) \quad \text{over} \quad [t_0, t_1] \\
	\text{then} & s(t, t_0, x_0, u) = s(t, t_0, x_0, \tilde{u})
\end{align*}
$$

What is substantial about this is that we do not care what happen before and after the chosen time interval. We can think of it as at $t_0$, whatever happened before has already been encapsulated into $x_0$, regardless of the previous control sequences, and if $u = \bar{u}$ over $[t_0, t_1]$, then the state transition function will go through the same sequence of states.

## Semigroup axiom
Given $t^* \in [t_0, t_1]$

$$
s(t_1, t_0, x_0, u) = s(t_1, t^*, s(t^*, t_0, x_0, u), u)
$$


