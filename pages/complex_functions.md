---
layout: post
title: 'Complex Functions'
---

## 2.1 The Complex Function

<div class="definition" markdown="1">

**Definition:** Complex Function

Given a subset of the complex plane $M \subset \CC$ a map $f: M \rightarrow \CC$ is called a complex function if it is injective, i.e. if it associates to each $z \in M$ exactly one $f(z) \in \CC$
</div>

Every complex function $f(z)$ has two components, $(u(x,y),v(x,y))$ respectively called the real and imaginary parts of $f$, each a real valued function of two variables
> $$f(z) = u(x,y) + iv(x,y),$$ $$z = x + iy$$

<div class="example" markdown="1">

**Example:** Find the real and imaginary parts of the function $f(z) = i z - \overline{z}$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

For $z = x + iy$ we have
> $f(z) = i(x + iy)^2 - (x-iy) = i(x^2 - y^2 + i2xy) - (x - iy)$ 
> $ \quad \quad = ix^2 - iy^2 - 2xy - x + iy = -x - 2xy + i(x^2 - y^2 + y)$
</details>
</div>

If $f(z)$ is a complex function, then its image is a curve on the complex plane. Unlike a real-valued functions of a single real variable which may be graphed in the Cartesian plane, the graph of a complex function lies in four-dimensional space. 

In order to present the image of a complex function $\omega = f(z)$ we must use two copies of the complex plane.  

<div class="definition" markdown="1">

**Definition:** Fixed Point

$z_0 \in M$ is called a fixed point of the complex function $f: M \rightarrow \CC$ if $f(z_0) = z_0$
</div>

## 2.2 Limits and Continuity

The complex numbers have the structure of a metric space $(\CC, d)$ where $d: \CC \times \CC \rightarrow \mathbb{R}$ is the metric induced by the modulus
> $d(z_1,z_2) = \vert z_1 - z_2 \vert$

<div class="definition" markdown="1">

**Definition:** Limit Point

Let $f(z)$ be a function defined on some neighborhood of $z_0 \in \CC$, we say that $w_0$ is the limit of $f(z)$ as $z$ tends to $z_0$, i.e. $\lim_{z \rightarrow z_0} f(z) = w_0$, if 
> $\forall_{\epsilon > 0} \exists_{\delta > 0} \; \vert z - z_0 \vert < \delta \; \implies \; \vert f(z) - w_0 \vert < \epsilon$

In the case that $z_0 = \infty$ we write that $\lim_{z \rightarrow \infty} f(z) = w_0$ if
> $\forall_{\epsilon > 0} \exists_{\delta > 0} \; \vert z \vert > \delta \; \implies \; \vert f(z) - w_0 \vert < \epsilon$
</div>


<div class="proposition" markdown="1">

**Proposition:** 

Suppose $\lim_{z \rightarrow \infty} f(z) = w_0$ then
1. $\lim_{z \rightarrow \infty} \overline{f(z)} = \overline{w_0}$
2. $\lim_{z \rightarrow \infty} \vert f(z) \vert = \vert w_0 \vert$

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

<div class="proof" markdown="1">

Suppose $\forall_{\epsilon > 0} \exists_{\delta > 0} \; \vert z - z_0 \vert < \delta \; \implies \; \vert f(z) - w_0 \vert < \epsilon$

**(1.)** For $\vert z - z_0 \vert < \delta$ we have
> $\vert f(z) - w_0 \vert = \vert \overline{f(z) - w_0} \vert = \vert \overline{f(z)} - \overline{w_0} \vert < \epsilon$

**(2.)** For $\vert z - z_0 \vert < \delta$ we have
> $\vert \vert (z) \vert - \vert w_0 \vert \vert \leq \vert f(z) - w_0 \vert < \epsilon$

</details>
</div>

</div>

<div class="example" markdown="1">

**Example:** Does the limit $\lim_{z \rightarrow 0} \frac{\overline{z}}{z}$ exist?

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

Set $z = x$ then 
> $\lim_{z \rightarrow 0} \frac{\overline{z}}{z} = \lim_{x \rightarrow 0} \frac{x}{x} = 1$

Set $z = iy$ then
> $\lim_{z \rightarrow 0} \frac{\overline{z}}{z} = \lim_{y \rightarrow 0} \frac{-iy}{iy} = -1$

Therefore, the limit does not exist.

</details>
</div>

<div class="definition" markdown="1">

**Definition:** Continuity

We say that $f(z)$ is continuous at $z_0 \in \CC$ if $f(z_0)$ is defined and $\lim_{z \rightarrow z_0}f(z) = f(z_0)$

If $f(z)$ is continuous at every point in a region $\Omega$ then $f(z)$ is said to be continuous in $\Omega$.
</div>

## 2.3 Elementary Maps


<div class="definition" markdown="1">

**Definition:** Translation

A translation transformation has the following general form
> $T(z) = A + z$

$T(z)$ translates every point by a complex constant $A \in \CC$
</div>

<div class="definition" markdown="1">

**Definition:** Rotation

A rotation transformation has the following general form
> $R(z) = e^{i \alpha}z$

$R(z)$ rotates every point by through an angle $\alpha \in \mathbb{R}$
</div>

<div class="definition" markdown="1">

**Definition:** Dilation

A dilation transformation has the following general form
> $D(z) = az$

$D(z)$ dilates the magnitude of every point by a factor of the real constant $a \in \mathbb{R}$
</div>

<div class="definition" markdown="1">

**Definition:** Linear Function

A linear transformation has the following general form, for complex constants $A,B \in CC$
> $L(z) = A + Bz$

Every linear transformation, $L(z)$, is a composition of translation, rotation, and dilation transformations.
</div>

<div class="definition" markdown="1">

**Definition:** Reciprocal Function

The reciprocal function is defined
> $r(z) = \frac{1}{z}$

</div>

<div class="proposition" markdown="1">

**Lemma:** 

The reciprocal function maps the circle $\vert z \vert = k$ onto the circle $\vert w \vert = \frac{1}{k}$

**Lemma:** 

The reciprocal function maps lines onto circles and circles onto circles.

</div>

## 2.4 The Fractional Linear Transformation

<div class="definition" markdown="1">

**Definition:** Fractional Linear Transformation

If $a,b,c,d$ are complex constants with $ad - bc \neq 0$ then the following transformation is called a fractional linear transformation
> $T(z) = \frac{az + b}{cz + d}$

</div>

<div class="proposition" markdown="1">

**Proposition:** 

Fractional linear transformations form a group with respect to composition.

</div>

A fractional linear transformation $T(z) = \frac{az + b}{cz + d}$ has continuous extension to the extended complex plane
> $\lim_{z \rightarrow \infty} T(z) = \frac{a}{c}, \quad \lim_{z \rightarrow \frac{-d}{c}} T(z) = \infty$

i.e. $T(z)$ maps $\infty$ to $\frac{a}{c}$ and $\frac{-d}{c}$ to $\infty$.

<div class="proposition" markdown="1">

**Proposition:** 

Let $z_1,z_2,z_3 \in \CC$ be distinct, then there exists a unique fractional linear transformation mapping these points to $0,1,\infty$ (respectively) given by
> $T(z) = \frac{z-z_1}{z_1 - z_2} \frac{z_2 - z_3}{z_3 - z}$
</div>

<div class="definition" markdown="1">

**Definition:** The Cross Ratio

The cross ratio of the four distinct points $z_1,z_2,z_3,z_4$ is defined
> $(z_1,z_2,z_3,z_4) := \frac{z_1-z_2}{z_2 - z_3} \frac{z_3 - z_4}{z_4 - z_1}$
</div>

<div class="proposition" markdown="1">

**Proposition:** 

For distinct $z_1,z_2,z_3 \in \CC$ there exists a unique fractional linear transformation, $L(z)$ mapping these points to $w_1,w_2,w_3 \in \CC$ respectively. Such a transformation can always be found by resolving the equality
> $(L(z),w_1,w_2,w_3) = (z,z_1,z_2,z_3)$
</div>

<div class="proposition" markdown="1">

**Theorem:** 

The cross ratio is invariant under fractional linear transformation, i.e. let  $z_1,z_2,z_3,z_4 \in \CC$ be distince and $T(z)$ any fractional linear transformation then
> $$(L(z_1),L(z_2),L(z_3),L(z_4)) = (z_1,z_2,z_3,z_4)$
</div>