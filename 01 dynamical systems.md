# Dynamical Systems

$$
\newcommand{\ds}{\displaystyle}

\newcommand{\R}{\mathbb R}

\newcommand{\parens}[1]{\left( #1 \right)}
\newcommand{\curlies}[1]{\left\{ #1 \right\}}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\inv}[1]{#1^{-1}}
$$

> Zenghao's favourite mathematics topic is calculus.

## Dynamical systems

A **dynamical system** is a pair $(T, X)$ of a set $X$ and a function $T: X \to X$. $T$ is usually called a **transformation**

### Newton's method

**Newton's method** is a method of using linear approximations of functions to iteratively estimate their roots

The tangent line to $f$ at $x_0$ is $g(x) = f(x_0) + (x - x_0) f'(x_0)$

Setting this to $0$, the tangent intersects the $x$-axis at $\ds x_1 = x_0 - \frac{f(x_0)}{f'(x_0)}$, so this is our starting guess for our next iteration.

```python
def newtons(f, df, x0, iterations):
  	x = x0
    i = 0
    while i < iterations:
        x = x - f(x) / df(x)
        i += 1
    return x
```

### Fixed points

A point $a \in X$ in a dynamical system is a **fixed point** if $T(a) = a$

### Basin of attraction

The basin of attraction of $x$ is the set

$$
A_x = \curlies{y \in X : \lim_{x \to \infty} T^n y = x}
$$

This set is not necessarily connected!

### Inverse image

If $f: A \to B$ is a function and $X \subseteq B$, the **inverse image** of $X$ under $f$ is

$$
\inv f (X) = \curlies{x \in A : f(x) \in X}
$$
Note that every function has inverse images, it does not need to be invertible.
