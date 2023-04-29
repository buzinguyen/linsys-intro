# 14. Bellman-Gronwall lemma
```{contents}
:local:
```
## Introduction
We will continue to look at the existence and uniqueness theorem, following the previous module, particularly on **uniqueness**. We will discuss Bellman-Gronwall lemma, a tool that we use to prove a uniqueness of a function, when we have some ideas that a function is a solution to an ODE.

## Bellman-Gronwall lemma
Suppose we have function $u(\cdot), K(\cdot)$ that are real-valued, $PC$ and positive on $R_+$. Let us also have some constant $c_1 \ge 0, t_0 \ge 0$, the Bellman-Gronwall states the following:
```{admonition} Bellman-Gronwall lemma
:class: important
If $u(t) \le c_1 + \int_{t_0}^t K(\tau)u(\tau)d\tau$ then:

$$
    u(t) \le c_1 e^{\int_{t_0}^t K(\tau)d\tau}
$$
```
It's worth noticing that in the resulting inequality, $u(t)$ only appears on the left hand side.
## Proof
Denotes $U(t) = c_1 + \int_{t_0}^t K(\tau)u(\tau)d\tau$, we have 

$$
u(t) \le U(t)
$$

Multiply both sides by the function $K(t)e^{-\int_{t_0}^t K(\tau)d\tau} \ge 0$, we have:

$$
u(t)K(t)e^{-\int_{t_0}^t K(\tau)d\tau} \le U(t)K(t)e^{-\int_{t_0}^t K(\tau)d\tau}
$$

proof continue: https://people.math.wisc.edu/~jwrobbin/angelic/gronwall.pdf

## Using Bellman-Gronwall lemma in proof of uniqueness of solution to differential equation
Suppose we have $\dot{x} = f(x, t)$,  $x(t_0) = x_0$ with solution $\phi(t)$. *How do we know that there is no other solution?* One way to prove this is to assume that it is not unique, and the find a contradiction.

```{admonition} Proving uniqueness
:class: note
In proving uniqueness, we often do contradiction.
```

Assume that $\phi(t)$ is not the unique solution, let us have $\chi(t)$ also the solution. We know that:

$$
\begin{align*}
	\dot{\phi}(t) &= f(\phi, t), \quad \phi(t_0) = x_0 \rightarrow \phi(t) = x_0 + \int_{t_0}^t f(\phi, t)dt\\
	\dot{\chi}(t) &= f(\chi, t), \quad \chi(t_0) = x_0 \rightarrow \chi(t) = x_0 + \int_{t_0}^t f(\chi, t)dt\\
\end{align*}
$$
If we take the difference between these two solutions:

$$
\begin{align*}
	||\phi(t) - \chi(t)|| \le \int_{t_0}^t ||f(\phi, \tau) - f(\chi, \tau)|| d\tau
\end{align*}
$$
Because $f(\cdot)$ is Lipschitz  continuous, there there exists a PC function $K(\cdot)$ such that $||f(x_1) - f(x_2)|| \le K(t)||x_1 - x_2||$. Also because $K(\cdot)$ is PC, there exists a supremum value of $K(\cdot)$ called $\bar{K}$. Then we have:

$$
||\phi(t) - \chi(t)|| \le \bar{K} \int_{t_0}^t||\phi(\tau) - \chi(\tau)|| d\tau
$$
Now this looks like the form that we can use the Bellman-Gronwall lemma on. For this, we will have $c_1=0$, and so with Bellman-Gronwall lemma, we can further bound this to:

$$
||\phi(t) - \chi(t)|| \le \bar{K} \int_{t_0}^t||\phi(\tau) - \chi(\tau)|| d\tau \rightarrow c_1 e^{\int_{t_0}^t \bar{K} d\tau} = 0
$$
Then we conclude that $\phi(t) = \chi(t)$.


