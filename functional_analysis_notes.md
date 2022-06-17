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

## $1.$ The Banach Space

### $1.1$ Normed Spaces

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

### $1.2$ Linear operators

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
> $$L(V,W):= \lbrace  T: V \rightarrow W \; \vert$$ $$T$$ is linear, $$T$$ is bounded $$ \rbrace $$

A bounded operator is *bounded* with respect to the **operator norm**, $\Vert \cdot \Vert: L(V,W) \rightarrow \mathbb{R}$, which we define as follows
> $$\Vert T \Vert := \sup_{\Vert x \Vert \leq 1} \Vert Tx \Vert$$

<div class="proposition" markdown="1">

**Proposition 1.07**

$(L(V,W),  \Vert \cdot \Vert)$ is a normed space where $\Vert \cdot \Vert : L(V,W) \rightarrow \mathbb{R}$ is the operator norm on $L(V,W)$.
</div>

<div class="proposition" markdown="1">

**Proposition 1.08**

Along with having the norm properites, the operator norm has the following additional property $\forall_{T \in L(V,W)$ $\forall_{S \in L(W,U)$ $\forall_{x \in V}$
> $$\Vert ST \Vert \leq \Vert S \Vert \cdot \Vert T \Vert$$ $$$$
</div>

### $1.3$ Banach Spaces

<div class="definition" markdown="1">

**Definition: Banach Space**

A normed space $(\mathbb{E}, \Vert \cdot \Vert$ is called a Banach space if $\mathbb{E}$ is a complete metric space with respect to the metric, $d: \mathbb{E} \times \mathbb{E} \rightarrow \mathbb{R}$, associated with the norm $\Vert \cdot \Vert$
> $$d(x,y) = \Vert x - y \Vert $$ $$$$

</div>

Recall, we call the sequence $\mathbb{x_n} \subset \mathbb{E}$ a Cauchy sequence if its terms are arbitrarily close when greater than some sufficiently large index, i.e. 
- $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}}$$ such that $$\forall_{n,m > N} \quad \Vert x_n - x_m \Vert < \epsilon$$

We say that a metric space $\mathbb{E}$ is complete if and only if every Cauchy sequence in $\mathbb{E}$ converges in $\mathbb{E}$.

**Remark:** If $\Vert \cdot \Vert_1$ and $\Vert \cdot \Vert_2$ are equivalent norms on $\mathbb{E}$, then completeness with respect to either of these norms will imply completeness with respect to the other.

### $1.4$ Educative Examples of Banach Spaces

#### $1.4.1$ Space of Bounded Functions

Let $(F, \Vert \cdot \Vert)$ be a Banach space and $X$ an arbitrary nonempty set. Consider the space of bounded functions $X \rightarrow F$
> $$E:=B(X; F):= \lbrace \phi: X \rightarrow F \; : \; \sup_{x \in X} \Vert \phi(x) \Vert < \infty \rbrace$$

Then $E$ is a Banach space when equipped with the so-called $\sup$-norm. 
> $$\Vert \phi \Vert_{\infty} = \sup_{x \in X} \Vert \phi(x) \Vert < \infty$$

#### $1.4.2$ Space of Bounded, Continuous Functions

<div class="proposition" markdown="1">

**Proposition 1.09:**

A closed subspace of a Banach space is also Banach.
</div>

Let $(F, \Vert \cdot \Vert)$ be a Banach space and $(X, d)$ an arbitrary metric space. Consider the space of continuous functions $X \rightarrow F$
> $$E:=BC(X; F):= \lbrace \phi \in B(X;F) \; : \; \phi$$ is continuous $$\rbrace$$

$(E, \Vert \cdot \Vert_{\infty})$ is a Banach space as a closed subspace of $B(X; F)$

<div class="proposition" markdown="1">

**Lemma 1.10:** The Uniform Convergence Theorem

Suppose $(X,d)$ is a metric space, $F$ is a normed space, and $\lbrace \phi_n: X \rightarrow F \rbrace$ is a family of continuous functions such that
1. $$\lbrace \phi_n \rbrace$$ has a well-defined limit function $$\phi$$ i.e.
    - $$\forall_{x \in X} \quad \lim_{n \rightarrow \infty} \phi_n(x) = \phi(x)$$ $$$$
2. $$\lbrace \phi_n \rbrace$$ uniformly converges to $$\phi$$ i.e.
    - $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n \geq N} \forall_{x \in X} \quad \Vert \phi_n(x) - \phi(x) \Vert < \epsilon$$ $$ $$

Then, $\phi: X \rightarrow F$ is continuous.

</div>


#### $1.4.3$ Space Continuous Functions From Compact Metric Spaces

Given a compact metric space $(X,d)$ then any continuous function $\phi: X \rightarrow F$ is bounded such that the space of continuous functions from $X \rightarrow F$ coincides with the set of bounded, continuous functions from $X \rightarrow F$ and so we might write
> $$C(X;F):= BC(X;F)$$ $$ $$

Where $$C(X;F)$$ denotes the space of continuous functions from $$X \rightarrow F$$

Which we have already shown is a Banach space with respect to the norm $\Vert \cdot \Vert_{\infty}$

### $1.5$ $L^p$ Spaces

#### Divergence Into Measure Theory

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

**Proposition 1.11:** 

For any non-negative measurable function $f: X \rightarrow [0, \infty]$ there exists a sequence of simple measurable functions $\lbrace s_n \rbrace$ such that $\forall_{x \in X}$
1. $$0 \leq s_1(x) \leq \cdots \leq s_n(x) \leq s_{n+1}(x) \leq \cdots \leq f(x)$$ $$$$
2. $$\lim_{n \rightarrow \infty} s_n(x) = f(x)$$ $$$$

</div>

#### Construction of the $L^p$ space on $(X, \mathcal{M}, \mu)$

For a simple measurable function, $s(x) = \sum_{i=1}^{N}{\alpha_i \chi_{A_i}(x)}$, with $A_n \cap A_m = \emptyset$ for $n \neq m$, the Lebesgue integral is defined
> $$ \int_{X} s d \mu := \sum_{i=1}^N{\alpha_i \mu(A_i)} $$ $$$$

For a non-negative measurable function, $f: X \rightarrow [0, \infty]$, we have a sequence of non-negative, simple, measurable functions $\lbrace s_n\rbrace$ with $\forall_{x \in X} \forall_{n \in \mathbb{N}} s_n(x) \leq f(x)$ and $\lim_{n \rightarrow \infty} s_n(x) = f(x)$. The Lebesgue integral of a non-negative measurable function is defined
> $$ \int_{X} f d \mu := \lim_{n \rightarrow \infty} \int_{X} s_n d \mu $$ $$$$

Finally, for any measurable function, $f: X \rightarrow \mathbb{R}$, we put $f_{+}(x) := \max{\lbrace 0, f(x)\rbrace}$ and $f_{-}(x) := \min{\lbrace 0, -f(x)\rbrace}$. Notice that $\forall_{x \in X}$ $f_{\pm}(x)$ are non-negative, measurable functions such that $f(x) = f_{+}(x) - f_{-}(x)$. And so we define the Lebesgue integral of any measurable function in terms of these non-negative counter-parts as follows
> $$ \int_{X} f d \mu := \int_{X} f_{+} d \mu - \int_{X} f_{-} d \mu$$ $$$$

If both $\int_{X} f_{+} d \mu$ and $\int_{X} f_{-} d \mu$ are finite, we say that $f$ is integrable. Notice also that as $\forall_{x \in X}$ we have $\vert f(x) \vert = f_{+}(x) + f_{-}(x)$ the absolute integral of measurable $f$ will be the sum of the integrals of its positive and negative counter parts
> $\int_{X} \vert f \vert d \mu := \int_{X} f_{+} d \mu + \int_{X} f_{-} d \mu$

One can identify the integrable functions $f,g: X \rightarrow \mathbb{R}$ if they differ on a set of measure zero, i.e.
> $$f \equiv g \; \iff \; \mu(\lbrace x \in X \; : \; g(x) \neq f(x) \rbrace)$$ $$$$

This is an equivalence relation on the space of integrable functions $X \rightarrow \mathbb{R}$ and we will say that $f$ and $g$ are almost everywhere equal if and only if $f \equiv g$.

Now we are ready to define the $L^p$ space on the measure space $(X, \mathcal{M}, \mu)$ as the space of measurable maps $X \rightarrow \mathbb{R}$ such that $$ \int_{X} \vert f \vert^p d \mu $ is finite.
> $$L^p(X, \mu):= \lbrace f: X \rightarrow \mathbb{R} \; : \; \begin{align*} (i.) f \; \text{is} \; \text{measurable}, \\ (ii.) \int_{X} \vert f \vert^p d \mu < \infty \end{align*} \rbrace$$ $$$$

Notice that $L^p(X, \mu)$ is a vector space, we will equip it with the so-called $p$-norm $\Vert \cdot \Vert_p: L^p(X, \mu) \rightarrow \mathbb{R}$ which is defined
> $$ \Vert f \Vert_p := (\int_{X} \vert f \vert^p)^{\frac{1}{p}}$$ $$$$

<div class="proposition" markdown="1">

**Proposition 1.12:** 

The map $\Vert \cdot \Vert_p$, defined above, is a norm on $L^p(X, \mu)$

</div>

<div class="proposition" markdown="1">

**Lemma 1.13:**  Young Inequality

Let $p,q \in \mathbb{N}$ be conjugate, i.e. such that $\frac{1}{p} + \frac{1}{q} = 1$, $p > 1$, then $\forall_{f \in L^p(X, \mu)}$ $\forall_{g \in L^q(X, \mu)}$ 
> $$ \int_{X} \vert f g \vert \leq \frac{1}{p} \Vert f \Vert_p^p +  \frac{1}{q} \Vert g \Vert_q^q = \frac{1}{p} \int_{X} \vert f \vert^p + \frac{1}{q} \int_{X} \vert g \vert^q$$ $$$$
</div>

<div class="proposition" markdown="1">

**Lemma 1.14:**  Holder Inequality

Let $p,q \in \mathbb{N}$ be conjugate, i.e. such that $\frac{1}{p} + \frac{1}{q} = 1$, $p > 1$, then $\forall_{f \in L^p(X, \mu)}$ $\forall_{g \in L^q(X, \mu)}$ 
> $$ \int_{X} \vert f g \vert \leq  \Vert f \Vert_p +   \Vert g \Vert_q =  (\int_{X} \vert f \vert^p)^{\frac{1}{p}} + (\frac{1}{q} \int_{X} \vert g \vert^q)^{\frac{1}{q}}$$ $$$$
</div>

<div class="proposition" markdown="1">

**Lemma 1.15:**  Minkowsky Inequality

$\forall_{f,g \in L^p(X, \mu)}$ 
> $$ \Vert f g \Vert_p \leq \Vert f \Vert_p + \Vert g \Vert_p$$ $$$$
</div>

<div class="proposition" markdown="1">

**Theorem 1.16:**  

The space $L^p(X, \mu)$, $p \geq 1$, is a Banachspace with respect to the norm $\Vert \cdot \Vert_p$
</div>