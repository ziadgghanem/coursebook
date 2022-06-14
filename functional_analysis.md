---
layout: post
title: 'Functional Analysis'
---

<blockquote>
        The object of mathematics is the honor of the human spirit.
        <footer>Jacobi</footer>
</blockquote>

<hr>

A mathematical result must first be appreciated according to its aesthetics and only after for any practical application. As in all things, an aesthetic result cuts to the heart of things using only as much as is necessary to make its point.  

# Basic Topology

## Compactness

A number of important topological notions, including compactness, are best understood in terms of the open-cover. We say that a family of sets covers a space if it is contained in their union.

<div class="definition" markdown="1">

**Definition: Cover**

Let $X$ be a set and $A \subset X$ we say that the family of sets $\lbrace B_i \rbrace_{i \in I} \subset \mathcal{P}(X)$ is a **cover** of $A$ if and only if $A = \bigcup_{i \in I} B_i$

In the case that $(X, {\Large \tau})$ is a topological space, a cover $\lbrace U_i \rbrace_{i \in I}$ is said to be an **open cover** if $\lbrace U_i \rbrace_{i \in I} \subset {\Large \tau}$

A cover $\lbrace U_i \rbrace_{i \in I}$ is said to be **finite** if the index set $I$ is finite.

Let $\lbrace B_i \rbrace_{i \in I}$ be a cover of $A$, we say that $\lbrace B_i \rbrace_{i \in J}$ is a **subcover** of $A$ if $J \subset I$ such that $\lbrace B_i \rbrace_{i \in J}$ covers $A$. 
</div>

Now that we have defined the open cover we are ready to approach compactness. A compact space, in plain terms, may be described with a finite cover.

<div class="definition" markdown="1">

**Definition: Compactness**

Let $(X, {\Large \tau})$ be a topological space, we say that $X$ is a **compact** space if every open cover of $X$ contains a finite subcover.

**Definition: Sequential Compactness**

$X$ is said to be **sequentially compact** if every sequence $\lbrace x_n \rbrace \subset X$ contains a convergent subsequence.
</div>

For metric spaces, $(X,d)$, compactness is equivalent to sequential compactness.

## From Vector Spaces to Normed Spaces to Metric Spaces to Topological Spaces

<div class="definition" markdown="1">

**Definition: Vector Space** 

A set $V$ containing at least the two elements $\mathbb{1}, \mathbb{0}$, is called a **vector space** if it is equipped with addition and scalar multiplication operations satisfying the following conditions $\forall u,v,w \in V$ $\forall a,b \in \mathbb{R}$
- Conditions on addition operation: $$\;$$ $$\forall u,v,w \in V$$ 
    1. *Commutivity:* $$u+v = v+u$$
    2. *Associativity:* $$u+(v+w) = (u + v) + w$$
    3. *Additive Identity:* $$u + \mathbb{0} = \mathbb{0} + u = u$$
    4. *Additive Inverse:* For all $$u$ \in V$$ there exists a unique $$-u \in V$$ such that $$u + (-u) = (-u) + u = \mathbb{0}$$
- Conditions on multiplicative operation: $$\;$$ $$\forall u,v,w \in V$$ $$\forall a,b \in \mathbb{R}$$
    1. *Associativity:* $$a \cdot (b \cdot u) = (a \cdot b) \cdot c$$
    2. *Multplicative Identity:* $$ u \cdot \mathbb{1} = \mathbb{1} \cdot u = u$$
    3. *Distributivity:* $$a \cdot (u + v) = a \cdot u + a \cdot v$$ and $$(a+b) \cdot v = a \cdot v + b \cdot v$$

Elements of a vector space are called vectors.
</div>

<div class="definition" markdown="1">
**Definition: Normed Space** 

A vector space $$V$$ together with a function $\Vert \cdot \Vert : V \rightarrow \mathbb{R}$ satisfying
$\forall v\in V, \forall r\in \mathbb{R}$ 
1.  $$\Vert v \Vert \ge 0$$ and $$\Vert v \Vert = 0 \iff v = 0$$
2.  $$\Vert rV \Vert$$ $$=$$ $$\vert r \vert \Vert v \Vert$$
3.  $$\Vert u+v \Vert \le \Vert v \Vert + \Vert u \Vert$$ $$$$

is called a normed space and the function $\Vert \cdot \Vert$ is called a norm on $V$.

A function satisfying these properties $\Vert \cdot \Vert : V \rightarrow \mathbb{R}$ is called a norm on $V$
The norm naturally induces a metric on $V$ which generalizes the notion of distance between vectors.

</div>

**Remark: Induced Metric On a Normed Space**

Any normed space $(V, \Vert \cdot \Vert)$ is also a metric space $(V,d)$ where
$d: VxV \rightarrow \mathbb{R}$ is the metric induced by $\Vert \cdot \Vert$
> $$d(u,v) := \Vert u-v \Vert$$ $$ $$

Such a map is indeed a metric, satisfying the metric space properties:
$\forall u,v,w\in V$ we have 
1.  $$d(u,v) \ge 0$$ and $$d(u,v) = 0 \iff u = v$$
2.  $$d(u,v)$$ $$=$$ $$d(v,u)$$
3.  $$d(u,v) \le d(u,w) + d(w,v)$$ $$$$

In turn, a metric induces a topology on $V$.

**Remark: Induced Topology On a Normed Space**

Any normed space $(V, \Vert \cdot \Vert)$ is also a topological space $(V, {\Large \tau})$ where the topology, ${\Large \tau}$, is a collection of subsets of $V$ such that
1.  $$V, \emptyset \in {\Large \tau}$$ $$ $$
2.  $$\lbrace  U_{\alpha}  \rbrace_{\alpha \in \Lambda} \subset {\Large {\Large \tau}} \rightarrow \bigcup_{\alpha \in \Lambda}U_{\alpha} \in {\Large \tau}$$ $$ $$
3.  $$\lbrace  \, U_{\alpha_1}, U_{\alpha_2}, \ldots , U_{\alpha_n} \,  \rbrace \subset {\Large \tau} \rightarrow U_{\alpha_1} \bigcap U_{\alpha_2} \bigcap \cdots \bigcap U_{\alpha_n} \in {\Large \tau}$$ $$ $$

The sets $U \in {\Large \tau}$ are called open.

<div class="definition" markdown="1">

**Open Sets**

Let $(V, \Vert \cdot \Vert)$ be a normed space, we say that $U \subset V$ is open iff
> $$ \forall_{ u \in U} \exists_{\epsilon \geq 0} \forall_{ v \in V} \quad \Vert u - v \Vert < \epsilon \; \implies \; v \in U$$ $$ $$

Or equivalently in terms of neighborhoods,
> $$\forall_{ u \in U} \exists_{\epsilon \geq 0} \quad B_{\epsilon}(u) \subset U $$ $$ $$

Where $B_{\epsilon}(u) := \lbrace v \in V: \Vert u - v \Vert < \epsilon \rbrace$ is the open ball of radius $\epsilon$ centered at $u$.
</div>

<hr>

**Set Manipulation** 

We will use $A + B$ to denote the algebraic sum of sets $A,B \subset V$ 
- $$A + B := \lbrace a + b: a \in A, b \in B \rbrace$$ $$$$

$x_0 + A$ is for us the algebraic sum of an element $x_0 \in V$ with the set $A \subset V$
- $$x_0 + A := \lbrace x_0 + a: a \in A \rbrace$$ $$$$

And by $rA$ we mean the scalar multiplication of a set $A \subset V$ with the real number $r \in \mathbb{R}$
- $$rA := \lbrace ra: a \in A \rbrace$$ $$$$

<div class="proposition" markdown="1">

**Proposition 1.01:**

1. $$ B_{\epsilon}(x_0) = x_0 + B_{\epsilon}(0) = x_0 + \epsilon B_1(0) $$ $$ \tag{..1.01a} \label{1.01a} $$
2. $$ B_{\epsilon}(x_0) + B_{\delta}(y_0) = (x_0+y_0) + (\epsilon + \delta)B_{1}(0) $$   $$ \tag{..1.01b} \label{1.01b} $$
</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

**(1.01a)**

Fix $\epsilon > 0$ and let $\tilde{A}:= B_{\epsilon}(x_0) = \lbrace x: \Vert x - x_0 \Vert < \epsilon \rbrace$, $\tilde{B}:= x_0 + B_{\epsilon}(0) = \lbrace x_0 + x: \Vert x \Vert < \epsilon \rbrace$, $\tilde{C}:= x_0 + \epsilon B_1(0) = \lbrace x_0 + x: \Vert \epsilon x \Vert < 1 \rbrace$ we will show the equality of these three sets. 

First that $\tilde{A} = \tilde{B}$ $\iff$ $x \in \tilde{A} \iff x \in \tilde{B}$
- Take $$z \in \tilde{A}$$ $$\rightarrow$$ $$ \Vert z - x_0 \Vert < \epsilon$$
    - $$\rightarrow \quad$$ $$(z - x_0) \in B_{\epsilon}(0)$$ $$\rightarrow$$ $$z \in \tilde{B}$$
- Take $$y \in \tilde{B}$$ $$\rightarrow$$ $$\exists x$$ with $$\Vert x \Vert < \epsilon$$ such that $$y = x_0 + x$$
    - $$\rightarrow \quad$$ $$\Vert y - x_0 \Vert = \Vert x_0 + x - x_0 \Vert = \Vert x \Vert < \epsilon$$ $$\rightarrow$$ $$y \in \tilde{A}$$

Next that $\tilde{B} = \tilde{C}$ $\iff$ $x \in B_{\epsilon}(0) \iff x \in \epsilon B_1(0)$
- Take $$x \in B_{\epsilon}(0)$$ $$\iff$$ $$\Vert x \Vert < \epsilon$$ $$\iff$$ $$\Vert \epsilon x \Vert < 1$$ $$\iff$$ $$x \in \epsilon B_1(0)$$

**(1.01b)**

</div>
</details>

<div class="proposition" markdown="1">

**Proposition 1.02**

Let $(V, \Vert\cdot\Vert)$ be a normed space with topology ${\Large \tau},$ then
1. The following functions are continous: $$\tag{..1.02a} \label{1.02a}$$
    1. The addition operator, $$ + : V \times V \rightarrow V $$ $$$$
    2. The scalar-multiplication operator, $$ \cdot : R \times V \rightarrow V $$ $$$$
    3. The norm operator, $$ \Vert \cdot \Vert : V \rightarrow R $$ $$$$
2. $$U \in {\Large \tau} \; \implies \; \forall_{ x_{0} \in V} \quad x_{0} + U \in {\Large \tau}$$ $$\tag{..1.02b} \label{1.02b}$$
3. $$U \in {\Large \tau} \; \implies \; \forall_{ r \neq 0} \quad rU \in {\Large \tau}$$ $$\tag{..1.02c} \label{1.02c}$$
</div>

<details>
<summary><i>Proof of 1.0.2b</i></summary>

<div class="proof" markdown="1">

Let $U \in {\Large \tau}$ then by the definition of open set
> $$\forall_{ x \in U} \exists_{\epsilon > 0} B_{\epsilon}(x) \subset U$$

Take $x_{0} \in V$ and denote the set $\tilde{U} = x_0 + U$ then $x_0 + B_{\epsilon}(x) \subset \tilde{U}$.
Put $z= x + x_0 \in \tilde{U}$. By (1.01a) 
> $$x_0 + B_{\epsilon}(x) = (x + x_0) B_{\epsilon}(0) = B_{\epsilon}(x+x_0) = B_{\epsilon}(z) \subset \tilde{U}$$

And so $\forall z \in \tilde{U}$ $\exists_{\epsilon > 0}$ such that $B_{\epsilon}(z) \subset \tilde{U}$ 
i.e. $\tilde{U} \in {\Large \tau}$

More generally if $A \in V$ then $A+U = \lbrace a+x: a \in A, x \in U  \rbrace = \cup_{a \in A} a + U \in {\Large \tau}$
</div>
</details>

**Equivalence of Norms** 

Let $\Vert \cdot \Vert_{1}: V \rightarrow \mathbb{R}$ $\Vert \cdot \Vert_{2}: V \rightarrow \mathbb{R}$
be two norms on vector space $V$. We say that $\Vert \cdot \Vert_{1}$ and $\Vert \cdot \Vert_{2}$ are **equivalent** 
when their associated topologies, ${\Large \tau}_{1}$, ${\Large \tau}_{2}$ coincide.

In the case that ${\Large \tau}_{1} \subset {\Large \tau}_{2},$ ${\Large \tau}_{1}$ is said to be **weaker** than ${\Large \tau}_{2}$
and furthermore $\Vert \cdot \Vert_{1}$ is said to be **weaker** than $\Vert \cdot \Vert_{2}$

<div class="proposition" markdown="1">

**Theorem 1.03** 

Given two norms $\Vert \cdot \Vert_{1}, \Vert \cdot \Vert_{2}$ on a vector space $V$ then
> $${\Large \tau}_{1} \subset {\Large \tau}_{2} \iff \exists_{c > 0} \forall_{x \in V} \Vert \cdot \Vert_{1} \leq c \Vert \cdot \Vert_{2}$$ 

</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

$(\rightarrow)$ 

Suppose ${\Large \tau}_1 \subset {\Large \tau}_2$ 
$\iff$ $U \in {\Large \tau}_1$ $\rightarrow$ $U \in {\Large \tau}_2$

In particular, consider the open ball in $(V, \Vert \cdot \Vert_1),$ 
$B^1_1(0):= \lbrace x: \Vert x \Vert_1 < 1 \rbrace \subset {\Large \tau}_1$ 
- As $$B^1_1(0)$$ is open in $${\Large \tau}_{1}$$ it is also open in $${\Large \tau}_2$$ $$\rightarrow$$ $$\exists_{\epsilon > 0}$$ such that $$B^2_{\epsilon}:= \lbrace x: \Vert x \Vert_2 < \epsilon \rbrace \subset B^1_1(0)$$

Equivalently, $\forall x \in V$ $\Vert x \Vert_2 \leq \epsilon$ $\rightarrow$ $\Vert x \Vert_1 < 1$
- $$\rightarrow \quad$$ $$\forall_{x \neq 0}$$ $$\Vert \epsilon \frac{x}{\Vert x \Vert_2} \Vert_2 = \epsilon$$ $$\rightarrow$$ $$\Vert \epsilon \frac{x}{\Vert x \Vert_2} \Vert_1 < 1$$ 
- $$\rightarrow \quad$$ $$\forall_{x \neq 0}$$ $$\Vert x \Vert_1 \leq \frac{1}{\epsilon} \Vert x \Vert_2$$
</div>
</details>

<div class="example" markdown="1">

**Example:**

Take $V = \mathbb{R}^n$ and the following functions are norms on $V$
1. $$\Vert \cdot \Vert_1: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_1 = \sum^n_{i = 1} \vert x_i \vert$$ $$$$
2. $$\Vert \cdot \Vert_2: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_2 = (\sum^n_{i = 1} (x_i)^2)^{\frac{1}{2}}$$ $$$$
3. $$\Vert \cdot \Vert_p: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_p = (\sum^n_{i = 1} (x_i)^p)^{\frac{1}{p}}$$ $$$$

</div>

<div class="proposition" markdown="1">

**Theorem 1.04:**

Any two norms on $\mathbb{R}^n$ are equivalent.
</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">


Let $\Vert \cdot \Vert: \mathbb{R}^n \rightarrow \mathbb{R}$ be any norm on $\mathbb{R}^n$ we will show that $\Vert \cdot \Vert$ is equivalent to the $1$-norm $\Vert \cdot \Vert_1$. <br>
We say that $\Vert \cdot \Vert, \Vert \cdot \Vert_1$ are equivalent $\iff$ $\exists c,d > 0$ such that $d  \Vert x \Vert_1 < \Vert x \Vert < c \Vert x \Vert_1$

Take $x = (x_1, \ldots, x_n) \in \mathbb{R}^n$ let $\lbrace e^i \rbrace^n_{i=1}$ be the standard basis vectors in $\mathbb{R}^n$ i.e. $e^j \in \mathbb{R}^n$ is the vector with a $1$ in its $j$-th index and $0$ elsewhere. Any element of $\mathbb{R}^n$ can be expressed $x = \sum^n_{i=1} x_i e^i$
- $$\Vert x \Vert = \Vert \sum^n_{i=1} x_i e^i \Vert \leq \sum^n_{i=1} \vert x_i \vert \Vert e^i \Vert$$ $$$$
    - Choose $$c = \max_{i = 1:n} \Vert e^i \Vert$$
- Then, $$\Vert x \Vert \leq  \sum^n_{i=1} \vert x_i \vert c = c \sum^n_{i=1} \vert x_i \vert = c \Vert x \Vert_1$$

For the other inequality we will make use of the **Weierstrass Theorem,** also known as the extreme-value theorem 
<div class="proposition" markdown="1">

**Weierstrass Theorem**

Let $K$ be a compact subset of metric space $M$ and $f:M \rightarrow \mathbb{R}$ a continuous map. Then $f$ achieves maximum
and minimum on $f(K)$.

</div>

Consider the unit sphere in $(V, \Vert \cdot \Vert_1)$, $S:= \lbrace x: \Vert x \Vert_1 = 1 \rbrace$. As demonstrated above, any normed space is also a metric space. In a metric space compactness is equivalent to closedness and boundedness $\rightarrow$ $S$ is compact. In addition, $\Vert \cdot \Vert$ is a continuous on $S$ as it is a norm. Put $d = \min_{x \in S} \Vert x \Vert$ then
- $$\forall_{x \neq 0}$$ $$ \frac{x}{\Vert x \Vert_1} \in S$$ $$\rightarrow$$ $$d \leq \Vert \frac{x}{\Vert x \Vert_1} \Vert = \frac{1}{\Vert x \Vert_1} \Vert x \Vert$$ 
- Hence, $$\forall_{x \neq 0}$$ $$d \Vert x \Vert_1 \leq \Vert x \Vert$$

</div>
</details>

<div class="proposition" markdown="1">

**Corollary 1.05:**

If $V$ is a finite dimensional vector space then any two norms $V$ are equivalent.
</div>

## Linear operators

Given two normed spaces, $(V, \Vert\cdot\Vert)$ and $(W, \Vert\cdot\Vert)$, consider a linear operator $T: V \rightarrow W$
Notice, if $dimV < \infty$ then $T$ must be continuous, if however, $dimV = \infty,$ $T$ might be discontinuous. We will later provide an example of a linear operator $f:V\rightarrow W$ with infinite dimensional domain such that $f$ is discontinuous. 

<div class="definition" markdown="1">

**Continuity**

We say that $T: V \rightarrow W$ is continous $\iff$
> $$ \forall_{x\in V} \forall_{\epsilon > 0} \, \exists_{\delta > 0} \, \forall_{y \in V} \quad \Vert x-y \Vert < \delta \rightarrow \Vert Tx-Ty \Vert < \epsilon$$
</div>

<div class="proposition" markdown="1">

**Proposition 2.01**

Let $T: V \rightarrow W$ be a linear operator. The following conditions are equivalent:
1. T is continuous
2. T is continuous at $$0\in V$$
3. $$T(B)$$ is bounded in $$W$$, where $$B:= \lbrace  x\in V \Vert \Vert x \Vert \leq 1  \rbrace$$ is the unit ball in $$V$$.
4. $$\exists_{c>0} \forall_{x \in V}$$ $$ \Vert Tx \Vert \leq c \Vert x \Vert$$
5. $$\Vert T \Vert:= \sup_{x\in B} \Vert Tx \Vert < \infty$$ where $$\Vert \cdot \Vert$$ is called the operator norm on linear operator $T$
</div>


<details>
<summary><i>Proof</i></summary>
  
<div class="proof" markdown="1">


(1) $\rightarrow$ (2) is immediate
<hr>

(2) $\rightarrow$ (1) <br>
Suppose $T$ is continuous at $0$, i.e. $\forall_{x\in V} \forall_{\epsilon > 0} \, \exists_{\delta > 0} \quad \Vert x \Vert < \delta \rightarrow \Vert Tx \Vert < \epsilon $ choose $y,z \in V$ such that $x = y-z$ then 
- $$\Vert x \Vert < \delta \iff \Vert y-z \Vert < \delta \rightarrow \Vert Tx \Vert < \epsilon$$ $$\iff$$ $$\Vert T(y-z) \Vert = \Vert Ty-Tz) \Vert< \epsilon$$ 
<hr>

(2) $\rightarrow$ (3) <br>
Suppose $T$ is continuous at $0$, i.e. $\forall_{x\in V} \forall_{\epsilon > 0} \, \exists_{\delta > 0} \quad \Vert x \Vert < \delta \rightarrow \Vert Tx \Vert < \epsilon$ choose $0 < c < \delta$ then
- $$\forall_{x\in V} \forall_{\epsilon > 0} \exists_{c > 0} \Vert x \Vert \leq c$$ $$\rightarrow$$ $$\Vert Tx \Vert \leq \epsilon$$

Take $y \in B$ with $\Vert y \Vert \leq 1$ such that $\Vert cy \Vert \leq c$ then,
- By above, $$\Vert cy \Vert \leq c$$ $$\rightarrow$$ $$\Vert T(cy) \Vert \leq \epsilon$$
- $$\iff \quad$$ $$\forall y \in B$$ $$\Vert Ty \Vert \leq \frac{\epsilon}{c} $$ i.e. $$T(B)$$ is indeed bounded
<hr>

(3) $\iff$ (4) <br>
Suppose $T(B) \subset W$ is bounded i.e. suppose $\exists C>0$ such that $\forall_{x \in V} \Vert x \Vert \leq 1$ we have $\Vert Tx \Vert \leq C$. Let $y \neq 0 \in V$ be arbitrary, then
- $$\Vert \frac{y}{\Vert y \Vert} \Vert \leq 1$$ $$\rightarrow$$ $$\Vert T(\frac{y}{\Vert y \Vert}) \Vert \leq C$$
- $$\iff \quad$$ $$\forall_{y \in V, y \neq 0}$$ $$\Vert Ty \Vert \leq C \Vert y \Vert$$
<hr>

(4) $\iff$ (5) is immediate.
<hr>

(4) $\rightarrow$ (1) <br>
Suppose $\exists C > 0$ such that $\Vert T(x-y) \Vert \leq C \Vert x-y \Vert$ but then $\forall_{\epsilon >0}$ if $\Vert x-y \Vert < \frac{\epsilon}{C}$ we will have $\Vert Tx - Ty \Vert \leq C \frac{\epsilon}{C} = \epsilon$ i.e.
- $$\forall_{x,y \in V} \forall_{\epsilon >0} \exists_{\delta} = \frac{\epsilon}{C}$$  such that $$\Vert x-y \Vert < \delta$$ $$\rightarrow$$ $$\Vert Tx - Ty \Vert < \epsilon$$ 

</div>
</details>

**Terminology**

Let $T:V \rightarrow W$ be a linear operator. If $T$ is, in addition, continuous, we call $T$ a bounded operator, and denote the set of all bounded operators from $V \rightarrow W$ with
> $$L(V,W):= \lbrace  T: V \rightarrow W \; \vert$$ $$T$$ is linear, $$T$$ is bounded $$ \rbrace $$

A bounded operator is *bounded* with respect to the **operator norm**, $\Vert \cdot \Vert: L(V,W) \rightarrow \mathbb{R}$, which we define as follows
> $$\Vert T \Vert := \sup_{\Vert x \Vert \leq 1} \Vert Tx \Vert$$

<div class="proposition" markdown="1">

**Proposition 2.02**

$(L(V,W),  \Vert \cdot \Vert)$ is a normed space where $\Vert \cdot \Vert : L(V,W) \rightarrow \mathbb{R}$ is the operator norm on $L(V,W)$.
</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

It is clear enough that $L(V,W)$ is a vector space, what must be checked is that $\Vert \cdot \Vert$ satisfies the norm properties.
1. $$ \Vert T \Vert \geq 0$$ $$\forall T \in L(V,W)$$ 
    - Take $$T \in L(V,W)$$ then $$\Vert T \Vert := \sup_{\Vert x \Vert \leq 1} \Vert Tx \Vert$$ where $$\Vert Tx \Vert \geq 0$$ for all $$x \in V$$, hence
    > $$ \Vert T \Vert \geq 0$$ $$\forall T \in L(V,W)$$ 
2. $$\Vert T \Vert = 0$$ $$\iff$$ $$T = 0$$
    - $$(\leftarrow)$$ if $$T = 0$$ then clearly $$\Vert T \Vert = 0$$
    - $$(\rightarrow)$$ Suppose $$\Vert T \Vert = 0$$
</div>
</details>

## Banach Spaces

<div class="definition" markdown="1">

**Banach Space**

A normed space $(\mathbb{E}, \Vert \cdot \Vert$ is called a Banach space if $\mathbb{E}$ is a complete metric space with respect to the metric, $d: \mathbb{E} \times \mathbb{E} \rightarrow \mathbb{R}$, associated with the norm $\Vert \cdot \Vert$
> $$d(x,y) = \Vert x - y \Vert $$

</div>

Recall, we call a sequence $\mathbb{x_n} \subset \mathbb{E}$ a Cauchy sequence if its terms are arbitrarily close when greater than some sufficiently large index, i.e. 
- $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}}$$ such that $$\forall_{n,m > N} \quad \Vert x_n - x_m \Vert < \epsilon$$

We say that a metric space $\mathbb{E}$ is complete if and only if every Cauchy sequence in $\mathbb{E}$ converges in $\mathbb{E}$.

**Remark:** If $\Vert \cdot \Vert_1$ and $\Vert \cdot \Vert_2$ aare equivalent norms on $\mathbb{E}$, then completeness with respect to either of these norms will imply completeness with respect to the other.

**Educative Examples of Banach Spaces**

<div class="example" markdown="1">

**Space of Bounded Functions**

Let $(F, \Vert \cdot \Vert)$ be a Banach space and $X$ an arbitrary nonempty set. Consider the space of bounded functions $X \rightarrow F$
> $$E:=B(X; F):= \lbrace \phi: X \rightarrow F \; : \; \sup_{x \in X} \Vert \phi(x) \Vert < \infty \rbrace$$

Then we equip $E$ with the so-called $\sup$-norm. 
> $$\Vert \phi \Vert_{\infty} = \sup_{x \in X} \Vert \phi(x) \Vert < \infty$$

<div class="proposition" markdown="1">

*Claim*: 

$\Vert \phi \Vert_{\infty}$ is a norm on $E$
</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

Clearly $(n1)$, $(n2)$ are satisfied, we must only check $(n3)$, namely that the triangle inequality is satisfied. Take $\phi, \psi \in E$
> $$\Vert \phi + \psi \Vert_{\infty} = \sup_{x \in X} \Vert \phi(x) + \psi(x) \Vert$$
> $$ \leq \sup_{x \in X} \lbrace  \Vert \phi(x) \Vert + \Vert \psi(x) \Vert \rbrace \leq \sup_{x \in X}\Vert \phi(x) \Vert + \sup_{x \in X}\Vert \phi(x) \Vert = \Vert \phi \Vert_{\infty} + \Vert \psi \Vert_{\infty}$$
</div>
</details>

<div class="proposition" markdown="1">

*Claim*:

$(E, \Vert \cdot \Vert_{\infty})$ is a Banach space

</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

Indeed, take any Cauchy sequence $\lbrace \phi_n \rbrace \subset B(X; F)$
> $$\rightarrow \quad \forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n,m > N} \quad \Vert \phi_n - \phi_m \Vert_{\infty} < \epsilon$$
> $$\iff \quad \forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n,m > N} \quad \sup_{x \in X} \Vert \phi_n(x) - \phi_m(x) \Vert_{\infty} < \epsilon$$
> $$\rightarrow \quad \forall_{x \in X} \forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n,m > N} \quad \sup_{x \in X} \Vert \phi_n(x) - \phi_m(x) \Vert_{\infty} < \epsilon$$

Now, $\phi_n(x)$ is a Cauchy sequence in the Banach space, $F$, hence,
$\exists \phi_0: X \rightarrow F$ such that $\forall_{x \in X} \lim_{n \rightarrow \infty} \phi_n(x) = \phi_0(x)$. We need to show that $\phi_0 \in E$ i.e. that $\Vert \phi_0 \Vert_{\infty}$ is bounded.

Choose $\epsilon > 0$ and find $N \in mathbb{N}$ such that
> $$ \forall_{n \geq N} \quad \sup \sup_{x \in X} \Vert \phi_n(x) - \phi_N(x) \Vert \leq \epsilon$$
> $$(\rightarrow) \quad$$ $$\forall_{x \in X} \forall_{n \geq N} \quad \Vert \phi_n(x) - \phi_N(x) \Vert \leq \epsilon$$

Now, by the reverse triangle inequality we have $\Vert \phi_n(x) \Vert - \Vert \phi_N(x) \Vert \leq \Vert \phi_n(x) - \phi_N(x) \Vert$ such that
> $$(\rightarrow) \quad$$ $$\forall_{x \in X} \forall_{n \geq N} \quad \Vert \phi_n(x) \Vert \leq \Vert \phi_N(x) \Vert + \epsilon$$

Notice, this inequality holds $\forall_{x \in X}$ and hence in particular for the $\sup_{x \in X}$
> $$(\rightarrow) \quad$$ $$\forall_{n \geq N} \quad \Vert \phi_n \Vert_{\infty} \leq \Vert \phi_N \Vert_{\infty} + \epsilon$$

In addition, as this inequality holds for $\forall_{n \geq N}$ it also holds in the limit as $n \rightarrow \infty$
> $$(\rightarrow) \quad$$ $$\Vert \phi_0 \Vert_{\infty} = \lim_{n \rightarrow \infty} \Vert \phi_n \Vert_{\infty} \leq \Vert \phi_N \Vert_{\infty} + \epsilon$$

Hence, $\Vert \phi_0 \Vert_{\infty} \leq \infty$ which implies $\phi_0 \in E$. And so, we conclude that $E$ is indeed a Banach space.
</div>
</details>

<div class="proposition" markdown="1">

**Proposition 2.04:**

A closed subspace of a Banach space is also Banach.
</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">


Let $C \subset B$ be a closed subspace of the Banach space $(B, \Vert \cdot \Vert)$. Take a sequence $\lbrace x_n \rbrace \subset C$ and suppose it satisfies the Cauchy property with respect to the norm $\Vert \cdot \Vert$
> $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n,m > N} \quad \Vert x_n - x_m \Vert < \epsilon$$

Then, as $B$ is complete, it contains the limit point of $\lbrace x_n \rbrace$
> $$\lim_{n \rightarrow \infty}{x_n} = x_0 \in B$$ $$ $$

But as $C$ is closed, it contains all of its limit points such that
> $$x_0 \in C$$

Hence, $C$ is also Banach

</div>
</details>

</div>


<div class="example" markdown="1">

**Space of Bounded, Continuous Functions**

Let $(F, \Vert \cdot \Vert)$ be a Banach space and $(X, d)$ an arbitrary metric space. Consider the space of continuous functions $X \rightarrow F$
> $$E:=BC(X; F):= \lbrace \phi \in B(X;F) \; : \; \phi$$ is continuous $$\rbrace$$

<div class="proposition" markdown="1">

*Claim*: 

$(E, \Vert \cdot \Vert_{\infty})$ is a Banach space
</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

We have already demonstrated that $B(X; F)$ is Banach, so by  **Proposition 2.04**, It is sufficient to show that $BC(X; F)$ is a closed subspace of $B(X; F)$.

Take any sequence $\lbrace \phi_n \rbrace \in E$ such that $\phi_n$ is continuous $\forall_{n \in \mathbb{N}}$ with $\lim_{n \rightarrow \infty} \phi_n = \phi_0 \in B(X; F)$. 
> $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n > N} \Vert \phi_n - \phi_0 \Vert_{\infty} < \frac{\epsilon}{3}$$

We must show that $\phi_0$ is continuous. Take $x_0 \in X$ and choose $n_0 > N$, by continuity of $\phi_{n_0}$ at $x_0$ we have
> $$\exists_{\delta > 0} \forall_{x \in X} \quad d(x,x_0) < \delta \; \rightarrow \; \Vert \phi_{n_0}(x) - \phi_{n_0}(x_0) \Vert < \frac{\epsilon}{3}$$

Therefore if we take any $x_0 \in X$ then $\forall_{\epsilon > 0} \forall_{x \in X}$ $\exists_{\delta > 0}$ such that if $d(x,x_0) < \delta$ then
> $$\Vert \phi_0(x) - \phi_0(x_0) \Vert$$ $$= \Vert \phi_0(x) - \phi_{n_0}(x) - (\phi_0(x_0) - \phi_{n_0}(x_0)) + \phi_{n_0}(x) - \phi_{n_0}(x_0) \Vert$$
> $$\leq \Vert \phi_0(x) - \phi_{n_0}(x) \Vert + \Vert \phi_0(x_0) - \phi_{n_0}(x_0) \Vert + \Vert \phi_{n_0}(x) - \phi_{n_0}(x_0) \Vert$$
> $$\leq \sup_{x \in X}{\lbrace \Vert \phi_0(x) - \phi_{n_0}(x) \Vert + \Vert \phi_0(x_0) - \phi_{n_0}(x_0) \Vert \rbrace} + \Vert \phi_{n_0}(x) - \phi_{n_0}(x_0) \Vert$$
> $$= 2 \Vert \phi - \phi_{n_0} \Vert_{\infty} + \Vert \phi - \phi_{n_0} \Vert_{\infty} + \Vert \phi_{n_0}(x) - \phi_{n_0}(x_0) \Vert$$
> $$ \leq 2 \frac{\epsilon}{3} + \frac{\epsilon}{3} = \epsilon$$
</div>
</details>

Alternatively we could use the following theorem to demonstrate the closedness of $BC(X; F)$.

<div class="proposition" markdown="1">

**Lemma 2.06:** The Uniform Convergence Theorem

Suppose $(X,d)$ is a metric space, $F$ is a normed space, and $\lbrace \phi_n: X \rightarrow F \rbrace$ is a family of continuous functions such that
1. $$\lbrace \phi_n \rbrace$$ has a well-defined limit function $$\phi$$ i.e.
    - $$\forall_{x \in X} \quad \lim_{n \rightarrow \infty} \phi_n(x) = \phi(x)$$ $$$$
2. $$\lbrace \phi_n \rbrace$$ uniformly converges to $$\phi$$ i.e.
    - $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n \geq N} \forall_{x \in X} \quad \Vert \phi_n(x) - \phi(x) \Vert < \epsilon$$ $$ $$

Then, $\phi: X \rightarrow F$ is continuous.

</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

Take $\epsilon > 0$ then as $\phi$ is the uniform limit of $\lbrace \phi_n \rbrace$ we have
> $$\exists_{N \in \mathbb{N}} \forall_{n \geq N} \forall_{x \in X} \quad \Vert \phi_n(x) - \phi(x) \Vert < \frac{\epsilon}{3}$$

Choose any $x_0 \in X$ and some $n_0 > N$, then as $\phi_{n_0}$ is continuous
> $$ \exists_{\delta > 0} \forall_{x \in X} \quad d(x,x_0) < \delta \; \rightarrow \; \Vert \phi_{n_0}(x) - \phi_{n_0}(x_0) \Vert < \epsilon$$

Therefore, $\forall_{x_0} \in X \forall_{\epsilon > 0} \exists_{\delta > 0} \forall_{x \in X}$ if $d(x,x_0) < \delta$ then
> $$\Vert \phi(x) - \phi(x_0) \Vert = \Vert  (\phi(x) - \phi_{n_0}(x)) + (\phi_{n_0}(x) - \phi_{n_0}(x_0)) + (\phi_{n_0}(x_0) - \phi(x_0)) \Vert$$
> $$ \leq \Vert \phi(x) - \phi_{n_0}(x) \Vert + \Vert \phi_{n_0}(x) - \phi_{n_0}(x_0) \Vert + \Vert \phi_{n_0}(x_0) - \phi(x_0) \Vert \leq \frac{\epsilon}{3} + \frac{\epsilon}{3} + \frac{\epsilon}{3} = \epsilon$$
</div>
</details>

<div class="proposition" markdown="1">

*Claim*: 

$BC(X; F)$ is a closed subspace of $B(X; F)$, 
- i.e. $$(BC(X; F), \Vert \cdot \Vert_{\infty})$$ is a Banach Space.
</div>

<details>
<summary><i>Proof</i></summary>

<div class="proof" markdown="1">

Recall that $BC(X;F)$ is closed iff it contains all of its limit points. Let $\lbrace \phi_n \rbrace \subset BC(X;F)$ be a sequence of continuous functions that converge to some bounded function, $\phi \in B(X;F)$. Then, as $BC(X; F)$ is equipped with the supremum norm, the sequence must converge uniformly to $\phi$. 

Indeed, suppose $lim_{n \rightarrow \infty} \phi_n = \phi$
> $$\forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n \geq N} \quad \Vert \phi_n - \phi \Vert_{\infty} < \epsilon $$

> $$(\iff) \quad \forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n \geq N} \quad \sup_{x \in X}{\Vert \phi_n(x) - \phi(x) \Vert} < \epsilon $$

> $$(\implies) \quad \forall_{\epsilon > 0} \exists_{N \in \mathbb{N}} \forall_{n \geq N} \forall_{x \in X} \quad \Vert \phi_n(x) - \phi(x) \Vert < \epsilon \quad$$ i.e. $$\lbrace \phi_n \rbrace$$ converges uniformly to $$\phi$$

Now, have a sequence of continuous functions that uniformly convegre to $\phi$ and so, by the Uniform Convergence Theorem, $\phi$ must also be continuous.

Therefore, $BC(X;F)$ is indeed closed as it contains all of its limit points. Hence, $(BC(X; F), \Vert \cdot \Vert_{\infty})$ is a Banach Space as the closed subspace of one.
</div>
</details>
</div>

<div class="example" markdown="1">

**Space of Continuous Functions**

Given a compact metric space $(X,d)$ then any continuous function $\phi: X \rightarrow F$ is bounded such that the space of continuous functions from $X \rightarrow F$ coincides with the set of bounded, continuous functions from $X \rightarrow F$ and so we might write
> $$C(X;F):= BC(X;F)$$ $$ $$
    - Where $$C(X;F)$$ denotes the space of continuous functions from $$X \rightarrow F$$

Which we have already shown is a Banach space with respect to the norm $\Vert \cdot \Vert_{\infty}$
</div>

<div class="example" markdown="1">

**Banach Space**

Take $X = [a,b] \subset \mathbb{R}$ any interval in the real numbers, $n \in \mathbb{n}$ any natural number, and $(F, \Vert \cdot \Vert)$ any normed space, then define the space
> $$E:= C^{n}([a,b]; F) := \lbrace \phi:[a,b] \rightarrow F \; : \;$$ $$1.)$$ $$\phi$$ is continuous,  $$2.)$$ $$\phi^{(k)}$$ exists and is continuous $$\forall_{1 \leq k \leq n}$$ $$\rbrace$$

</div>

### Measure Theory

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


<div class="example" markdown="1">

**The Metric Measure** 

For a metric space $(X,d)$, we consider the Borel algebra, $\mathcal{B} = \mathcal{B}(X)$, and define the metric measure, $\mu: \mathcal{B} \rightarrow [0,\infty]$, as
> $$\forall_{A \in \mathcal{B}} \quad \mu(A) = \inf{\lbrace \mu(U): A \subset U, \; U \; \text{open} \rbrace}$$ $$ $$
    > $$ = \sup{\lbrace \mu(K): K \subset A, \; K \; \text{compact} \rbrace}$$ $$ $$

In the case that $X = \mathbb{R}^n$ we call the measure $\mu: \mathcal{B}(\mathbb{R}^n) \rightarrow [0,\infty]$ the Lebesgue measure.
</div>

Let $(X, \mathcal{M}, \mu)$ be a measure space, $\mathcal{B}(X)$ its Borel algebra, where $\mu$ is a metric measure on $\mathcal{B}(X)$.

A function $f: X \rightarrow \mathbb{R}$ is called **$\mu$-measurable**, or simply measurable, iff
> $$\forall_{A \subset \mathcal{B}(\mathbb{X})} \quad f^{-1}(A) \in \mathcal{M}$$

A function $s: X \rightarrow \mathbb{R}$ is called **simple** if $s(X)$ is finite

Let $(X,d)$ be a metric space. We denote by $\mathcal{B}(X)$ the smallest $\sigma$-algebra generated by the set of open sets in $X$. Elements (sets) in $\mathcal{B}(X)$ are called Borel sets and $\mathcal{B}(X)$ itself is called the Borel $\sigma$-algebra
