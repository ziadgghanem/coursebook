---
layout: post
title: 'Brouwer Degree'
---

<div class="definition" markdown="1">

**Definition:** Admissiblity

Let $\Omega \subset \RR^n$ be an open bounded set and $f: \RR^n \rightarrow \RR^n$ a continuous map. The pair $(f, \Omega)$ is called admissible (equivalently, $f$ might be called $\Omega$-admissible) if 
$$\forall_{x \in \partial \Omega} f(x) \neq 0$$
</div>

The theory of the Brouwer Degree is concerned with algebraically counting the solutions of the equation
$$\begin{equation} f(x) = 0, \; x \in \Omega \end{equation}$$
for admissible pairs $(f,\Omega)$. 

For a Euclidean space $\RR^n$ we denote by $\mathcal{M}(\RR^n)$ the set of all admissible pairs $(f, \Omega)$ in $\RR^n$ and, taking a union over all Euclidean spaces, we put 
$$\mathcal{M} := \bigcup_n \mathcal{M}(\RR^n)$$

<div class="definition" markdown="1">

**Definition:** Local Brouwer Degree

The Local Brouwer degree is a function
$$deg: \mathcal{M} \rightarrow \mathbb{Z}$$
satisfying the following three conditions
1. (Additivity): If $(f, \Omega) \in \mathcal{M}(\RR^n)$ with $(f^{-1}(0) \cap \Omega) \subset (\Omega_1 \cup \Omega_2) \subset \Omega$ for disjoint open subsets $\Omega_1, \Omega_2$ then
    - $deg(f, \Omega) = deg(f, \Omega_1) + deg(f, \Omega_2)$
</div>