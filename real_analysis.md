---
layout: post
title: 'Real Analysis'
---

<blockquote>
        It is not enough to have a good mind; the main thing is to use it well.
        <footer>Descartes</footer>
</blockquote>

<hr>

A good mind, already a rare thing, and the best of us struggle to use our minds at all, let alone use them well.

## 1. Real Numbers

### Binary Relations

In simple terms, a binary relation between two sets is a rule of association between elements of each set. 

Consider the *cartesian product* of sets $A$ and $B$
> $A \times B = \lbrace (a,b): \quad a \in A, \; b \in B \rbrace$

We will see that the cartesian product is the most general binary relation between sets as each element in one is associated with every element of the other.

<div class="definition" markdown="1">

**Definition: Binary Relation**

Given $A, B$ any subset $\sigma \subset A \times B$ is called a binary relation. We denote an element of binary relation $\sigma$ with $(a,b) \in \sigma,$ or we may equivalently write $a \; \sigma \; b$
- In the case that $A = B,$ we say that $\sigma \subset A \times A$ is a binary relation on A.
</div>

In general a binary relation between sets $A$ and $B$ defines a map from $A$ to $B$ iff it is a transitive relation. 
- i.e. $\sigma \subset A \times B$ is a map $:A \rightarrow B$ $\iff$ $\begin{cases} a \; \sigma \; b \\ b \; \sigma \; c \end{cases} \implies a \; \sigma \; c$

<div class="example" markdown="1">

**Examples: Binary Relation**

Some instructive examples of binary relations:
1. Let $A$ be the set of all straight lines in the plane, we define $\sigma \subset A \times A$ such that 
    > $a \; \sigma \; b$ $\iff a \parallel b$
2. Again, let $A$ be the set of all straight lines in the plane
    > This time we define $\sigma \subset A \times A$ such that $a \; \sigma \; b \iff a \perp b$
3. Let $A_m = \mathbb{Z}$ the set of all integer numbers with $m$ some fixed integer, we define $\sigma \subset A \times A$ such that 
    > $a \; \sigma \; b \iff a \equiv b \; mod \; m \iff \exists k \in \mathbb{Z}$ such that $a-b = km$
4. Let $X$ be any set and put $A = 	\mathcal{P}(X)$ the set of all subsets of $X,$ we define $\sigma \subset A \times A$ such that 
    >  $a \; \sigma \; b \iff a \subset b$ where $a,b \subset X$
5. Let $A = \mathbb{R}$ and $B = \mathbb{C},$ we define $\sigma \subset A \times B$ such that,
    >  $t \; \sigma \; z \iff$ $z = e^{it}$
</div>

*Properties of Binary Relations:*
1. $\sigma \subset A \times A$ is called **reflexive** if $\forall a \in A$ we have $a \; \sigma \; a$
    - $1,3,4$ are reflexive relations, $2,5$ are not.
2. $\sigma \subset A \times A$ is called **transitive** if $\forall a,b,c \in A$ if $a \; \sigma \; b$ and $b \; \sigma \; c$ then $a \; \sigma \; c$
    - $1,3,4$ are transitive relations, $2,5$ are not.
3. $\sigma \subset A \times A$ is called **symmetric** if $\forall a,b \in A$ if $a \; \sigma \; b$ then $b \; \sigma \; a$
    - $1,2,3$ are symmetric relations $4,5$ are not.
4. $\sigma \subset A \times A$ is called **anti-symmetric** if $\forall a,b \in A$ if $a \; \sigma \; b$ and $b \sigma a$ then it must be the case that $a = b$
    - Only $4$ is an anti-symmetric relation.
5. $\sigma \subset A \times A$ is called an **equivalence relation** if it is at once reflexive, transitive and symmetric.
    - $1,3$ are equivalence relations, $2,4,5$ are not.
6. $\sigma \subset A \times A$ is called a **partial order** if it is at once reflexive, transitive, and anti-symmetric 
    - Only $4$ is a partial order.

<div class="example" markdown="1">

**Statement on Equivalence Relations**

Let $\sigma$ be an equivalence relation on $A,$ then $\sigma$ *partitions* $A,$ i.e. denote by $\sigma_x$ the set of all elements from $A$ equivalent to $x$ ($y \in \sigma_x \iff y \; \sigma \; x$)
1. $\forall x \in A$ there exists a unique $\sigma_x$ such that $x \in \sigma_x$
2. $\forall x,y \in A$ either $\sigma_x = \sigma_y$ or $\sigma_x \cap \sigma_y = \emptyset$
3. $ \bigcup_{x \in A}$ $= A$
</div>

### Algebraic Operations

An algebraic operation on a set is any map from the cartesian product of a set with itself to the set.

<div class="definition" markdown="1">

**Definition: Algebraic Operation**

We call any map $\phi: A \times A \rightarrow A$ an algebraic operation.

When it is unclear, we will denote an algebraic operation as a pair $(A, \phi)$
specifying the map and the set on which it acts.
</div>

<div class="example" markdown="1">

**Examples: Algebraic Operations**

Some instructive examples and non-examples of algebraic operations:
1. Let $A = \mathbb{N}$ the set of natural numbers
    - $(\mathbb{N}, +)$ is an algebraic operation.
    - $(\mathbb{N}, -)$ is not an algebraic operation.
2. Let $A = \mathbb{Z}$ the set of integers
    - $(\mathbb{Z}, +),(\mathbb{Z}, -),(\mathbb{Z}, \cdot)$ are algebraic operations.
    - $(\mathbb{Z}, \div)$ is not an algebraic operation.
3. Let $A = \mathbb{Q}$ the set of rational numbers
    - $(\mathbb{Q}, +),(\mathbb{Q}, -),(\mathbb{Q}, \cdot),(\mathbb{Q}, \div)$ are all algebraic operations.
3. Let $A = \mathbb{R}$ the set of real numbers
    - $(\mathbb{R}, +),(\mathbb{R}, -),(\mathbb{R}, \cdot),(\mathbb{R}, \div)$ are all algebraic operations.
</div>

### Fields

Simply, a field is a set on which algebraic operations behave as they do on $\mathbb{R}$ and $\mathbb{Q}$

<div class="definition" markdown="1">

**Definition: Field**

A set $\mathbb{F},$ containing at least the two elements $\mathbb{1}, \mathbb{0}$, is called a **field** if it is equipped with two field (algebraic) operations, $+$ and $\cdot,$ satisfying the following conditions:
1. Conditions on addition operation $+: \quad$ $\forall a,b,c \in \mathbb{F}$ 
    1. *Associativity:* $a + (b+c) = (a+b) + c$
    2. *Additive Identity:* $a + \mathbb{0} = \mathbb{0} + a = a$
    3. *Additive Inverse:* For all $a$ there exists a unique $b$ such that $a+b = b+a = \mathbb{0}$
    4. *Commutativity:* $a+b = b+a$
2. Conditions on multiplicative operation $\cdot: \quad$ $\forall a,b,c \in \mathbb{F}$ 
    1. *Associativity:* $a \cdot (b \cdot c) = (a \cdot b) \cdot c$
    2. *Multplicative Identity:* $a \cdot \mathbb{1} = \mathbb{1} \cdot a = a$
    3. *Multplicative Inverse:* For all $a \neq 0$ there exists a unique $b$ such that $a \cdot b = b \cdot a = \mathbb{1}$
    4. *Commutativity:* $a \cdot b = b \cdot a$
3. Conditions between $+$ and $\cdot: \quad$ $\forall a,b,c \in \mathbb{F}$ 
    1. *Right Distributivity* $(a+b) \cdot c = a \cdot c + b \cdot c$
    2. *Left Distributivity* $c \cdot (a+b) = c \cdot a + c \cdot b$
</div>

We say that $\mathcal{S} \subset \mathcal{F}$ is a **subfield** of the field $\mathcal{F}$ if it is a field in its own right with the field operations of $\mathcal{F}.$

<div class="example" markdown="1">

**Examples: Fields**

Some instructive examples and non-examples of fields:
1. $\mathbb{Q},\mathbb{R},\mathbb{C}$ are fields
2. $\mathbb{Z}$ is not a field
3. The set of rational functions over $\mathbb{R},$ $X = \lbrace \frac{a_0 + a_1x + \cdots + a_n x^n}{b_0 + b_1x + \cdots + b_m x^m} \rbrace$ with $a_i, b_j \in \mathbb{R}$ is a field.
</div>

### Order

Informally, we think of an ordered set as a set $A$ equipped with a binary relation $\leq \in A \times A$ that describes a comparison rule between its elements. 

<div class="definition" markdown="1">

**Partial and Total Orders**

Let $A$ be a set and $\leq \in A \times A$ a binary relation
1. We say that $\leq$ is a partial order on $A$ if it is reflexive, transitive, and anti-symmetric, i.e. 
    - *Reflexive:* every element is comparable to itself, $a \leq a$
    - *Transitive:* comparable elements form a *chain*, $a \leq b \, \land b \leq c \implies a \leq c$
    - *Anti-Symmetric:* elements may only be compared in at most one direction, if $a \leq b$ then not $b \leq a$
2. We say that $\leq$ is a total order on $A$ if it is a partial order with the condition that any two elements are comparable, i.e.
    - *Totality:* If $a,b \in A$ then either $a \leq b$ or $b \leq a$

</div>

<div class="example" markdown="1">

**Examples: Ordered Sets**

Some instructive examples of ordered sets:
1. $(\mathbb{R},<)$ and $(\mathbb{R},\leq)$ describe respectively total and partial orders on $\mathbb{R}$
2. Any set $M$ can be partially ordered with the following relation
    - $a \; \sigma \; b$ $\iff$ $a=b$
</div>

We call sets with partial and total orders partially and totally ordered, respectively. The ordering of field comes with the extra complication that the relation respect field operations.

<div class="definition" markdown="1">

**Ordered Field**

Let $\mathbb{F}$ be a set with total order $\leq \subset \mathbb{F} \times \mathbb{F}$ we say that $\mathbb{F}$ is ordered if $\forall a,b,c \in \mathbb{F}$
1. The order respects addition: $a \leq b \implies a+c \leq b+c$
2. The order respects multiplication: $a \leq b \implies ac \leq bc$ for $c \geq \mathcal{0}$

</div>

<div class="example" markdown="1">

**Examples: Ordered Fields**

Some instructive examples and ordered fields:
1. $(\mathbb{Q}, \leq), (\mathbb{R}, \leq)$ are ordered fields
2. Any subfield of an ordered field is again ordered.
3. The field of rational functions is an ordered field.
</div>

The canonical example of an ordered field is the real numbers. We will introduce the notion of order-completeness and the archimedian property
which provide sufficient condtitions for a field isomorphism to $\mathbb{R}.$

**Fundamental Concepts from Analysis**

Assume $(\mathbb{F}, \leq)$ is an ordered field with $A \subset \mathbb{F}$
1. $A$ is called bounded from above with *upper bound* $\alpha$ if
    > $\exists \alpha \in \mathbb{F}$ such that $\forall x \in A$ $x \leq \alpha$
2.  $A$ is called bounded from below with *lower bound* $\beta$ if
    > $\exists \beta \in \mathbb{F}$ such that $\forall x \in A$ $ \beta \leq x$
3. An element $\gamma \in \mathbb{F}$ is called a *supremum* for $A$ if
    1. $\gamma$ is an upper bound for $A$
    2. If $\gamma'$ is also an upper bound for $A$ then $\gamma \leq \gamma',$ i.e. $\gamma$ is the least upper bound for $A$
4. An element $\delta \in \mathbb{F}$ is called a *infimum* for $A$ if
    1. $\delta$ is an lower bound for $A$
    2. If $\delta'$ is also an lower bound for $A$ then $\delta' \leq \delta,$ i.e. $\delta$ is the greatest lower bound for $A$

If a supremum for $A \subset \mathbb{F}$ belongs to $A$ then we call it a maximum of $A.$ 
Similarly, we define a minimum of $A$ as a greatest lower bound belonging to $A.$

<div class="proposition" markdown="1">

**Proposition**

Any supremum for a subset of the real numbers, $A \subset \mathbb{R}$, is also a limit point. i.e.
- $\forall \epsilon > 0$ $\exists a \in A$ such that $\sup{A} \leq a + \epsilon$
</div>

<div class="proof" markdown="1">

*Proof:*

Let $\sup{A}$ be the supremum of some set $A \subset \mathbb{R}$. Suppose, for contradiction, that $\sup{A}$ is not a limit point of $A$ i.e. suppose
- $\exists \epsilon > 0$ such that $\forall a \in A$ $\sup{A} > a + \epsilon$

Then the quantity $\sup{A} - \epsilon$ is an upper bound for $A$ and as $\epsilon > 0$ $\sup{A} - \epsilon < \sup{A}$.

However, $\sup{A}$ was assumed to be the *least* upper bound for $A$, contradiction.
</div>

<div class="problem" markdown="1">

**Problem**

Let $A,B \subset \mathbb{R}$ be bounded above. Show that
> $A + B = \lbrace x+y \in \mathbb{R} \; \vert \; x \in A, \; y \in B \rbrace$

is bounded above, and that
> $\sup{(A+B)} = \sup{A} + \sup{B}$

[Solution](/pdf/RA_HW1_1.pdf)

</div>


<div class="definition" markdown="1">

**Order-Complete Fields**

An ordered field $\mathbb{F}$ is called order complete if any set bounded from above, $A \subset \mathbb{F},$ admits a supremum.

Equivalently, we might require the existence of a infimum for any set bounded from below.
</div>

<div class="example" markdown="1">

**Examples: Order-Complete Fields**

Some instructive examples and nonexamples of order-complete fields:
1. $(\mathbb{R}, <)$ is order complete.
2. $(\mathbb{Q}, <), (\mathbb{N}, <), (\mathbb{Z}, <)$ are not order complete.
    - Indeed, put $A:= \lbrace x \in \mathbb{Q}: \quad x^2 < 2 \rbrace$ which has supremum $\sqrt{2} \notin \mathbb{Q}$
</div>

The Archimedian property is very nicely described by Euclid himself. In Book $\textrm{V}$ of Euclid's Elements we read
<blockquote>
        Magnitudes are said to have a ratio to one another which can, when multiplied, exceed one another.
</blockquote>

<div class="definition" markdown="1">

**Archimedian Property**

We say that an ordered field $(\mathbb{F}, <)$ is Archimedian if 
> $\forall a,b \in \mathbb{F}$ with $a < b$ 
    >$\exists n \in \mathbb{N}$ such that $b < na $
</div>

<div class="proposition" markdown="1">

**Proposition:** 

Any complete ordered field is Archimedian.

</div>

<div class="proof" markdown="1">

*Proof:*

Let the field, $(\mathbb{F}, <),$ be order complete.
> $\iff$ any bounded set $A \subset \mathbb{F}$ admits a supremum

Suppose, by contradiction, that $\mathbb{F}$ is not Archimedian
> $\rightarrow$ $\exists a,b \in \mathbb{F}$ with $a < b$ such that $\forall n \in \mathbb{N}$ we have $na < b$

Now, take the set $A: = \lbrace na \rbrace_{n \in \mathbb{N}},$ by negation of the Archimedian property this set is bounded above by $b \in \mathbb{F}.$

Also, by order completeness of $\mathbb{F},$ we are guarenteed the existence of some supremum $\gamma = \sup A$
> $\rightarrow$ $\forall n \in \mathbb{N}$ we have $na < \gamma$

> In particular we have $\forall n \in \mathbb{N} \,$ $(n+1)a < \gamma$ 

> $\rightarrow$ $\forall n \in \mathbb{N} \,$ $na + a < \gamma$ $\rightarrow$ $na < \gamma - a < \gamma$

But now we must conclude that $\gamma - a$ is an upper bound for $A$ and $\gamma - a < \gamma$ which contradicts our assumption that
$\gamma$ is the *least upper bound* for $A$ and so the proposition follows.

</div>

<div class="proposition" markdown="1">

**Proposition:** 

It is not possible to define an order, $<,$ on the complex numbers such that the restriction of $(\mathbb{C}, <)$ to 
$(\mathbb{R}, <)$ coincides with the natural order on the reals.

</div>

<div class="proof" markdown="1">

*Proof:*

Suppose, by contradiction, that such an order exists. 

Case $1:$ Assume that $0 < i$ 

Then, by the axioms of ordered fields, 
> $0 \cdot i < i \cdot i $ $\rightarrow$ $0 < -1,$ 
    > contradiction. 

Case $1:$ Assume that $i < 0$ 

Then, $0 < -i$ and by the axioms of ordered fields 
> $0 \cdot -i < -i \cdot -i $ $\rightarrow$ $0 < -1,$ 
    > again a contradiction. 
</div>

### Topology in $\mathbb{R}$

Given $a \in \mathbb{R}$ we denote by $N_{\epsilon}(a) = \lbrace  x \in \mathbb{R}: a - \epsilon < x < a + \epsilon \rbrace$ the *$\epsilon-$ 
neighborhood* of $a$ 
and by $N^{\star}_{\epsilon}(a) = N_{\epsilon}(a) \setminus \lbrace a \rbrace $ the *deleted* $\epsilon$ 
-neighborhood of $a$.

**Fundamental Concepts from Topology take $A \subset \mathbb{R}$** 
1. $a \in A$ is called an *interior point* of $A$ if $\exists \epsilon > 0$ such that $N_{\epsilon}(a) \subset A$
    - We denote the union of all interior points with $int(A)$ and call this set the *interior* of $A$
2. $b \in A$ is called a *boundary point* of $A$ if $\forall \epsilon > 0$ the neighborhood $N_{\epsilon}(b)$ has nonempty intersection with both $A$ and its complement $A^{C}$ i.e. if  $N_{\epsilon}(b) \cap A \neq \emptyset$ $\land$ $N_{\epsilon}(b) \cap A^{C} \neq \emptyset$
    - We denote the union of all boundaary points with $\partial(A)$ and call this set the *boundary* of $A$
3. $c \in A$ is called an *accumulation point* of $A$ if  $\forall \epsilon > 0$ the deleted neighborhood of $c$ has nonempty intersection with $A$ i.e. if $N^{\star}_{\epsilon}(c) \cap A \neq \emptyset$
4. $d \in A$ is called an *isolated point* of $A$ if $\exists \epsilon > 0$ such that $N_{\epsilon}(d) \cap A = \lbrace d \rbrace$
5. The union of of accumulation points and isolated points constitute a set called the limit points of $A$
6. We define the closure of $A$ as the union of $A$ and the limit points of $A$.
    - The closure of $A$ is often denoted $cl(A) = A \cup \lbrace $ limit points of $A \rbrace$

$A$ is called *open* if $A = int(A),$ in turn we say that $A$ is *closed* if $A^{C}$ is open. $A$ is said to be *compact* if it is both bounded and closed

### Metric Spaces

A metric space is a set together with a map, called a metric, that defines a rule of distance between elements of the set. A well defined concept of distance must be understood as a pillar of analysis without which the analysist would be unable to take limits, define continuity or begin to explore calculus.

<div class="definition" markdown="1">

**Metric Space**

A set $M$ is called a metric space if there exists a map $\rho : M \times M \rightarrow \mathbb{R}$ satisfying 
the metric properties $\forall x,y,z \in M$
1. *Positive Semi-Definiteness:* $\rho(x,y) \geq 0$
2. *Indiscernibility:* $\rho(x,y) = 0 \iff x = y$
3. *Symmetry:* $\rho(x,y) = \rho(y,x)$
4. *Triangle Inequality:* $\rho(x,y) \leq \rho(x,z) + \rho(z,y)$

</div>

<div class="example" markdown="1">

**Examples: Metric Spaces**

Some instructive examples of metric spaces:
1. It is the case that any set $X$ can be made into a metric space with the so-called trivial metric
    > $\rho(x,y) =$ $\begin{cases}1, \quad x \neq y \\ 0, \quad x=y \end{cases}$
2. Consider $M = \mathbb{R}^n$ where $\mathbb{R}^n := \lbrace (x_1,x_2, \ldots, x_n): \quad x_i \in \mathbb{R} \forall i \rbrace$ and define the $p-$ metric
    > $\rho(x,y)_p =$ $(\sum_{i=1}^{n} \vert x_i - y_i \vert^p)^{\frac{1}{p}}$ 
3. Take $M = C([a,b],\mathbb{R})$ the space of real-valued, continuous functions defined over the interval $[a,b] \subset \mathbb{R}$ and define the supremum metric
    > $\rho(f,g) =$ $\sup_{x \in [a,b]} \vert f(x) - g(x) \vert$
4. Again, take $M = C([a,b],\mathbb{R})$ but this time define the integral metric
    > $\rho(f,g) =$ $\int_a^b \vert f(x) - g(x) \vert dx$ 
5. Consider the set of convergent infinite sequences $M = \ell^2 := \lbrace (x_1,x_2,\ldots): \quad \sum_{i=1}^{\infty} \vert x_i \vert^2 < \infty \rbrace$ equipped with the euclidean metric
    > $\rho(x,y) =$ $( \sum_{i=1}^{\infty} \vert x_i - y_i \vert^2 )^{\frac{1}{2}}$
</div>

### Topology in Metric Spaces

In order to define topological concepts in $\mathbb{R}$ we first had to introduce the $\epsilon$- neighborhood of a point.
Given a metric space, $(M, \rho),$ we generalize the notion of a neighborhood with the open ball centered at a point $x_0 \in M$ with radius $r$, $B_r(x_0):= \lbrace x \in M: \rho(x,x_0)< r \rbrace$, 
Now the topological concepts in $(M, \rho)$ using balls follow
as they did in $\mathbb{R}$ using neighborhoods.

**Fundamental Concepts from Topology take $A \subset M$** 
1. $a \in A$ is called an *interior point* of $A$ if $\exists \epsilon > 0$ such that $B_{\epsilon}(a) \subset A$
    - We denote the union of all interior points with $int(A)$ and call this set the *interior* of $A$
2. $b \in A$ is called a *boundary point* of $A$ if $\forall \epsilon > 0$ the ball $B_{\epsilon}(b)$ has nonempty intersection with both $A$ and its complement $A^{C}$ i.e. if  $B_{\epsilon}(b) \cap A \neq \emptyset$ $\land$ $B_{\epsilon}(b) \cap A^{C} \neq \emptyset$
    - We denote the union of all boundaary points with $\partial(A)$ and call this set the *boundary* of $A$
3. $c \in A$ is called an *accumulation point* of $A$ if  $\forall \epsilon > 0$ the deleted ball of $c$ 
has nonempty intersection with $A$ i.e. if $B^{\star}_{\epsilon}(c) \cap A \neq \emptyset$
4. $d \in A$ is called an *isolated point* of $A$ if $\exists \epsilon > 0$ such that $B_{\epsilon}(d) \cap A = \lbrace d \rbrace$
5. The union of of accumulation points and isolated points constitute a set called the limit points of $A$
6. We define the closure of $A$ as the union of $A$ and the limit points of $A$.
    - The closure of $A$ is often denoted $cl(A) = A \cup \lbrace $ limit points of $A \rbrace$

Just as with subsets of $\mathbb{R},$ $A$ is called *open* if $A = int(A),$ in turn we say that $A$ is *closed* if $A^{C}$ is open. $A$ is said to be *compact* if it is both bounded and closed

<div class="proposition" markdown="1">

**Proposition:** 

Let $A \subset X$ for some metric space $(M, \rho)$ then $cl(A)$ is the minimal closed subset of $X$ that contains $A$ 

</div>

<div class="proof" markdown="1">

*Proof:* 

That $cl(A)$ is closed follows from the face that closure is an idempotent operation, i.e. that $cl(cl(A)) = cl(A)$. We will show that any other closed set containing $A$ must also contain $cl(A)$.

Recall that the closure of $A$ is defined to be the union of $A$ the limit points of $A$. Let $B \subset X$ be a closed set with $A \subset B$. As $B$ is closed, it contains all of its limit points. Let $\lbrace a_n \rbrace \subset A$ be a sequence with $a_n \rightarrow a$. As $\lbrace a_n \rbrace$ also belongs to $B$ and $B$ is closed it must be that $a \in B$. Hence, as $B$ contains both $A$ and all of its limit points $B$ must also contain the closure of $A$.

</div>

<div class="problem" markdown="1">

**Problem:** 

Let $X$ be a metric space. Show that for $A,B \subset X$ the closure satisfies the following properties:
1. If $A \subset B$ then $cl(A) \subset cl(B)$.
2. $cl(A\cup B) = cl(A) \cup cl(B)$ $$
3. $cl(A \cap B) \subset cl(A) \cap cl(B)$ $$

[Solution](/pdf/RA_HW1_3.pdf)

</div>

<div class="proposition" markdown="1">

**Statement:** Let $(M,\rho)$ be a metric space
1. The arbitrary union of open sets is open $M$. 
    - i.e. If $\lbrace U_{\alpha} \rbrace_{\alpha \in I}$ is an arbitrary collection of open subsets in $M$ then $\bigcup_{\alpha} U_{\alpha}$ is open.
2. The finite intersection of open sets is open in $M$
    - i.e. if $\lbrace U_{\alpha} \rbrace^{N}_{n=1}$ is a finite collection of open subsets in $M$ then $\bigcap^{N}_{n=1} U_{n}$ is open.
3. The arbitrary intersection of closed sets is closed $M$. 
    - i.e. If $\lbrace V_{\alpha} \rbrace_{\alpha \in I}$ is an arbitrary collection of closed subsets in $M$ then $\bigcap_{\alpha} V_{\alpha}$ is closed.
4. The finite union of closed sets is closed in $M$
    - i.e. if $\lbrace V_{\alpha} \rbrace^{N}_{n=1}$ is a finite collection of closed subsets in $M$ then $\bigcup^{N}_{n=1} V_{n}$ is closed.
</div>

<div class="example" markdown="1">

**Example:** The arbitrary intersection of open subsets of a metric space is not, in general, open.

Consider the family of open neighborhoods of the origin $A = \lbrace (-\frac{1}{n},\frac{1}{n}) \rbrace^{\infty}_{n=1}$

The intersection of this family is the singleton set $0 = \bigcap^{\infty}_{n=1} (-\frac{1}{n},\frac{1}{n})$ which is, 
of course, closed in $\mathbb{R}$.

</div>

Now that we have reviewed some fundamental concepts of topology in metric spaces we are ready to define the notion of
convergence in a metric space.

<div class="definition" markdown="1">

**Convergence in Metric Spaces:**

Let $(M, \rho)$ be a metric space, a sequence $\lbrace x_n \rbrace \subset M$ is said to be convergent to an element $a \in M$ if 
all but finitely many terms of the sequence belong to any neighborhood of $a,$ i.e. 
- $ \lim_{n \rightarrow \infty } \lbrace x_n \rbrace = a$ $\iff$ $\forall \epsilon > 0 \exists N \in \mathbb{N}: \, \forall n > N \, 
    \rho(x_n,a) < \epsilon$

</div>

<div class="definition" markdown="1">

**Cauchy Sequences:**

Given a metric space $(M, \rho)$ a sequence $\lbrace x_n \rbrace \subset M$ is called a Cauchy sequence if its terms 
become arbitarily close together, i.e.
- $\lbrace x_n \rbrace$ Cauchy $\iff$ $\forall \epsilon > 0 \exists N \in \mathbb{N}: \, \forall n,m > N \, \rho(x_n,x_m)< \epsilon$
</div>

<div class="proposition" markdown="1">

**Proposition:** 

Any convergent sequence in a metric space is a Cauchy sequence.
</div>

<div class="proof" markdown="1">

*Proof:* 

Given metric space $(M, \rho),$ suppose $\lbrace x_n \rbrace \subset M$ is convergent to $a \in M$
> $\rightarrow$ $\lim_{n \rightarrow \infty } \rho(x_n, a) = 0$

Now consider the distance between the $n$-th and $m$-th terms of our sequence. By the triangle inequality metric axiom:
> $\rho(x_n, x_m) \leq \rho(x_n, a) + \rho(x_m, a)$

Where, both terms on the RHS of the inequality vanish in the limit such that
> $\lim_{n \rightarrow \infty } \rho(x_n, x_m) = 0$
</div>

<div class="example" markdown="1">

**Example:** The inverse statement, that any Cauchy sequence in a metric space $(M, \rho)$ must converge in $M$ is not true, in general.

Consider the sequence $\lbrace 2, 2.7, 2.71, 2.718, 2.7182, 2.71828, 2.718281, \ldots \rbrace$ which converges to Euler's constant $e.$ 
We note that this is a sequence of rational numbers and yet the sequence does not converge in $\mathbb{Q}$

</div>

This last example gives motivation for the concept of a complete metric space.

<div class="definition" markdown="1">

**Complete Metric Space:**

A metric space, $(M, \rho),$ is called complete if any Cauchy sequence in $M$ converges to an element of the space.
</div>

<div class="example" markdown="1">

**Examples: Complete Metric Spaces**

Some instructive examples of complete metric spaces:
1. $(X, \rho)$ is a complete metric space for any set $X$ and the trivial metric $\rho(x,y) = \begin{cases}1, \quad x \neq y \\ 0, \quad x=y \end{cases}$
    - Indeed, let $\lbrace x_n \rbrace$ be a Cauchy sequence in $X$ and choose $\epsilon = \frac{1}{2},$ we are guarenteed the existence of some $N \in \mathbb{N}$ such that $\forall n,m > N \, \rho(x,y) < \frac{1}{2}$ but then $\rho(x,y) = 0$ $\rightarrow$ $x=y.$ 
    - Hence, any Cauchy sequence in such a metric space must become constant for all indices $n >N$ and as such is convergent to that constant value, which belongs to $X$.
2. $(\mathbb{R}, \rho)$ is a complete metric space with the natural metric $\rho(x,y) = \vert x-y \vert$
    - This will be shown later.
3. $(\mathbb{R}^n, \rho_p)$ is a complete metric space, where $\rho_p(x,y) = (\sum^n_{i=1} \vert x-y \vert^p)^{\frac{1}{p}}$
4. Let $X =C([a,b],\mathbb{R})$ then for $\rho(f,g) =\sup_{x \in [a,b]} \vert f(x) - g(x) \vert,$ the metric space $(X, \rho)$ is complete
    - Take fundamental sequence of functions $\lbrace f_n \rbrace \subset X$
</div>

### Compactness in Metric Spaces

The *Heine-Borel Theorem* (for now stated without proof) is one of the central theorems in Real-Analysis and will serve
as motivation for a more general theorem concerning compactness in general metric spaces.

<div class="proposition" markdown="1">

**Heine-Borel Theorem:**

The following properties are equivalent in any Euclidean space $\mathbb{R}^n$ for the closed subset $S \subset \mathbb{R}^n$
1. If $\lbrace U_n \rbrace_{n \in I}$ is an open cover of $S$ then there exissts a finite subcover $\lbrace U_{n_1},U_{n_2}, \ldots U_{n_k} \rbrace$ with $S \subset \bigcup^k_{i=1} U_{n_i}$
2. Any sequence $\lbrace x_n \rbrace \subset S$ admits a convergent subsequence, $\lbrace x_{n_k} \rbrace,$ with $\lim_{k \rightarrow \infty} x_{n_k} \in S$
3. $S$ is bounded
</div>

<div class="definition" markdown="1">

**Compactness:**

Let $(M, \rho)$ be a metric space with subset $K \subset M$
1. $K$ is called compact if any open cover of $K$ admits a finite subcoverr
2. K is called sequentially compact if any sequence $\lbrace x_n \rbrace \subset K$ admits a subsequence convergent to some $a \in K$
</div>

<div class="proposition" markdown="1">

**Statement:**

For any metric space compactness is equivalent to sequential compactness.
</div>

This is not true for topological spaces in general. 
Furthermore, it is not in general true that for a metric space $(M, \rho)$ 
compactness is equivalent to closedness $+$ boundedness. 

<div class="example" markdown="1">

**Example: Closed, Bounded, but not Compact**

Take the metric space $(\ell^2,\rho)$ which we recall was equipped with the metric
> $\rho(x,y)$ $= ( \sum_{i=1}^{\infty} \vert x_i - y_i \vert^2 )^{\frac{1}{2}}$

Consider the unit sphere $S^{\infty} \subset \ell^2,$ the set of all vectors in $\ell^2$
with distance $1$ away from the origin.
> $S^{\infty}:= \lbrace x \in \ell^2: \rho(x,0) \rbrace = 1$ where $0 = (0,0,\ldots)$

Such a subset is both closed and bounded but we will show that it is not sequentially compact. Indeed consider the sequence
> $\begin{cases} (1,0,0,0,\ldots) \\ (0,1,0,0,\ldots) \\ (0,0,1,0,\ldots) \\ \cdots  \end{cases}$

Clearly this sequence does not admit any convergent subsequences. Indeed, let $z_j \in \ell^2$ denote the element with a $1$ 
in its $j$-th index and $0$s otherwise, then
> $\rho(z_j,z_i) = 2$ $\forall i,j \in \mathbb{N}$

</div>

Though the Heine-Borel Theorem proposes that closedness $+$ boundedness is an equivalent condition to compactness 
in Euclidean spaces, it has been demonstrated that this is not the case in general metric spaces. We will need the following 
definition to generalize the result.

<div class="definition" markdown="1">

**Totally Bounded**

Given a metric space $(M, \rho),$ a set $K \subset M$ is called totally bounded if it can be covered by finitely many
balls of any fixed size, i.e.
> $K \subset M$ is totally bounded $\iff$ $\forall \epsilon > 0$ $\exists x_1,\ldots,x_n \in K$ such that $K \subset \bigcup^n_{i=1} B_{\epsilon}(x_i)$
</div>

<div class="proposition" markdown="1">

**Theorem:**

The followinig conditions are equivalent for any subset of a metric space.
1. Compactness (in the sense of open covers)
2. Sequential Compactness
3. Total Boundedness $+$ Completeness (or Closedness)
</div>

### Continuity In Metric Spaces

We recall the $\epsilon - \delta$ definition of continuity of real functions: informally that closeness of elements in the domain
imply closeness of their images in the codomain. We will generalize this notion to functions between metric spaces. 

<div class="definition" markdown="1">

**Continuity**

Given two metric spaces $(M_1, \rho_1),$ $(M_2, \rho_2),$ and a map $f: M_1 \rightarrow M_2$ then
1. $f$ is called continuous at $x_0 \in M_1$ if $\forall \epsilon > 0 \, \exists \delta > 0$ such that
    > $\rho_1(x,x_0) < \delta$ implies $\rho_2(f(x),f(x_0)) < \epsilon$
2. $f$ is called sequentially continuous if $x_n \rightarrow x_0$ implies $f(x_n) \rightarrow f(x_0)$
3. $f$ is said to be open if for any open subset $U \subset M_2,$ its preimage $f^{-1}(U)$ is open in $M_1$
4. If $f$ is continuous at any point of some subset $A \subset M_1$ then we say that $f$ is continuous on $A$

Continuity, sequential continuity, and openess of a map are equivalent conditions.
</div>

<div class="proposition" markdown="1">

**Proposition**

If a map between metric spaces $f: M_1 \rightarrow M_2$ is continuous and $K \subset M_1$ is compact then its image
$f(K)$ is compact in $M_2$
</div>

<div class="proof" markdown="1">

*Proof:*

Take any sequence belonging to the image of $K,$ $\lbrace y_n \rbrace \subset f(K)$ and find the corresponding sequence $\lbrace x_n \rbrace \subset$ such that 
$f(x_n) = y_n$ $\forall n.$

As $K$ is compact, $\lbrace x_n \rbrace$ has a convergent subsequence $\lbrace x_{n_k} \rbrace$ with $x_{n_k} \rightarrow x_0 \in K$

As $f$ is continuous, it is sequentially continuous such that $f(x_{n_k}) \rightarrow f(x_0) \in f(K).$ 

So, any sequence $\lbrace y_n \rbrace \subset K$ has a convergent subsequence $\lbrace y_n = f(x_{n_k} \rbrace$ which converges in $f(K).$

Hence, $f(K)$ is sequentially compact $\iff$ $f(K)$ is compact.
</div>

A very useful corrolary to this proposition is the *Weierstrass Theorem* (also known as the extreme value theorem) which 
states that a continuous function on a compact set obtains its extreme values. We recall that for real functions the extreme
value theorem was formulated that a continuous function on a closed and bounded set obtains its extreme values.

<div class="proposition" markdown="1">

**Weierstrass Theorem**

Let $K$ be a compact subset of some metric space $M$ and $f:M \rightarrow \mathbb{R}$ a continuous map. Then $f$ achieves maximum
and minimum on $f(K)$.
</div>

<div class="proof" markdown="1">

**Proof:**

Let $K \subset M$ be a compact, then by the previous result, for any continuous map $f:M \rightarrow \mathbb{R}$ we
have that $f(K) \subset \mathbb{R}$ is compact.

As $\mathbb{R}$ is Euclidean, by Heine-Borel, we know that $f(K)$ compact $\iff$ $f(K)$ closed and bounded.

As a bounded subset of the order-complete field $\mathbb{R},$ $f(K)$ must admit both infimum and supremum.

As a closed set, $f(K)$ contains all of its limit points and in particular $\inf f(K), \sup f(K) \in f(K).$
</div>

Isometries are distance preserving bijections between metric spaces.

<div class="definition" markdown="1">

**Isometry**

Given two metric spaces $(M_1, \rho_1),$ $(M_2, \rho_2),$ a map $f: M_1 \rightarrow M_2$ is called
an isometry if $\forall x,y \in M_1$
1. $\rho_1(x,y) = \rho_2(f(x),f(y))$ $$
2. $f$ is bijective
</div>

### Completion of a Metric Space

<div class="definition" markdown="1">

**Completion of a Metric Space**

Given a metric space $(M', \rho),$ we say that it is the completion
of the metric space $(M, \rho)$ if 
1. $M'$ complete (in the sense of Cauchy sequences)
2. $M'$ contains $M$ i.e. $M \subset M'$
3. $M$ is dense in $M'$ i.e. $cl(M) = M'$
</div>

We will prove that every metric space has a completion which is unique up to isometry.

<div class="proposition" markdown="1">

**Theorem**

Given a metric space $(M, \rho),$ 
1. There exists a completion of $M$ 
2. If $M_1$ and $M_2$ are two completions of M, then
    - There exists an isometry $f: M_1 \rightarrow M_2$ such that $f \vert_M = \mathbb{1}$
</div>

<div class="proof" markdown="1">

*Proof:*

**Step 1:** Define Equivalence Relation

Denote by $\tilde{M}$ the set of all Cauchy sequences in metric space $(M, \rho)$ and take $\sigma$, a 
binary relation on $\tilde{M}$ defining the following rule
> $\lbrace x_n \rbrace \; \sigma \; \lbrace y_n \rbrace$ $\iff$ $\lim_{n \rightarrow \infty} \rho(x_n,y_n) = 0$

**Claim 1:** $\sigma$ is an equivalence relation which partitions $\tilde{M}$ into equivalence classes.
- verify

<hr>

**Step 2:** Construct Quotient Space

Take the quotient space $M^{\star}:= \tilde{M}/_{\sigma}$ and define the following metric on $M^{\star}$
> $(1)$ $\rho^{\star}(\bar{x}, \bar{y}) = \lim_{n \rightarrow \infty} \rho(x_n,y_n)$ where $\bar{x}, \bar{y}$ represent 
the Cauchy sequences $\lbrace x_n \rbrace,\lbrace y_n \rbrace$ respectively.

**Claim 1:** Such a map, $(1)$, exists. <br>
As $\mathbb{R}$ is complete, it is enough to show that $\rho(x_n,y_n)$ is a Cauchy sequence.
- Indeed, $\vert \rho(x_n,y_n) - \rho(x_m,y_m) \vert$ 
- *Add and subtract term:* $ = \vert \rho(x_n,y_n) - \rho(x_m,y_n) + \rho(x_m,y_n) - \rho(x_m,y_m) \vert$
- *Triangle Inequality:* $ \leq \vert \rho(x_n,y_n) - \rho(x_m,y_n) \vert + \vert \rho(x_m,y_n) - \rho(x_m,y_m) \vert$
- *Reverse Triangle Inequality:* $ \leq \rho(x_n,x_m) + \rho(y_n,y_m) \rightarrow 0$

**Claim 2:** The limit in $(1)$ is independent of choice of representative. <br>
- Assume $\lbrace x_n \rbrace \; \sigma \; \lbrace x_n' \rbrace \in [\bar{x}]$ and $\lbrace y_n \rbrace \; \sigma \; \lbrace y_n' \rbrace \in [\bar{y}]$
- We want to show that $ \vert \rho(x_n,y_n) - \rho(x_n',y_n') \vert \rightarrow 0,$ which follows from the same argument used above. 


**Claim 3:** $(1)$ is indeed a metric on $M^{\star}$ <br>
We will only show the triangle inequality.   
- Let $\bar{x}, \bar{y}, \bar{z} \in M^{\star}$ be represented by the Cauchy sequences $\lbrace x_n \rbrace, \lbrace y_n \rbrace, \lbrace z_n \rbrace \subset M$
- As $\rho: M \times M \rightarrow \mathbb{R}$ is a metric it satisfies the triangle inequality $\rho(x_n,y_n) \leq \rho(x_n,z_n) + \rho(z_n,y_n)$
- The inequality is preserved in the limit $\lim_{n \rightarrow \infty} \rho(x_n,y_n) \leq \lim_{n \rightarrow \infty} \rho(x_n,z_n) + \lim_{n \rightarrow \infty} \rho(z_n,y_n)$
- And by construction of $\rho^{\star}$ this is exactly $\rho^{\star}(\bar{x}, \bar{y}) \leq \rho^{\star}(\bar{x}, \bar{z}) + \rho^{\star}(\bar{y}, \bar{z})$

<hr>

**Step 3:** Realization of $M$ in $M^{\star}$

Take $x \in M,$ we must show that this element manifests as the limit point of some class of Cauchy sequences in $M^{\star}$
- Consider the stationary sequence $\lbrace x,x, \ldots \rbrace$ which is by inspection
    1. A Cauchy Sequence
    2. Convergent to $x \in M$
- As an equivalence relation on $\tilde{M}$ *partitions* the space, we are guaranteed our stationary sequence represents exactly one 
equivalence class in $M^{\star}$
- Hence, $M \subset M^{\star}$

<hr>

**Step 4:** Density of $M$ in $M^{\star}$

We will show that $cl(M) = M^{\star}:$ Take $\bar{x} \in M^{\star}$, fix $\epsilon > 0$, find Cauchy sequence, $\lbrace x_n \rbrace$ representing 
$\bar{x}$
- As $\lbrace x_n \rbrace$ is Cauchy $\exists N$ such that $\forall n,m > N$ we have $\rho(x_n,x_m)$
- Choose any $k > N$ and take the stationary sequence $\lbrace x_k,x_k, \ldots \rbrace$ and denote its equivalence class $\hat{x} \in M^{\star}$
- Now, $\lim_{n \rightarrow \infty} \rho(x_n, x_k) < \epsilon$ $\rightarrow$ $\rho^{\star}(\bar{x}, \hat{x}) < \epsilon$

<hr>

**Step 5:** Completeness of $M^{\star}$

$\ldots$

</div>

### Cantor's Construction of Real Numbers

## The Lebesgue Measure

### Construction of a Measure

The goal is to define the map $\mu: \mathcal{S} \rightarrow \mathbb{R}$ on some reasonable collection
of subsets of $\mathbb{R}^n,$ $ \mathcal{S}$ satisfying the following four properties of measure
1. *Positivity:* $\mu > 0$
2. *$\sigma$- additivity:*
3. *Normalization:* $\mu(I^n) = 1$ where $I = [0,1]$
4. *Congruency:* If $A$ is obtained from $B$ by translation or orthogonal transformation 
(i.e. if $A,B\subset \mathbb{R}^n$ are congruent) then $\mu(A) = \mu(B)$

Such a map is called a measure and its construction will be the focus of this section.

A reasonable question to ask: can a map satisfying these properties
be defined on $\mathcal{P}(\mathbb{R}^n),$ the set of all subsets of $\mathbb{R}^n$?

<div class="proposition" markdown="1">

**Proposition**

There is no map $\mu: \mathcal{P}(\mathbb{R}^n) \rightarrow \mathbb{R}$ satisfying the properties of measure.

</div>

<div class="proof" markdown="1">

*Proof:*

Assume for simplicity that $n=1,$ suppose, for contradiction, that $\mu: \mathcal{P}(\mathbb{R}) \rightarrow \mathbb{R}$ is a map
satisfying the listed properties.

Consider the family of subsets $\lbrace N_r \rbrace^{\infty}_{r=1}$ constructed such that
1. $ \bigcup_{r} N_r = [0,1)$ $ $
2. $ N_r \cap N_s = \emptyset$ for all $r \neq s$
3. $\mu(N_r) = \mu(N_s)$ for all $r,s$

As $\lbrace N_r \rbrace^{\infty}_{r=1}$ are disjoint and $\mu$ is $\sigma$- additive
- $\mu[0,1) = \sum^{\infty}_{r=1} \mu(N_r)$ $ $

And by normalization 
- $\sum^{\infty}_{r=1} \mu(N_r) = 1$ $ $

Now consider two cases that both lead to contradiction
1. *Case:* assume that $\forall r$ $\mu(N_r) = 0$
    - But then, $1 = 0 + 0 + \cdots = 0$ $\rightarrow$ contradiction.
2. *Case:* assume that $\forall r$ $\mu(N_r) = \alpha > 0$
    - But then, $1 = \alpha + \alpha + \cdots = \infty$ $\rightarrow$ contradiction.

What remains is to show that such a family of sets $\lbrace N_r \rbrace^{\infty}_{r=1}$ indeed exists.
</div>

### Lebesgue Measure on the Plane

<div class="definition" markdown="1">

**Measure on Rectangles**

Let $X$ be any one of the following sets 
> $[a,b],[a,b),(a,b],(a,b)$  $$

And $Y$ any one of 
> $[c,d],[c,d),(c,d],(c,d)$ $$

Then the set $P = X \times Y$ is called a **rectangle**.

In the degenerate case that either $a=b$ or $c=d$ then we say that the rectangle is *empty* and write $P = \emptyset$ 

We define the measure of a rectangle $P$ as follows:
> $\mu(P) = \begin{cases}(b-a)(d-c), \quad \text{if} \; \text{P} \neq \emptyset \\ 0, \quad \text{if} \; \text{P} = \emptyset \end{cases}$

</div>

<div class="proof" markdown="1">

It is clear that such a measure on the set of planar rectangles is well-defined and satisfies the four properties of measure
namely:
1. *Positivity:* $\mu \geq 0$ as $b>a$ and $d>c$
2. *$\sigma$- additivity:* If $\lbrace P_n \rbrace^{k}_{n=1}$ is a finite collection of disjoint rectangles we have
    - $ \mu(\bigcup^k_{n=1} P_n) = \sum^{k}_{n=1} \mu(P_n)$ $ $
3. *Normalization:* By inspection, $\mu([0,1] \times [0,1]) = 1 $
4. *Congruence*

</div>

So, we have a valid measure theory on the set of planar rectangles.
Our proximate goal is to extend this theory to as wide a collection of subsets of $\mathbb{R}^2$ as possible, while preserving
the properties of measure. The next step is to consider how our measure acts on sets built from finitely many disjoint rectangles.

<div class="definition" markdown="1">

**Elementary Sets**

A set $A \subset \mathbb{R}^2$ is called *elementary* if it can be represented as a finite union of disjoint rectangles.
</div>


<div class="proposition" markdown="1">

**Proposition**

Suppose that $A,B$ are elementary sets, then so are
1. $A \cap B$ $ $
2. $A \cup B$ $ $
3. $A \setminus B$ $ $
4. $A \Delta B = (A \cup B) \setminus (A \cap B)$ where $A \Delta B$ is called the symmetric difference of $A$ and $B$
</div>

<div class="proof" markdown="1">

*Proof:*

First, we make an observation: if $P,Q$ are rectangles then $P \cap Q$ is also a rectangle and $P \setminus Q$
is elementary.

Now assume $A,B$ are elementary with representations $A = \bigcup^n_{i=1} P_i$ and $B = \bigcup^k_{j=1} Q_j$ for rectangles $P_i,Q_j$

$(1)$ First we consider their intersection: $A \cap B$
- $A \cap B$ $=$ $ (\bigcup^n_{i=1} P_i) \bigcap (\bigcup^k_{j=1} Q_j)$ $=$ $\bigcup_{i,j} (P_i \cap Q_j)$ 

where $P_i \cap Q_j$ are rectangles by observation such that $A \cap B$ is indeed elementary.

<hr>

**Corollary:** Let $P$ be a rectangle and $A \subset P$ an elementary set. Then, $P \setminus A$ is also elementary.

*Proof:* 

Express our elementary set as a finite disjoint union of rectangles $A = \bigcup^n_{i=1} P_i$ Now,
- $P \setminus A = P \setminus \bigcup^n_{i=1} P_i = \bigcap^n_{i=1} (P \ P_i)$
- By initial observation, each $(P \ P_i)$ is elementary 
- And so, by result $(1)$ $P \setminus A$ is elementary

<hr>

$(2)$ Next we consider their union: $A \cup B$
- Take a rectangle $P$ containing both $A$ and $B$
- So, $A \cup B = P \setminus [(P \setminus A) \cap (P \setminus B)]$ 
- $(P \setminus A)$ and $(P \setminus B)$ are elementary by collary
- In turn, $A \cup B$ is elementary by corollary

<hr>

$(3)$ Consider their difference: $A \setminus B$
- Again, take a rectangle $P$ containing both $A$ and $B$
- Now, $A \setminus B = A \cap (P \setminus B)$ 
- $(P \setminus B)$ and $A \cap (P \setminus B)$ are elementary by collary and $(1)$ respectively.

<hr>

$(4)$ Finally consider their symmetric difference: $A \Delta B$
- Write $A \Delta B = (A \cup B) \setminus (A \cap B)$
- $A \Delta B$ is elementary by $(1),(2),(3)$

</div>

We are now equpped to extend our measure theory to include elementary sets. For simplicity, we will initially
only consider subsets of the unit square $E = [0,1] \times [0,1]$ and then show how this assumption is easily discarded.

<div class="definition" markdown="1">

**Measure on Elementary Sets**

Let $E =  = [0,1] \times [0,1]$ an take elementary set $A \subset E$ with expression as finite union of disjoint rectangles
> $A = \bigcup^n_{i=1} P_i$ where $\begin{cases} \lbrace P_i \rbrace \; \text{rectangles} \\ P_i \cap P_j = \emptyset \; i \neq j \end{cases}$

We define the measure of $A$ as
> $ \mu(A):= \sum^n_{i=1} \mu(P_i)$

</div>

Every elementary set must have expression as the finite union of disjoint rectangles, however, this expression need not be unique.
There is a reasonable concern that distinct rectangular partitions of $A$ might have different measures. We will prove that this is not 
the case.

<div class="proposition" markdown="1">

**Proposition**

The measure of an elementary set is independent of its partition.

</div>

<div class="proof" markdown="1">

*Proof:*

Given elementary $A$ take any two partitions
- $A = \bigcup^n_{i=1} P_i,$ $\bigcup^m_{j=1} Q_j$ $ \quad \begin{cases} \lbrace P_i,Q_j \rbrace \; \text{rectangles} \\ P_i \cap P_l = \emptyset \; i \neq l \\ Q_j \cap Q_k = \emptyset \; j \neq k \end{cases}$

We make the observation that
1.  $ \sum^n_{i=1} \mu(P_i) = \sum^n_{i=1} \sum^m_{j=1} \mu(P_i \cap Q_j)$ $ $
2.  $ \sum^m_{j=1} \mu(Q_j) = \sum^m_{j=1} \sum^n_{i=1} \mu(Q_j \cap P_i)$ $ $

Hence $\mu(A):= \sum^n_{i=1} \mu(P_i) = \sum^m_{j=1} \mu(Q_j)$

</div>

A measure must satisfy the properties of a measure, lets check that $\mu$ is $\sigma$-additive on elementary sets

<div class="proposition" markdown="1">

**Proposition**

The measure of an elementary set is $\sigma$-additive i.e.

Suppose $A, \lbrace A_n \rbrace^{\infty}_{n=1} \subset E$ are elementary sets with $A \subset \bigcup^{\infty}_{n=1} A_n$ then,
> $\mu(A) \leq \sum^{\infty}_{n=1} \mu(A_n)$
</div>

<div class="proof" markdown="1">

*Proof:*

Fix some $\epsilon > 0$

**Step 1:** Approximation of $A$ by compact subset

<hr>

As an elementary set, $A$ may be expressed as the finite union of disjoint rectangles
> $A = \bigcup^{k}_{i=1} B_i$ where $ \lbrace B_i \rbrace$ is the disjoint family of rectangles

For each $B_i$ find a closed rectangle $\hat{B}_i$ such that
1. $\hat{B}_i$ \subset B_i$ $$
2. $\mu(B_i) \leq \mu(\hat{B}_i) + \frac{\epsilon}{2k}$ $ $

Put $\hat{A}:= \bigcup^{k}_{i=1} \hat{B}_i,$ then 
1. $\hat{A}$ is an compact 
2. $\hat{A} \subset A$ $ $
3. $\mu(A) \leq \sum^{k}_{i=1} [\mu(\hat{B}_i) + \frac{\epsilon}{2k}]$ $$
    > $\leq \sum^{k}_{i=1} \mu(\hat{B}_i) + \sum^{k}_{i=1} \frac{\epsilon}{2k} $ $$
    > $ \leq \mu(\hat{A}) + \frac{\epsilon}{2}$ $$

**Step 2:** Open approximation of $\lbrace A_n \rbrace$ 

<hr>

For each $A_n$ find an elementary set $\mathring{A}_n$ such that
1. $A_n \subset \mathring{A}_n$ $ $
2. $\mathring{A}_n$ is open
3. $\mu(\mathring{A}_n) \leq \mu(A_n) + \frac{\epsilon}{2^{n+1}}$ $ $
 
**Step 3:** Application of Heine Borel

<hr>

We have both, $\hat{A} \subset A$ and $\bigcup^{\infty}_{n=1} A_n \subset \bigcup^{\infty}_{n=1} \mathring{A}_n$, by construction and $A \subset \bigcup^{\infty}_{n=1} A_n$ by assumption such that $\lbrace \mathring{A}_n \rbrace^{\infty}_{n=1}$ is an open cover of $\hat{A}$ i.e.
> $\hat{A} \subset  \bigcup^{\infty}_{n=1} \mathring{A}_n$ $$

As $\hat{A}$ is compact there exists a finite open subcover $\lbrace \mathring{A}_{n_1},\mathring{A}_{n_2}, \ldots, \mathring{A}_{n_s} \rbrace$ such that $\hat{A} \subset  \bigcup^{s}_{k=1} \mathring{A}_{n_k}$. As this cover is, in particular, *finite*, we have
> $\mu(\hat{A}) \leq \sum^{s}_{k=1} \mu(\mathring{A}_{n_k})$

Finally, as $\lbrace \mathring{A}_{n_1},\mathring{A}_{n_2}, \ldots, \mathring{A}_{n_s} \rbrace \subset \lbrace \mathring{A}_n \rbrace^{\infty}_{n=1}$ we can bound $\sum^{s}_{k=1} \mu(\mathring{A}_{n_k}) \leq \sum^{\infty}_{n=1} \mu(\mathring{A}_{n})$ such that
> $\mu(\hat{A}) \leq \sum^{\infty}_{n=1} \mu(\mathring{A}_{n})$

**Step 4:** Final Estimate

<hr>

In **(Step 1)** we obtained 
> $\mu(A) \leq \mu(\hat{A}) + \frac{\epsilon}{2}$ $$

In **(Step 3)** we further bound this with 
> $\mu(A) \leq \mu(\hat{A}) + \frac{\epsilon}{2} \leq \sum^{s}_{k=1} \mu(\mathring{A}_{n_k}) + \frac{\epsilon}{2} \leq \sum^{\infty}_{n=1} \mu(\mathring{A}_{n})  + \frac{\epsilon}{2}$

Now, using positivity of $\epsilon$ and linearity of addition,
> $\mu(A) \leq \sum^{\infty}_{n=1}{(\mu(\mathring{A}_{n})  + \frac{\epsilon}{2^{n+1}})} + \frac{\epsilon}{2}$ $$
> $ = \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \sum^{\infty}_{n=1}{\frac{\epsilon}{2^{n+1}}} + \frac{\epsilon}{2}$ $$
 > $ = \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \frac{\epsilon}{2} + \frac{\epsilon}{2} = \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \epsilon$ $$

And so, we have $\mu(A) \leq \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \epsilon$. As $\epsilon>0$ was chosen arbitrarily we conclude that the measure is indeed semi-$\sigma$-additive on elementary sets
> $\mu(A) \leq \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})}$ $$

</div>

It has been demonstrated that the measure on elementary sets is semi-$\sigma$-additive. We will prove further that the measure is $\sigma$-additive on elementary sets. 

<div class="definition" markdown="1">

**Proposition:** 

The measure of elementary sets is $\sigma$-additive, i.e. if $A$ is an elementary set with $A = \bigcup_{n=1}^{\infty} A_n$ where $\lbrace A_n \rbrace_{n=1}^{\infty}$ is a disjoint family of elementary sets,then
> $\mu(A) = \sum^{\infty}_{n=1}{\mu(A_{n})}$ $$

</div>

<div class="proof" markdown="1">

*Proof:* 

We will show two inequalities, 

$(\leq) \quad$ in which we show that 
> $\mu(A) \leq \sum^{\infty}_{n=1}{\mu(A_{n})}$ $$

Indeed, as $A = \bigcup_{n=1}^{\infty} A_n$, in particular $A \subset \bigcup_{n=1}^{\infty} A_n$, and so by $\sigma$-semi-additivity we have
> $\mu(A) \leq \sum^{\infty}_{n=1}{\mu(A_{n})}$ $$

$(\geq) \quad$ in which we show that 
> $\mu(A) \geq \sum^{\infty}_{n=1}{\mu(A_{n})}$ $$

Again we start from the assumption that $A = \bigcup_{n=1}^{\infty} A_n$, if we truncate this union at some finite number $N \in \mathbb{N}$ it must be the case that $\bigcup_{n=1}^{N} A_n \subset A$ such that
> $\mu(A) \geq \sum^{N}_{n=1}{\mu(A_{n})}$ $$

Now, as $\lim_{N \rightarrow \infty}{\sum^{N}_{n=1}{\mu(A_{n})}} = \sum^{\infty}_{n=1}{\mu(A_{n})}$ we simply take the limit as $N \rightarrow \infty$ of both sides of this inequality to obtain the desired result
> $\mu(A) \geq \sum^{\infty}_{n=1}{\mu(A_{n})}$ $$

</div>

<div class="definition" markdown="1">

**Outer Measure**

Take $A \subset E$ and denote by $\mathcal{M}$ the set of all collections of the form $\lbrace A_n \rbrace_{n=1}^{\infty}$ such that
1. $\forall_{n} \quad$ $A_n \subset E$
2. $\forall_{n} \quad$ $A_n$ is a rectangle
3. $A \subset \bigcup_{n=1}^{\infty} A_n$ $$

The outer measure of $A$ is here defined
> $\mu^{\star}(A):= \inf_{\lbrace A_n \rbrace \in \mathcal{M}} \sum_{n=1}^{\infty}{\mu(A_n)} $

</div>

*Remark:* it is clear that the outer measure of a rectangle must coincide with the measure constructed above. 

<div class="proposition" markdown="1">

**Properties of the Outer Measure**

1. $\mu^{\star}$ is correctly defined (finite) for any $A \subset E$
2. $\mu^{\star}$ is $\sigma$-semi-additive, i.e.
    > If $A \subset \bigcup_{n=1}^{\infty} A_n, \; A_n \subset E \;$ then $\mu^{\star}(A) \leq \sum_{n=1}^{\infty} \mu^{\star}(A_n)$

</div>

<div class="proof" markdown="1">

*Proof:*

<div class="proposition" markdown="1">

**Lemma:**

Let $\lbrace A_n \rbrace_{n=1}^{\infty} \in \mathcal{M}$ then 
> $\forall_{\epsilon>0} \forall_{n \in \mathbb{N}} \quad \exists$ a countable collection of rectangles $\lbrace P_{n_k} \rbrace_{k=1}^{\infty} \in \mathcal{M}$ such that
1. $A_n \subset \bigcup_{k=1}^{\infty} P_{n_k}$ $$
2. $\sum_{k=1}^{\infty} \mu(P_{n_k}) \leq \mu^{\star}(A_n) + \frac{\epsilon}{2^n}$ $$
</div>

Then by the **lemma**, we have the following inclusions
> $A \subset \bigcup_{n=1}^{\infty}{A_n} \subset \bigcup_{n=1}^{\infty}{\bigcup_{k=1}^{\infty}{P_{n_k}}}$ $$

And as the outer-measure of $A$ is an infimum over the set of infinite rectangular covers of $A$ we have the inequality
> $\mu^{\star}(A) \leq \sum_{n=1}^{\infty}{\sum_{k=1}^{\infty}{\mu(P_{n_k})}}$ $$
> $ \leq \sum_{n=1}^{\infty}{(\mu^{\star}(A_n) + \frac{\epsilon}{2^n})}$ (by the second claim of **lemma**)
> $ = \sum_{n=1}^{\infty}{\mu^{\star}(A_n)} + \sum_{n=1}^{\frac{\epsilon}{2^n}} = \sum_{n=1}^{\infty}{\mu^{\star}(A_n)} + \epsilon$

Since, this holds $\forall_{\epsilon>0}$ we have our result
> $\mu^{\star}(A) \leq \sum_{n=1}^{\infty}{\mu^{\star}(A_n)}$ $$
</div>

<div class="definition" markdown="1">

**Inner Measure**

Given $A \subset E$ define its inner measure as
> $\mu_{\star}(A):= 1 - \mu^{\star}(E \setminus A)$ $$

A set $A \subset E$ is called Lebesgue measurable if
>  $\mu_{\star}(A)$ $=$  $\mu^{\star}(A)$ 
</div>

<div class="proposition" markdown="1">

**Proposition**
> $\mu_{\star}(A)$ $\leq$  $\mu^{\star}(A)$
</div>

<div class="proof" markdown="1">

*Proof:*

Assume for contradiction that it is not the case, i.e. suppose
> $\mu_{\star}(A)$ $>$  $\mu^{\star}(A)$

Using our definition of inner measure we rewrite this inequality
> $1 - \mu^{\star}(E \setminus A)$ $>$  $\mu^{\star}(A)$

Rearrange terms to find
> $\mu^{\star}(E \setminus A) + \mu^{\star}(A)$ $<$ $\mu^{\star}(E)$

However, we have shown that the outer measure is $\sigma$-additive. Now, as $E = A + (E \setminus A)$ we have $E \subset A + (E \setminus A)$ and so by $\sigma$-additivty of the outer measure
> $\mu^{\star}(E) \leq \mu^{\star}(E \setminus A) + \mu^{\star}(A)$

Contradiction.
</div>

We will show that the Lebesgue measure is an extension of the measure on elementary sets. 

<div class="proposition" markdown="1">

**Proposition**

Let $A$ be an elementary set, then it is Lebesgue measurable and if $\mu_{E}$ denotes the measure on elementary sets
and $\mu$ the Lebesgue measure then
> $\mu_{E}(A) = \mu(A)$ $$
</div>

<div class="proof" markdown="1">

*Proof:*

Take $A \subset E$ elementary, we will prove that $A$ is Lebesgue measurable, i.e. that $\mu^{\star}(A) = \mu_{\star}(A)$, by demonstrating two inequalities
1. $\mu^{\star}(A) \leq \mu(A)$ $$
2. $\mu_{\star}(A) \geq \mu(A)$ $$

<hr>

$(1.):$ in which we show
> $\mu^{\star}(A) \leq \mu(A)$ $$

As $A$ is elementary it may be represented by the finite union of disjoint rectangles
> $A = \bigcup_{i=1}^n P_i$ where $\forall_{i = 1,\ldots,n} \; P_i$ is a rectangle and $P_i \cap P_j = \emptyset$ for $i \neq j$

We have already the elementary measure of $A$
> $\mu(A) = \sum_{i=1}^n{\mu(P_i)}$ $$

and the outer measure of $A$
> $\mu^{\star}(A) = \inf_{\lbrace Q_k \rbrace_{k =1} \in \mathcal{M}}^{\infty}{\sum_{k =1}^{\infty} \mu(Q_k)}$ $$

In particular, $A \subset \bigcup_{i=1}^n P_i$, such that by $\sigma$-additivity of the outer measure
> $\mu^{\star}(A) \leq \sum_{i=1}^n{\mu^{\star}(P_i)} = \sum_{i=1}^n{\mu(P_i)}$ $$

And so, we have our first inequality
> $\mu^{\star}(A) \leq \mu(A)$ $$

<hr>

$(2.):$ in which we show
> $\mu^{\star}(A) \geq \mu(A)$ $$

Choose a countable rectangular cover $\lbrace P_n \rbrace_{n=1}^{\infty} \in \mathcal{M}$ of $A$, then by the $\sigma$-additivity of the measure on elementary sets
> $\sum_{n=1}^{\infty}{\mu(P_n)} \geq \mu(A)$ $$

Consider the definition of the outer measure, as the infimum over countable rectangular covers of our set $\mu^{\star}(A) = \inf_{\lbrace Q_k \rbrace \in \mathcal{M}} \sum_{k=1}^{\infty}{\mu(Q_k)}$ it must be that
> $\mu^{\star}(A) \geq \sum_{n=1}^{\infty}{\mu(P_n)}$ $$

and hence we have our result
> $\mu^{\star}(A) \geq \mu(A)$ $$

<hr>

$(3.):$ in which we show
> $\mu_{\star}(A) = \mu(A)$ $$

By ($1.$) and ($2.$) we have $\mu^{\star}(A) = \mu(A)$ for any elementary set $A$, in particular, as $E \setminus A$, is elementary 
> $\mu^{\star}(E \setminus A) = \mu(E \setminus A)$ $$ 
> $(\rightarrow)$ $1 - \mu^{\star}(E \setminus A) = 1 - \mu(E \setminus A)$ 
> $(\rightarrow)$ $\mu_{\star}(A) = \mu(A)$ 

</div>

The **Caratheodory Theorem** gives us a criterion for the Lebesgue measurability of a set.

<div class="proposition" markdown="1">

**Theorem** (Caratheodory Theorem)

A set $A$ is Lebesgue measurable if and only if $\forall_{\epsilon > 0}$ there exists an elementary set $B \subset E$ such that
> $\mu^{\star}(A \Deleta B) < \epsilon$ $$
</div>

<div class="proof" markdown="1">

*Proof:*

We will need two lemmas to complete this proof

<div class="proposition" markdown="1">

**Lemma A** 

For any two sets $A,B \subset E$
> $\vert \mu^{\star}(A) - \mu^{\star}(B) \vert \leq \mu^{\star}(A \Delta B)$ $$
</div>

<div class="proof" markdown="1">

*Proof of Lemma A* 

Recall $A \Delta B = (A \cup B) \setminus (A \cap B)$ such that $A \subset B \cup (A \Delta B)$ and now by $\sigma$-additivity of the outer measure
> $\mu^{\star}(A) \leq \mu^{\star}(B) + \mu^{\star}(A \Delta B)$
> Hence, $\mu^{\star}(A) - \mu^{\star}(B) \leq \mu^{\star}(A \Delta B) \tag{\star}$

Likewise we have $B \subset A \cup (A \Delta B)$ and obtain the analagous result
> Hence, $\mu^{\star}(B) - \mu^{\star}(A) \leq \mu^{\star}(A \Delta B) \tag{\star \star}$

Now consider the case when $\mu^{\star}(A) \geq \mu^{\star}(B)$, then by $\star$ we have
> $\mu^{\star}(A) - \mu^{\star}(B) = \vert \mu^{\star}(A) - \mu^{\star}(B) \vert \ leq \mu^{\star}(A \Delta B)$

Suppose, on the otherhand, that $\mu^{\star}(A) \leq \mu^{\star}(B)$ then by $\star \star$ we have
> $\mu^{\star}(B) - \mu^{\star}(A) = \vert \mu^{\star}(A) - \mu^{\star}(B) \vert \ leq \mu^{\star}(A \Delta B)$
</div>

<div class="proposition" markdown="1">

**Lemma B** 

For any two sets $A,B \subset E$
> $A \Delta B = (E \setminus A) \Delta (E \setminus B)$ $$
</div>

<div class="proof" markdown="1">

*Proof of Lemma B* 

We must recall De Morgan's Laws
1. $(A \cup B)^c = A^c \cap B^c$
2. $(A \cap B)^c = A^c \cup B^c$


Starting from the definition of symmetric difference 
> $\cdots$
</div>

**Proof of Sufficiency**

**Proof of Necessity**

</div>


<div class="proposition" markdown="1">

**Theorem** 

If $A_1, \ldot, A_n \subset E$ are measurable sets then so are
1. $\bigcup_{i=1}^n{A_n}$ $$
2. $\bigcap_{i=1}^n{A_n}$ $$
3. $A_i \setminus A_j$ $$
4. $A_j \Delta A_j$ $$
</div>

<div class="proof" markdown="1">

*Proof* 

<hr>

$(1.)$ In which we prove
> $\bigcup_{i=1}^n{A_n}$ $$

It is enough to prove that the union of two measurable sets is again measurable and then by induction extend it to any finite union. Take measurable sets $A_1,A_2$ then by Caratheodory $\forall_{\epsilon > 0} \; \exists B_1,B_2$, elementary sets, such that
- $\mu^{\star}(A_1 \Delta B_1) < \frac{\epsilon}{2},$ and $\mu^{\star}(A_2 \Delta B_2) < \frac{\epsilon}{2},$ 

$\cdots$
</div>


<div class="proposition" markdown="1">

**Theorem** 

Assume that $A_1,A_2$ are measurable with $A_1 \cap A_2 = \emptyset$ then
> $\mu(A_1 \cup A_2) = \mu(A_1) + \mu(A_2)$ $$

This result extends, by induction, to any finite disjoint family of measurable sets, let us call this property **finite additivity** of the Lebesgue measure.
</div>

<div class="proof" markdown="1">

*Proof* 

$\cdots$
</div>


<div class="proposition" markdown="1">

**Theorem** ($\sigma$-additivity of the Lebesgue Measure)

Given a countable collection of disjoint measurable sets $\lbrace A_n \rbrace_{n=1}^{\infty}$ 
> $\mu(\bigcup_{n=1}^{\infty}{A_n}) = \sum_{n=1}^{\infty}{\mu(A_n)} $ $$

</div>

<div class="proof" markdown="1">

*Proof* 

Put $A = \bigcup_{n=1}^{\infty}{A_n}$, as the countable union of measurable sets, $A$ is measurable. In particular as $A \subset \bigcup_{n=1}^{\infty}{A_n}$ we use $\sigma$-semi-additivity of the outer measure to conclude
> $\mu^{\star}(A) \leq \sum_{n=1}^{\infty}{\mu^{\star}(A_n)}$ $$

As $A$ and $A_n$ are measurable $\forall_{n}$ the outer measure coincides with the Lebesgue measure
> $\mu(A) \leq \sum_{n=1}^{\infty}{\mu(A_n)}$ $$

Conversely, $\forall_{N \in \mathbb{N}}$ we have the inclusion $\bigcup_{n=1}^{N}{A_n} \subset A$ and again by $\sigma$-semi-additivity of the outer measure and the measurability of all sets concerned
> $\sum_{n=1}^{N}{\mu(A_n)} \leq \mu(A)$ $$

Finally, as we take the limit as $N \rightarrow \infty$ the inclusion remains true such that
> $\lim_{N \rightarrow \infty}{\sum_{n=1}^{N}{\mu(A_n)}} = \sum_{n=1}^{\infty}{\mu(A_n)} \leq \mu(A)$

</div>

<div class="proposition" markdown="1">

**Theorem** (Continuity of the Lebesgue Measure)

Assume $\lbrace A_n \rbrace_{n=1}^{\infty}$ is a countable collection of measurable subsets of $E$ and
- $A_1 \supset	A_2 \supset \cdots \supset A_n \supset \cdots$ $$

Then,
> $\mu(\bigcap_{n=1}^{\infty}{A_n} = \lim_{n \rightarrow \infty}{\mu(A_n)}$ $$

</div>

<div class="proof" markdown="1">

*Proof* 

$\cdots$
</div>

<div class="proposition" markdown="1">

**Theorem** (Corollary to Continuity of the Lebesgue Measure)

Assume $\lbrace A_n \rbrace_{n=1}^{\infty}$ is a countable collection of measurable subsets of $E$ and
- $A_1 \subset	A_2 \subset \cdots \subset A_n \subset \cdots$ $$

Then,
> $\mu(\bigcup_{n=1}^{\infty}{A_n} = \lim_{n \rightarrow \infty}{\mu(A_n)}$ $$

Which follows directly from De Morgan's laws.
</div>

<div class="proposition" markdown="1">

**Theorem** (Completeness of the Lebesgue Measure)

Let $A \subset E$ be a measurable set such that $\mu(A) = 0$, then for any $B \subset A$ one has
1. $B$ is measurable
2. $\mu(B) = 0$ $$ 

</div>

<div class="proof" markdown="1">

*Proof* 

That $\mu(B) = 0$ follows from the claim that $B$ is measurable, non-negativeness of the Lebesgue measure, and semi-$\sigma$-additivity of the Lebesgue measure.

Take the set $C = \lbrace \emptyset \rbrace$, then as an *empty* rectangle, $C$ is, in particular, elementary and measurable.
Consider, the symmetric difference of $B$ and $C$
- $B \Delta C = (B \cup C) \setminus (B \cap C)$ 

$\cdots$

</div>

## Measurability and Topology in $E$

<div class="proposition" markdown="1">

**Theorem** (Measurability of open sets)

Any open subset $A \subset E$ is measurable

</div>

<div class="proof" markdown="1">

*Proof* 

Take the cartesian product of the rational numbers with itself $Q^2 = Q \times Q$

</div>

Informally we say that $A \subset E$ is a Borel set if it can be expressed with countable unions and intersections of open and closed subsets of $E$

### Measure in $\mathbb{R}^2$

$\cdots$

## Jordan Measure

For simplicity we assume that all sets are subsets of $E:= I^n = [0,1] \times \cdots \times [0,1]$

<div class="definition" markdown="1">

**Definition:** Jordan Measurable Sets

A set $A \subset E$ is called **Jordan measurable** if $\forall \epsilon > 0$ there exist two elementary sets $A_1,A_2 \subset E$ such that
1. $A_1 \subset A \subset A_2$ $$
2. $\mu(A_2 \setminus A_1) < \epsilon$
</div>

*Statement:* If a set is Jordan measurable, then it is Lebesgue measurable. The converse is not necessarily true.

<div class="proposition" markdown="1">

**Proposition:** Properties of Jordan Measurable Sets

If $A$ and $B$ are Jordan measurable then so are
1. $A \cup B$ $$
2. $A \cap B$ $$
3. $A \setminus B$ $$
4. $A \Delta B$ $$

</div>

<div class="proof" markdown="1">

*Proof:* (only of union)

Take $\epsilon > 0$ by definition, there exist elementary sets $A_1,A_2,B_1,B_2$ such that $A_1 \subset A \subset A_2$, $B_1 \subset B \subset B_2$ and $\mu(A_2 \setminus A_1) < \frac{\epsilon}{2}$, $\mu(B_2 \setminus B_1) < \frac{\epsilon}{2}$

As $A_1 \subset A$, $B_1 \subset B$ and $A \subset A_2$ and $B \subset B_2$ we have
> $A_1 \cup B_1 \subset A \cup B \subset A_2 \cup B_2$ $$

If $A_2,B_2$ are disjoint we have the equality
> $(A_2 \cup B_2) \setminus (A_1 \cup B_1) = (A_2 \setminus A_1) \cup (B_2 \setminus B_1)$ $$

In general, we have the inclusion
> $(A_2 \cup B_2) \setminus (A_1 \cup B_1) \subset (A_2 \setminus A_1) \cup (B_2 \setminus B_1)$ $$

And hence by semi-$\sigma$-additivity of the lebesgue measure
> $\mu((A_2 \cup B_2) \setminus (A_1 \cup B_1)) \leq \mu((A_2 \setminus A_1) \cup (B_2 \setminus B_1)) < \epsilon$ $$
</div>


<div class="definition" markdown="1">

**Definition:** Outer/Inner Jordan Measure

For $A \subset E$ we define the **outer Jordan measure** of $A$ as the infimum over the Lebesgue measure of elementary sets containing $A$
> $\overline{\mu}(A) = \inf_{S \supset A, S \; \text{elementary}}{\mu(S)}$ $$

Similarly we define the **inner Jordan measure**  of $A$ as the supremum over the Lebesgue measure of elementary sets contained in $A$
> $\underline{\mu}(A) = \sup_{S \subset A, S \; \text{elementary}}{\mu(S)}$ $$

</div>

<div class="proposition" markdown="1">

**Theorem:** 

Given $A \subset E$, $A$ is Jordan measurable if and only if 
> $\overline{\mu}(A) = \underline{\mu}(A)$ $$

</div>

<div class="proposition" markdown="1">

**Theorem:** (Crieterion of Jordan Measurability)

A set $A \subset E$, $A$ is Jordan measurable if and only if the boundary of $A$ has outer measure 0. 
> $\mu^{\star}(\partial A) = 0$ $$

</div>

## Measure on $\sigma$-ring

<div class="definition" markdown="1">

**Definition:** Rings/Algebras

Let $\Sigma$ be a collection of subsets of $A$. We say that $\Sigma$ is a **ring** if it is closed with respect to $\cap, \cup, \setminus, \Delta$ i.e. if $\sigma_1, \sigma_2 \in \Sigma$ then
1. $\sigma_1 \cap \sigma_2 \in \Sigma$ $$
2. $\sigma_1 \cup \sigma_2 \in \Sigma$ $$
3. $\sigma_1 \setminus \sigma_2 \in \Sigma$ $$
4. $\sigma_1 \Delta \sigma_2 \in \Sigma$ $$

If, in addition, there exists a set $B$ such that $\forall \sigma \in \Sigma$ $\sigma \subset B$ then the ring is called an algebra
</div>

<div class="example" markdown="1">

**Examples:** Rings

1. The collection of all Lebesgue measurable sets in $\mathbb{R}^n$ is a ring.
2. The collection of all Jordadn measurable sets in $\mathbb{R}^n$ is a ring.
3. The trivial algebra containing exactly the two elements $\lbrace A, \emptyset \rbrace$
4. The power set, $\mathcal{P}(A)$, which contains all subsets of $A$ is a ring
5. The collection of all finite subsets of $A$ is a ring
6. If $A$ is a subset of metric space $X$, the collection of all bounded subsets of $A$ is a ring.
</div>

<div class="proposition" markdown="1">

**Proposition:** 

Let $\lbrace A_{\alpha} \rbrace_{\alpha \in I}$ be a collection of rings, then $\bigcap_{\alpha \in I} A_{\alpha}$ is a ring aswell
</div>

<div class="proof" markdown="1">

*Proof:*

Let $A = \bigcap_{\alpha \in I} A_{\alpha}$ then $x \in A$ if and only if $x \in A_{\alpha} \; \forall_{\alpha \in I}$ and as each $A_{\alpha}$ is a ring in its own right its elements are already closed under the necessary operations.
</div>

<div class="definition" markdown="1">

**Definition:** Minimal Rings

Given a collection $\Sigma$ of subsets of $X$ we call $\mathcal{M}(\Sigma)$ a minimal ring containing $\Sigma$ if the following three properties are satisfied
1. $\sigma \subset \mathcal{M}(\Sigma)$ $$
2. $\mathcal{M}(\Sigma)$ is a ring
3. If $\mathcal{M'}(\Sigma)$ is any other ring containing $\Sigma$ then $\mathcal{M}(\Sigma) \subset \mathcal{M'}(\Sigma)$
</div>

<div class="proposition" markdown="1">

**Theorem:** 

A minimal ring always exists and is unique
</div>

<div class="proof" markdown="1">

*Proof:* 

**Existence**

Take a collection of sets $\Sigma$ and put $X_0:= \bigcap_{A \in \Sigma} A$. Consider the set of all subsets of $X_0$, $\mathcal{P}(X_0)$. Let $S$ be the set of all rings containing subsets of $\mathcal{P}(X_0)$ and containing $\Sigma$
> $S = \lbrace X \; : \; $\sigma$ \subset X \subset \mathcal{P}(X_0), X$ is a ring  $\rbrace$

The intersection of this set $\mathcal{M}_1(\Sigma) = \bigcap_{X \in S} X$ is again a ring and must be minimal as an intersection of all rings containing $\Sigma$.

**Uniqueness**

Assume that $\mathcal{M}_1(\Sigma)$ is not unique, i.e. suppose there exists another minimal ring containing $\Sigma$, $\mathcal{M}_2(\Sigma)$. Then $\mathcal{M}_1(\Sigma) \cap \mathcal{M}_2(\Sigma)$ is also a ring containing $\Sigma$ and is contained in both $\mathcal{M}_1(\Sigma)$ and $\mathcal{M}_2(\Sigma)$ but this contradicts the minimality of $\mathcal{M}_1(\Sigma)$

</div>


<div class="definition" markdown="1">

**Definition:** Semi-Rings

A collection of sets $\Sigma$ is called a semi-ring if it satisfies the following properties
1. $\lbrace \emptyset \rbrace \in \Sigma$ $$
2. If $A,B \in \Sigma$ then $A \cap B \in \Sigma$  
3. If $A_1,A \in \Sigma$ with $A_1 \subset A$ then $\exists A_2, \ldots A_n \in \Sigma$ such that $i. \; \lbrace A_i \rbrace_{i=1}^n$ is a disjoint family and $\bigcup_{i=1}^n A_i = A$

</div>

<div class="example" markdown="1">

**Examples:** Semi-Rings

1. Any ring is also a semi-ring
2. The collection of rectangles in $\mathbb{R}^2$ is a semi-ring but not a ring (not closed under union)
3. The collection of poly-rectangles (boxes) in $\mathbb{R}^n$ is a semi-ring but not a ring
</div>

<div class="proposition" markdown="1">

**Theorem:** 

Assume $\Sigma$ is a semi-ring and $\mathcal{M}(\Sigma)$ the minimal ring generated by $\Sigma$, then  $\mathcal{M}(\Sigma)$ coincides with $\mathcal{M}$, the collection of sets constructed as the finite union of semi-ring elements, i.e.
> $A \in \mathcal{M} \; \iff \; A = \bigcup_{i=1}^k A_i, \; A_i \in \Sigma$ $$

</div>


<div class="proof" markdown="1">

*Proof:* 

It is enough to show that $\mathcal{M}$ is a ring

</div>

<div class="definition" markdown="1">

**Definition:** $\sigma$-rings and $\sigma$-algebras

Let $\mathcal{M}$ be a ring, then $\mathcal{M}$ is called
1. a $\delta$-ring if $\forall \lbrace A_n \rbrace_{n=1}^{\infty}, \; A_n \in \mathcal{M}$ one has $\bigcap_{n=1}^{\infty} \in \mathcal{M}$
2. a $\sigma$-ring if $\forall \lbrace A_n \rbrace_{n=1}^{\infty}, \; A_n \in \mathcal{M}$ one has $\bigcup_{n=1}^{\infty} \in \mathcal{M}$
3. a $\sigma$-algebra if $\mathcal{M}$ is a $\sigma$-ring for which $\exists_{A \in \mathcal{M}}$ such that $\forall{B \in \mathcal{M}}$ one has $A \cap B = B$, i.e. $B \subset A$.
</div>

**Remarks**
1. If $\mathcal{M}$ is a $\sigma$-ring then it is also a $\delta$-ring, though the converse is not true.
2. $\mathcal{M}$ is a $\sigma$-algebra if and only if $\mathcal{M}$ is a $\delta$-algebra

### Rings, Algebras, and Maps

Let $X,Y$ be sets and $f:X \rightarrow Y$ with $\mathcal{M}$ a collection of subsets of $Y$ we express the pre-image of $\mathcal{M}$ in $X$ as
> $f^{-1}(\mathcal{M}) := \lbrace A \subset X \; : \; \exists_{B \in \mathcal{M}} \; f^{-1}(B)=A \rbrace$ $$

<div class="proposition" markdown="1">

**Proposition:** 

Let $X,Y, \mathcal{M}$ be as above and $f:X \rightarrow Y$
1. If $\mathcal{M}$ is a ring, then so is $$f^{-1}(\mathcal{M})$
2. If $\mathcal{M}$ is an algebra, then so is $$f^{-1}(\mathcal{M})$
3. If $\mathcal{M}$ is an $\sigma$-algebra, then so is $$f^{-1}(\mathcal{M})$

</div>

<div class="proof" markdown="1">

*Proof:* 

These results follow directly from the following properties of pre-images
- $f^{-1}(\bigcup_{\alpha} B_{\alpha}) = \bigcup_{\alpha}(f^{-1}(B_{\alpha}))$ $$
- $f^{-1}(\bigcap_{\alpha} B_{\alpha}) = \bigcap_{\alpha}(f^{-1}(B_{\alpha}))$ $$
</div>

### General Measure Theory

<div class="definition" markdown="1">

**Definition:** Measure on a $\sigma$-ring 

Let $\Sigma$ be a $\sigma$-ring then $\mu: \Sigma \rightarrow [0, \infty]$ is called a measure if it is finite additive on $\Sigma$, i.e. if
> $\forall_{A_1, \ldots, A_n \in \Sigma} \; \mu(\bigcup_{i=1}^n A_i) = \sum_{i=1}^n \mu(A_i)$ $$
</div>

<div class="proposition" markdown="1">

**Proposition:** Properties of the measure on a $\sigma$-ring 

Let $\mu: \Sigma \rightarrow [0, \infty]$ be a measure on a $\sigma$-ring, $\Sigma$, then
1. $\mu(\emptyset) = 0$ $$
2. Let $\lbrace A_i \rbrace_{i=1}^n$ be a disjoint collection of sets $A_i \in \Sigma$ then for any $A \in \Sigma$ with $\forall_i \; A_i \subset A$ we have 
    - $\mu(A) \geq \sum_{i=1}^n \mu(A_i)$ $$
3. Let $\lbrace A_i \rbrace_{i=1}^n$ be any collection of sets $A_i \in \Sigma$ and $A \subset \bigcup_{i=1}^n$ then 
    - $\mu(A) \leq \sum_{i=1}^n \mu(A_i)$ $$
4. For $A,B \in \Sigma$ with $A \subset B$ we have
    - $\mu(A) \leq \mu(B)$ $$

</div>

<div class="proof" markdown="1">

*Proof:* 

$1.$ *Claim*: $\mu(\emptyset) = 0$ <br>
It is the unique property of the empty set that $\emptyset = \emptyset \cup \emptyset$ and so by finite-additivity
> $\mu(\emptyset) = \mu(\emptyset \cup \emptyset) = \mu(\emptyset) + \mu(\emptyset) = 2 \mu(\emptyset)$ $$
    > $\rightarrow \mu(\emptyset) = 0$ $$

</div>

<div class="definition" markdown="1">

**Definition:** Extension of measure on a semi-ring

If $\Sigma_m$, $\Sigma_{\mu}$ are two semi-rings and $\Sigma_m \subset \Sigma_{\mu}$ then the measure $\mu: \Sigma_{\mu} \rightarrow [0, \infty]$ is called an extension of the measure $m: \Sigma_m \rightarrow [0, \infty]$ if they coincide on all elements of $\Sigma_m$, i.e. if
> $\forall_{A \in \Sigma_m} \; \mu(A) = m(A)$

</div>

<div class="proposition" markdown="1">

**Proposition:** Extension of measure from a semi-ring to its minimal ring

Let $\Sigma$ be a semi-ring with measure $m: \Sigma \rightarrow [0, \infty]$ then there exists a unique extension of $m$ to $\mathcal{M}(\Sigma)$, the minimal ring generated by $\Sigma$.

</div>

<div class="proof" markdown="1">

*Proof:* 

$\cdots$

</div>

<div class="proposition" markdown="1">

**Proposition:** 

Let $\Sigma$ be a semi-ring and $\mu: \Sigma \rightarrow [0, \infty]$ a map, then $\mu$ is a measure if it is $\sigma$-additive

</div>

<div class="proposition" markdown="1">

**Proposition:** 

Let $\Sigma$ be a semi-ring, $\matcal{M}(\Sigma)$ the minimal ring generated by $\Sigma$, $m: \Sigma \rightarrow [0, \infty]$ a  $\sigma$-additive measure and $\mu: \matcal{M}(\Sigma) \rightarrow [0, \infty]$ the canonical extension of $m$ to $\matcal{M}(\Sigma)$, then $\mu$ is $\sigma$-additive as well. 

</div>


<div class="proposition" markdown="1">

**Proposition:** 

Assume that $\Sigma$ is a semi-ring and $\mu: \Sigma \rightarrow [0, \infty]$ a $\sigma$-additive measure. Let $\lbrace A_n \rbrace_{n=1}^{\infty}, A \in \Sigma$ with $A \subset \bigcup_{n=1}^{\infty} A_n$ then
> $\mu(A) \leq \sum_{n=1}^{\infty} \mu(A_n)$ $$

</div>


## Measurable Functions 

<div class="definition" markdown="1">

**Definition:** Measurable function

Let $X,Y$ be sets and $\Sigma_X, \Sigma_Y$ collections of subsets of $X$ and $Y$ respectively. Given a map $f: X \rightarrow Y$ we say that $f$ is $(\Sigma_X, \Sigma_Y)$-measurable if $\forall_{B \in \Sigma_Y}$ one has $f^{-1}(B) \in \Sigma_X$ i.e.

</div>

**Remark:** If $X,Y$ are metric spaces and $\Sigma_X, \Sigma_Y$ their respective topologies, then the definition of $(\Sigma_X, \Sigma_Y)$-measurability coincides with the that of continuity for any function $f: X \rightarrow Y$.

<div class="definition" markdown="1">

**Definition:** Borel $\sigma$-algebra

Given a metric space $X$ with topology $\tau$, denote by $\mathcal{B}(X)$ the minimal $\sigma$-algebra generated by $\tau$, i.e. $\mathcal{B}(X)$ is the minimal $\sigma$-algebra generated by the collection of open subsets of $X$.

</div>

Let $X$ be any sets, $\Sigma_X$ a $\sigma$-algebra of subsets of $X$ and $\mu: \Sigma_X \rightarrow \mathbb{R}$ a $\sigma$-additive measure, then the triple $(X,\Sigma_X,\mu)$ is called a measure space. Furthermore, we say that $A \subset X$ is measurable if and only if $A \in \Sigma_X$ (and likewise that $B \subset \mathbb{R}$ is measurable if and only if $B \in B(\mathbb{R})$, the Borel algebra of $\mathbb{R}$?)

<div class="definition" markdown="1">

**Definition:** Measurable real-valued function

Let $(X,\Sigma_X,\mu)$ be a measure space and $f: X \rightarrow \mathbb{R}$, we say that $f$ is measurable if it is $(\Sigma_X, \mathcal{B}(\mathbb{R}))$ measurable, i.e. if $f^{-1}(\mathcal{B}(\mathbb{R})) \subset \Sigma_X$
</div>

<div class="proposition" markdown="1">

**Proposition:** Criterion for measurability of real-valued function

Let $(X,\Sigma_X,\mu)$ be a measure space, a function, $f: X \rightarrow \mathbb{R}$, is measurable if and only if $\forall_{x \in X}$ the set $\lbrace x \in X \; : \; f(x) < c \rbrace$ is measurable, i.e. $\lbrace x \in X \; : \; f(x) < c \rbrace \in \Sigma_X$
</div>

<div class="proposition" markdown="1">

**Corollary:** Criterion for measurability of real-valued function

The Borel algebra $\mathcal{B}(\mathbb{R})$ coincides with the minimal algebra generated by sets of the form $\lbrace x \in \mathbb{R} \; : \; x < c$
</div>


<div class="proposition" markdown="1">

**Theorem:** Preservation of measurability under point-wise limit

Let $\lbrace f_n: X \rightarrow \mathbb{R} \rbrace_n$ be a collection of measurable functions, with $f(x):=\lim_{n \rightarrow \infty} f_n(x), \; \forall_{x \in X}$ then $f$ is also measurable
</div>

<div class="proposition" markdown="1">

**Proposition:** Preservation of measurability under composition

Let $(X,\Sigma_X,\mu)$ be a measure space, $f: X \rightarrow \mathbb{R}$ $(\Sigma_X, \mathcal{B}(\mathbb{R}))$-measurable function, and $g: \mathbb{R} \rightarrow \mathbb{R}$ a $(\mathcal{B}(\mathbb{R}),\mathcal{B}(\mathbb{R}))$-measurable, then $g \circ f$ is $(\Sigma_X, \mathcal{B}(\mathbb{R}))$-measurable.
</div>

<div class="definition" markdown="1">

**Definition:** Simple Functions

Let $(X,\Sigma_X,\mu)$ be a measure space, the function $f: X \rightarrow \mathbb{R}$ is called simple if
1. $f$ takes at most countably many values
2. $f$ is measurable
</div>

**Remark:** If $A \subset X$ is a non-measurable set then the function $f(x) := \begin{cases} 1, \quad x \in A \\ 0, \quad x \notin A \end{cases}$ is not simple.

<div class="proposition" markdown="1">

**Proposition:** Condition on measurability for function taking at most countably many values

Let  $f: X \rightarrow \mathbb{R}$ be a function taking countably many values $\lbrace y_1, \ldots, y_n, \ldots \rbrace$ then $f$ is measurable (and hence simple) if and only if $f^{-1}(y_n)$ is measurable $\forall_{n}$
</div>

<div class="proof" markdown="1">

*Proof:* 

Suppose the set $f^{-1}(y_n)$ is measurable $\forall_{n}$, choose $c \in \mathbb{R}$ and find $\lbrace y_{n_1}, \ldots y_{n_k}, \ldots \rbrace$, all the values in the image of $f$ such that $y_{n_k} < c$. Then $f^{-1}(\bigcup_k y_{n_k}) = \bigcup_k f^{-1}(y_{n_k})$ is measurable as the countable union of measurable sets, hence $f$ is measurable.
</div>

<div class="proposition" markdown="1">

**Theorem:** Criterion for measurability

Any function,  $f: X \rightarrow \mathbb{R}$, is measurable if and only if there exists a sequence $\lbrace f_n: X \rightarrow \mathbb{R} \rbrace_n^{\infty}$ with
1. $f_n$ is simple $\forall_n$
2. $\lbrace f_n \rbrace$ converges uniformly to $f$
</div>

<div class="proposition" markdown="1">

**Theorem:** Preservation of measurability under algebraic operations

Suppose $f,g: X \rightarrow \mathbb{R}$ are measurable functions, then so are the functions

1. $f + g$ $$
2. $\alpha f$ $\; \forall_{\alpha \in \mathbb{R}$
3. $fg(x):= f(x)g(x)$ $$
4. $\frac{f}{g}(x):= \frac{f(x)}{g(x)}$ $$
</div>

<div class="definition" markdown="1">

**Definition:** Equivalent functions

Two functions $f,g: X \rightarrow \mathbb{R}$ are said to be equivalent if
> $\mu(\lbrace x \in X \; : \; f(x) \neq g(x) \rbrace) = 0$ $$

The equivalence of functions is an equivalence relation.
</div>

<div class="proposition" markdown="1">

**Theorem:** 

Suppose $f,g: X \rightarrow \mathbb{R}$ are equivalent functions, then $f$ is measurable if and only if $g$ is.

</div>

<div class="definition" markdown="1">

**Definition:** Convergence almost everywhere

Let $X$ be a measure space and $\lbrace f_n: X \rightarrow \mathbb{R} \rbrace_n^{\infty}$ a sequence and suppose $\exists_{A \subset X}$ such that
1. $\mu(X \setminus A) = 0$ $$
2. $ \lbrace f_n \vert_A \rbrace_n^{\infty}$ converges to $f(x)$ $\forall_{x \in A}$

Then $ \lbrace f_n \rbrace$ is said to be convergent to $f$ almost everywhere.
</div>

<div class="example" markdown="1">

**Example:** 

Define the sequence of functions $\lbrace f_n: X \rightarrow \mathbb{R} \rbrace_n^{\infty}$
> $f_n(x):= (-x)^n$

then $\lim_{n \rightarrow \infty} f_n(x) = \begin{cases} 0, \quad 0 \leq x < 1 \\ \text{DNE}, \quad x = 1 \end{cases}$
</div>

**Remark:** we have the following chain of implications
> (Uniform Convergence) $\implies$ Pointwise Convergence $\implies$ Convergence Almost Everywhere

The next theorem will give a partial inversion from almost everywhere convergence to uniform convergence.

<div class="proposition" markdown="1">

**Theorem:** D. Egorov

Let $\lbrace f_n: E \rightarrow \mathbb{R} \rbrace_n^{\infty}$ be a sequence of measurable functions convergent to $f$ almost everywhere then $\forall_{\delta > 0}$ there exists a subset $E_{\delta} \subset E$ such that
1. $\mu(E \setminus E_{\delta}) < \delta$ $$
2. $f_n \vert_{E_{\delta}}$ converges to $f$ uniformly
</div>

<div class="definition" markdown="1">

**Definition:** Convergence in measure

Let $X$ be a measure space and $\lbrace f_n: X \rightarrow \mathbb{R} \rbrace_n^{\infty}$ a sequence of measurable functions. $\lbrace f_n \rbrace$ is said to be convergent in measure to $f: X \rightarrow \mathbb{R}$ if $\forall_{\sigma > 0}$
> $\lim_{n \rightarrow \infty} \mu(\lbrace x \in X \; : \; \vert f_n(x) - f(x) \vert \geq \sigma \rbrace) = 0$ $$

</div>

<div class="proposition" markdown="1">

**Proposition:** Convergence almost everywhere is stronger than convergence in measure

Let $E$ be a measure space and $\lbrace f_n: E \rightarrow \mathbb{R} \rbrace_n^{\infty}$ a sequence of measurable functions, if $\lbrace f_n \rbrace$ converges to $f: E \rightarrow \mathbb{R}$ almost everywhere then $\lbrace f_n \rbrace$ converges to $f$ in measure.
</div>


<div class="proposition" markdown="1">

**Theorem:** Riesz

Let $X$ be a measure space and $\lbrace f_n: X \rightarrow \mathbb{R} \rbrace_n^{\infty}$ a sequence of measurable functions convergent in measure to $f: X \rightarrow \mathbb{R}$, then there exists a subsequence $\lbrace f_{n_k} : X \rightarrow \mathbb{R} \rbrace$ which converges to $f$ almost everywhere.
</div>

## Lebesgue Integration

Our starting point will be the Lebesgue integral of a simple function.

<div class="definition" markdown="1">

**Definition:** Lebesgue integral of simple function

Let $(X, \Sigma_X, \mu)$ be a measure space, $A \subset X$ a measurable set (i.e. $A \in \Sigma_X$), and $f: X \rightarrow \mathbb{R}$ a simple functions taking the values $\lbrace y_1, y_2, \ldots, y_n, \ldots \rbrace$, put $A_n:= \lbrace x \in A \; : \; f(x) = y_n \rbrace$ and define the Lebesgue integral as
> $\int\limits_A f d\mu := \sum_{n=1}^{\infty} y_n \mu(A_n)$

provided that the summation converges. If, in addition, the summation converges absolutely then $f$ is called integrable.

</div>

**Remark:** our definition is well-defined for any simple function and any measurable $A$ even in the case that $f(x)$ takes the same value on two disjoint subsets of $A$, i.e. $y_i = y_j$ with $i \neq j$

<div class="example" markdown="1">

**Example:** 

Take $A = X$ and $f: X \rightarrow \mathbb{R}$ as the constant function $f(x) \equiv 1$ then
> $\int\limits_A f d \mu := \mu(A)$ $$

</div>

<div class="proposition" markdown="1">

**Proposition:** Linearity of integrability

Suppose $f,g: X \rightarrow \mathbb{R}$ are both simple and integrable functions on $A \in \Sigma_X$ then so are 
1. $f+g$ $$
2. $\alpha f,$ $\forall_{alpha \in \mathbb{R}}$
</div>

**Remark:** for the sake of brevity we will always assume the context of a measure space $(X, \Sigma_X, \mu)$ and when we consider the map $f: A \rightarrow \mathbb{R}$ we will assume that $A \in \Sigma_X$ unless otherwise stated

<div class="proposition" markdown="1">

**Proposition:** Criterion for integrability of simple functions and estimate

Suppose $f A \rightarrow \mathbb{R}$ is simple with $\vert f(x) \vert \leq M$, $\forall_{x \in A}$ then
1. $f$ is integrable on $A$, provided $\mu(A) < \infty$
2. $\vert \int\limits_A f d \mu \vert \leq M \mu(A)$ $$
</div>

<div class="definition" markdown="1">

**Definition:** Lebesgue integral of a measurable function

Let $f: A \rightarrow \mathbb{R}$ be a measurable function and $\lbrace f_n: A \rightarrow \mathbb{R} \rbrace $ a sequence of integrable, simple functions converging uniformly to $f$ on $A$. Define the Lebesgue integral of $f$ over $A$ as  
> $\int\limits_A f d\mu := \lim_{n \rightarrow \infty} \int\limits_A f_n d\mu$

</div>

<div class="proposition" markdown="1">

**Proposition:** 

The above definition for the Lebesgue integral is correctly defined, i.e.
1. **Existence:** Given the existence of a uniformly convergent sequence of simple, integrable functions, $\lbrace f_n: A \rbrace$ the limit exists.
2. **Uniqueness:** The limit is independent of the choice of $\lbrace f_n: A \rbrace$
3. **Consistency:** For $f$ simple, this definition coincides with the earlier definition of Lebesgue integration
</div>

<div class="proposition" markdown="1">

**Theorem:** On majorating functions

Let $f: A \rightarrow \mathbb{R}$ be a measurable function and $g: A \rightarrow \mathbb{R}$ an integrable function such that
1. $g(x) \geq 0$ almost everywhere on $A$
2. $\vert f(x) \vert \leq g(x)$ almost everywhere on $A$

then $f$ is integrable.
</div>

<div class="proposition" markdown="1">

**Proposition:** $\sigma$-additivity of the Lebesgue integral

Suppose $f: A \rightarrow \mathbb{R}$ is integrable and $A$ such that $A = \bigcup_{n=1}^{\infty} A_n$ with $A_j \cap A_k = \empty$ for $j \neq k$ then
> $\int\limits_A f d \mu = \sum _{n=1}^{\infty} \int\limits_{A_n} f d \mu$

</div>

<div class="proposition" markdown="1">

**Theorem:** Absolute continuity of the Lebesgue integral

Suppose $f: X \rightarrow \mathbb{R}$ is integrable, then $\forall_{\epsilon > 0} \exists_{\delta > 0}$ such that if for any $E \subset X$, $\mu(E) < \delta$ then $\vert \int\limits_E f d \mu \vert < \epsilon$

</div>

**Remark:** For Riemann integration we have the following result, if $f:[0,1] \rightarrow \mathbb{R}$ is continuous and such that $\int_0^1 \vert f \vert dx = 0$, then $f \equiv 0$ on $[0,1]$. What follows is the analagous result for Lebesgue integration

<div class="proposition" markdown="1">

**Proposition:** 

Suppose $f: A \rightarrow \mathbb{R}$ is such that 
> $\int\limits_A \vert f \vert d \mu = 0$ $$

then $f = 0$ almost everywhere on $A$
</div>

<div class="proposition" markdown="1">

**Lemma:** Chebyshev's inequality

Suppose $f: A \rightarrow \mathbb{R}$ is integrable and almost everywhere non-negative then $\forall_{c > 0}$
> $ \mu (\lbrace x \in A \; : \; f(x) \geq c \rbrace) < \frac{1}{c} \int\limits_A \vert f \vert d \mu$ $$

<div class="proof" markdown="1">

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

Take $c>0$ and put $A':= \lbrace x \in A \; : \; f(x) \geq c \rbrace$ then 
> $\int\limits_A f d \mu = \int\limits_{A'} f  d \mu + \int\limits_{A \setminus A'}  f  d \mu \geq \int\limits_{A'}  f  d \mu \geq c \mu(A')$ $$ 

</details>
</div>
</div>

<div class="proof" markdown="1">

<details>
<summary><i style="font-size:150%;">Proof of Proposition</i></summary>

Take $n \in \mathbb{N}$, then by Chebyshev and by assumption that $\int\limits_A \vert f \vert d \mu = 0$
> $0 \leq \mu (\lbrace x \in A \; : \; f(x) \geq \frac{1}{n} \rbrace) \leq n \int\limits_A \vert f \vert d \mu = 0$ $$ 

Put $M:= \lbrace x \in A \; : \; f(x) \neq 0 \rbrace$ and $M_n:= \lbrace x \in A \; : \; \vert f(x) \vert \geq \frac{1}{n} \rbrace$ then $M = \bigcup_{n} M_n$ and by $\sigma$-additivty of measure
> $\mu(M) \leq \sum_n \mu(M_n)$ $$

As we have shown, $\mu(M_n) = 0$, $\forall_n$, hence $\mu(\lbrace x \in A \; : \; f(x) \neq 0 \rbrace) = 0$
</details>
</div>

### Passage to the limit under the Lebesgue integral

A statement of the problem: assume $f_n: [0,1] \rightarrow \mathbb{R}$ are continuous functions which converge point-wise to a continuous function $f:  [0,1] \rightarrow \mathbb{R}$. In general, it is not the case that
> $\lim_{n \rightarrow \infty} \int_0^1 f_n dx = \int_0^1 \lim_{n \rightarrow \infty} f_n dx = \int_0^1 f dx$

For example, consider the the following sequence of real-valued functions $f_n(x):= nxe^{-nx^{2}}$ over the interval $[0,1]$. We can compute the pointwise limit using L'hospital's rule
> $f(x):= \lim_{n \rightarrow \infty}f_n(x) = \lim_{n \rightarrow \infty} \frac{nx}{e^{nx^{2}}} = \lim_{n \rightarrow \infty} \frac{x}{2xne^{nx^{2}}}=0$

Such that $f(x) \equiv 0$ and 
> $\int_0^1 f(x)dx = \int_0^1 0 dx = 0$ $$

Now, lets use u-substitution to calculate $\int f_n$. Put $u = x^2$ such that $xdx = \frac{du}{2}$ then
> $\int_0^1 f_n(x)dx = \int_0^1 nxe^{-nx^{2}}dx = \frac{n}{2} \int_0^1 e^{-nu} du = \frac{-1}{2}[e^{-n} - 1]$ $$

Notice that $\lim_{n \rightarrow \infty} e^{-n} = 0$ and so,
> $ \lim_{n \rightarrow \infty} \int_0^1 f_n(x)dx = \frac{1}{2} \neq  \int_0^1 \lim_{n \rightarrow \infty} f_n(x)dx = 0$

Therefore, pointwise convergence is NOT a sufficient condition for the interchange of the limit and the integral. However if a sequence $g_n$ converges uniformly on $[a,b]$ then it will be the case that $\lim_{n \rightarrow \infty} \int_a^b g_n dx = \int_a^b \lim_{n \rightarrow \infty} g_n dx$

Finally, we should make sure that the original sequence $f_n$ does not converge uniformly on $[0,1]$


<div class="proposition" markdown="1">

**Theorem:** Lebesgue Bounded Convergence Theorem

Given a measure space $(X, \Sigma_X, \mu)$, a measurable set $A \in \Sigma_X$, a sequence of integrable functions $\lbrace f_n: A \rightarrow \mathbb{R} \rbrace_{n=1}^{\infty}$ converging almost everywhere to some $f:A \rightarrow \mathbb{R}$, if there $\exists_{\phi: A \rightarrow \mathbb{R}}$ a nonnegative integrable function with $\vert f_n(x) \vert \leq \phi(x)$ almost everywhere $\forall_n$ then
1. $f$ is integrable
2. $\int\limits_A f_n d \mu \rightarrow \int\limits_A f d \mu$ $$

<div class="proof" markdown="1">

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

**Integrability of limit** <br>
Take $\epsilon > 0$ then for almost every $x \in A$
> $ \vert f(x) \vert = \vert f(x) - f_n(x) + f_n(x) \vert \leq \vert f(x) - f_n(x) \vert + \vert f_n(x) \vert \leq \vert f(x) - f_n(x) \vert + \phi(x)$

Now, in the limit as $n \rightarrow \infty$, $\vert f(x) \vert \leq \phi(x)$ so by the theorem on majorating functions, $f(x)$ is integrable

</details>
</div>

</div>

<div class="proposition" markdown="1">

**Corollary:** 

Suppose $\lbrace f_n: A \rightarrow \mathbb{R} \rbrace_{n=1}^{\infty}$ is a sequence of integrable functions converging almost everywhere to $f:A \rightarrow \mathbb{R}$, if there $\exists_{M > 0}$ such that $\vert f_n(x) \vert \leq M$ almost everywhere $\forall_n$ then
1. $f$ is integrable
2. $\int\limits_A f_n d \mu \rightarrow \int\limits_A f d \mu$ $$
</div>

<div class="proposition" markdown="1">

**Levi's Monotone Convergence Theorem:** 

Given a measure space $(X, \Sigma_X, \mu)$, $A \in \Sigma_X$ with $\mu(A) < \infty$ let $\lbrace f_n: A \rightarrow \mathbb{R} \rbrace$ a sequence of functions satisfying
1. $f_n$ is integrable $\forall_n$
2. $\forall_{x \in A} \; f_1(x) \leq f_2(x) \leq \cdots \leq f_n(x) \leq \cdots$ $$
3. $\exists_{M > 0}$ such that $\forall_{n} \; \vert \int\limits_A f_n d \mu \leq M$ 

Then $f_n$ converges almost everywhere to an integrrable function $f: A \rightarrow \mathbb{R}$ and
$\lim_{n \rightarrow \infty} \int\limits_A f_n d \mu =  \int\limits_A f d \mu$

</div>

<div class="proposition" markdown="1">

**Corollary:** 

Given a measure space $(X, \Sigma_X, \mu)$, $A \in \Sigma_X$ with $\mu(A) < \infty$ let $\lbrace \phi_k: A \rightarrow \mathbb{R} \rbrace$ a sequence of functions such that 
1. $\phi_k$ is integrable $\forall_k$
2. $\phi_k(x) \geq 0$ almost everywhere $\forall_k$
3. $\sum_{k=1}^{\infty} (\int\limits_A \phi_k d \mu) \leq M < \infty$ $$

then $\sum_{k=1}^{\infty} \phi_k(x)$ converges almost everywhere and
> $\int\limits_A (\sum_{k=1}^{\infty} \phi_k(x))d \mu = \sum_{k=1}^{\infty} (\int\limits_A \phi_k d \mu)$ $

<div class="proof" markdown="1">

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

Define the sequence of partial sums $f_n(x) := \sum_{k=1}^n \phi_k(x)$ then
1. $\lbrace f_n \rbrace_{n=1}^{\infty}$ are integrable $\forall_n$ as the finite sum of integrable functions
2. $f_1(x) \leq f_2(x) \leq \cdots \leq f_n(x) \leq \cdots$ for almost all $x \in A$

For finite sums we use linearity of integration to interchange the summation and integral signs
> $\int\limits_A f_n d \mu = \int\limits_A (\sum_{k=1}^n \phi_k) d \mu = \sum_{k=1}^n(\int\limits_A \phi_k d \mu)$

From the monotonicity of $\lbrace f_n \rbrace$ and boundedness of $\sum_{k=1}^{\infty} (\int\limits_A \phi_k d \mu)$
> $\int\limits_A f_n d \mu = \sum_{k=1}^n(\int\limits_A \phi_k d \mu) \leq \sum_{k=1}^{\infty}(\int\limits_A \phi_k d \mu) < M$

Hence, $\lbrace f_n \rbrace$ satisfies the conditions of Levi, put $\lim_{n \rightarrow \infty} f_n = f$ then 
> $\int\limits_A f d \mu = \sum_{k=1}^{\infty}(\int\limits_A \phi_k d \mu) = \int\limits_A (\sum_{k=1}^{\infty} \phi_k) d \mu$

</details>
</div>

</div>

<div class="proposition" markdown="1">

**Lemma:** Fatou's Lemma

Assume $(X, \Sigma_X, \mu)$ is a measure space with $A \in \Sigma_X$, and $f_n: A \rightarrow \mathbb{R}$ a sequence of functions such that $\forall_n$
1. $f_n$ is integrable 
2. $f_n(x)$
3. $\exists_{M > 0}$ independent of $n$ such that $\int\limits_A f_n d \mu$
4. $f_n$ converges almost everywhere to $f:A \rightarrow \mathbb{R}$

then $f$ is integrable and
> $\int\limits_A f d \mu < M$ $$

</div>


<div class="proposition" markdown="1">

**Lemma:** Reconciliation with Riemann integration

Let $f:[a,b] \rightarrow \mathbb{R}$ be Reimann integrable, then
1. $f$ is Lebesgue integrable
2. $\int\limits_{[a,b]} f d \mu = \int_a^b f(x) dx$ $$

</div>

## $L^p$ Spaces

### Convexity

In calculus we learn the following equivalent definitions of convexity

Let $f:(a,b) \rightarrow \mathbb{R}$ be twice differentiable on $(a,b)$ then $f$ is said to be convex on this interval if its second derivative is nonegative, i.e. if $\forall_{x \in (a,b)}$
> $f''(x) \geq 0$ $$

Assume that $f$ is atleast once differentiable on $(a,b)$ then $f$ is convex if its first derivative increases monotonically, i.e. if $\forall_{u,v \in (a,b)}$ 
> $u \leq v \; \implies \; f'(u) \leq f'(v)$

The definition of convexity we will use does not require any assumption of differentiability, however if $f$ is differentiable it will coincide with the above notions

For our purposes, a function $f:(a,b) \rightarrow \mathbb{R}$ is said to be convex if $\forall_{s,t,p \in (a,b)$
> $s < t < p \; \implies \; \frac{f(t) - f(s)}{t-s} \leq \frac{f(p) - f(t)}{p-t}$ $$

<div class="proposition" markdown="1">

**Lemma:** First Jensen's Inequality 

A function $f:(a,b) \rightarrow \mathbb{R}$ is convex if and only if $\forall_{x,y \in (a,b)}$
> $x \leq y \; \implies \; \forall_{\lambda \in [0,1]} \; f(\lambda x + (1- \lambda) y) \leq \lambda f(x) + (1-\lambda)f(y)$ $$

</div>

<div class="proposition" markdown="1">

**Proposition:** Continuity of convex functions

Let $f:(a,b) \rightarrow \mathbb{R}$ be convex, then it is continuous.

<div class="proof" markdown="1">

<details>
<summary><i style="font-size:150%;">Proof</i></summary>

Without loss of generality, assume $x \leq y$ such that $x,y \in [c,d] \subset (a,b)$, choose any $z \in [c,d]$ with $y \leq z$ then $(y - x) \leq (z - x) $, now put $\lambda = \frac{y - x}{z - x}$, clearly $0 \leq \lambda \leq 1$. Now, $(z - x) \lambda = y - x$ such that $y = \lambda z + (1- \lambda)x$ so by convexity of $f$
> $f(y) \leq \lambda f(z) + (1- \lambda)f(x) = f(x) + \lambda (f(z) - f(x)$


Finally note, a convex function is bounded on any closed set so let $\max_{x \in [c,d]} f(x) = M$ and $\min_{x \in [c,d]} f(x) = m$. 
> $$
</details>
</div>

</div>

**Remark:** A convex function, $f:[a,b] \rightarrow \mathbb{R}$, need not be continuous, indeed consider $\phi: [0,1] \rightarrow \mathbb{R}$
> $\phi(x) = \begin{cases} 0, \quad 0 \leq x < 1 \\ 1, \quad x = 1 \end{cases}$

<div class="proposition" markdown="1">

**Lemma:** General Jensen's Inequality 

Assume $\Omega$ is a measure space with $\mu(\Omega) = 1$, $f: \Omega \rightarrow (a,b)$ Lebesgue integrable and $\phi: (a,b) \rightarrow \mathbb{R}$ convex then
> $\phi( \int\limits_{\Omega} f d \mu) \leq \int\limits_{\Omega} (\phi \circ f) d \mu$ $$ 

</div>


<div class="proposition" markdown="1">

**Corollary:** 

Assume $\phi(x) = e^x$ then for $\mu(\Omega) = 1$ and $f: \Omega \rightarrow (a,b)$ Lebesgue integrable Jensen's inequality reads
> $e^{\int\limits_{\Omega} f d \mu} =  \int\limits_{\Omega} e^{f} d \mu$
</div>

<div class="proposition" markdown="1">

**Corollary:** 

Let $\Omega = \lbrace p_1, \ldots, p_n \rbrace$ with $\mu(p_i) = \frac{1}{n}$ and $f: \Omega \rightarrow (a,b)$ such that $f(p_i) = x_i$ then it follows from Jensen's inequality that
> $\phi( \int\limits_{\Omega} f d \mu) = \phi(x_1 \frac{1}{n} + \cdots + x_n \frac{1}{n}) = \phi(\frac{1}{n}(x_1 + \cdots + x_n))$
> $ \leq \int\limits_{\Omega} (\phi \circ f) d \mu = \frac{1}{n} \phi(x_1) + \cdots + \frac{1}{n} \phi(x_n)$
</div>

