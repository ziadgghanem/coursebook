---
layout: post
title: 'Complex Differentiation'
---

Recall that a real valued function $f: \mathbb{R} \rightarrow \mathbb{R}$ is said to be differentiable at $x_0 \in \mathbb{R}$ if there exists $f'(x_0) \in \mathbb{R}$ such that 
> $f'(x_0) = \lim_{x \rightarrow x_0} \frac{f(x) - f(x_0)}{x - x_0}$ 

Similarly $f: \CC \rightarrow \CC$ is complex differentiable at $z_0 \in \CC$ if there exists $f'(z_0) \in CC$ such that 
> $f'(z_0) = \lim_{x \rightarrow x_0} \frac{f(z) - f(z_0)}{z - z_0}$

We might equivalently express the derivative as $f'(z_0) = \lim_{\Delta z \rightarrow 0} \frac{\Delta f}{\Delta z}$ where $\Delta z = z - z_0 = \Delta x + i \Delta y$ and $\Delta f = f(z) - f(z_0) = f(z) - f(z_0 + \Delta z)$

<div class="example" markdown="1">

**Example:** Investigate the complex-differentiability of $f(z) = \overline{z}$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>


Let $z = x + iy$ and $z_0 = x_0 + iy_0$ and consider the difference quotient
> $\frac{\Delta f}{\Delta z} = \frac{f(z) - f(z + \Delta z)}{\Delta z} = \frac{\overline{z} - \overline{z + \Delta z}{\Delta z} = \frac{\overline{\Delta z}}{\Delta{z}} = \frac{\Delta x - i \Delta y}{\Delta x + i \Delta y}$

The increment $\Delta z$ may tend to zero in any direction and for the derivative to exist this limit must be independent of path. 

In particular, let $\Delta y = 0$ then $\lim_{\Delta z \rightarrow 0} \frac{\Delta f}{\Delta z} = lim_{\Delta z \rightarrow 0} \frac{\Delta x}{\Delta x} = 1$

Next, let $\Delta x = 0$ then $\lim_{\Delta z \rightarrow 0} \frac{\Delta f}{\Delta z} = lim_{\Delta z \rightarrow 0} \frac{- \Delta y}{\Delta y} = -1$

Therefore $f(z)$ is nowhere differentiable
<details>


</div>

<div class="proposition" markdown="1">

**Proposition:** Properties of the complex derivative

Let $f(z),g(z)$ be differentiable and $c \in \CC$
1. $(c)' = 0$ $$
2. $(c f(z))' = c f'(z)$ $$
3. $(f(z) \pm g(z))' = f'(z) \pm g'(z)$ $$
4. $(f(z)g(z))' = f'(z)g(z) + f(z)g'(z)$ $$
5. $ (\frac{f(z)}{g(z)})' = \frac{f'(z)g(z) - f(z)g'(z)}{g^2(z)}$ $$

</div>


<div class="proposition" markdown="1">

**Proposition:** Chain rule

If $f(z)$ is differentiable at $z_0$ and $g(z)$ is differentiable at $f(z_0)$ then
> $(g(f(z_0)))' = g'(f(z_0))f'(z_0)$

</div>

### The Cauchy Riemann Equations

A complex function, $f(z) = u(x,y) + iv(x,y)$, is said to satisfy the Cauchy Riemann equations if the following relations are satsified on the partial derivatives of $u$ and $v$
$$\left. \begin{array}{cc}
        u_x = v_y \\
        u_y = -v_x
    \end{array} \right\}$$


<div class="proposition" markdown="1">

**Theorem:** Condition for differentiablity

The function $f(z) = u(x,y) + iv(x,y)$ is complex differentiable at a point $z_0 = x_0 + iy_0$ if and only if its real-valued component functions $u(x,y),v(x,y)$ are differentiable at $(x_0,y_0)$ and satisfy the Cauchy Riemann equations there.
</div>

If $f(z) = u(x,y) + iv(x,y)$ is complex differentiable at a point $z_0$ then the derivative can be presented as
> $f'(z) = \frac{\partial u}{\partial x} + i  \frac{\partial v}{\partial x}$

<div class="example" markdown="1">

**Example:** Investigate the complex-differentiability of $f(z) = \overline{z}$ using the CRE.

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

Our function has the following decomposition into real and imaginary parts 
> $f(z) = (u(x,y),v(x,y)) = (x, -y)$

Checking the partial derivatives
- $u_x = \frac{\partial}{\partial x} x = 1$
- $u_y = \frac{\partial}{\partial y} x = 0$
- $v_x = \frac{\partial}{\partial x} y = 0$
- $v_y = \frac{\partial}{\partial y} -y = -1$

We find that $u_x$ and $v_y$ do not coincide at any point on the complex plane and therefore $f(z)$ is nowhere differentiable, as we found earlier.

<details>

**Example:** Investigate the complex-differentiability of $f(z) = z^2$ using the CRE.

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

Our function has the following decomposition into real and imaginary parts 
> $f(z) = (x+iy)^2 = (u(x,y),v(x,y))= (x^2 - y^2, 2xy)$

Checking the partial derivatives
- $u_x = \frac{\partial}{\partial x} x^2 - y^2 = 2x$
- $u_y = \frac{\partial}{\partial y} x^2 - y^2 = -2y$
- $v_x = \frac{\partial}{\partial x} 2xy = 2y$
- $v_y = \frac{\partial}{\partial y} 2xy = 2x$

Such that $u_x = v_y$ and $u_y = - v_x$ for all points $z = (x,y)$ and therefore $f(z)$ is differentiable on the whole complex plane with derivative
> $f'(z) = 2x + i2y = 2z$

<details>
</div>

### Geometrical Interpretation of the Cauchy Riemann Equations

Let $u: \mathbb{R^2} \rightarrow \mathbb{R}$ be a function, the level set $[u = c]$ is the set of all points $(x,y)$ such that $u(x,y) = c$. When $T$ is differentiable, the gradient vector $\Delta u = (\frac{\partial u}{\partial x},\frac{\partial u}{\partial y}) $ is perpendicular to the level sets $[u = c]$.

Given two functions real-valued functions $u(x,y)$, $v(x,y)$ satisfying the CRE we have
$\Delta v = (\frac{\partial v}{\partial x},\frac{\partial v}{\partial y}) = (- \frac{\partial u}{\partial y},\frac{\partial u}{\partial x})$ such that $\Delta v$ and $\Delta u$ are orthogonal, i.e. such that
> $\Delta v \cdot \Delta u = 0$

<div class="proposition" markdown="1">

**Theorem:** Level sets and the CRE

If a function $f(z) = (u(x,y),v(x,y))$ satisfies the Cauchy Riemann Equations then at each point of intersection, the level sets of $u$ and $v$ interesct orthogonally.

</div>

## Analyticity

<div class="definition" markdown="1">

**Definition:** Analytic Functions

A complex function $f(z)$ is said to be analytic (or holomorphic) at a point $z_0 \in CC$ if it is complex-differentiable in a neighborhood of $z_0$

We say that $f(z)$ is analytic at $\infty$ if the function $g(z) = f(\frac{1}{z})$ is analytic at $z=0$

If $f(z)$ is complex differentiable at all points in a region $\Omega$ it is said to be analytic in $\Omega$.

Points of nonanalyticity are called singular points.
</div>

<div class="proposition" markdown="1">

**Lemma:** Analyticity in a region

If the Cauchy Riemann equations are not satisfied at every point in a domain $\Omega$ then a function cannot be analytic in $\Omega$.
</div>

<div class="definition" markdown="1">

**Definition:** Harmonic Functions

Let $u : \Omega \rightarrow \mathbb{R}$ have continuous second partial derivatives in a region $\Omega \subset \CC$ then it is said to be harmonic if it satisfies the Laplace equation
> $\Delta u = \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0$
</div>

<div class="proposition" markdown="1">

**Proposition:** 

$f(z) = u(x,y) + iv(x,y)$ is analytic if and only if both $u$ and $v$ are harmonic.

If two harmonic functions form the real and imaginary parts of a complex function then they are said to be harmonic conjugates.

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

<div class="proposition" markdown="1">

If $f(z) = u(x,y) + iv(x,y)$ is analytic in a region $\Omega \subset \CC$ then it satisfies the Cauchy Riemann equations there $u_x = v_y, u_y = v_x$ such that 
> $\Delta u = u_{xx} + u_{yy} = v_{xy} - v_{yx} = 0$

Similarly $\Delta v = 0$
</div>
<details>

</div>

### Restoring an analytic function from harmonic conjugate

Suppose a harmonic function $u(x,y)$ is given, it is possible to construct the analytic function whose real part is $u(x,y)$ by finding its harmonic conjugate using the relations guaranteed by the Cauchy Riemann equations
- $u_x = v_y \; \implies \; v = \int u_x dy + a(x) + C_1$
- $u_y = -v_x \; \implies \; v = \int -u_y dx + b(y) + C_2$

Comparing the two expression the unkowns, $a(x),b(y),C_1,C_2$ can be determined and 
> $f(z) = u(x,y) + iv(x,y) + Ci$

<div class="example" markdown="1">

**Example:** Given $u(x,y) = e^x \cos y$, first confirm that the function is harmonic and then find its harmonic conjugate $v(x,y)$ such that $f(z) = u(x,y) + iv(x,y)$ is an analytic function.

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

We first check that $u$ satisfies Laplace's equation
- $u_x = e^x \cos y, \; u_{xx} = e^x \cos y$
- $u_y = -e^x \sin y, \' u_{yy} = -e^x \cos y$

And by observation $u_{xx} + u_{yy} = 0$. Now in order to find $v(x,y)$ we make use of the fact that $u_x = v_y, u_y = -v_x$ 
> $v = \int u_x dy + a(x) + C_1 = \int e^x \cos y dy + a(x) + C_1 = e^x \sin y + a(x) + C_1$
> $v = \int -u_y dx + b(y) + C_2 = \int e^x \sin y dx + b(y) + C_2 = e^x \sin y + b(y) + C_2$

We determine that $a(x),b(y) \equiv 0$ such that 
> $f(z) = e^x (\cos y + i \sin y) + iC = e^{x + iy} + iC = e^z + iC$

<details>

**Example:** Given $v(x,y) = x^3 + 6x^2y - 3xy^2 - 2y^3$, first confirm that the function is harmonic and then find its harmonic conjugate $u(x,y)$ such that $f(z) = u(x,y) + iv(x,y)$ is an analytic function.

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

We first check that $u$ satisfies Laplace's equation
- $v_x = 3x^2 + 12xy - 3y^2, \; v_{xx} = 6x + 12y$
- $v_y = 6x^2 - 6xy - 6y^2, \' v_{yy} = -6x - 12y $

And by observation $v_{xx} + v_{yy} = 0$. Now in order to find $u(x,y)$ we make use of the fact that $u_x = v_y, u_y = -v_x$ 
> $u = \int -v_x dy + a(x) + C_1 = \int -3x^2 - 12xy + 3y^2dy + a(x) + C_1 = -3x^2y -6xy^2 + y^3 + a(x) + C_1$
> $u = \int v_y dx + b(y) + C_2 = \int 6x^2 - 6xy - 6y^2 dx + b(y) + C_2 = 2x^3 - 3x^2y - 6y^2x + b(y) + C_2$

We determine that $a(x) = 2x^3$ and $b(y) = y^3$  such that 
> $f(z) = 2x^3 + y^3 + -3x^2y - 6xy^2 + C + i(x^3 + 6x^2y - 3xy^2 - 2y^3)$



<details>


</div>
