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

## Vector Spaces Normed Spaces, Metric Spaces, Topological Spaces

**Vector Space:** 

A set $V$ containing at least the two elements $\mathbb{1}, \mathbb{0}$, is called a **vector space** if it is equipped with an addition and scalar multiplication operations satisfying the following conditions $\forall u,v,w \in V$ $\forall a,b \in \mathbb{R}$
- Conditions on addition operation $$+: \quad$$ $$\forall u,v,w \in V$$ 
    1. *Commutivity:* $$u+v = v+u$$
    2. *Associativity:* $$u+(v+w) = (u + v) + w$$
    3. *Additive Identity:* $$u + \mathbb{0} = \mathbb{0} + u = u$$
    4. *Additive Inverse:* For all $$u$ \in V$$ there exists a unique $$-u \in V$$ such that $$u + (-u) = (-u) + u = \mathbb{0}$$
- Conditions on multiplicative operation $$\cdot: \quad$$ $$\forall u,v,w \in V$$ $$\forall a,b \in \mathbb{R}$$
    1. *Associativity:* $$a \cdot (b \cdot u) = (a \cdot b) \cdot c$$
    2. *Multplicative Identity:* $$ u \cdot \mathbb{1} = \mathbb{1} \cdot u = u$$
    3. *Distributivity:* $$a \cdot (u + v) = a \cdot u + a \cdot v$$ and $$(a+b) \cdot v = a \cdot v + b \cdot v$$

Elements of a vector space are called vectors.

**Normed Space** 

A vector space $$V$$ together with a function $\Vert \cdot \Vert : V \rightarrow \mathbb{R}$ satisfying
$\forall v\in V, \forall r\in \mathbb{R}$ 
1.  $$\Vert v \Vert \ge 0$$ and $$\Vert v \Vert = 0 \iff v = 0$$
2.  $$\Vert rV \Vert$$ $$=$$ $$\vert r \vert \Vert v \Vert$$
3.  $$\Vert u+v \Vert \le \Vert v \Vert + \Vert u \Vert$$
is called a normed space and the function $\Vert \cdot \Vert$ is called a norm on $V$.

A function satisfying these properties $\Vert \cdot \Vert : V \rightarrow \mathbb{R}$ is called a norm on $V$
The norm naturally induces a metric on $V$ which generalizes the notion of distance between vectors.

**Induced Metric On a Normed Space**

Any normed space $(V, \Vert \cdot \Vert)$ is also a metric space $(V,d)$ where
$d: VxV \rightarrow \mathbb{R}$ satisfies the metric space properties:
$\forall u,v,w\in V$ we have 
1.  $$d(u,v) \ge 0$$ and $$d(u,v) = 0 \iff u = v$$
2.  $$d(u,v)$$ $$=$$ $$d(v,u)$$
3.  $$d(u,v) \le d(u,w) + d(w,v)$$

Indeed it is sufficient to take $d(u,v) := \Vert u-v \Vert$. 

In turn, a metric induces a topology on $V$ which defines the notion of an open set. 

**Induced Topology On a normed space**

Any normed space $(V, \Vert \cdot \Vert)$ is also a topological space $(V, {\Large \tau})$ where the topology, ${\Large \tau}$, is a collection of subsets of $V$ such that
1.  $$V, \emptyset \in {\Large \tau}$$ $$ $$
2.  $$\rbrace  U_{\alpha}  \lbrace_{\alpha \in \Lambda} \subset {\Large {\Large \tau}} \rightarrow \bigcup_{\alpha \in \Lambda}U_{\alpha} \in {\Large \tau}$$ $$ $$
3.  $$\rbrace  \, U_{\alpha_1}, U_{\alpha_2}, \ldots , U_{\alpha_n} \,  \lbrace \subset {\Large \tau} \rightarrow U_{\alpha_1} \bigcap U_{\alpha_2} \bigcap \cdots \bigcap U_{\alpha_n} \in {\Large \tau}$$ $$ $$

The sets $U \in {\Large \tau}$ are called open.

<div class="definition" markdown="1">

**Open Sets**

Let $(V, \Vert \cdot \Vert)$ be a normed space, we say that $U \subset V$ is open iff
> $$ \forall_{ u \in U} \exists_{\epsilon \geq 0} \forall_{ v \in V} \| u - v \| < \epsilon \Rightarrow	v \in U $$ $$ $$

Or equivalently,
> $$\forall_{ u \in U} \exists_{\epsilon \geq 0} B_{\epsilon}(u) \subset U $$ $$ $$

Where $B_{\epsilon}(u) := \rbrace v \in V: \| u - v \| < \epsilon \lbrace$ is the open ball of radius $\epsilon$ centered at $u$.
</div>

**Set Manipulation** 

We will use $A + B$ to denote the algebraic sum of sets $A,B \subset V$ 
- $$A + B := \rbrace a + b: a \in A, b \in B \lbrace$$ $$$$

$x_0 + A$ is for us the algebraic sum of an element $x_0 \in V$ with the set $A \subset V$
- $$x_0 \in V \qquad x_0 + A := \rbrace x_0 + a: a \in A \lbrace$$ $$$$

And by $rA$ we mean the scalar multiplication of a set $A \subset V$ with the real number $r \in \mathbb{R}$
- $$r \in \mathbb{R} \qquad rA := \rbrace ra: a \in A \lbrace$$ $$$$

<div class="proposition" markdown="1">

**Proposition 1.01:**

For convenience we denote by $B$ the open unit ball $B:= B_1{0}$
1. $$ B_{\epsilon}(x_0) = x_0 + B_{\epsilon}(0) = x_0 + \epsilon B_1(0) $$ $$ \tag{..1.01a} \label{1.01a} $$
2. $$ B_{\epsilon}(x_0) + B_{\delta}(y_0) = (x_0+y_0) + (\epsilon + \delta)B_{1}(0) $$   $$ \tag{..1.01b} \label{1.01b} $$
</div>

<div class="proof" markdown="1">

*Proof:*

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


<div class="proposition" markdown="1">

**Proposition 1.02**

Let $(V, \|\cdot\|)$ be a normed space with topology ${\Large \tau},$ then
1. The following functions are continous: $$\tag{..1.02a} \label{1.02a}$$
    1. $$ + : V \times V \rightarrow V $$ $$$$
    2. $$ \cdot : R \times V \rightarrow V $$ $$$$
    3. $$ \Vert \cdot \Vert : V \rightarrow R $$ $$$$
2. $$U \in {\Large \tau} \Rightarrow \forall_{ x_{0} \in V} x_{0} + U \in {\Large \tau}$$ $$\tag{..1.02b} \label{1.02b}$$
3. $$U \in {\Large \tau} \Rightarrow \forall_{ r \neq 0} rU \in {\Large \tau}$$ $$\tag{..1.02c} \label{1.02c}$$
</div>

<div class="proof" markdown="1">

*Proof 1.0.2b:*

Let $U \in {\Large \tau}$ then $\forall_{ x \in U} \exists_{\epsilon > 0} B_{\epsilon}(x) \subset U$
- Take $$x_{0} \in V$$ and denote the set $$\tilde{U} = x_0 + U$$ then $$x_0 + B_{\epsilon}(x) \subset \tilde{U}$$
- Put $$z= x + x_0 \in \tilde{U}$$ By (1.01a) $$x_0 + B_{\epsilon}(x) = (x + x_0) B_{\epsilon}(0) = B_{\epsilon}(x+x_0) = B_{\epsilon}(z) \subset \tilde{U}$$
- And so $$\forall z \in \tilde{U}$$ $$\exists_{\epsilon > 0}$$ such that $$B_{\epsilon}(z) \subset \tilde{U}$$ 
- i.e. $$\tilde{U} \in {\Large \tau}$$

More generally if $A \in V$ then $A+U = \rbrace a+x: a \in A, x \in U  \lbrace = \cup_{a \in A} a + U \in {\Large \tau}$
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
> $${\Large \tau}_{1} \subset {\Large \tau}_{2} \iff \exists_{c > 0} \forall_{x \in V} \Vert \cdot \Vert_{1} \leq c \Vert \cdot \Vert_{2}$$ 

</div>

<div class="proof" markdown="1">

*Proof 1.0.2b:*

$(\rightarrow)$ 

Suppose ${\Large \tau}_{1} \subset {\Large \tau}_{2}$ $\iff$ $U \in {\Large \tau}_{1}$ $\rightarrow$ $U \in {\Large \tau}_{2}$

In particular, consider the open ball in $(V, \Vert \cdot \Vert_{1}),$ $B^1_1(0):= \lbrace x: \Vert x \Vert_1 < 1 \rbrace \subset {\Large \tau}_{1}$ 
- As $$B^1_1(0)$$ is open in $${\Large \tau}_{1}$$ it is also open in $${\Large \tau}_{2}$$ $$\rightarrow$$ $$\exists_{\epsilon > 0}$$ such that $$B^2_{\epsilon}:= \lbrace x: \Vert x \Vert_2 < \epsilon \rbrace \subset B^1_1(0)$$

Equivalently, $\forall x \in V$ $\Vert x \Vert_2 \leq \epsilon$ $\rightarrow$ $\Vert x \Vert_1 < 1$
- $$\rightarrow \quad$$ $$\forall_{x \neq 0}$$ $$\Vert \epsilon \frac{x}{\Vert x \Vert_2} \Vert_2 = \epsilon$$ $$\rightarrow$$ $$\Vert \epsilon \frac{x}{\Vert x \Vert_2} \Vert_1 < 1$$ 
- $$\rightarrow \quad$$ $$\forall_{x \neq 0}$$ $$\Vert x \Vert_1 \leq \frac{1}{\epsilon} \Vert x \Vert_2$$
</div>

<div class="example" markdown="1">

**Example:**

Take $V = \mathbb{R}^n$ and define the functions
1. $$\Vert \cdot \Vert_1: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_1 = \sum^n_{i = 1} \vert x_i \vert$$
2. $$\Vert \cdot \Vert_2: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_2 = (\sum^n_{i = 1} (x_i)^2)^{\frac{1}{2}}$$
3. $$\Vert \cdot \Vert_p: \mathbb{R}^n \rightarrow \mathbb{R}$$ $$$$
    > $$\Vert x \Vert_p = (\sum^n_{i = 1} (x_i)^p)^{\frac{1}{p}}$$ 

Each of these functions are norms on $V$ and they are all equivalent.
</div>

<div class="proposition" markdown="1">

**Theorem 1.04:**

Any two norms on $\mathbb{R}^n$ are equivalent.
</div>

<div class="proof" markdown="1">

*Proof:*

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
and minimum on $f(K$).$
</div>

Consider the unit sphere in $(V, \Vert \cdot \Vert_1)$, $S:= \lbrace x: \Vert x \Vert_1 = 1 \rbrace$. As demonstrated above, any normed space is also a metric space. In a metric space compactness is equivalent to closedness and boundedness $\rightarrow$ $S$ is compact. In addition, $\Vert \cdot \Vert$ is a continuous on $S$ as it is a norm. Put $d = \min_{x \in S} \Vert x \Vert$ then
- $$\forall_{x \neq 0}$$ $$ \frac{x}{\Vert x \Vert_1} \in S$$ $$\rightarrow$$ $$d \leq \Vert \frac{x}{\Vert x \Vert_1} \Vert = \frac{1}{\Vert x \Vert_1} \Vert x \Vert$$ 
- Hence, $$\forall_{x \neq 0}$$ $$d \Vert x \Vert_1 \leq \Vert x \Vert$$

</div>

<div class="proposition" markdown="1">

**Corollary 1.05:**

If $V$ is a finite dimensional vector space then any two norms $V$ are equivalent.
</div>

## Linear operators

Given two normed spaces, $(V, \|\cdot\|)$ and $(W, \|\cdot\|)$, consider a linear operator $T: V \rightarrow W$
Notice, if $dimV < \infty$ then $T$ must be continuous, if however, $dimV = \infty,$ $T$ might be discontinuous. We will later provide an example of a linear operator $f:V\rightarrow W$ with infinite dimensional domain such that $f$ is discontinuous. 

<div class="definition" markdown="1">

**Continuity**

We say that $T: V \rightarrow W$ is continous $\iff$
> $$ \forall_{x\in V} \forall_{\epsilon > 0} \, \exists_{\delta > 0} \, \forall_{y \in V} \quad \| x-y \| < \delta \rightarrow \| Tx-Ty \| < \epsilon$$
</div>

<div class="proposition" markdown="1">

**Proposition 2.01**

Let $T: V \rightarrow W$ be a linear operator. The following conditions are equivalent:
1. T is continuous
2. T is continuous at $$0\in V$$
3. $$T(B)$$ is bounded in $$W$$, where $$B:= \rbrace  x\in V \Vert \| x \| \leq 1  \lbrace$$ is the unit ball in $$V$$.
4. $$\exists_{c>0} \forall_{x \in V}$$ $$ \Vert Tx \Vert \leq c \Vert x \Vert$$
5. The operator norm of T is bounded, i.e. $$\| T \|:= \sup_{x\in B} \| Tx \| < \infty$$
</div>


<div class="proof" markdown="1">

*Proof*

(1) $\rightarrow$ (2) is immediate
<hr>

(2) $\rightarrow$ (1) <br>
Suppose $T$ is continuous at $0$, i.e. $\forall_{x\in V} \forall_{\epsilon > 0} \, \exists_{\delta > 0} \quad \| x \| < \delta \rightarrow \| Tx \| < \epsilon $ choose $y,z \in V$ such that $x = y-z$ then 
- $$\| x \| < \delta \iff \| y-z \| < \delta \rightarrow \| Tx \| < \epsilon$$ $$\iff$$ $$\| T(y-z) \| = \| Ty-Tz) \|< \epsilon$$ 
<hr>

(2) $\rightarrow$ (3) <br>
Suppose $T$ is continuous at $0$, i.e. $\forall_{x\in V} \forall_{\epsilon > 0} \, \exists_{\delta > 0} \quad \| x \| < \delta \rightarrow \| Tx \| < \epsilon$ choose $0 < c < \delta$ then
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
- $$\forall_{x,y \in V} \forall_{\epsilon >0} \exists_{\delta = \frac{\epsilon}{C}$$  such that $$\Vert x-y \Vert < \delta$$ $$\rightarrow$$ $$\Vert Tx - Ty \Vert < \epsilon$$ 

</div>

**Terminology**

Let $T:V \rightarrow W$ be a linear operator. If $T$ is, in addition, continuous, we call $T$ a bounded operator, and $\Vert T \Vert$ the operator norm of $T$. Finally, we denote the set of all bounded operators from $V \rightarrow W$ with
> $$L(V,W):= \rbrace  T: V \rightarrow W \vert  \begin{cases} (1) \text{T} \; \text{linear} \\ (2) \text{T} \; \text{bounded} \end{cases}  \lbrace $$

<div class="proposition" markdown="1">

**Proposition 2.02**

$(L(V,W),  \Vert \cdot \Vert)$ is a normed space where $\Vert \cdot \Vert : L(V,W) \rightarrow \mathbb{R}$ is the operator norm on $L(V,W)$.
</div>

<div class="proof" markdown="1">

*Proof:*

It is clear enough that $L(V,W)$ is a vector space, what must be checked is that $\Vert \cdot \Vert$ satisfies the norm properties.
1. $$ \Vert T \Vert \ge 0$$ $$\forall T \in L(V,W)$$ and $$ \Vert T \Vert = 0 \iff T = 0$$