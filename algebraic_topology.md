---
layout: post
title: 'Algebraic Topology'
---
### Topology

## Topological Equivalence

Two topological spaces $X, Y$ are *homeomorphic* if there exists a homeomorphism $\phi : X \rightarrow Y$ between them
<label for="homeomorphism" class="margin-toggle">&#8853;</label><input type="checkbox" id="homeomorphism" class="margin-toggle"/><span class="marginnote">A homeomorphism between topological spaces is a continuous function with continuous inverse.</span> 

- $$X \simeq Y \iff \exists_{\phi : X \rightarrow Y}$$ 

*Topological Invariant:* An algebraic object that is unchanged under homeomorphism. 
- e.g.: # of connected components, Euler characteristic, fundamental group.

*Topological Property:* A property that is unchanged under homeomorphism
- e.g.: compactness, connectedness, path connectedness, seperability.


### The Fundamental Group

## paths and homotopy

A path in a space $X$ is a continuous map $f:I \rightarrow X$ 

Two paths $f,g$ are said to be homotopic, denoted $f \simeq g$, if one can be continuously deforrmed to the other with endpoints fixed.

We define a homotopy of paths as the family of maps $f_t:I \rightarrow X$ such that
1. $f_t(0) = x_0$ and $f_t(1) = x_1$ for all $t \in I$
2. The map $F: I \times I \rightarrow X$ defined by $F(t,x) := f_t(x)$ is continuous

In these terms, the paths $f_1, f_2$ with coincident endpoints $x_0,x_1$ are homotopic if there exists a homotopy $f_t$ connecting them.

<div class="example">
  <h3>Example: Path Homotopy in Convex Spaces</h3>

  In any convex space $X$ two paths $f,g:I \rightarrow X$ having the same endpoints are homotopoic via the homotopy $h_t(x) = (1-t)f(x) + tg(x)$

</div>


<div class="example">
  <h3>Proposition: Homotopy as Equivalence Relation</h3>

  Homotopy is an equivalence relation on the space of paths with fixed endpoints in any topological space $X$.

</div>

We will call the equivalence class of a path $f$ under this relation a homotopy class, denoted $[f]$ such that $f \simeq g$ if and only if $g \in [f].$

Given two paths $f,g$ whose initial and terminal points coincide, we will define the composition path which traverses first 
$f$ then $g$ over $I$: <br> 
Let $f,g:I \rightarrow X$ be such that $f(1) = g(0)$ we define $f \cdot g:I \rightarrow X$ as
$$
f \cdot g(t) =\begin{cases}
          f(2t), \quad 0 \leq t \leq \frac{1}{2} \\
          g(2t-1), \quad \frac{1}{2} \leq t \leq 1 \\
     \end{cases}
$$

## loops and fundamental groups

In particular, we will be concerned with the class of paths, called loops, that start and end at the same point, $f:I \rightarrow X$ such that $f(0) = f(1) = x_0,$ the point $x_0 \in X$ is called the base point of $f$.

A loop that can be contracted to a point (by which we mean a loop that is homotopic to the constant map $\alpha \simeq \cdot$) is called *simple.*

We define, ${\Large \pi}_1(X,x_0)$, the **fundamental group** of topological space $X$ at base point $x_0$ as the set of homotopy classes $[f]$ based at $x_0$. 


${\Large \pi}_1(X,x_0)$ is a group with respect to the multiplication on homotopy classes induced by the composition of paths $[f][g] = [f \cdot g]$



Let $h: I \rightarrow X$ be a path from x_0 to x_1


**Definition (Simply Connected Space):**  
We say that $$X$$ is simply connected if it is path connected and $$\Large{\pi}_1(X,p) = {0}$$

**Lemma**  
$$X$$ is simply connected iff there exists a unique homotopy class of paths between any two paths in $$X$$.