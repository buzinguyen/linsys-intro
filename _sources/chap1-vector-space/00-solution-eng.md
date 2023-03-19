# Solution
Use what you have learned from previous sections to answer the following questions:

1. What is the difference between *injective*, *surjective* and *bijective*?

    ```{admonition} Answer
    :class: note
    **Injective** (one-to-one) means that an element in $Y$ cannot be a mapping of more than 1 element from $X$. We can write it as:

    $$f(x_1) = f(x_2) \leftrightarrow x_1 = x_2$$

    **Surjective** (onto) means that all elements in $Y$ is a mapping of an element in $X$ through $f$. This is the case when range of $f$ spans the entire co-domain. We write this as:

    $$\forall y \in Y, \exists x \in X \ni y = f(x)$$ 

    **Bijective** is both injective and surjective, i.e. range spans entire co-domain, and for every $y$ there is a unique $x$ that maps to $y$ through $f$.
    ```

2. When will the range of a function equals the co-domain?</span>

    ```{admonition} Answer
    :class: note
    When the function is surjective or bijective.
    ```

3. Given $\mathcal{f}: X \rightarrow Y$, when will $\mathcal{f}$ be called a function?</span>
    ```{admonition} Answer
    :class: note
    $f$ is a function when the mapping from $X$ to $Y$ is unique, i.e. there exist a unique value of $f(x) \forall x \in X$.
    ```