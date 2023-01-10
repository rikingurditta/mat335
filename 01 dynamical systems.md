# Dynamical Systems

$$
\newcommand{\ds}{\displaystyle}

\newcommand{\R}{\mathbb R}
\newcommand{\C}{\mathbb C}
\newcommand{\parens}[1]{\left( #1 \right)}
\newcommand{\curlies}[1]{\left\{ #1 \right\}}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
$$

> Zenghao's favourite mathematics topic is calculus.

## Dynamical systems

A **dynamical system** is a pair $(T, X)$ of a set $X$ and a function $T: X \to X$. $T$ is usually called a **transformation**

### Newton's method

**Newton's method** is a method of using linear approximations of functions to iteratively estimate their roots

```python
def newtons(f, df, x0, tolerance):
  	x = x0
    while |f(x)| >= tolerance:
        x = x - f(x) / df(x)
    return x
```

The tangent line to $f$ at $x_0$ is $g(x) = f(x_0) + (x - x_0) f'(x_0)$

Setting this to $0$, it intersects the $x$-axis at $\ds x_1 = x_0 - \frac{f(x_0)}{f'(x_0)}$, so this is our starting guess for our next iteration.

### Fixed points

A point $a \in X$ in a dynamical system is a **fixed point** if $T(a) = a$

### Basin of attraction

The basin of attraction of $x$ is the set $\ds A_x = \curlies{y \in X : \lim_{x \to \infty} T^n y = x}$

This set is not necessarily connected!
