---
layout: post
title: 'Complex Functions'
---

## X.1 The Complex Function

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