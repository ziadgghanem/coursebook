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

### In which we formulate the most simple degree theory.

Take $\Omega \subset \mathbb{R}^1$ a bounded open set. 
<label for="open_sets" class="margin-toggle">&#8853;</label><input type="checkbox" id="open_sets" class="margin-toggle"/><span class="marginnote">We know that open sets in $\mathbb{R}^1$ are characterized as the (at most) countable union of disjoint open intervals.</span> 

For the sake of simplicity we assume $\Omega$ us a finite disjoint union of open intervals.

Consider a map $f: \bar{\Omega} \rightarrow \mathbb{R}$ with $f(t) \neq 0$ $\forall t \in \partial \Omega.$ We will the pair $(f,\Omega)$ admissible. That is, an admissible pair consists of an open set $\Omega$ and a map $f: \bar{\Omega} \rightarrow \mathbb{R}$ that does not vanish on its boundary.

Denote by $M(\mathbb{R}^1)$ the collection of all admissible pairs.

The formulation of a degree theory on $\mathbb{R}^1$ involves the construction of a map
> $$deg: M(\mathbb{R}^1) \rightarrow \mathbb{Z}$$

satisfying reasonable properties.

<div class="example" markdown="1">

**Reasonable Properties of a Degree**

Let $\Omega$ be an open, non-empty, bounded subset of $\mathbb{R}^n$

(1) _Additivity_: 

For subsets $\Omega_1, \Omega_2 \subset \Omega$ with
* Empty intersection: $$\Omega_1 \cap \Omega_2 = \emptyset $$
* Containing all zeros of $$f$$: $$ f^{-1}(0) \subset \Omega_1 \cup \Omega_2$$

then $deg(f,\Omega) = deg(f,\Omega_1) + deg(f,\Omega_2)$

(2) _Homotopy_:

<div class="definition" markdown="1">

**Definition: Homotopy**

Let $h: [0,1] \times \bar{\Omega} \rightarrow \mathbb{R}$ be a continuous map such that $\forall \lambda \in [0,1]$ $h_{\lambda}: \bar{\Omega} \rightarrow \mathbb{R}$ is $\Omega-$ admissible. Then, we say that $h$ is an admissible homotopy joining $h_0$ and $h_1$
</div>

For any $\Omega-$ admissible homotopy $h(\lambda, t)$ we have
> $$deg(h(\lambda, \cdot),\Omega) =$$ constant.

i.e. the degree of of an $\Omega-$ admissible homotopy is independent of $\lambda \in [0,1]$

(3) _Normalization_:

Consider the map $f(t) = t - t_0$ with $t\in \Omega$ and $t_0$ arbitrary. then
> $$deg(f,\Omega) = x = \begin{cases} 1, t_0 \in \Omega \\ 0, t_0 \notin \Omega \end{cases}$$ 

(4) _Existence_:

For any admissible pair $(f,\Omega),$ if $deg(f,\Omega) \neq 0$ then $\exists p \in \Omega$ such that $f(c) = 0$
</div>

With these reasonable properties of a degree theory in mind, we are ready to explicitly define the degree function in $\mathbb{R}^1.$

<div class="proposition" markdown="1">

**<u>Theorem (Degree in $\mathbb{R}^1.$):</u>**

Let $(f,\Omega) \in M(\mathbb{R}^1),$ then, 
> $$deg(f,\Omega) = x = \begin{cases} 1, \qquad \text{if} \; f(a)<0 \; \text{and} \; f(b)>0 \\ -1, \qquad \text{if} \; f(a)>0 \; \text{and} \; f(b)<0 \\ 0, \qquad \text{else} \end{cases}$$ 

correctly defines a degree theory in $\mathbb{R}^1.$
</div>

For $\Omega = \bigcup_{n=1}^{\infty} (a_n,b_n)$ and $f: \bar{\Omega} \rightarrow \mathbb{R}$ $\Omega-$ admissible,
> $$deg(f,\Omega) = \sum_{n=1}^{\infty} deg(f, (a_n,b_n))$$


## 1. Rotation of a Vector Field

### 1.1 Vector Fields

<div class="definition" markdown="1">

**<u>Definition(Vector Field):</u>**

Let $\Omega \subset \mathbb{R}^n$ be a set such that for every point $p \in \Omega$ we associate a vector $\Phi(p) \in \mathbb{R}^n.$

We call the map $\Phi: \Omega \rightarrow \mathbb{R}^n$ a vector field over $\Omega$
</div>

In particular we are concerned with _planar vector fields_ which are defined over sets $\Omega \subset \mathbb{R}^2$.

Any planar vector field $\Phi: \Omega \rightarrow \mathbb{R}^2$ is specified by two _component vectors,_ which are real functions $\phi, \psi: \Omega \rightarrow \mathbb{R}$ such that
> $$\Phi(p) = [\phi(p), \psi(p)]$$

To describe a vector field as continuous is equivalent to describing ech of its component vectors as continuous functions.

<div class="example" markdown="1">

**Example: Complex Functions**

Any complex function $f: \mathbb{C} \rightarrow \mathbb{C}$
can be decomposed into real and imaginary component functions
> $$f(z) = f(x+iy) = u(x,y) + iv(x,y) = {u(x,y), v(x,y)}$$

And so, complex functions are naturally expressed as vector fields.
</div>

### 1.2 Curves

<div class="definition" markdown="1">

**<u>Definition(Planar Curve):</u>**

A map $[0,1] \rightarrow \mathbb{R}^2$ is called a curve.

We will call the image of a curve its trajectory.
</div>

A planar curve if given once two component functions are specified
> $$\begin{pmatrix} x \\\ y \end{pmatrix} = \begin{pmatrix} x(t) \\\ y(t) \end{pmatrix}$$

A curve is continuous $\iff$ its component functions are continuous

A curve is called closed if $$\begin{pmatrix} x(a) \\\ y(a) \end{pmatrix} = \begin{pmatrix} x(b) \\\ y(b) \end{pmatrix}$$

Often, we will define a vector field, $\Phi(x,y) = [\phi(x,y), \psi(x,y)],$ over a curve $\Gamma(t) = [x(t),y(t)].$ In which case the vector field is paramaterized by the variable $ $t \in [0,1].$
> $$\Phi(t) = \begin{pmatrix} \phi(x(t),y(t) \\\ \psi(x(t),y(t)) \end{pmatrix}$$

