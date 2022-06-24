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

**Example:** Calculate the integral $\int_{\gamma} e^{\overline{z}} dz$ where $\gamma$ is the line segment connecting points $z_0 = 0$ and $z_1 = \pi - i \pi$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

$\gamma$ might be parameterized as $z(t) = (1-t)z_0 + t z_1 = \pi t - i \pi t$ where $0 \leq t \leq 1$ with $z'(t) = \pi - i \pi$ and $f(z(t)) = e^{t(\pi + i \pi )}$ such that
> $$\int\limits_{\gamma} e^{z} dz =  (\pi - i \pi) \int_0^1 e^{t(\pi + i \pi)}dt$$ $$$$
> $$ \quad \quad = \frac{(\pi - i \pi)}{(\pi + i \pi)} e^{t(\pi + i \pi)} \vert_0^1 = \frac{(\pi - i \pi)}{(\pi + i \pi)}(e^{\pi(1 + i)} - 1) $$ $$$$
> $$ \quad \quad =  \frac{(\pi - i \pi)}{(\pi + i \pi)}(e^{\pi}e^{i \pi} - 1) = \frac{(\pi - i \pi)}{(\pi + i \pi)} (- e^{\pi} - 1)$$ $$$$
> $$ \quad \quad = - \frac{(\pi - i \pi)^2}{2 \pi}(e^{\pi} + 1) = - \frac{\pi^2 -2i \pi - \pi^2}{2 \pi}(e^{\pi} + 1) = -i(e^{\pi} + 1)$$ $$$$

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

<div class="proposition" markdown="1">

**Theorem:** Fundamental Theorem of Contour Integration

Suppose that $f(z)$ is continuous on a domain $\Omega$ and has antiderivative $F(z)$ defined for all $z \in \Omega$, then for any curve $\gamma$ in $\Omega$ connecting $z_0$ to $z_2$ we have
> $$\int\limits_{\gamma}f(z) dz = F(z_1) - F(z_2)$$ $$$$

i.e. the integral is path independent
</div>



## 5.3 Cauchy's Theorem


<div class="proposition" markdown="1">

**Theorem:** Cauchy's Theorem in a Disk

If $f$ is analytic in an open disk $D$ then for every closed curve $\gamma \in D$
> $$\int\limits_{\gamma}f(z) dz = 0$$ $$$$

**Theorem:** Cauchy's Theorem in a Disk

If $f$ is analytic in a disk $D$, except perhaps at finitely many points $a_1, \ldots, a_n$ which are removeable singularities of $f$ (i.e. $\forall_i \; \lim_{z \rightarrow a_i} (z-a_i)f(z) = 0$) then for any closed curve not passing through any $a_i$
> $$\int\limits_{\gamma}f(z) dz = 0$$ $$$$

</div>

<div class="example" markdown="1">

**Example:** Calculate the integral $\int_{\gamma} \frac{dz}{1 + z^2}$ where $\gamma$ is the the positively oriented circle $\vert z + i \vert = 1$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

First we find the singular points of $f(z)$ as $z = \pm i$ and note that only $-i$ is locted inside $\gamma$
> $$\frac{1}{1 + z^2} = \frac{1}{(z-i)(z+i)} = \frac{A}{z-i} + \frac{B}{z+i}$$ $$$$

next, we perform partial fraction decomposition $\frac{1}{(z-i)(z+i)} = \frac{A}{z-i} + \frac{B}{z+i}$
where 
- $$A = \lim_{z \rightarrow i} (z-i)f(z) = \lim_{z \rightarrow i} \frac{1}{z+i} = \frac{1}{2i}$$ $$$$
- $$B = \lim_{z \rightarrow -i} (z+i)f(z) = \lim_{z \rightarrow -i} \frac{1}{z-i} = \frac{-1}{2i}$$ $$$$

and so we write $\frac{1}{1 + z^2} = \frac{1}{2i}( \frac{1}{z-i} - \frac{1}{z+i})$, as the term $\frac{1}{z-i}$ is analytic in the region bounded by $\gamma$, it will vanish under integration such that
> $$ \int\limits_{\gamma} \frac{1}{2i}( \frac{1}{z-i} - \frac{1}{z+i}) dz = \frac{-1}{2i} \int\limits_{\gamma} \frac{1}{z+i} = \frac{- 2 \pi i}{2 i} = - \pi$$ $$$$

</details>
</div>

## 5.4 Winding Number


<div class="definition" markdown="1">

**Definition:** Index (Winding Number)

The index of a curve $\gamma$ about a point $p$, not lying on $\gamma$ is given by
> $$n(\gamma,p):= \frac{1}{2 \pi i}  \int\limits_{\gamma}  \frac{dz}{z-p}$$ $$$$

If our curve is defined $\gamma: [a,b] \rightarrow \mathbb{C}$ then the above integral can be expressed 
> $$\int\limits_{\gamma}  = \int_a^b \frac{\gamma'(t)}{\gamma(t)-p}$$ $$$$
</div>

The index $n(\gamma,p)$, if known, might be used to compute the value of any integral $\int\limits_{\gamma}  \frac{dz}{z-p} = 2 \pi i n(\gamma,p)$

<div class="example" markdown="1">

**Example:** Let $\gamma(t) = e^{2n \pi i t}$ for some $n \in \mathbb{N}$ and where $0 \leq 1$. Calculate $n(\gamma,0)$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

$\gamma$ is the curve that traces the unit circle $n$-times in the positive direction, we can directly calculate its index
> $$n(\gamma,0) = \frac{1}{2 \pi i}  \int\limits_{\gamma}  \frac{dz}{z} = \frac{1}{2 \pi i}  \int_0^1 \frac{1}{e^{2n \pi i t}} 2 n \pi i e^{2n \pi i t} dt = \int_0^1 n dt = n$$ $$$$


</details>


**Example:** Let $\gamma(t) = e^{-2n \pi i t}$ for some $n \in \mathbb{N}$ and where $0 \leq 1$. Calculate $n(\gamma,0)$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

$\gamma$ is the curve that traces the unit circle $n$-times in the negative direction, we can directly calculate its index
> $$n(\gamma,0) = \frac{1}{2 \pi i}  \int\limits_{\gamma}  \frac{dz}{z} = \frac{- 1}{2 \pi i}  \int_0^1 \frac{1}{e^{- 2n \pi i t}} 2 n \pi i e^{- 2n \pi i t} dt = - \int_0^1 n dt = - n$$ $$$$


</details>
</div>

<div class="proposition" markdown="1">

**Proposition:** 

For any closed, piece-wise smooth curve $\gamma$ and $p \notin \gamma$, the index $n(\gamma,p)$ is an integer.

**Proposition:** 

Let $\gamma$ be a closed, piece-wise smooth curve then the index, $n(\gamma, p)$, is continuous with respect to $p$ on $\CC \setminus \gamma$

**Corollary:** 

For any closed, piece-wise smooth curve $\gamma$, $n(\gamma, p)$ is constant on connected components of $\CC \setminus \gamma$

**Corollary:** 

Suppose any curve $\gamma$ lies inside a circle, then $n(\gamma, p) = 0$ for all points outside the same circle.

**Corollary:** 

If $\gamma$ is a circle and $p$ lies inside $\gamma$, then $\vert n(\gamma, p) \vert = 1$

</div>

## 5.5 Cauchy's Integral Formula

<div class="proposition" markdown="1">

**Theorem:** Cauchy's Integral Formula

Suppose $f(z)$ is analytic in a region $\Omega$ and $\gamma$ is any closed curve in the region, then for any $p \notin \gamma$
> $$n(\gamma, p) f(p) = \frac{1}{2 \pi i} \int\limits_{\gamma} \frac{f(z)}{z-p}dz$$ $$$$

In the case that $n(\gamma, p) = 1$ we have the simplified formula
> $$f(p) = \frac{1}{2 \pi i} \int\limits_{\gamma} \frac{f(z)}{z-p}dz$$ $$$$

<div class="proof" markdown="1">

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

We will consider the case where $\Omega$ is an open disk, then the function $F(z) = \frac{f(z) - f(p)}{z-p}$ is analytic for any $z \neq p$ and furthermore, $p$ is a removeable singularity of the function. Indeed,
> $$ \lim_{z \rightarrow p}F(z)(z-p) = \lim_{z \rightarrow p} f(z) - f(p) = 0$$ $$$$

Hence, $F(z)$ satisfies Cauchy's theorem in a disk, i.e. for any closed curve $\gamma$ in $\Omega$
> $$ \int\limits_{\gamma} \frac{f(z) - f(p)}{z-p} dz = 0$$ $$ \; \iff \;$$ $$\int\limits_{\gamma} \frac{f(z)}{z-p} dz = \int\limits_{\gamma} \frac{f(p)}{z-p} dz$$

Where $\frac{1}{2 \pi i} \int\limits_{\gamma} \frac{dz}{z-p}$ is exactly the index $n(\gamma, p)$
</details>
</div>
</div>

<div class="example" markdown="1">

**Example:** Compute the integral $\int\limits_{\gamma} \frac{z}{(11-z^2)(z+2i)} dz$ where $\gamma$ is the positively oriented circle $\vert z \vert = 3$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

The point $z_0 = -2i$ is the only singular point of the integrand lying inside $\gamma$. Indeed, the map $f(z) = \frac{z}{11-z^2}$ is analytic at all points inside $\gamma$ and $n(\gamma,-2i) = 1$
> $$\int\limits_{\gamma} \frac{z}{(11-z^2)(z+2i)} dz = \int\limits_{\gamma} \frac{\frac{z}{(11-z^2)}}{(z+2i)} dz = 2 \pi i n(\gamma,-2i)f(-2i) = 2 \pi i \frac{-2i}{11 + 4} = \frac{4 \pi}{15}$$
</details>
</div>