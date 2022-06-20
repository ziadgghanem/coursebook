---
layout: post
title: 'Functional Analysis Notes'
---

<blockquote>
        The object of mathematics is the honor of the human spirit.
        <footer>Jacobi</footer>
</blockquote>

<hr>

Long have we fallen from that age of men who sought only to honor the human spirit and yet we may pay them tribute by studying their works and thereby honoring them who had such vision. May we ever walk in their footsteps.

# $1.$ The Banach Space

## $1.1$ Normed Spaces

<div class="definition" markdown="1">

**Definition: Normed Space** 

A vector space $$V$$ together with a function $\Vert \cdot \Vert : V \rightarrow \mathbb{R}$ satisfying
$\forall u,v\in V, \forall r\in \mathbb{R}$ 
1.  $$\Vert v \Vert \ge 0$$ and $$\Vert v \Vert = 0 \iff v = 0$$
2.  $$\Vert rV \Vert$$ $$=$$ $$\vert r \vert \Vert v \Vert$$
3.  $$\Vert u+v \Vert \le \Vert v \Vert + \Vert u \Vert$$ $$$$

is called a normed space and the function $\Vert \cdot \Vert$ is called a norm on $V$.

</div>

**Remark: Induced Metric On a Normed Space**

Any normed space $(V, \Vert \cdot \Vert)$ is naturally also a metric space $(V,d)$ where
$d: VxV \rightarrow \mathbb{R}$ is the metric induced by $\Vert \cdot \Vert$
> $$d(u,v) := \Vert u-v \Vert$$ $$ $$

<div class="definition" markdown="1">

**Definition: Metric Space** 

A vector space $$V$$ together with a function $d: V \times V \rightarrow \mathbb{R}$ satisfying
$\forall u,v,w \in V$ 
1.  $$d(u,v) \ge 0$$ and $$d(u,v) = 0 \iff u = v$$
2.  $$d(u,v)$$ $$=$$ $$d(v,u)$$
3.  $$d(u,v) \le d(u,w) + d(w,v)$$ $$$$

is called a metric space and the function $d (\cdot, \cdot)$ is called a metric on $V$.

</div>

**Remark: Induced Topology On a Metric Space**

In turn, any metric space $(V,d)$ is naturally a topological space $(V, {\Large \tau})$ where ${\Large \tau}$ is the topology induced by the metric such that $U \in {\Large \tau}$ if and only if
> $$ \forall_{ u \in U} \exists_{\epsilon \geq 0} \forall_{ v \in V} \quad d(u,v) < \epsilon \; \implies \; v \in U$$ $$ $$

Or equivalently in terms of neighborhoods,
> $$\forall_{ u \in U} \exists_{\epsilon \geq 0} \quad B_{\epsilon}(u) \subset U $$ $$ $$

Where $B_{\epsilon}(u) := \lbrace v \in V: d(u,v) < \epsilon \rbrace$ is the open ball of radius $\epsilon$ centered at $u$.

In the case that $d: VxV \rightarrow \mathbb{R}$ is the induced metric of some norm $\Vert \cdot \Vert$ (as will often be the case in our study) the induced topology, ${\Large \tau}$ is such that $U \in {\Large \tau}$ if and only if
> $$ \forall_{ u \in U} \exists_{\epsilon \geq 0} \forall_{ v \in V} \quad \Vert u - v \Vert < \epsilon \; \implies \; v \in U$$ $$ $$

And the open ball, $B_{\epsilon}$ is expressed 
> $$B_{\epsilon}(u) := \lbrace v \in V: \Vert u - v \Vert < \epsilon \rbrace$$ $$$$

<div class="definition" markdown="1">

**Definition: Topological Space** 

A vector space $$V$$ together with a collection of subsets ${\Large \tau} \subset \mathcal{P}(V)$ satisfying
1.  $$V, \emptyset \in {\Large \tau}$$ $$ $$
2.  $$\lbrace  U_{\alpha}  \rbrace_{\alpha \in \Lambda} \subset {\Large {\Large \tau}} \rightarrow \bigcup_{\alpha \in \Lambda}U_{\alpha} \in {\Large \tau}$$ $$ $$
3.  $$\lbrace  \, U_{\alpha_1}, U_{\alpha_2}, \ldots , U_{\alpha_n} \,  \rbrace \subset {\Large \tau} \rightarrow U_{\alpha_1} \bigcap U_{\alpha_2} \bigcap \cdots \bigcap U_{\alpha_n} \in {\Large \tau}$$ $$ $$

is called a topological space and the sets $U \in {\Large \tau}$ are called open.

</div>

**Set Manipulation** 

We will use $A + B$ to denote the algebraic sum of sets $A,B \subset V$ 
- $$A + B := \lbrace a + b: a \in A, b \in B \rbrace$$ $$$$

$x_0 + A$ is for us the algebraic sum of an element $x_0 \in V$ with the set $A \subset V$
- $$x_0 + A := \lbrace x_0 + a: a \in A \rbrace$$ $$$$

And by $rA$ we mean the scalar multiplication of a set $A \subset V$ with the real number $r \in \mathbb{R}$
- $$rA := \lbrace ra: a \in A \rbrace$$ $$$$

<div class="proposition" markdown="1">

**Proposition 1.01:** Properties of Balls

1. $$ B_{\epsilon}(x_0) = x_0 + B_{\epsilon}(0) = x_0 + \epsilon B_1(0) $$ $$ \tag{..1.01a} \label{1.01a} $$
2. $$ B_{\epsilon}(x_0) + B_{\delta}(y_0) = (x_0+y_0) + (\epsilon + \delta)B_{1}(0) $$   $$ \tag{..1.01b} \label{1.01b} $$
</div>

<div class="proposition" markdown="1">

**Proposition 1.02** Properties of the Topology induced by a Norm

Let $(V, \Vert\cdot\Vert)$ be a normed space with topology ${\Large \tau},$ then
1. The following functions are continous: $$\tag{..1.02a} \label{1.02a}$$
    1. The addition operator, $$ + : V \times V \rightarrow V $$ $$$$
    2. The scalar-multiplication operator, $$ \cdot : R \times V \rightarrow V $$ $$$$
    3. The norm operator, $$ \Vert \cdot \Vert : V \rightarrow R $$ $$$$
2. $$U \in {\Large \tau} \; \implies \; \forall_{ x_{0} \in V} \; x_{0} + U \in {\Large \tau}$$ $$\tag{..1.02b} \label{1.02b}$$
3. $$U \in {\Large \tau} \; \implies \; \forall_{ r \neq 0} \; rU \in {\Large \tau}$$ $$\tag{..1.02c} \label{1.02c}$$
</div>

**Equivalence of Norms** 

Let $\Vert \cdot \Vert_{1}: V \rightarrow \mathbb{R}$ $\Vert \cdot \Vert_{2}: V \rightarrow \mathbb{R}$
be two norms on vector space $V$. We say that $\Vert \cdot \Vert_{1}$ and $\Vert \cdot \Vert_{2}$ are **equivalent** 
when their associated topologies, ${\Large \tau}_{1}$, ${\Large \tau}_{2}$ coincide.

In the case that ${\Large \tau}_{1} \subset {\Large \tau}_{2},$ ${\Large \tau}_{1}$ is said to be **weaker** than ${\Large \tau}_{2}$
and furthermore $\Vert \cdot \Vert_{1}$ is said to be **weaker** than $\Vert \cdot \Vert_{2}$

<div class="proposition" markdown="1">

**Theorem 1.03** 

Given two norms $\Vert \cdot \Vert_{1}, \Vert \cdot \Vert_{2}$ on a vector space $V$ then
> $${\Large \tau}_{1} \subset {\Large \tau}_{2} \iff \exists_{c > 0} \forall_{x \in V} \; \Vert \cdot \Vert_{1} \leq c \Vert \cdot \Vert_{2}$$ 

</div>

<div class="example" markdown="1">

**Example:** Norms on $\mathbb{R}^n$

Take $V = \mathbb{R}^n$ and the following functions are norms on $V$
1. $$\Vert \cdot \Vert_1: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_1 = \sum^n_{i = 1} \vert x_i \vert$$ $$$$
2. $$\Vert \cdot \Vert_2: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_2 = (\sum^n_{i = 1} (x_i)^2)^{\frac{1}{2}}$$ $$$$
3. $$\Vert \cdot \Vert_p: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_p = (\sum^n_{i = 1} (x_i)^p)^{\frac{1}{p}}$$ $$$$

</div>

<div class="proposition" markdown="1">

**Theorem 1.04:** Equivalence of norms on $\mathbb{R}^n$

Any two norms on $\mathbb{R}^n$ are equivalent.
</div>

<div class="proposition" markdown="1">

**Corollary 1.05:** Equivalence of norms on finite dimensional vector spaces

If $V$ is a finite dimensional vector space then any two norms $V$ are equivalent.
</div>

## $1.2$ Linear operators

Given two normed spaces, $(V, \Vert\cdot\Vert)$ and $(W, \Vert\cdot\Vert)$, consider the linear operator $T: V \rightarrow W$

Notice, if $dimV < \infty$ then $T$ must be continuous, if however, $dimV = \infty,$ it might be that $T$ is discontinuous. We will later provide an example of a linear operator $f:V\rightarrow W$ with infinite dimensional domain such that $f$ is discontinuous. 

<div class="definition" markdown="1">

**Continuity**

We say that $T: V \rightarrow W$ is continous $\iff$
> $$ \forall_{x\in V} \forall_{\epsilon > 0} \, \exists_{\delta > 0} \, \forall_{y \in V} \quad \Vert x-y \Vert < \delta \rightarrow \Vert Tx-Ty \Vert < \epsilon$$
</div>

<div class="proposition" markdown="1">

**Proposition 1.06**

Let $T: V \rightarrow W$ be a linear operator. The following conditions are equivalent:
1. T is continuous
2. T is continuous at $$0\in V$$
3. $$T(B)$$ is bounded in $$W$$, where $$B:= \lbrace  x\in V \Vert \Vert x \Vert \leq 1  \rbrace$$ is the unit ball in $$V$$.
4. $$\exists_{c>0} \forall_{x \in V}$$ $$ \Vert Tx \Vert \leq c \Vert x \Vert$$
5. $$\Vert T \Vert:= \sup_{x\in B} \Vert Tx \Vert < \infty$$ $$$$

</div>

Let $T:V \rightarrow W$ be a linear operator. If $T$ is, in addition, continuous, we call $T$ a bounded operator, and denote the set of all bounded operators from $V \rightarrow W$ with
> $$L(V,W):= \left{ T: V \rightarrow W \; : \; \begin{align*} i. \; T \; \text{is} \; \text{linear}, \\ ii. \;  \; T \; \text{is} \; \text{bounded} \end{align*} \right}$$

A bounded operator is *bounded* with respect to the **operator norm**, $\Vert \cdot \Vert: L(V,W) \rightarrow \mathbb{R}$, which we define as follows
> $$\Vert T \Vert := \sup_{\Vert x \Vert \leq 1} \Vert Tx \Vert$$

<div class="proposition" markdown="1">

**Proposition 1.07** Properties of the Operator Norm $\Vert \cdot \Vert: L(V,W) \rightarrow \mathbb{R}$
Let $A \in L(V,W)$ then
1. $$\Vert A \Vert := \sup_{\Vert x \Vert \leq 1} \Vert Ax \Vert = \Vert A \Vert := \sup_{\Vert x \Vert = 1} \Vert Ax \Vert$$ $$$$
2. $$\Vert A \Vert := \inf{ \lbrace c > 0 \; : \; \forall_{x \in V} \; \Vert Ax \Vert \leq c \Vert x \Vert \rbrace}$$ $$$$
3. $$\Vert A + B \Vert \leq \Vert A \Vert + \Vert B \Vert$$ $$$$
4. $$\Vert r A \Vert \leq \vert r \vert \Vert A \Vert$$ $$\; \forall_{r \in \mathbb{R}$$
5. $$\Vert A x \Vert \leq \Vert A \Vert \Vert x \Vert$$ $$\; \forall_{x \in V}$$
6. If $$B \in L(W,U)$$ then $$\Vert AB \Vert \leq \Vert A \Vert \Vert B \Vert$$
</div>

<div class="proposition" markdown="1">

**Proposition 1.08**

$(L(V,W),  \Vert \cdot \Vert)$ is a normed space where $\Vert \cdot \Vert : L(V,W) \rightarrow \mathbb{R}$ is the operator norm on $L(V,W)$.
</div>

<div class="proposition" markdown="1">

**Proposition 1.09**

Along with having the norm properites, the operator norm has the following additional property $\forall_{T \in L(V,W)$ $\forall_{S \in L(W,U)$ $\forall_{x \in V}$
> $$\Vert ST \Vert \leq \Vert S \Vert \cdot \Vert T \Vert$$ $$$$
</div>

## $1.3$ Banach Spaces

<div class="definition" markdown="1">

**Definition: Banach Space**

A normed space $(\mathbb{E}, \Vert \cdot \Vert$ is called a Banach space if $\mathbb{E}$ is a complete metric space with respect to the metric, $d: \mathbb{E} \times \mathbb{E} \rightarrow \mathbb{R}$, associated with the norm $\Vert \cdot \Vert$
> $$d(x,y) = \Vert x - y \Vert $$ $$$$

</div>

Recall, we call the sequence $\mathbb{x_n} \subset \mathbb{E}$ a Cauchy sequence if its terms are arbitrarily close when greater than some sufficiently large index, i.e. 
- $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}}$$ such that $$\forall_{n,m > N} \quad \Vert x_n - x_m \Vert < \epsilon$$

We say that a metric space $\mathbb{E}$ is complete if and only if every Cauchy sequence in $\mathbb{E}$ converges in $\mathbb{E}$.

**Remark:** If $\Vert \cdot \Vert_1$ and $\Vert \cdot \Vert_2$ are equivalent norms on $\mathbb{E}$, then completeness with respect to either of these norms will imply completeness with respect to the other.

## $1.4$ Educative Examples of Banach Spaces

### $1.4.1$ Space of Bounded Functions

Let $(F, \Vert \cdot \Vert)$ be a Banach space and $X$ an arbitrary nonempty set. Consider the space of bounded functions $X \rightarrow F$
> $$E:=B(X; F):= \lbrace \phi: X \rightarrow F \; : \; \sup_{x \in X} \Vert \phi(x) \Vert < \infty \rbrace$$

Then $E$ is a Banach space when equipped with the so-called $\sup$-norm. 
> $$\Vert \phi \Vert_{\infty} = \sup_{x \in X} \Vert \phi(x) \Vert < \infty$$

### $1.4.2$ Space of Bounded, Continuous Functions

<div class="proposition" markdown="1">

**Proposition 1.10:**

A closed subspace of a Banach space is also Banach.
</div>

Let $(F, \Vert \cdot \Vert)$ be a Banach space and $(X, d)$ an arbitrary metric space. Consider the space of continuous functions $X \rightarrow F$
> $$E:=BC(X; F):= \lbrace \phi \in B(X;F) \; : \; \phi$$ is continuous $$\rbrace$$

$(E, \Vert \cdot \Vert_{\infty})$ is a Banach space as a closed subspace of $B(X; F)$

<div class="proposition" markdown="1">

**Lemma 1.11:** The Uniform Convergence Theorem

Suppose $(X,d)$ is a metric space, $F$ is a normed space, and $\lbrace \phi_n: X \rightarrow F \rbrace$ is a family of continuous functions such that
1. $$\lbrace \phi_n \rbrace$$ has a well-defined limit function $$\phi$$ i.e.
    - $$\forall_{x \in X} \quad \lim_{n \rightarrow \infty} \phi_n(x) = \phi(x)$$ $$$$
2. $$\lbrace \phi_n \rbrace$$ uniformly converges to $$\phi$$ i.e.
    - $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n \geq N} \forall_{x \in X} \quad \Vert \phi_n(x) - \phi(x) \Vert < \epsilon$$ $$ $$

Then, $\phi: X \rightarrow F$ is continuous.

</div>


### $1.4.3$ Space Continuous Functions From Compact Metric Spaces

Given a compact metric space $(X,d)$ then any continuous function $\phi: X \rightarrow F$ is bounded such that the space of continuous functions from $X \rightarrow F$ coincides with the set of bounded, continuous functions from $X \rightarrow F$ and so we might write
> $$C(X;F):= BC(X;F)$$ $$ $$

Where $$C(X;F)$$ denotes the space of continuous functions from $$X \rightarrow F$$

Which we have already shown is a Banach space with respect to the norm $\Vert \cdot \Vert_{\infty}$

## $1.5$ $L^p$ Spaces

### Divergence Into Measure Theory

<div class="definition" markdown="1">

**Definition: $\sigma$-algebra** 

A set $X$ with a family of subsets $\mathcal{M} \subset \mathcal{P}(X)$ is called a $\sigma$-algebra if
1. $$\emptyset, X \in \mathcal{M}$$ $$$$
2. $$A \in \mathcal{M} \;$$ $$\implies$$ $$\; X \setminus{A} \in \mathcal{M}$$ 
3. $$\lbrace A_n \rbrace \subset \mathcal{M} \;$$ $$\implies$$ $$\; \bigcup_{n} A_n \in \mathcal{M}$$ 

By convention, the sets $A \in \mathcal{M}$ are called measurable sets

</div>

<div class="definition" markdown="1">

**Definition: Measure** 

A function $\mu: \mathcal{M} \rightarrow [0,\infty]$ is called a measure on $X$ if
1. $$\forall_{A \in \mathcal{M}} \quad$$ $$\mu(A) \geq 0$$ 
2. $$\mu(\emptyset) = 0$$ $$$$
3. For $$\lbrace A_n \rbrace \subset \mathcal{M}$$ with $$\forall_{n \neq k} \; A_n \cap A_k = \emptyset \quad$$ $$\mu(\bigcup^{\infty}_{n} A_n) = \sum^{\infty}_{n} \mu(A_n)$$

And the triple $(X, \mathcal{M}, \mu)$ is called a measure space.
</div>

<div class="definition" markdown="1">

**Definition: Borel Algebra** 

Let $(X,d)$ be a metric space. We denote by $\mathcal{B}(X)$ the smallest $\sigma$-algebra generated by the set of open sets in $X$. Elements (sets) in $\mathcal{B}(X)$ are called Borel sets and $\mathcal{B}(X)$ itself is called the Borel $\sigma$-algebra or  simply the Borel algebra
</div>

Put $X = \mathbb{R}^n$ and, $\mathcal{B} = \mathcal{B}(X)$, the Borel algebra over $\mathbb{R}^n$. The Lebesgue measure $\mu: \mathcal{M} \rightarrow R$ satisfies the property
> $$\forall_{A \in \mathcal{B}} \quad \mu(A) = \inf{\lbrace \mu(U): A \subset U, \; U \; \text{open} \rbrace}$$ $$ \quad \quad \quad = \sup{\lbrace \mu(K): K \subset A, \; K \; \text{compact} \rbrace} \tag{*}$$

Now, let $(X,d)$ be any measure space. We call a measure which satisfies property $\star$ a metric measure.

<div class="definition" markdown="1">

**Definition: Measurable Functions** 

Assume $(X, \mathcal{M}, \mu)$ is a metric measure space with Borel algebra $\mathcal{B}(X)$.

A function $f: X \rightarrow \mathbb{R}$ is called **$\mu$-measurable**, or measurable, iff
> $$\forall_{A \subset \mathcal{B}(X)} \quad f^{-1}(A) \in \mathcal{M}$$

A function $s: X \rightarrow \mathbb{R}$ is called simple if it takes only a finite number of values i.e. $s(X) = \lbrace \alpha_1 \ldots \alpha_N \rbrace$. Put $A_k := s^{-1}(\alpha_k} = \lbrace x \in X \; : \; s(x) = \alpha_k \rbrace$ then we write
> $$s(x) = \sum_{i=1}^{N}{\alpha_i \chi_{A_i}(x)}$$ $$$$

where $\chi_{A}$ is the characteristic function of the set $A$ defined by
> $$\chi_{A}(x) = \begin{cases} 0 \quad x \notin A \\ 1 \quad x \in A \end{cases}$$

A simple function, $s: X \rightarrow \mathbb{R}$, is measurable if and only if $\forall_{k = 1, \ldots, N} A_k \in \mathcal{M}$
</div>

<div class="proposition" markdown="1">

**Proposition 1.12:** 

For any non-negative measurable function $f: X \rightarrow [0, \infty]$ there exists a sequence of simple measurable functions $\lbrace s_n \rbrace$ such that $\forall_{x \in X}$
1. $$0 \leq s_1(x) \leq \cdots \leq s_n(x) \leq s_{n+1}(x) \leq \cdots \leq f(x)$$ $$$$
2. $$\lim_{n \rightarrow \infty} s_n(x) = f(x)$$ $$$$

</div>

### $1.5.1$ Construction of the $L^p$ space on $(X, \mathcal{M}, \mu)$

For a simple measurable function, $s(x) = \sum_{i=1}^{N}{\alpha_i \chi_{A_i}(x)}$, with $A_n \cap A_m = \emptyset$ for $n \neq m$, the Lebesgue integral is defined
> $$ \int\limits_{X} s \; d \mu := \sum_{i=1}^N{\alpha_i \mu(A_i)} $$ $$$$

For a non-negative measurable function, $f: X \rightarrow [0, \infty]$, we have a sequence of non-negative, simple, measurable functions $\lbrace s_n\rbrace$ with $\forall_{x \in X} \forall_{n \in \mathbb{N}} s_n(x) \leq f(x)$ and $\lim_{n \rightarrow \infty} s_n(x) = f(x)$. The Lebesgue integral of a non-negative measurable function is defined
> $$ \int\limits_{X} f \; d \mu := \lim_{n \rightarrow \infty} \int\limits_{X} s_n \; d \mu $$ $$$$

Finally, for any measurable function, $f: X \rightarrow \mathbb{R}$, we put $f_{+}(x) := \max{\lbrace 0, f(x)\rbrace}$ and $f_{-}(x) := \min{\lbrace 0, -f(x)\rbrace}$. Notice that $\forall_{x \in X}$ $f_{\pm}(x)$ are non-negative, measurable functions such that $f(x) = f_{+}(x) - f_{-}(x)$. And so we define the Lebesgue integral of any measurable function in terms of these non-negative counter-parts as follows
> $$ \int\limits_{X} f \; d \mu := \int\limits_{X} f_{+} \; d \mu - \int\limits_{X} f_{-} \; d \mu$$ $$$$

If both $\int\limits_{X} f_{+} \; d \mu$ and $\int\limits_{X} f_{-} \; d \mu$ are finite, we say that $f$ is integrable. Notice also that as $\forall_{x \in X}$ we have $\vert f(x) \vert = f_{+}(x) + f_{-}(x)$ the absolute integral of measurable $f$ will be the sum of the integrals of its positive and negative counter parts
> $\int\limits_{X} \vert f \vert \; d \mu := \int\limits_{X} f_{+} \; d \mu + \int\limits_{X} f_{-} \; d \mu$

One can identify the integrable functions $f,g: X \rightarrow \mathbb{R}$ if they differ on a set of measure zero, i.e.
> $$f \equiv g \; \iff \; \mu(\lbrace x \in X \; : \; g(x) \neq f(x) \rbrace)$$ $$$$

This is an equivalence relation on the space of integrable functions $X \rightarrow \mathbb{R}$ and we will say that $f$ and $g$ are almost everywhere equal if and only if $f \equiv g$.

Now we are ready to define the $L^p$ space on the measure space $(X, \mathcal{M}, \mu)$ as the space of measurable maps $X \rightarrow \mathbb{R}$ such that $$ \int\limits_{X} \vert f \vert^p \; d \mu $ is finite.
> $$L^p(X, \mu):= \lbrace f: X \rightarrow \mathbb{R} \; : \; \begin{align*} i. \; f \; \text{is} \; \text{measurable}, \\ ii. \; \int\limits_{X} \vert f \vert^p \; d \mu < \infty \end{align*} \rbrace$$ $$$$

Notice that $L^p(X, \mu)$ is a vector space, we will equip it with the so-called $p$-norm $\Vert \cdot \Vert_p: L^p(X, \mu) \rightarrow \mathbb{R}$ which is defined
> $$ \Vert f \Vert_p := (\int\limits_{X} \vert f \vert^p)^{\frac{1}{p}}$$ $$$$

We also define the space $L^{\infty}(X, \mu)$
> $$L^p(X, \mu):= \left{ f: X \rightarrow \mathbb{R} \; : \; \begin{align*} i. \; f \; \text{is} \; \text{measurable}, \\ ii. \; \exists_{c > 0} \vert f(x) \vert \leq c \; \text{a.e.} \end{align*} \right}$$

And introduce the essential supremum norm $ess \sup_{x \in X} := \Vert \cdot \Vert_{\infty}: L^{\infty}(X, \mu) \rightarrow \mathbb{R}$
> $$ \Vert f \Vert_{\infty} := \inf{ \lbrace c > 0 \; : \; \vert f(x) \vert \leq c \; \text{a.e.} \rbrace}$$ $$$$

<div class="proposition" markdown="1">

**Proposition 1.13:** 

The map $\Vert \cdot \Vert_p$, defined above, is a norm on $L^p(X, \mu)$

</div>

<div class="proposition" markdown="1">

**Lemma 1.14:**  Young Inequality

Let $p,q \in \mathbb{N}$ be conjugate, i.e. such that $\frac{1}{p} + \frac{1}{q} = 1$, $p > 1$, then $\forall_{f \in L^p(X, \mu)}$ $\forall_{g \in L^q(X, \mu)}$ 
> $$ \int\limits_{X} \vert f g \vert \leq \frac{1}{p} \Vert f \Vert_p^p +  \frac{1}{q} \Vert g \Vert_q^q = \frac{1}{p} \int\limits_{X} \vert f \vert^p + \frac{1}{q} \int\limits_{X} \vert g \vert^q$$ $$$$
</div>

<div class="proposition" markdown="1">

**Lemma 1.15:**  Holder Inequality

Let $p,q \in \mathbb{N}$ be conjugate, i.e. such that $\frac{1}{p} + \frac{1}{q} = 1$, $p > 1$, then $\forall_{f \in L^p(X, \mu)}$ $\forall_{g \in L^q(X, \mu)}$ 
> $$ \int\limits_{X} \vert f g \vert \leq  \Vert f \Vert_p +   \Vert g \Vert_q =  (\int\limits_{X} \vert f \vert^p)^{\frac{1}{p}} + (\frac{1}{q} \int\limits_{X} \vert g \vert^q)^{\frac{1}{q}}$$ $$$$
</div>

<div class="proposition" markdown="1">

**Lemma 1.16:**  Minkowsky Inequality

$\forall_{f,g \in L^p(X, \mu)}$ 
> $$ \Vert f g \Vert_p \leq \Vert f \Vert_p + \Vert g \Vert_p$$ $$$$
</div>

<div class="proposition" markdown="1">

**Theorem 1.17:**  

For $p \geq 1$, the space $L^p(X, \mu)$ is a Banach space with respect to the norm $\Vert \cdot \Vert_p$
</div>

## $1.6$ Additional Properties of Banach Spaces

<div class="proposition" markdown="1">

**Theorem 1.18:**  

Let $V$ be a normed space and $F$ a Banach space, then the space of bounded linear maps from $V \rightarrow F$
> $$\begin{equation} L(V;F) = \left\{ A: V \rightarrow F \; : \; \begin{aligned} &i. \; \text{(A is linear)} \\ &ii. \; \text{(A is bounded)} \end{aligned} \right\} \end{equation}$$

when eqipped with the operator norm, is a Banach space.
</div>


<div class="proposition" markdown="1">

**Definition:** Dual Space

If $E$ is a normed space then the space of linear functionals, $L(E;\mathbb{R})$ is denoted $E^*$ and called the dual space of $E$. A dual space on $E$ induces the bilinear functional $\langle \cdot,\cdot \rangle: E^* \times E \rightarrow \mathbb{R}$ such that
> $$\langle f,x \rangle := f(x)$$ $$$$

The dual space on a normed space is always a Banach space with respect to the operator norm.
> $$ \Vert f \Vert = \sup_{\Vert x \Vert \leq 1}{\langle f,x \rangle} $$ $$$$
</div>


<div class="example" markdown="1">

**Example:** The Dual of a Euclidean Space

Let $E = \mathbb{R}^n$, then $E^* = \mathbb{R}^n$. Indeed, $\forall_{f \in E^*} \exists_{y \in \mathbb{R^n}} y = (y_1, \ldots, y_n)$ such that $\forall_{x \in \mathbb{R^n}} x = (x_1, \ldots, x_n)$  we have
> $$f(x) = \langle y,x \rangle = \sum_{i=1}^n{x_i y_i}$$ $$$$

Notice that the operator norm on $E^* = (\mathbb{R}^n)^*$ may be expressed in terms of the $y \in \mathbb{R^n}$ associated with $f \in E^*$ i.e.
> $$\Vert f \Vert = \Vert y \Vert_{*} = \sup_{\Vert x \Vert \leq 1}{\langle y,x \rangle}$$ $$$$

</div>

<hr>

**A Few Remarks**

<div class="definition" markdown="1">

**Definition:** Totally Bounded

Let $(X,d)$ be a metric space, then a set $A \subset X$ is called totally bounded if for any specified radius $\epsilon > 0$ there exist at most finitely many points such the union of $\epsilon$-balls about these points constitute a cover for $A$, i.e.
> $$\forall_{\epsilon >0} \exists_{\lbrace x_1, \ldots x_n \rbrace}$$ such that $$A \subset \bigcup_{i=1}^n B_{\epsilon}(x_i)$$

</div>

<div class="proposition" markdown="1">

**Proposition 1.19:**  

For any metric space, $(X,d)$, the following are equivalent concerning a subset $A \subset X$
1. $A$ is compact
2. $A$ is totally bounded and complete (with respect to $$d$$)
3. Every sequence in $A$ has a convergent subsequence with limit in $A$.

</div>

<hr>

<div class="proposition" markdown="1">

**Theorem 1.20:**  

Let $E$ be a normed space and denote $B:= \lbrace x \in E \; : \; \Vert x \Vert \leq 1 \rbrace$, then $B$ is totally bounded if and only if $E$ is finite dimensional.

**Corollary 1.21:**  

If $\EE$ is an infinite-dimensional Banach space then the closed unit ball $B \subset \EE$ is never compact.
</div>

# 2 Classical Theorems of Functional Analysis

## 2.1 Hahn Banach, Analytic Version

<div class="proposition" markdown="1">

**Theorem 2.01:**  (Hahn-Banach Analytic Version)

Let $\EE$ be a vector space and $p: \EE \rightarrow \mathbb{R}$ a function such that $\forall_{x,y \in \EE}$ $\forall_{\lambda > 0}$
1. $$p(\lambda x) = \lambda p(x)$$ $$$$
2. $$p(x+y) \leq p(x) + p(y)$$ $$$$

Assume that $\LL \subset \EE$ is a linear subspace and $g: \EE \rightarrow \mathbb{R}$ a linear functional such that
> $$\forall_{x \in \LL} \; g(x) \leq p(x)$$ $$$$

Then there exists a linear functional $f: E \rightarrow \mathbb{R}$ with
1. $$\forall_{x \in \LL} \; f(x) = g(x)$$ $$$$
2. $$\forall_{x \in \EE} \; f(x) \leq p(x)$$ $$$$
</div>

<div class="proposition" markdown="1">

**Corollary 2.02:** 

Let $(\mathbb{L}, \Vert \cdot \Vert_{\LL}$ be a subspace of normed space $\mathbb{E}$ and $g \in L(\mathbb{L},\mathbb{R})$ a linear functional with $\Vert g \Vert:= \sup_{\Vert x \Vert \leq 1}{g(x)} \leq \infty$, then there exists $f \in L(\mathbb{L},\mathbb{R})$ such that
> $$\Vert f \Vert = \Vert g \Vert$$ 

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

<div class="proof" markdown="1">

Take $p(x) = \Vert g \Vert \Vert x \Vert_{\LL}$ and check that it satisfies the conditions of the Hahn-Banach Theorem.

*Claim 1:* $p(x)$ satisfies $\forall_{x \in E} \forall_{\lambda > 0} p(\lambda x) = \lambda p(x)$
- This property follows from $$\Vert \lambda x \Vert_L = \lambda \Vert \lambda x \Vert_{\LL}$$ 

*Claim 2:* $p(x)$ satisfies $p(x+y) \leq p(x) + p(y)$
- Again, as $$\Vert \cdot \Vert_{\LL}$$ is a norm on $$\mathbb{L}$$ this is simply a result of the triangle inequality.

*Claim 3:* $\forall_{x \in \LL} \; g(x) \leq p(x)$
- $$\cdots$$

</div>
</details>

</div>

<div class="proposition" markdown="1">

**Corollary 2.03:** 

Let $\mathbb{E}$ be a normed space and $x_0 \in \EE$ then $\exists_{f_0 \in \EE^*}$ such that
1. $$\Vert f_0 \Vert = \Vert x_0 \Vert$$ $$$$
2. $$ \langle f_0,x_0 \rangle = \Vert x_0 \Vert^2$$

</div>

Notice that the bilinear operator $\langle \cdot, \cdot \rangle: \EE^* \times \EE \rightarrow \mathbb{R}$ satisfies similar properties as does the inner product on a vector space $\mathcal{H}$. 

An inner product is a bilnear map, $\langle \cdot, \cdot \rangle: \mathcal{H} \times \mathcal{H} \rightarrow \mathbb{R}$, satisfying $\forall_{x,y \in \mathcal{H}}$
1. $$\langle x, x \rangle \geq 0$$ and $$\langle x, x \rangle = 0 \; \iff \; x=0$$
2. $$\langle x, y \rangle = \langle y, x \rangle$$ $$$$
3. $$\langle x, \alpha y_1 + \beta y_2 \rangle = \alpha \langle x, y_1 \rangle + \beta \langle x, y_2 \rangle$$ $$$$
4. $$\langle \alpha x_1 + \beta x_2, y \rangle = \alpha \langle x_1, y \rangle + \beta \langle x_2, y \rangle$$ $$$$

We call the pair $(\mathcal{H}, \langle \cdot, \cdot \rangle)$ an inner product space and define the induced norm
> $$\Vert x \Vert := \sqrt{\langle x, x \rangle}$$ $$\tag{*}$$

<div class="definition" markdown="1">

**Definition:** Hilbert Space

An inner product space $(\mathcal{H}, \langle \cdot, \cdot \rangle)$ is said to be a Hilbert space if $\mathcal{H}$ is complete with respect to the norm $\tag{*}$

</div>

*Remark:* It will be shown that for a Hilbert space $(\mathcal{H}, \langle \cdot, \cdot \rangle)$, for every $f \in \mathcal{H}^*$ there exists a unique $x_0 \in \mathcal{H}$ such that $\forall_{x \in \mathcal{H}}$ $f(x) = \langle x,x_0 \rangle$. This result is known as the Riesz-Representation Theorem and will be our proximate goal.

<div class="proposition" markdown="1">

**Lemma 2.04:** 

Let $\mathbb{E}$ be a normed space and $f: \rightarrow \EE \rightarrow \mathbb{R}$ with $f \not\equiv 0$ be a linear functional then
$f$ is continuous if and only if $Ker(f):= \lbrace x\in \EE \; : \; \langle f,x \rangle = 0 \rbrace$ is a closed subspace.

</div>

## 2.2 Hahn Banach, Geometric Version

<div class="definition" markdown="1">

**Definition:** Hyperplane

Let $A,B$ be two non-empty subsets of $(\EE, \Vert \cdot \Vert)$ with $A \cap B = \emptyset$. We say that a functional $f \in \EE^*$ separates $A$ and $B$ if $\exists_{\alpha \in \mathbb{R}}$ such that
> $$\forall_{a \in A} \forall_{b \in B} \; f(a) \leq \alpha \leq f(b)$$ $$$$

We might also say that the hyperplane $[f = \alpha]$ separates $A$ and $B$ where
> $$[f = \alpha]:= \lbrace x \in \EE \; : \; f(x) = \alpha \rbrace$$ $$$$

In addition, it is said that $[f = \alpha]$ strictly separates two sets $A,B$ if $\exists_{\alpha \in \mathbb{R}}$ and $\exists_{\delta > 0}$ such that
> $$\forall_{a \in A} \forall_{b \in B} \; f(a) \leq \alpha - \delta < \alpha \leq f(b)$$ $$$$

</div>

**Recall:** That a set $C$ in a vector space $V$ is convex if and only if
> $$\forall_{x,y \in C} \forall_{t\in [0,1]} \; tx + (1-t)y \in C$$ $$$$

<div class="proposition" markdown="1">

**Lemma 2.05:** 

Let $(\EE, \Vert \cdot \Vert)$ be a normed space and $C \subset \EE$ a convex set, then
1. $$int(C)$$ is convex
2. $$\overline{C}$$ is convex

</div>

<div class="proposition" markdown="1">

**Lemma 2.06:** 

If $(\EE, \Vert \cdot \Vert)$ is a normed space and $C \subset \EE$ is a nonempty convex set, then
> $$\overline{int(C)} = \overline{C}$$

</div>

<div class="definition" markdown="1">

**Definition:** Gauge Function

Let $\EE$ be a normed space and $C \subset \EE$ and open, convex neighborhood of zero. Define the map $p_C: \EE \rightarrow \mathbb{R}$ by
> $$\forall_{x \in \EE} p_C(x):= \inf{\lbrace \alpha > 0 \; : \; x \in \alpha C \rbrace}

Such a function $p_C$ is called the gauge function of $C$.

</div>

<div class="proposition" markdown="1">

**Proposition 2.07:** Properties of the Gauge Function

Let $p_C$ be the gauge function of $C$, an open convex neighborhood of zero, in a normed space $\EE$ then 
1. $$\forall_{x,y \in \EE} \; p_C(x+y) \leq p_C(x) + p_C(y)$$ $$$$
2. $$\forall_{\lambda > 0} \forall_{x \in \EE} \; p_C(\lambda x) = \lambda p_C(x)$$ $$$$
3. $$\exists_{M} \forall_{x \in E} \; 0 \leq p_C(x) \leq M \Vert x \Vert$$
4. $$C:= \lbrace x \in \EE \; : \; p_C(x) \leq 1 \rbrace$$

</div>

<div class="proposition" markdown="1">

**Lemma 2.08:** 

Let $\EE$ be a normed space and $C \subset \EE$ and open, convex set with $0 \in C$. Take $x_0 \in \EE$ with $x_0 \notin C$ then there exists $f \in \EE^*$ such that
>$$\forall_{x \in C} f(x) < f(x_0)$$ $$$$

</div>

<div class="proposition" markdown="1">

**Theorem 2.09:** Hahn-Banach Geometric V.1

Let $\EE$ be a normed space, and $A,B \subset \EE$ two non-empty, convex sets such that
1. $$A \cap B = \emptyset$$ $$$$
2. $$A$$ is open

Then, there exists $f \in \EE^*$ and $\alpha \in \mathbb{R}$ such that the hyperplane $[f = \alpha]$ separates $A$ and $B$ i.e.
> $$\forall_{a \in A} \forall_{b \in B} \; \langle f,a \rangle \leq \alpha \leq \langle f, b \rangle$$ $$$$

</div>


<div class="proposition" markdown="1">

**Theorem 2.09:** Hahn-Banach Geometric V.2

Let $\EE$ be a normed space, and $A,B \subset \EE$ two non-empty, convex, closed sets such that
1. $$A \cap B = \emptyset$$ $$$$
2. $$A$$ is compact

Then, there exists $f \in \EE^*$ and $\alpha \in \mathbb{R}$ such that the hyperplane $[f = \alpha]$ strictly separates $A$ and $B$ i.e.
> $$\forall_{a \in A} \forall_{b \in B} \; \langle f,a \rangle \leq \alpha - \delta < \alpha \leq \langle f, b \rangle$$ $$$$

</div>


<div class="proposition" markdown="1">

**Corollary 2.10:** 

Let $\EE$ be a normed space, and $\LL \subset \EE$ a subspace such that $\overline{\LL} \subsetneq \EE$ (i.e. such that $\LL$ is *not* a dense subspace of $\EE$) then $\exists_{f \in \EE^*}$ such that
1. $$f \notequiv 0$$ $$$$
2. $$\forall_{x \in \LL} \langle f,x \rangle = 0$$ $$$$
</div>


<div class="proposition" markdown="1">

**Corollary 2.11:** 

Let $\EE$ be a normed space, and $\LL \subset \EE$ a subspace then $\LL$ is a dense subspace of $\EE$  if and only if any linear functional in $\EE^*$ with all of $\LL$ in its kernel must be the zero map, i.e.
> $$\overline{\LL} \subset \EE \;$$ $$\iff$$ $$\; \forall_{f \in \EE^*} \forall_{x \in \LL} \; \langle f,x \rangle = 0 \; \rightarrow f \equiv 0$$ 
</div>

## 2.3 Orthogonality Relations in Banach Spaces
