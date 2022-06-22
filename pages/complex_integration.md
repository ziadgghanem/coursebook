---
layout: post
title: 'Complex Integration'
---

## 5.1 Complex Curves

We call a continuous map $\gamma: [a,b] \rightarrow \mathbb{C}$ a **continuous curve**, the set $\Gamma:= \lbrace \gamma(t) \; : \; a \leq t \leq b \rbrace  \subset \mathbb{C}$ is called the **trajectory** of $\gamma$. In fact, $\gamma$ is only one parametrization of the trajectory $\Gamma$. 

A curve $\gamma: [a,b] \rightarrow \mathbb{C}$ can expressed as a complex-function $\gamma(t) = z(t) = x(t) + iy(t)$ where $(x(t),y(t))$ are continuous real-valued maps.

<div class="proposition" markdown="1">

**Theorem 5.01:** On the non-uniqueness of parametrization

Two continuous curves $\gamma, \tau: [a,b] \rightarrow \mathbb{C}$ parametrize the same trajectory if there exists a continuous, monotonically increasing map $\phi: [0,1] \rightarrow [0,1]$ such that $\tau \circ \phi = \gamma$
</div>

A **smooth complex curve** can be represented $\gamma(t) = (x(t),y(t))$ where $x(t)$, $y(t)$ are smooth, real-valued functions on $[a,b]$. A **differentiable curve** is piece-wise smooth, i.e. the concatenation of any finite number of smooth curves.

<div class="example" markdown="1">

**Example:** Common parametrizations of Complex Curves

1. The line consisting of thepoints $z_0$ and $z_1$
    - $$z(t) = z_0(1-t) + z_1t, \; -\inft < t < \inf$$
2. The line segment between the points $z_0$ and $z_1$
    - $$z(t) = z_0(1-t) + z_1t, \; 0 \leq t \leq 1$$
3. The circle centered at $z_0$ with radius $r$
    - $$z(t) = z_0 + r(\cos(t) + i\sin(t)) = z_0 + re^{it} \; 0 \leq t \leq 2 \pi$$

These parametrizations are not unique.
</div>

## 5.2 Introducing the Integral

<div class="example" markdown="1">

**Definition:** Integral of complex function over real interval

Let $f(t) = u(t) + iv(t)$ be continuous over the real interval $(a,b)$ then we define the definite integral of $f$ over $(a,b)$ as a generalization of the definite integral of a real-valued function
> $$\int_a^b f(t) dt = \int_a^b u(t)dt + i \int_a^b v(t)dt$$ $$$$
</div>

<div class="example" markdown="1">

**Example:** Calculate the integral $\int_0^{\frac{\pi}{2}} e^{it}$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

Direct application of Euler's formula gives us $e^{it} = \cos(t) + i \sin(t)$, 
> $$\int_0^{\frac{\pi}{2}} e^{it} = \int_0^{\frac{\pi}{2}} \cos(t) + i \int_0^{\frac{\pi}{2}} \sin(t)$$ $$$$
> $$ \quad \quad = \sin(t) \vert_0^{\frac{\pi}{2}} + i \cos(t) \vert_0^{\frac{\pi}{2}} = 1 + i$$ $$$$
</details>
</div>

<div class="definition" markdown="1">

**Definition:** Integral of complex function over differentiable curve

Given piece-wise smooth curve $\gamma: [a,b] \rightarrow \mathbb{C}$ and complex function $f(z)$ continuous on $\gamma([a,b])$ which has, then $f(z)$ has continuous parameterization $f(z(t))$ and the parameterization of $\gamma$, $z(t)$ has continuous derivative $z'(t)$
> $$\int\limits_{\gamma}f(z) dz = \int_a^b f(z(t))z'(t)dt$$ $$$$
</div>

<div class="example" markdown="1">

**Example:** Calculate the integral $\int_{\gamma} e^{z} dz$ where $\gamma$ is the line segment connecting points $z_0 = 0$ and $z_1 = \pi - i \pi$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

$\gamma$ might be parameterized as $z(t) = (1-t)z_0 + t z_1 = \pi t - i \pi t$ where $0 \leq t \leq 1$ with $z'(t) = \pi - i \pi$ and $f(z(t)) = e^{t(\pi - i \pi )}$ such that
> $$\int\limits_{\gamma} e^{z} dz =  (\pi - i \pi) \int_0^1 e^{t(\pi - i \pi)}dt$$ $$$$
> $$ \quad \quad = \frac{(\pi - i \pi)}{(\pi - i \pi)} e^{t(\pi - i \pi)} \vert_0^1 = e^{\pi(1 - i)} - 1$$
> $$ \quad \quad =  e^{\pi}e^{- i \pi} - 1 = e^{\pi}(\cos(-\pi) + i \sin(-\pi)) - 1 = -e^{\pi} - 1$$

</details>
</div>

<div class="proposition" markdown="1">

**Proposition:** Properties of Complex Integral

For any complex numbers $(c_1 = \alpha_1 + i \beta_1), (c_2 = \alpha_2 + i \beta_2) \in \mathbb{C}$
1. $$\int\limits_{\gamma}c_1f(z) + c_2g(z) dz = c_1 \int\limits_{\gamma}f(z) dz + c_2 \int\limits_{\gamma}g(z) dz$$ $$$$
2. Suppose $$\vert f(z) \vert \leq M$$ on $$\gamma$$ and $$\mathcal{l}$$ is the length of $$\gamma$$ then
    - $$\vert \int\limits_{\gamma}f(z) dz \vert \leq M \mathcal{l}$$ $$$$
3. If $$f$$ is integrated over the opposite arc $$- \gamma(t) = \gamma(-t)$$ then
    - $$\int\limits_{- \gamma}f(z) dz =\int\limits_{\gamma}f(z) dz$$ $$$$
4. If a curve is defined as the piecewise concatenation $$\gamma = \gamma_1 + \gamma_2 + \cdots + \gamma_n$$ then
    - $$\int\limits_{\gamma}f(z) dz =\int\limits_{\gamma_1}f(z) dz + \int\limits_{\gamma_2}f(z) dz + \cdots + \int\limits_{\gamma_n}f(z) dz$$ $$$$

</div>
