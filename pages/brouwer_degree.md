---
layout: post
title: 'Brouwer Degree'
---

<div class="definition" markdown="1">

**Definition:** Admissiblity

Let $\Omega \subset \RR^n$ be an open bounded set and $f: \RR^n \rightarrow \RR^n$ a continuous map. The pair $(f, \Omega)$ is called admissible (equivalently, $f$ might be called $\Omega$-admissible) if 
> $\forall_{x \in \partial \Omega} f(x) \neq 0$
</div>

The theory of the Brouwer Degree is concerned with algebraically counting the solutions of the equation

\begin{align}
f(x) = 0, \; x \in \Omega \end{equation} \tag{1} \label{1}
\end{align}

for admissible pairs $(f,\Omega)$. 


For a Euclidean space $\RR^n$ we denote by $\mathcal{M}(\RR^n)$ the set of all admissible pairs $(f, \Omega)$ in $\RR^n$ and, taking a union over all Euclidean spaces, we put 
> $\mathcal{M} := \bigcup_n \mathcal{M}(\RR^n)$

<div class="definition" markdown="1">

**Definition:** Local Brouwer Degree

The Local Brouwer degree is a function
> $deg: \mathcal{M} \rightarrow \mathbb{Z}$
satisfying the following three conditions
1. (Additivity): If $(f, \Omega) \in \mathcal{M}(\RR^n)$ with $(f^{-1}(0) \cap \Omega) \subset (\Omega_1 \cup \Omega_2) \subset \Omega$ for disjoint open subsets $\Omega_1, \Omega_2$ then
    - $deg(f, \Omega) = deg(f, \Omega_1) + deg(f, \Omega_2)$
2. (Homotopy): Given an $\Omega$-admissible homotopy, $h: [0,1] \times \RR^n \rightarrow \RR^n$, 
    - $deg(h_t, \Omega)$ is constant with respect to $t \in [0,1]$
3. (Normalization): Let $\Omega \subset \RR^n$ be open, bounded with $a \in \RR^n$, $a \notin \partial \Omega$ then
    - $deg(Id - a, \Omega) = \begin{cases} 0 \\ 1 \end{cases}$
</div>

**Remark:** A homotopy, $h: [0,1] \times \RR^n \rightarrow \RR^n$, is said to be $\Omega$ admissible if $\forall_{x \in \partial \Omega,} \forall_{t \in [0,1]} h_t(x) \neq 0$, i.e. $h$ is an $\Omega$-admissible homotopy if $\forall_{t \in [0,1]} (h_t, \Omega) \in \mathcal{M}(\RR^n)$.

### Additional Properties of the Degree

<div class="proposition" markdown="1">

**Proposition:** Existence

For $(f, \Omega) \in \mathcal{M}(\RR^n)$, if $deg(f, \Omega) \neq 0$ then $\exists_{x_0 \in \Omega}$ with $f(x_0) = 0$

<div class="proof" markdown="1">

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

Consider the contrapositive of the proposition: 
> $\forall_{x \in \Omega} f(x) \neq 0 \; \implies \; deg(f, \Omega) = 0$

Suppose $f$ has no zeros in $\Omega$, i.e. suppose $f^{-1}(0) \cap \Omega = \emptyset$, and take $\Omega_1, \Omega_2 = \emptyset$ then
1. $f^{-1}(0) \cap \Omega \subset \Omega_1 \cup \Omega_2$
2. $\Omega_1 \cap \Omega_2 = \emptyset$

So, by additivity of the degree

\begin{align}
deg(f, \Omega) & = deg(f, \Omega_1) + deg(f, \Omega_2) \\
 & = deg(f, \emptyset) + deg(f, \emptyset) \\ 
 & = 2deg(f, \emptyset) & = 2deg(f, \emptyset) + 2deg(f, \emptyset) & = 0
\end{align}

</details>
</div>

</div>