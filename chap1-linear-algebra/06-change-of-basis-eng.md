# 6. Change of Basis

We have seen how to create matrix representation of linear mapping between vector spaces, let's now look at how that matrix changes when the choice of basis of vector space changes.

Suppose we have the linear map $\mathcal{A}: U \rightarrow V$, with choice of basis $\{u_i\}^n$, coordinate $\{\xi_i\}$ for $U$, and basis $\{v_i\}^m$, coordinate $\{\eta_i\}$ for $V$. The corresponding matrix representation for this is $A$. Suppose also that we have another choice of basis and corresponding new coordinate $\{\bar{u}_i\}^n, \{\bar{\xi_i}\}$ for $U$ and $\{\bar{v}_i\}^m, \{\bar{\eta_i}\}$ for $V$, with the matrix representation $\bar{A}$. We now want to find the connection between $A$ and $\bar{A}$, i.e. given $A$, how can we construct $\bar{A}$ directly.

Let's start with $x \in U$. We can write $x$ as 

$$
x = \xi_1 u_1 + \xi_2 u_2 + \dots + \xi_n u_n =\begin{bmatrix}u_1 & u_2 & \dots & u_n\end{bmatrix}\xi = \begin{bmatrix}\bar{u_1} & \bar{u_2} & \dots & \bar{u_n}\end{bmatrix}\bar{\xi}
$$

Therefore:

$$
\begin{bmatrix}u_1 & u_2 & \dots & u_n\end{bmatrix}\xi = \begin{bmatrix}\bar{u_1} & \bar{u_2} & \dots & \bar{u_n}\end{bmatrix}\bar{\xi}
$$

Since $\{u_i\}$ are set of basis, they are linearly independent, meaning that the matrix constructed by them is invertible. Hence:

$$
\xi = P \bar{\xi} \;\;\text{with}\;\; P = \begin{bmatrix}u_1 & u_2 & \dots & u_n\end{bmatrix}^{-1}\begin{bmatrix}\bar{u_1} & \bar{u_2} & \dots & \bar{u_n}\end{bmatrix}
$$

Following similar steps for the co-domain, we have:

$$
\bar{\eta} = Q \eta \;\;\text{with}\;\; Q = \begin{bmatrix}\bar{v_1} & \bar{v_2} & \dots & \bar{v_m}\end{bmatrix}^{-1}\begin{bmatrix}v_1 & v_2 & \dots & v_m\end{bmatrix}
$$

In order to construct the relationship between the coordinates of different basis with respect to each other, we need a **bijective** relationship between the coordinates. Meaning that, the matrices $P, Q$, need to be bijective (see [Functions](../chap1-linear-algebra/01-functions-eng.md)).

From $P$ and $Q$, we can now construct the mapping between $A$ and $\bar{A}$:

$$
\begin{align*}
    & \eta = A \xi = AP\bar{\xi} \\
    & \rightarrow \bar{\eta} = Q \eta = Q A P \bar{\xi} \tag 1
\end{align*}
$$

The equation $(1)$ gives us the mapping between $\bar{\eta}$ and $\bar{\xi}$. And because the coordinate is *unique* w.r.t the choice of basis, then we can also say that $(1)$ gives us the mapping between the vector space with basis $\{\bar{v_i}\}$ and vector space with basis $\{\bar{u_i}\}$. This means that:

$$
\bar{A} = QAP \tag 2
$$

This means that to map $\bar{\xi}$ to $\bar{\eta}$, we can either go through matrix multiplication $\bar{A}$, or we can go through first $P$, then $A$, then $Q$.

On the other hand, if we replace $\{v_i\}$, $\{\bar{v_i}\}$ with $\{u_i\}$, $\{\bar{u_i}\}$ (domain and co-domain is the same), the $Q$ matrix becomes $P^{-1}$. Then $(2)$ will become:

$$
\bar{A} = P^{-1}AP \tag 3
$$

Equation $(3)$ is a standard when we talk about **similarity transform**. In fact, $(2)$ is a general representation of **similarity transform** between matrices, that these matrices have lots of similar properties that we will soon see.

**Example**: Let $\mathcal{A}: \mathbb{R}^3 \rightarrow \mathbb{R}^3$. Consider 2 different sets of basis:

$$
\mathcal{B} = \{\begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix}, \begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix}, \begin{bmatrix}0 \\ 0 \\ 1\end{bmatrix}\} 
\;\; \text{and} \;\; 
\mathcal{C} = \{c_1, c_2, c_3\} = \{\begin{bmatrix}1 \\ 1 \\ 0\end{bmatrix}, \begin{bmatrix}0 \\ 1 \\ 1\end{bmatrix}, \begin{bmatrix}1 \\ 0 \\ 1\end{bmatrix}\} 
$$

Suppose $\mathcal{A}(b_1) = \begin{bmatrix}2 \\ -1 \\ 0\end{bmatrix}$, $\mathcal{A}(b_2) = \begin{bmatrix}0 \\ 0 \\ 0\end{bmatrix}$, $\mathcal{A}(b_3) = \begin{bmatrix}0 \\ 4 \\ 2\end{bmatrix}$ as how the linear map $\mathcal{A}$ operates on the bases in $\mathcal{B}$. Write down the matrix representation of the mapping $\mathcal{A}$.

Now, the following up question that we need to ask here is which are the basis that we are mapping to. In case that we have $\mathcal{A}: \mathbb{R}^3_{\mathcal{B}} \rightarrow \mathbb{R}^3_{\mathcal{B}}$, then it is really simple to find $A$, that is:

$$
\begin{aligned}
    A &= \begin{bmatrix}\mathcal{A}(b_1) & \mathcal{A}(b_2) & \mathcal{A}(b_2)\end{bmatrix} \\
    &= \begin{bmatrix}2 & 0 & 0 \\ -1 & 0 & 4 \\ 0 & 0 & 2\end{bmatrix}
\end{aligned}
$$

Now, suppose that we change our linea map definition to $\mathcal{A}: \mathbb{R}^3_{\mathcal{B}} \rightarrow \mathbb{R}^3_{\mathcal{C}}$. We are both working on the vector space $\mathbb{R}^3$ for domain and co-domain, and we are changing the choice of basis from $\mathcal{B}$ for domain and $\mathcal{C}$ for co-domain. Then our new $A$ is:

$$
A = 
$$