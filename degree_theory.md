---
layout: post
title: 'Planar Degree Theory'
---

<blockquote>
        What is, is what must be.
        <footer>Leibniz</footer>
</blockquote>

<hr>

## 0. Degree Theory in $\mathbb{R}^1$

### Motivation
We will begin this exposition into degree theory with a recolection of the _intermediate value thorem,_ and a skech of its famous proof by Cauchy.

<div class="proposition" markdown="1">

**Theorem: The Intermediate Value Theorem**

Let $f(x)$ be a continuous function defined on an interval $[a,b]$ with $f(a),f(b)$ having different signs. The IVT guarantees the existence of some point $c \in [a,b]$ such that $f(c) = 0.$
</div>

<div class="proof" markdown="1">
Without loss of generality, we assume $f(a)$ is negative and $f(b)$ positive. You may be familiar with the bisection method: we set $a_0 = a, \; b_0 = b$ and consider the sign of the function at the midpoint of our interval $\frac{b_0-a_0}{2}.$ If $f(\frac{b_0-a_0}{2}) = 0,$ we have found the promised root so instead we assume $f(\frac{b_0-a_0}{2}) \neq 0.$ If $f(\frac{b_0-a_0}{2})<0$ we set $a_1 := \frac{b_0-a_0}{2},$ $b_1:= b_0$ if, on the otherhand, $f(\frac{b_0-a_0}{2})>0$ we set $a_1 = a_0$ $b_1:= \frac{b_0-a_0}{2}$ the process is then repeated for the interval $[a_1,b_1].$ Such an algorithm will generate a monotonically increasing sequence $a_0,a_1,a_2,\ldots$ at which our function is negative, and a monotonically decreasing sequence $b_0,b_1,b_2,\ldots$ at which our function is positive. The difference of our sequences, $\vert a_n - b_n \vert,$ goes to zero and hence must have a common limit $\lim_{n \rightarrow \infty} a_n = \lim_{n \rightarrow \infty} b_n = c$ and as our function is continuous, the sequences $f(a_n)$ and $f(b_n)$ must also have a common limit $f(c).$ Finally, as $f(a_n),$ $f(b_n)$ are respectively non-positive and non-negative, they can only converge to zero. Hence, for some $c \in [a,b]$ we have $f(c) = 0.$
</div>

This simple argumentation on the existence of a solution for the equation $f(x) = 0$ is the motivation of the entire field of degree theory.

### In which we formulate the most simple degree theory.

Take $\Omega \subset \mathbb{R}^1$ a bounded open set. 
For the sake of simplicity we assume $\Omega$ is a finite disjoint union of open intervals.
<label for="open_sets" class="margin-toggle">&#8853;</label><input type="checkbox" id="open_sets" class="margin-toggle"/><span class="marginnote">We know that open sets in $\mathbb{R}^1$ are characterized as (at most) countable union of disjoint open intervals.</span> 

Consider a map $f: \bar{\Omega} \rightarrow \mathbb{R}$ with $f(t) \neq 0$ $\forall t \in \partial \Omega.$ 

We will call the pair $(f,\Omega)$ admissible. That is, an admissible pair consists of an open set $\Omega$ and a map $f: \bar{\Omega} \rightarrow \mathbb{R}$ that does not vanish on its boundary.

Denote by $M(\mathbb{R}^1)$ the collection of all admissible pairs.

The formulation of a degree theory on $\mathbb{R}^1$ involves the construction of a map
> $$deg: M(\mathbb{R}^1) \rightarrow \mathbb{Z}$$

satisfying reasonable properties.

<div class="definition" markdown="1">

**Reasonable Properties of a Degree**

Let $\Omega$ be an open, non-empty, bounded subset of $\mathbb{R}^1$

- _Additivity_: For subsets $\Omega_1, \Omega_2 \subset \Omega$ with
    1. Empty intersection: $$\Omega_1 \cap \Omega_2 = \emptyset $$
    2. Containing all zeros of $$f$$: $$ f^{-1}(0) \subset \Omega_1 \cup \Omega_2$$
- then $deg(f,\Omega) = deg(f,\Omega_1) + deg(f,\Omega_2)$

<hr>

<div class="definition" markdown="1">

**Definition: Homotopy**

Let $h: [0,1] \times \bar{\Omega} \rightarrow \mathbb{R}$ be a continuous map such that $\forall \lambda \in [0,1]$ $h_{\lambda}: \bar{\Omega} \rightarrow \mathbb{R}$ is $\Omega-$ admissible. Then, we say that $h$ is an admissible homotopy joining $h_0$ and $h_1$
</div>

- _Homotopy_: For any $\Omega-$ admissible homotopy $h(\lambda, t)$ we have
    > $$deg(h(\lambda, \cdot),\Omega) =$$ constant.
i.e. the degree of of an $\Omega-$ admissible homotopy is independent of $\lambda \in [0,1]$

<hr>

- _Normalization_: Consider the map $f(t) = t - t_0$ with $t\in \Omega$ and $t_0$ arbitrary, then
    > $$deg(f,\Omega) = x = \begin{cases} 1, \quad t_0 \in \Omega \\ 0, \quad t_0 \notin \Omega \end{cases}$$ 

<hr>

- _Existence_: For any admissible pair $(f,\Omega),$ if $deg(f,\Omega) \neq 0$ then $\exists p \in \Omega$ such that $f(c) = 0$

</div>

With these reasonable properties of a degree theory in mind, we are ready to explicitly define the degree function in $\mathbb{R}^1.$

<div class="definition" markdown="1">

**Degree in $\mathbb{R}^1.$**

Let $(f,(a,b)) \in M(\mathbb{R}^1),$ then, 
> $$deg(f,(a,b)) = \begin{cases} \, 1, \qquad \text{if} \; f(a)<0 \; \text{and} \; f(b)>0 \\ -1, \qquad \text{if} \; f(a)>0 \; \text{and} \; f(b)<0 \\ \, 0, \qquad \text{otherwise} \end{cases}$$ 

</div>

For $\Omega = \bigcup_{i=1}^{n} (a_i,b_i)$ with $(a_i,b_i) \cap (a_j,b_j) = \emptyset$ for $i \neq j$ and $f: \bar{\Omega} \rightarrow \mathbb{R}$ $\Omega-$ admissible,
> $$deg(f,\Omega) = \sum_{i=1}^{n} deg(f, (a_i,b_i))$$

So far we have only considered sets consisting of the finite union of disjoint open intervals, we would like to extend our degree theory to the countable union of disjoint open intervals

<div class="proposition" markdown="1">

**<u>Theorem:</u>**

Suppose $\Omega = \bigcup_{i=1}^{\infty} (a_i,b_i),$ a countable union of disjoint open intervals with $f: \bar{\Omega} \rightarrow \mathbb{R}$ $\Omega-$ admissible.
> $$deg(f,\Omega) = \sum_{i=1}^{\infty} deg(f, (a_i,b_i))$$

</div>

<div class="proof" markdown="1">

We will show that this definition is well-defined, i.e. that the sum is always finite which in turn is equivalent to the claim that all but finitely many of the terms are zero. 

It is necessary to recall a result from analysis: in a metric space, the condition of compactness is equivalent to that of sequential compactness. In particular, a set $K \in \mathbb{R}$ is compact iff every sequence of points $\{ x_n \} \subset K$ has a convergent subsequence $ \{ x_{n_k} \}$ with $\lim_{k \rightarrow \infty} \in K.$ 
</div>

<div class="example" markdown="1">

**Proposition:** Any polynomial $p: \mathbb{R} \rightarrow \mathbb{R}$ of an odd degree has at least one real root.

*Proof:* Take $p(t) = a_0 + a_1 t + \cdots + a_n t^n,$ with $n$ odd and $a_n \neq 0.$ Then on a sufficiently large ball, $p$ is admissibly homotopic to the leading term $a_n t^n$ such that
> $$ \begin{cases} \text{if} \; a_n > 0 \qquad \text{then} deg(p) = deg(a_n t^n) = 1 \\ \text{if} \; a_n < 0 \qquad \text{then} deg(p) = deg(a_n t^n) = -1 \end{cases} $$

In either case, the degree is different then zero and the existence property guarentees a solution to the equation $p(t) = 0.$

</div>

## 1. Degree in $\mathbb{R}^2$

### 1.1 Vector Fields

<div class="definition" markdown="1">

**Definition(Planar Vector Field):**

Let $\Omega \subset \mathbb{R}^2$ be a set such that for every point $p \in \Omega$ we associate a vector $\Phi(p) \in \mathbb{R}^2.$

We call the map $\Phi: \Omega \rightarrow \mathbb{R}^2$ a vector field over $\Omega$
</div>

Any planar vector field $\Phi: \Omega \rightarrow \mathbb{R}^2$ is specified by two _component functions,_ which are real-valued functions $\phi, \psi: \Omega \rightarrow \mathbb{R}$ such that
> $$\Phi(p) = [\phi(p), \psi(p)]$$

<div class="example" markdown="1">

**Example: Complex Function as Vector Field**

Consider the complex function $f: \mathbb{C} \rightarrow \mathbb{C}$
> $$f(z) = z^2$$

Let $z = x+iy,$ then $f(z) = (x+iy)^2 = x^2 - y^2 + i2xy$ such that $f$ is specified by component functions
>  $$f(z) = \begin{pmatrix} x^2 - y^2 \\\ 2xy \end{pmatrix}$$

</div>

Indeed, any complex function $f: \mathbb{C} \rightarrow \mathbb{C}$
can be decomposed into real and imaginary component functions
> $$f(z) = f(x+iy) = u(x,y) + iv(x,y) = {u(x,y), v(x,y)}$$

And so, complex functions are naturally expressed as vector fields.

<div class="example" markdown="1">

**Example: Differential System as Vector Field**
Consider the differential system
> $$\begin{cases} \dot{x} = P(x,y) \\ \dot{y} = Q(x,y) \end{cases}$$

Then, $\Phi = (P,Q)$ is a vector field. In fact, such a system is often called a velocity field.

</div>

To describe a vector field as continuous, smooth, differrentiable is equivalent to describing each of its component vectors as respectively continuous, smooth, differrentiable functions.

<div class="example" markdown="1">

**Examples: Tangent Field, Fields of Normals**

Consider the unit circle $x^2 + y^2 = 1$ and define the tangent field 
> $$\tau(x,y) = (-y,x)$$

 <figure>
          <label for="figure-1" class="margin-toggle">&#8853;</label><input type="checkbox" id="figure-1" class="margin-toggle"/><span class="marginnote">We call $\tau$ the *tangent field* as $\left< \tau, \mathbb{1} \right> = (-y,x) \cdot (x,y)^{T} = -yx + xy = 0$.</span>
          <img src="img/tangent_field.png" alt="Sketch of Tangent Field" />
</figure>

Alternatively consider the field of external normals
> $$\eta(x,y) = (x,y)$$

 <figure>
          <label for="figure-2" class="margin-toggle">&#8853;</label><input type="checkbox" id="figure-2" class="margin-toggle"/><span class="marginnote">In other settings this is also known as the identity vector field, for the obvious reason.</span>
          <img src="img/external_normal.png" alt="Sketch of external normals" />
</figure>

Finally we consider the field of internal normals
> $$\omega(x,y) = (-x,-y)$$

 <figure>
          <label for="figure-3" class="margin-toggle">&#8853;</label><input type="checkbox" id="figure-3" class="margin-toggle"/><span class="marginnote">At every point on the circle $\omega$ assumes an internal normal.</span>
          <img src="img/external_normal.png" alt="Sketch of internal normals" />
</figure>

</div>

### 1.2 Curves

<div class="definition" markdown="1">

**<u>Definition(Planar Curve):</u>**

A piecewise-smooth map $\Gamma:[a,b] \rightarrow \mathbb{R}^2$ is called a curve.

A planar curve if given once two component functions are specified
> $$\Gamma(t) = \begin{pmatrix} x(t) \\\ y(t) \end{pmatrix}$$

</div>

The image of a curve will be called its trajectory. We define the *reparametrization* of a curve $\Gamma$ to be its composition with any continuous map $\gamma:[0,1] \rightarrow [0,1]$ with $\gamma(0) = 0$ and $\gamma(1) = 1$. It is clear that all parameterizations of a curve share the same trajectory.

A curve, $\Gamma:[a,b] \rightarrow \mathbb{R}^2$, is called **closed** if it begins and ends at the ssame place, i.e., $\Gamma(a) = \Gamma(b)$

We say that $\Gamma$ is **simple** if it does not intersect itself, that is if $\Gamma$ is injective over $(a,b).$ Precisely, $\Gamma$ is **simple** iff $\Gamma(s) \neq \Gamma(t)$ for all $s,t \in (a,b)$ with $s \neq t$

A simple closed planar curve, $\Gamma$ is called a Jordan curve. It's namesake, The Jordan Curve Theorem, asserts that $\Gamma$ divides the plane into two connected components, one bounded by the curve and one unbounded. For our purposes we will assume that all closed curves are also simple and without further reference to the JCT we will denote the planar region bounded by $\Gamma$ as $\Omega.$

A Curve has an *orientation* which describes a rule for which one of two directions to travel along its trajectory. By convention, a closed curve has positive orientation if its interior region is to the left of a path along its trajectory. Otherwise, the orientation is negative.

We may define a vector field $\Phi(x,y) = [\phi(x,y), \psi(x,y)]$ over a region $\Omega$ bounded by some curve $\Gamma.$ It will be necessary to consider the field

A vector field, $\Phi(x,y) = [\phi(x,y), \psi(x,y)],$ may be defined over a curve $\Gamma(t) = [x(t),y(t)].$ In which case the vector field is also paramaterized by the variable $t \in [a,b]$ and can be expressed as a vector function:
> $$\Phi(t) = \begin{pmatrix} \phi(x(t),y(t)) \\\ \psi(x(t),y(t)) \end{pmatrix}$$

### Angular Function

Let $\Phi: [a,b] \rightarrow \mathbb{R}^2$ be the continuous vector function associated with a vector field $\Phi$ defined over some curve $\Gamma.$ Assume that $\Phi$ is nonzero on $\Gamma$ i.e. asumme that $\Phi(t) \neq 0$ $\forall t \in [a,b].$
<label for="nonzero_vectors" class="margin-toggle">&#8853;</label><input type="checkbox" id="nonzero_vectors" class="margin-toggle"/><span class="marginnote">The angle between a vector and the zero vector is, of course, not defined.</span> 
Then, we introduce the map $\angle: [a,b] \rightarrow \mathbb{R}$ which returns the angle between $\Phi(a)$ and $\Phi(t)$ in radians. 
<label for="angular_function" class="margin-toggle">&#8853;</label><input type="checkbox" id="angular_function" class="margin-toggle"/><span class="marginnote">The map, $\angle,$ is multivalued $\angle(t) = \angle(t) + 2 \pi = \angle(t) + 4 \pi \cdots$.</span> 
We define the **angular function**, $\theta : [a,b] \rightarrow [0,2 \pi]$ as the continuous branch of $\angle(t)$


<div class="example" markdown="1">

**Examples: Angular Function of Vector Fields**

Consider the curve with a trajectory of the upper-half unit circle parameterized by
> $$\Gamma(t) = \begin{pmatrix} x(t) \\\ y(t) \end{pmatrix} = \begin{pmatrix} \cos(t) \\\ \sin(t) \end{pmatrix}$$ $$ \quad t \in [0, \pi]$$

<hr style="margin: auto;" />

**(1)** Take the identity vector field 
> $$ \Phi(x,y) = (x,y) $

Over $\Gamma$ we have the following parameterization
> $$ \Phi(t) = (\cos(t),\sin(t))

The angular function of $\Phi$ satisfies the equation
> $$tan(\Theta(t)) = \frac{y(t)}{x(t)} = \frac{\sin(t)}{\cos(t)} = \tan(t)$$

Hence $\Phi$ has angular function
> $$\Theta(t) = t$$
<hr>

**(2)** Take the vector field 
> $$ \Phi(x,y) = (y,-x) $$
    > $$\rightarrow$$

> $$tan(\Theta(t)) = \frac{-\cos(t)}{ \sin(t)} = - \cot(t) = - \tan(\frac{\pi}{2}-t)$$

> $$\rightarrow$$

> $$\Theta(t) = -(\frac{\pi}{2}-t)$$
<hr>

**(3)** Take the complex vector field 
> $$ \Phi(x,y) = (x^2 - y^2,2xy) $$
> $$\rightarrow$$

> $$tan(\Theta(t)) = \frac{2\cos(t) \sin(t)}{\cos^2(t) - \sin^2(t)} = \frac{\sin(2t)}{\cos(2t)} = \tan(2t)$$
> $$\rightarrow$$

> $$\Theta(t) = 2t$$

</div>

**Properties of the Angular Function:** Let $\Phi$ be a planar vector field,
1. Positive scalar multiples of $$\Phi$$ all share the same angular function.
2. Vector fields obtained from $$\Phi$$ through rotating every vector by some fixed angle (less than $\pi$) all share the same angular function.
3. In general, if $$\Phi$$ is defined over different parameterizations of the same curve it will have different angular functions.
    * In fact, if we pass from the parameter of a curve $$t$$ to $$\tau:= -t$$ then $$\Theta(\tau) = - \Theta(t)$$
4. If the vectors $$\Phi(a)$$ and $$\Phi(b)$$ point in the same direction then $$\Theta(b)$$ is a multiple of $$2 \pi$$

### Degree

<div class="definition" markdown="1">

**<u>Definition(Degree of a vector field on a curve):</u>**

Let $\Phi(t) = [\phi(x(t),y(t))), \psi(x(t),y(t))]$ be a vector field defined over the curve $ \Gamma(t) = [x(t),y(t)],$ $t \in [a,b]$ such that $\Phi(t) \neq 0 \forall t$ with angular function, $\Theta(t)$. We define the degree of $\Phi$ on $ \Gamma$ as
> $$ deg(\Phi(t), \Gamma(t)) := \frac{1}{2 \pi} [\Theta(b) - \Theta(a)] = \frac{1}{2 \pi}[\Theta(b)]$$

</div>

**Properties of the Degree:** Let $\Phi$ be a vector field defined over the planar curve $\Gamma$
1. The degree of $\Phi$ on $ \Gamma$ is independent of parameterization so long as the orientation is unchanged.
2. If $$\Gamma = \Gamma_1 \cup \Gamma_2 \cup \cdots \cup \Gamma_n$$ then
    > $$deg(\Phi, \Gamma) = \sum_{i=1}^n deg(\Phi, \Gamma_i)$$
3. If the vectors $$\Phi(a)$$ and $$\Phi(b)$$ point in the same direction then $$deg(\Phi, \Gamma)$$ is an integer.
    > e.g. if $$\Gamma$$ is a closed curve $$\Phi(a)=\Phi(b)$$


<div class="example" markdown="1">

**Examples: Degree of Vector Fields on Planar Curves**

Consider the curve with a trajectory of the upper-half unit circle parameterized by
> $$\Gamma(t) = \begin{pmatrix} x(t) \\\ y(t) \end{pmatrix}$ = \begin{pmatrix} \cos(t) \\\ \sin(t) \end{pmatrix}$$ $$t \in [0, \pi]$$

**(1)** Take the vector field
> $$ \Phi(x,y) = (x,y) t$$

We found already that the pair, $(\Phi, \Gamma),$ has angular function
> $$\Theta(t) = t$$

As $\Phi$ is nonzero on $\Gamma$ we can directly find the degree
> $$deg(\Phi, \Gamma) = \frac{1}{2 \pi}[\pi - 0] = \frac{1}{2}$$

**(2)** Take the vector field
> $$ \Phi(x,y) = (x^2 - y^2,2xy) t$$
    > $$\rightarrow$$
> $$\Theta(t) = 2t$$
> $$ \Phi(t) \neq 0 \, \forall t \in [0, \pi]$$
    > $$\rightarrow$$
> $$ deg(\Phi, \Gamma) = \frac{1}{2 \pi} [2 \pi - 0] = 1$$
</div>

### The Poincare Formula

We will derive the Poincare formula on a smooth curve 
> $$\Gamma(t) = \begin{cases} x = x(t) \\ y = y(t) \end{cases}$$ 

for a continuously differentiable vector field
> $$\Phi(x,y) = \begin{pmatrix} \phi(x,y) \\\ \psi(x,y) \end{pmatrix}$$

such that the component functions $\phi(x(t),y(t)),$ $\phi(x(t),y(t))$ are also continuously differentiable. Let $\Theta(t)$ be the angular function of the pair $(\Phi, \Gamma),$ then:
> $$ d \Theta = d(arctan(\frac{\psi}{\phi})) = \frac{1}{1 + (\frac{\psi}{\phi})^2} \frac{\phi d \psi - \psi d \phi}{\phi^2}= \frac{\phi d \psi - \psi d \phi}{\phi^2 + \psi^2} $$  

It follows that
> $$ deg(\Phi, \Gamma)= \frac{1}{2 \pi} [ \Theta(b) - \Theta(a) ] = \frac{1}{2 \pi} \int_a^b \frac{\phi(t) \psi'(t) - \psi(t)  \phi'(t)}{\phi^2(t) + \psi^2(t)} dt$$

<div class="example" markdown="1">

**Example: Degree of Vector Fields on Planar Curve Using Poincare Formula**

Consider the curve with trajectory of the unit circle parameterized as follows
> $$\Gamma(t): \begin{cases} x(t) = \cos(t) \\  y(t) = \sin(t) \end{cases}$$ $$ \; 0 \leq t \leq 2 \pi $$

Define the vector field induced by the complex function $f(z) = z^2$
> $$\Phi(x,y) = \begin{pmatrix} x^2-y^2 \\\ 2xy \end{pmatrix}$$

Which, on $\Gamma,$ is parameterized by $t \in [0, 2 \pi]$ 
> $$\Phi(t) = \begin{pmatrix} \cos^2(t) - \sin^2(t) \\\ 2 \cos(t) \sin(t) \end{pmatrix}$$

Using the trigonometric identities $\cos^2(t) - \sin^2(t) = \cos(2t)$ and $2 \cos(t) \sin(t) = \sin(2t)$ we write
> $$\Phi(t) = \begin{pmatrix} \cos(2t) \\\ \sin(2t) \end{pmatrix}$$

Now we use the Poincare formula
> $$ deg(\Phi, \Gamma) = \frac{1}{2 \pi} \int^{2 \pi}_0 \frac{2 \cos(2t) cos(2t) - 2 \sin(2t) \sin(2t)}{\cos^2(2t) + \sin^2(2t)}dt = \frac{1}{2 \pi} \int^{2 \pi}_0 2dt = 2$$

As we found using the angular function formula for degree.

</div>

### Partitions of Closed Curves

Let $\Gamma: [a,b] \rightarrow \mathbb{R}^2$ be a closed curve we want to consider the degree of a continuous vector field $\Phi$ on *partitions* of $\Gamma.$

We say that the points $\lbrace A_1, \ldots, A_n \rbrace \in \Gamma$ partition a curve into segments $\lbrace \Gamma_1 , \ldots, \Gamma_n \rbrace$ where $\Gamma_j$ is the section of curve between points $A_j$ and $A_{j+1}$ if $\exists \lbrace p_1, \ldots, p_n \rbrace \in [a,b]$ with $a \leq p_1 < p_2 < \cdots < p_n \leq b$ such that
1. $$\Gamma(p_j) = A_j,$$ $$\; \forall j = 1:n$$
2. $$\Gamma = \bigcup^n_{j=1} \Gamma_j$$ $$$$

The most simple *nontrivial* partition on a closed curve $\Gamma$ is to split $\Gamma$ into two sections. It should be clear that results demonstrated below for a $2$-partition can be generalized by induction to an $n$-partition.

Choose two points on $\Gamma$ say $(A_1,A_2) = (\Gamma(p_1), \Gamma(p_2))$ with $p_1,p_2 \in [a,b]$ and $p_1 < p_2$

Now, $\Gamma$ is *split* into two sections, say $\Gamma_1$ running from $A_1$ to $A_2$ and $\Gamma_2$ from $A_2$ to $A_1,$ whose union gives us again the original closed curve. The sum of the rotations of $\Phi$ over $\Gamma_1$ and then $\Gamma_2$ must equal the rotation $\Phi$ over $\Gamma$ so we might suspect that the sum of the degrees of $\Phi$ over each section of the curve should equal the degree of $\Phi$ over the curve itself.

<div class="proposition" markdown="1">

If closed curve $\Gamma$ is split into disjoint sections $\Gamma_1, \Gamma_2$ then for any continuous vector field $\Phi$
> $$deg(\Phi, \Gamma) = deg(\Phi, \Gamma_1) + deg(\Phi, \Gamma_2)$$

This definition is independent of where the curve is split, i.e. if $\Gamma_1', \Gamma_2'$ is any other partition of $\Gamma$ then
> $$deg(\Phi, \Gamma) deg(\Phi, \Gamma_1') + deg(\Phi, \Gamma_2')$$

The degree of a continuous vector field over a closed curve must be an integer.
</div>

In many problem settings it is not so much important to calculate the value of the degree as it is to show that it is different than zero.

<div class="proposition" markdown="1">

**Borsuk's Theorem:** 

Let $\Phi: S^1 \rightarrow \mathbb{R}^2 \setminus 0$ be a continuous, odd map. Then, $deg(\phi,S^1)$ is odd, in particular different from zero.

</div>

<div class="proof" markdown="1">

*Proof:* 

Split the unit circle into upper and lower hemispheres $\Gamma_1, \Gamma_2$ respectively. The rotation of $\Phi$ over $S^1$ is equal to the sum of its rotations over $\Gamma_1$ and $\Gamma_2.$
> $$deg(S^1) = deg(\Gamma_1) + deg(\Gamma_2)$$

As $\Phi$ is odd the vectors the field takes at antipodal points of $S^1$ are parallel but point in opposite directions i.e. $\Phi(-x,-y) = - \Phi(x,y),$ such that the rotation of $\Phi$ over the upper hemisphere must equal its rotation over the lower hemisphere
> $$deg(\Gamma_1) = deg(\Gamma_2)$$

In particular any odd vector field must rotate some odd multiple $\pi$ radians over each hemisphere as $\Phi(-1,0) = - \Phi(1,0)$ and so, using the angular rotation formula for the degree $deg(\Gamma_1) = \frac{1}{2 \pi}((2n + 1) \pi) = n + \frac{1}{2}$ Hence, the degree over the entire circle must be odd
> $$ deg(S^1) = 2n + 1$$

</div>

### Poincare Formula for Closed Curves

Recall how the normalization property of a degree was introduced in $\mathbb{R^1}:$ </br>
Given the map $f(t) = t - t_0$ with $t\in \Omega$ and $t_0$ arbitrary
> $$deg(f,\Omega) = \begin{cases} 1, \quad t_0 \in \Omega \\ 0, \quad t_0 \notin \Omega \end{cases}$$ 

We will reformulate this property on the plane: </br>
Given the vector field $\Phi(x,y) = (x-x_0,y-y_0)$ and $\Gamma$ a closed curve with $u_0 = (x_0,y_0) \notin \Gamma$ bounding
the planar region $\Omega$
> $$deg(\Phi,\Omega) = \begin{cases} 1, \quad u_0 \in \Omega \\ 0, \quad u_0 \notin \Omega \end{cases}$$

<div class="proposition" markdown="1">

**Proposition:**

The Poincare Formula for degree of a vector field on a closed curve satisfies the normalization property.

</div>

<div class="proof" markdown="1">

*Proof:*

We will prove a slightly weaker result. Take the identity vector field, $\Phi(x,y) = (x,y),$ and $\Gamma$ a closed curve bounding a region
$\Omega.$ We will show that, using the Poincare formula, the following *simplified* normalization property holds 
> $$deg(f,\Omega) = \begin{cases} 1, \quad (0,0) \in \Omega \\ 0, \quad (0,0) \notin \Omega \end{cases}$$

The Poincare formula is especially easy to use when $\Phi(x,y) = (\phi, \psi) = (x,y)$
> $$deg(f,\Gamma) = \frac{1}{2 \pi} \int_{\Gamma} \frac{x dy - y dx}{x^2 + y^2} = \frac{1}{2 \pi} \int_{\Gamma} \frac{x}{x^2 + y^2}dy + \frac{1}{2 \pi} \int_{\Gamma} \frac{-y}{x^2 + y^2}dx $$

<div class="proposition" markdown="1">

**Stoke's Theorem:** Let $\Omega$ be the region enclosed by closed curve $\Gamma.$ If $P(x,y),Q(x,y)$ have continuous partial derivatives on $\Omega$ then
> $$ \int_{\Gamma} P(x,y)dx + Q(x,y)dy = \iint_{\Omega} \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} dA$$

</div>

Let's use the notation of Stoke's Theorem, put $Q(x,y) = \frac{x}{x^2 + y^2}$ and $P(x,y) = \frac{-y}{x^2 + y^2}.$ If we assume, that $(0,0) \notin \Omega$ then these maps have continuous partials
and we can calculate them without too much difficulty
- $$ \frac{\partial P}{\partial y} = \frac{-(x^2 + y^2) - (-y)(2y)}{(x^2 + y^2)^2} = \frac{y^2 - x^2}{(x^2 + y^2)^2}$$
- $$ \frac{\partial Q}{\partial x} =  \frac{(x^2 + y^2) - (x)(2x)}{(x^2 + y^2)^2} = \frac{y^2 - x^2}{(x^2 + y^2)^2}$$

We found $\frac{\partial Q}{\partial x} =  \frac{\partial P}{\partial y}$ so by Stoke's, if $(0,0) \not in \Omega$ then $deg(f,\Omega) = 0$

</div>

### Degree of Tangent Field over Closed Curve

Using two very simple Lemmas we will prove a useful result regarding the degree of tangent fields over closed curves.

<div class="proposition" markdown="1">

**Lemma A:** 

The sum of exterior angles of a polygon is $2 \pi$
</div>

<div class="proof" markdown="1">

*Proof:* 

Consider a polygon $P$ with $n$ sides. We will use two facts
1. Interior and exterior angles are supplementary. 
2. The sum of interior angles of $P$ is $(n-2) \pi$

Let $e$ be the sum of exterior angles and $i$ the sum of interior angles of $P$ Then,
- Using fact $$1:$$ $$e + i = n \pi$$ $$\rightarrow$$ $$e = n \pi - i$$
- Using fact $$2:$$ $$e = n \pi - (n - 2) \pi = 2 \pi$$
</div>


Given a closed curve $\Gamma$ and a partition, $A_1, \ldots, A_n \in \Gamma$ take the polygonal path formed by the tangents at each $A_i$ and call it the polygonal path generated by the partition $\lbrace A_1, \ldots, A_n \rbrace$

If we want to approximate $\Gamma$ by its polygonal path and use it for degree computation we must take into consideration the following pathology resulting from a poor choice of partition
- If $$\lbrace A_1, \ldots, A_n \rbrace$$ is not sufficiently dense then the polygonal path generated might form a polygon at all.

<div class="proposition" markdown="1">

**Lemma B:** 

Given a closed curve $\Gamma$ and the tangent field $\tau(x,y) = (-y,x)$ it is possible to choose a sufficiently dense partition $\lbrace A_1, \ldots, A_n \rbrace$ such that
1. The polygonal path generated by $\lbrace A_1, \ldots, A_n \rbrace$ forms a polygon
2. The increment of the angular function of $$(\tau, \Gamma)$$ between $$A_i$$ and $$A_{i+1}$$ coincides with the angle between the tangents at $$A_i$$ and $$A_{i+1}$$ 

</div>

The following theorem will now follow directly as corollary of Lemmas A and B.

<div class="proposition" markdown="1">

**Theorem:** 

Given a closed curve $\Gamma$ and a tangent field $\tau: \Gamma \rightarrow \mathbb{R}^2 \setminus \rbrace 0 \lbrace$ 
> $$deg(\tau, \Gamma) = 1$$ 
</div>

Recall that the angular function of a vector field $\Phi'$ that is obtained from $\Phi$ by rotating each vector by a some fixed angle less than $\pi$ coincides with the angular function of $\Phi.$

*Remark:* Consider the field of tangents $\tau$ we can obtain the following familiar vector fields by simple angular rotation
1. Rotating each vector of $$\tau$$ by $$- \frac{\pi}{2}$$ we obtain the field of external normals.
2. Similarly, rotating each vector of $$\tau$$ by $$\frac{\pi}{2}$$ we obtain the field of internal normals.

Hence, it follows from the theorem on the degree of tangent fields on a closed curve that the degrees of the field of external and internal normals are also $1$.