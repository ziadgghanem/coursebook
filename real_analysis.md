---
layout: post
title: 'Real Analysis'
---

<blockquote>
        It is not enough to have a good mind; the main thing is to use it well.
        <footer>Descartes</footer>
</blockquote>

<hr>

## 1. Real Numbers

### Binary Relations

In simple terms, a binary relation between two sets is a rule of association between elements of each set. 

Consider the *cartesian product* of sets $A$ and $B$
> $$A \times B = \lbrace (a,b): \quad a \in A, \; b \in B \rbrace$$

We will see that the cartesian product of sets is the most general binary relation between them as each element in $A$ is 
associated with every element in $B$.

<div class="definition" markdown="1">

**Definition: Binary Relation**

Given $A, B$ any subset $\sigma \subset A \times B$ is called a binary relation. We denote an element of binary relation $\sigma$ with $(a,b) \in \sigma,$ or we may equivalently write $a \; \sigma \; b$
- In the case that $$A = B,$$ we say that $\sigma \subset A \times A$ is a binary relation on A.
</div>

In general a binary relation between sets $A$ and $B$ defines a map from $A$ to $B$ iff it is a transitive relation. 
- i.e. $$\sigma \subset A \times B$$ is a map $$:A \rightarrow B$$ $$\iff$$ $$\begin{cases} a \; \sigma \; b \\ b \; \sigma \; c \end{cases} \implies a \; \sigma \; c$$

<div class="example" markdown="1">

**Examples: Binary Relation**

Some instructive examples of binary relations:
1. Let $$A$$ be the set of all straight lines in the plane, we define $$\sigma \subset A \times A$$ such that 
    > $$a \; \sigma \; b$$ $$\iff a \parallel b$$
2. Again, let $$A$$ be the set of all straight lines in the plane
    > This time we define $$\sigma \subset A \times A$$ such that $$a \; \sigma \; b \iff a \perp b$$
3. Let $$A_m = \mathbb{Z}$$ the set of all integer numbers with $$m$$ some fixed integer, we define $$\sigma \subset A \times A$$ such that 
    > $$a \; \sigma \; b \iff a \equiv b \; mod \; m \iff \exists k \in \mathbb{Z}$$ such that $$a-b = km$$
4. Let $$X$$ be any set and put $$A = 	\mathcal{P}(X)$$ the set of all subsets of $$X,$$ we define $$\sigma \subset A \times A$$ such that 
    >  $$a \; \sigma \; b \iff a \subset b$$ where $$a,b \subset X$$
5. Let $$A = \mathbb{R}$$ and $$B = \mathbb{C},$$ we define $$\sigma \subset A \times B$$ such that,
    >  $$t \; \sigma \; z \iff$$ $$z = e^{it}$$
</div>

*Properties of Binary Relations:*
1. $$\sigma \subset A \times A$$ is called **reflexive** if $$\forall a \in A$$ we have $$a \; \sigma \; a$$
    - $$1,3,4$$ are reflexive relations, $$2,5$$ are not.
2. $$\sigma \subset A \times A$$ is called **transitive** if $$\forall a,b,c \in A$$ if $$a \; \sigma \; b$$ and $$b \; \sigma \; c$$ then $$a \; \sigma \; c$$
    - $$1,3,4$$ are transitive relations, $$2,5$$ are not.
3. $$\sigma \subset A \times A$$ is called **symmetric** if $$\forall a,b \in A$$ if $$a \; \sigma \; b$$ then $$b \; \sigma \; a$$
    - $$1,2,3$$ are symmetric relations $$4,5$$ are not.
4. $$\sigma \subset A \times A$$ is called **anti-symmetric** if $$\forall a,b \in A$$ if $$a \; \sigma \; b$$ and $$b \sigma a$$ then it must be the case that $$a = b$$
    - Only $4$ is an anti-symmetric relation.
5. $$\sigma \subset A \times A$$ is called an **equivalence relation** if it is at once reflexive, transitive and symmetric.
    - $$1,3$$ are equivalence relations, $$2,4,5$$ are not.
6. $$\sigma \subset A \times A$$ is called a **partial order** if it is at once reflexive, transitive, and anti-symmetric 
    - Only $4$ is a partial order.

<div class="example" markdown="1">

**Statement on Equivalence Relations**

Let $\sigma$ be an equivalence relation on $A,$ then $\sigma$ *partitions* $A,$ i.e. denote by $\sigma_x$ the set of all elements from $A$ equivalent to $x$ ($y \in \sigma_x \iff y \; \sigma \; x$)
1. $$\forall x \in A$$ there exists a unique $$\sigma_x$$ such that $$x \in \sigma_x$$
2. $$\forall x,y \in A$$ either $$\sigma_x = \sigma_y$$ or $$\sigma_x \cap \sigma_y = \emptyset$$
3. $$ \bigcup_{x \in A}$$ $$= A$$
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
1. Let $$A = \mathbb{N}$$ the set of natural numbers
    - $$(\mathbb{N}, +)$$ is an algebraic operation.
    - $$(\mathbb{N}, -)$$ is not an algebraic operation.
2. Let $$A = \mathbb{Z}$$ the set of integers
    - $$(\mathbb{Z}, +),(\mathbb{Z}, -),(\mathbb{Z}, \cdot)$$ are algebraic operations.
    - $$(\mathbb{Z}, \div)$$ is not an algebraic operation.
3. Let $$A = \mathbb{Q}$$ the set of rational numbers
    - $$(\mathbb{Q}, +),(\mathbb{Q}, -),(\mathbb{Q}, \cdot),(\mathbb{Q}, \div)$$ are all algebraic operations.
3. Let $$A = \mathbb{R}$$ the set of real numbers
    - $$(\mathbb{R}, +),(\mathbb{R}, -),(\mathbb{R}, \cdot),(\mathbb{R}, \div)$$ are all algebraic operations.
</div>

### Fields

Simply, a field is a set on which algebraic operations behave as they do on $$\mathbb{R}$$ and $$\mathbb{Q}$$

<div class="definition" markdown="1">

**Definition: Field**

A set $$\mathbb{F},$$ containing at least the two elements $$\mathbb{1}, \mathbb{0}$$, is called a **field** if it is equipped with two field (algebraic) operations, $$+$$ and $$\cdot,$$ satisfying the following conditions:
1. Conditions on addition operation $$+: \quad$$ $$\forall a,b,c \in \mathbb{F}$$ 
    1. *Associativity:* $$a + (b+c) = (a+b) + c$$
    2. *Additive Identity:* $$a + \mathbb{0} = \mathbb{0} + a = a$$
    3. *Additive Inverse:* For all $$a$$ there exists a unique $$b$$ such that $$a+b = b+a = \mathbb{0}$$
    4. *Commutativity:* $$a+b = b+a$$
2. Conditions on multiplicative operation $$\cdot: \quad$$ $$\forall a,b,c \in \mathbb{F}$$ 
    1. *Associativity:* $$a \cdot (b \cdot c) = (a \cdot b) \cdot c$$
    2. *Multplicative Identity:* $$a \cdot \mathbb{1} = \mathbb{1} \cdot a = a$$
    3. *Multplicative Inverse:* For all $$a \neq 0$$ there exists a unique $$b$$ such that $$a \cdot b = b \cdot a = \mathbb{1}$$
    4. *Commutativity:* $$a \cdot b = b \cdot a$$
3. Conditions between $$+$$ and $$\cdot: \quad$$ $$\forall a,b,c \in \mathbb{F}$$ 
    1. *Right Distributivity* $$(a+b) \cdot c = a \cdot c + b \cdot c$$
    2. *Left Distributivity* $$c \cdot (a+b) = c \cdot a + c \cdot b$$
</div>

We say that $\mathcal{S} \subset \mathcal{F}$ is a **subfield** of the field $\mathcal{F}$ if it is a field in its own right with the field operations of $\mathcal{F}.$

<div class="example" markdown="1">

**Examples: Fields**

Some instructive examples and non-examples of fields:
1. $$\mathbb{Q},\mathbb{R},\mathbb{C}$$ are fields
2. $$\mathbb{Z}$$ is not a field
3. The set of rational functions over $$\mathbb{R},$$ $$X = \lbrace \frac{a_0 + a_1x + \cdots + a_n x^n}{b_0 + b_1x + \cdots + b_m x^m} \rbrace$$ with $$a_i, b_j \in \mathbb{R}$$ is a field.
</div>

Informally, we think of an ordered set as a set, $A,$ equipped with a binary relation $$\leq \in A \times A$$ that describes a comparison rule between its elements.

<div class="definition" markdown="1">

**Partial and Total Orders**

Let $A$ be a set and $\leq \in A \times A$ a binary relation
1. We say that $$\leq$$ is a partial order on $$A$$ if it is reflexive, transitive, and anti-symmetric, i.e. 
    - *Reflexive:* every element is comparable to itself, $$a \leq a$$
    - *Transitive:* comparable elements form a *chain*, $$a \leq b \, \land b \leq c \implies a \leq c$$
    - *Anti-Symmetric:* elements may only be compared in at most one direction, if $$a \leq b$$ then not $$b \leq a$$
2. We say that $$\leq$$ is a total order on $$A$$ if it is a partial order with the condition that any two elements are comparable, i.e.
    - *Totality:* If $$a,b \in A$$ then either $$a \leq b$$ or $$b \leq a$$

</div>

We call sets with partial and total orders partially and totally ordered, respectively. The ordering of field comes with the extra complication that the relation respect field operations.

<div class="definition" markdown="1">

**Ordered Field**

Let $\mathbb{F}$ be a set with total order $\leq \in \mathbb{F} \times \mathbb{F}$ we say that $\mathbb{F}$ is ordered if $\forall a,b,c \in \mathbb{F}$
1. The order respects addition: $$a \leq b \implies a+c \leq b+c$$
2. The order respects multiplication: $$a \leq b \implies ac \leq bc$$ for $$c \geq \mathcal{0}$$

</div>

<div class="example" markdown="1">

**Examples: Ordered Fields**

Some instructive examples and ordered fields:
1. $$(\mathbb{Q}, \leq), (\mathbb{R}, \leq)$$ are ordered fields
2. Any subfield of an ordered field is again ordered.
3. The field of rational functions is an ordered field.
</div>

The canonical example of an ordered field is the real numbers. We will introduce the notion of order-completeness and the archimedian property
which provide sufficient condtitions for a field isomorphism to $\mathbb{R}.$

**Fundamental Concepts from Analysis**

Assume $(\mathbb{F}, \leq)$ is an ordered field with $A \subset \mathbb{F}$
1. $$A$$ is called bounded from above with *upper bound* $$\alpha$$ if
    > $$\exists \alpha \in \mathbb{F}$$ such that $$\forall x \in A$$ $$x \leq \alpha$$
2.  $$A$$ is called bounded from below with *lower bound* $$\beta$$ if
    > $$\exists \beta \in \mathbb{F}$$ such that $$\forall x \in A$$ $$ \beta \leq x$$
3. An element $$\gamma \in \mathbb{F}$$ is called a *supremum* for $$A$$ if
    1. $$\gamma$$ is an upper bound for $$A$$
    2. If $$\gamma'$$ is also an upper bound for $$A$$ then $$\gamma \leq \gamma',$$ i.e. $$\gamma$$ is the least upper bound for $$A$$
4. An element $$\delta \in \mathbb{F}$$ is called a *infimum* for $$A$$ if
    1. $$\delta$$ is an lower bound for $$A$$
    2. If $$\delta'$$ is also an lower bound for $$A$$ then $$\delta' \leq \delta,$$ i.e. $$\delta$$ is the greatest lower bound for $$A$$

If a supremum for $A \subset \mathbb{F}$ belongs to $A$ then we call it a maximum of $A.$ 
Similarly, we define a minimum of $A$ as a greatest lower bound belonging to $A.$

<div class="definition" markdown="1">

**Order-Complete Fields**

An ordered field $\mathbb{F}$ is called order complete if any set bounded from above, $A \subset \mathbb{F},$ admits a maximum.

Equivalently, we might require the existence of a minimum for any set bounded from below.
</div>

<div class="example" markdown="1">

**Examples: Order-Complete Fields**

Some instructive examples and nonexamples of order-complete fields:
1. $$(\mathbb{R}, <)$$ is order complete.
2. $$(\mathbb{Q}, <), (\mathbb{N}, <), (\mathbb{Z}, <)$$ are not order complete.
    - Indeed, put $$A:= \lbrace x \in \mathbb{Q}: \quad x^2 < 2 \rbrace$$ which has supremum $$\sqrt{2} \notin \mathbb{Q}$$
</div>

The Archimedian property is very nicely described by Euclid himself. In Book $\textrm{V}$ of Euclid's Elements we read
<blockquote>
        Magnitudes are said to have a ratio to one another which can, when multiplied, exceed one another.
</blockquote>

<div class="definition" markdown="1">

**Archimedian Property**

We say that an ordered field $$(\mathbb{F}, <)$$ is Archimedian if 
> $$\forall a,b \in \mathbb{F}$$ with $$a < b$$ 
    >$$\exists n \in \mathbb{N}$$ such that $$b < na $$
</div>

<div class="proposition" markdown="1">

**Proposition:** 

Any complete ordered field is Archimedian.

</div>

<div class="proof" markdown="1">

*Proof:*

Let the field, $(\mathbb{F}, <),$ be order complete.
> $$\iff$$ any bounded set $$A \subset \mathbb{F}$$ admits a supremum

Suppose, by contradiction, that $\mathbb{F}$ is not Archimedian
> $$\rightarrow$$ $$\exists a,b \in \mathbb{F}$$ with $$a < b$$ such that $$\forall n \in \mathbb{N}$$ we have $$na < b$$

Now, take the set $A: = \lbrace na \rbrace_{n \in \mathbb{N}},$ by negation of the Archimedian property this set is bounded above by $b \in \mathbb{F}.$

Also, by order completeness of $\mathbb{F},$ we are guarenteed the existence of some supremum $\gamma = \sup A$
> $$\rightarrow$$ $$\forall n \in \mathbb{N}$$ we have $$na < \gamma$$

> In particular we have $$\forall n \in \mathbb{N} \,$$ $$(n+1)a < \gamma$$ 

> $$\rightarrow$$ $$\forall n \in \mathbb{N} \,$$ $$na + a < \gamma$$ $$\rightarrow$$ $$na < \gamma - a < \gamma$$

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
> $$0 \cdot i < i \cdot i $$ $$\rightarrow$$ $$0 < -1,$$ 
    > contradiction. 

Case $1:$ Assume that $i < 0$ 

Then, $0 < -i$ and by the axioms of ordered fields 
> $$0 \cdot -i < -i \cdot -i $$ $$\rightarrow$$ $$0 < -1,$$ 
    > again a contradiction. 
</div>

### Topology in $\mathbb{R}$

Given $a \in \mathbb{R}$ we denote by $N_{\epsilon}(a) = \lbrace  x \in \mathbb{R}: a - \epsilon < x < a + \epsilon \rbrace$ the *$\epsilon-$ 
neighborhood* of $a$ 
and by $N^{\star}_{\epsilon}(a) = N_{\epsilon}(a) \setminus \lbrace a \rbrace $ the *deleted* $\epsilon$ 
-neighborhood of $a$.

**Fundamental Concepts from Topology take $A \subset \mathbb{R}$** 
1. $$a \in A$$ is called an *interior point* of $$A$$ if $$\exists \epsilon > 0$$ such that $$N_{\epsilon}(a) \subset A$$
    - We denote the union of all interior points with $$int(A)$$ and call this set the *interior* of $$A$$
2. $$b \in A$$ is called a *boundary point* of $$A$$ if $$\forall \epsilon > 0$$ the neighborhood $$N_{\epsilon}(b)$$ has nonempty intersection with both $$A$$ and its complement $$A^{C}$$ i.e. if  $$N_{\epsilon}(b) \cap A \neq \emptyset$$ $$\land$$ $$N_{\epsilon}(b) \cap A^{C} \neq \emptyset$$
    - We denote the union of all boundaary points with $$\partial(A)$$ and call this set the *boundary* of $$A$$
3. $$c \in A$$ is called an *accumulation point* of $$A$$ if  $$\forall \epsilon > 0$$ the deleted neighborhood of $$c$$ 
has nonempty intersection with $$A$$ i.e. if $$N^{\star}_{\epsilon}(c) \cap A \neq \emptyset$$
4. $$d \in A$$ is called an *isolated point* of $$A$$ if $$\exists \epsilon > 0$$ such that $$N_{\epsilon}(d) \cap A = \lbrace d \rbrace$$
5. The union of of accumulation points and isolated points constitute a set called the limit points of $$A$$
6. We define the closure of $$A$$ as the union of $$A$$ and the limit points of $$A$$.
    - The closure of $$A$$ is often denoted $$\bar{A} = A \cup \lbrace $$ limit points of $$A \rbrace$$

$A$ is called *open* if $A = int(A),$ in turn we say that $A$ is *closed* if $A^{C}$ is open. $A$ is said to be *compact* if it is both bounded and closed

### Metric Spaces

A metric space is a set together with a map, called a metric, that defines a rule of distance between elements of the set.

<div class="definition" markdown="1">

**Metric Space**

A set $M$ is called a metric space if there exists a map $\rho : M \times M \rightarrow \mathbb{R}$ satisfying 
the metric properties $\forall x,y,z \in M$
1. *Positive Semi-Definiteness:* $$\rho(x,y) \geq 0$$
2. *Indiscernibility:* $$\rho(x,y) = 0 \iff x = y$$
3. *Symmetry:* $$\rho(x,y) = \rho(y,x)$$
4. *Triangle Inequality:* $$\rho(x,y) \leq \rho(x,z) + \rho(z,y)$$

</div>

<div class="example" markdown="1">

**Examples: Metric Spaces**

Some instructive examples of metric spaces:
1. It is the case that any set $$X$$ can be made into a metric space with the so-called trivial metric
    > $$\rho(x,y) =$$ $$\begin{cases}1, \quad x \neq y \\ 0, \quad x=y \end{cases}$$
2. Consider $$M = \mathbb{R}^n$$ where $$\mathbb{R}^n := \lbrace (x_1,x_2, \ldots, x_n): \quad x_i \in \mathbb{R} \forall i \rbrace$$ and define the $$p-$$ metric
    > $$\rho(x,y)_p =$$ $$(\sum_{i=1}^{n} \vert x_i - y_i \vert^p)^{\frac{1}{p}}$$ 
3. Take $$M = C([a,b],\mathbb{R})$$ the space of real-valued, continuous functions defined over the interval $$[a,b] \subset \mathbb{R}$$ and define the supremum metric
    > $$\rho(f,g) =$$ $$\sup_{x \in [a,b]} \vert f(x) - g(x) \vert$$
4. Again, take $$M = C([a,b],\mathbb{R})$$ but this time define the integral metric
    > $$\rho(f,g) =$$ $$\int_a^b \vert f(x) - g(x) \vert dx$$ 
5. Consider $$M = \ell^2 := \lbrace (x_1,x_2,\ldots): \quad \sum_{i=1}^{\infty} \vert x_i \vert^2 < \infty \rbrace$$ equipped with the euclidean metric
    > $$\rho(x,y) =$$ $$( \sum_{i=1}^{\infty} \vert x_i - y_i \vert^2 )^{\frac{1}{2}}$$
</div>

### Topology in Metric Spaces

In order to define topological concepts in $\mathbb{R}$ we first had to introduce the $\epsilon$- neighborhood of a point.
Given a metric space, $(M, \rho),$ we generalize the notion of a neighborhood with the open ball centered at a point $x_0 \in M$ with radius $r$, $B_r(x_0):= \lbrace x \in M: \rho(x,x_0)< r \rbrace$, 
Now the topological concepts in $(M, \rho)$ using balls follow
as they did in $\mathbb{R}$ using neighborhoods.

**Fundamental Concepts from Topology take $A \subset M$** 
1. $$a \in A$$ is called an *interior point* of $$A$$ if $$\exists \epsilon > 0$$ such that $$B_{\epsilon}(a) \subset A$$
    - We denote the union of all interior points with $$int(A)$$ and call this set the *interior* of $$A$$
2. $$b \in A$$ is called a *boundary point* of $$A$$ if $$\forall \epsilon > 0$$ the ball $$B_{\epsilon}(b)$$ has nonempty intersection with both $$A$$ and its complement $$A^{C}$$ i.e. if  $$B_{\epsilon}(b) \cap A \neq \emptyset$$ $$\land$$ $$B_{\epsilon}(b) \cap A^{C} \neq \emptyset$$
    - We denote the union of all boundaary points with $$\partial(A)$$ and call this set the *boundary* of $$A$$
3. $$c \in A$$ is called an *accumulation point* of $$A$$ if  $$\forall \epsilon > 0$$ the deleted ball of $$c$$ 
has nonempty intersection with $$A$$ i.e. if $$B^{\star}_{\epsilon}(c) \cap A \neq \emptyset$$
4. $$d \in A$$ is called an *isolated point* of $$A$$ if $$\exists \epsilon > 0$$ such that $$B_{\epsilon}(d) \cap A = \lbrace d \rbrace$$
5. The union of of accumulation points and isolated points constitute a set called the limit points of $$A$$
6. We define the closure of $$A$$ as the union of $$A$$ and the limit points of $$A$$.
    - The closure of $$A$$ is often denoted $$\bar{A} = A \cup \lbrace $$ limit points of $$A \rbrace$$

Just as with subsets of $\mathbb{R},$ $A$ is called *open* if $A = int(A),$ in turn we say that $A$ is *closed* if $A^{C}$ is open. $A$ is said to be *compact* if it is both bounded and closed

<div class="proposition" markdown="1">

**Statement:** Let $(M,\rho)$ be a metric space
1. The arbitrary union of open sets is open $M$. 
    - i.e. If $$\lbrace U_{\alpha} \rbrace_{\alpha \in I}$$ is an arbitrary collection of open subsets in $$M$$ then $$\bigcup_{\alpha} U_{\alpha}$$ is open.
2. The finite intersection of open sets is open in $M$
    - i.e. if $$\lbrace U_{\alpha} \rbrace^{N}_{n=1}$$ is a finite collection of open subsets in $$M$$ then $$\bigcap^{N}_{n=1} U_{n}$$ is open.
3. The arbitrary intersection of closed sets is closed $M$. 
    - i.e. If $$\lbrace V_{\alpha} \rbrace_{\alpha \in I}$$ is an arbitrary collection of closed subsets in $$M$$ then $$\bigcap_{\alpha} V_{\alpha}$$ is closed.
4. The finite union of closed sets is closed in $M$
    - i.e. if $$\lbrace V_{\alpha} \rbrace^{N}_{n=1}$$ is a finite collection of closed subsets in $$M$$ then $$\bigcup^{N}_{n=1} V_{n}$$ is closed.
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
- $$ \lim_{n \rightarrow \infty } \lbrace x_n \rbrace = a$$ $$\iff$$ $$\forall \epsilon > 0 \exists N \in \mathbb{N}: \, \forall n > N \, 
    \rho(x_n,a) < \epsilon$$

</div>

<div class="definition" markdown="1">

**Cauchy Sequences:**

Given a metric space $(M, \rho)$ a sequence $\lbrace x_n \rbrace \subset M$ is called a Cauchy sequence if its terms 
become arbitarily close together, i.e.
- $$\lbrace x_n \rbrace$$ Cauchy $$\iff$$ $$\forall \epsilon > 0 \exists N \in \mathbb{N}: \, \forall n,m > N \, \rho(x_n,x_m)< \epsilon$$
</div>

<div class="proposition" markdown="1">

**Proposition:** 

Any convergent sequence in a metric space is a Cauchy sequence.
</div>

<div class="proof" markdown="1">

*Proof:* 

Given metric space $(M, \rho),$ suppose $\lbrace x_n \rbrace \subset M$ is convergent to $a \in M$
> $$\rightarrow$$ $$\lim_{n \rightarrow \infty } \rho(x_n, a) = 0$$

Now consider the distance between the $$n$$-th and $$m$$-th terms of our sequence. By the triangle inequality metric axiom:
> $$\rho(x_n, x_m) \leq \rho(x_n, a) + \rho(x_m, a)$$

Where, both terms on the RHS of the inequality vanish in the limit such that
> $$\lim_{n \rightarrow \infty } \rho(x_n, x_m) = 0$$
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
1. $$(X, \rho)$$ is a complete metric space for any set $$X$$ and the trivial metric $$\rho(x,y) = \begin{cases}1, \quad x \neq y \\ 0, \quad x=y \end{cases}$$
    - Indeed, let $$\lbrace x_n \rbrace$$ be a Cauchy sequence in $$X$$ and choose $$\epsilon = \frac{1}{2},$$ we are guarenteed the existence of some $$N \in \mathbb{N}$$ such that $$\forall n,m > N \, \rho(x,y) < \frac{1}{2}$$ but then $$\rho(x,y) = 0$$ $$\rightarrow$$ $$x=y.$$ 
    - Hence, any Cauchy sequence in such a metric space must become constant for all indices $$n >N$$ and as such is convergent to that constant value, which belongs to $$X$$.
2. $$(\mathbb{R}, \rho)$$ is a complete metric space with the natural metric $$\rho(x,y) = \vert x-y \vert$$
    - This will be shown later.
3. $$(\mathbb{R}^n, \rho_p)$$ is a complete metric space, where $$\rho_p(x,y) = (\sum^n_{i=1} \vert x-y \vert^p)^{\frac{1}{p}}$$
4. Let $$X =C([a,b],\mathbb{R})$$ then for $$\rho(f,g) =\sup_{x \in [a,b]} \vert f(x) - g(x) \vert,$$ the metric space $$(X, \rho)$$ is complete
    - Take fundamental sequence of functions $$\lbrace f_n \rbrace \subset X$$
</div>

### Compactness in Metric Spaces

The *Heine-Borel Theorem* (for now stated without proof) is one of the central theorems in Real-Analysis and will serve
as motivation for a more general theorem concerning compactness in general metric spaces.

<div class="proposition" markdown="1">

**Heine-Borel Theorem:**

The following properties are equivalent in any Euclidean space $\mathbb{R}^n$ for the closed subset $S \subset \mathbb{R}^n$
1. If $$\lbrace U_n \rbrace_{n \in I}$$ is an open cover of $$S$$ then there exissts a finite subcover $$\lbrace U_{n_1},U_{n_2}, \ldots U_{n_k} \rbrace$$ with $$S \subset \bigcup^k_{i=1} U_{n_i}$$
2. Any sequence $$\lbrace x_n \rbrace \subset S$$ admits a convergent subsequence, $$\lbrace x_{n_k} \rbrace,$$ with $$\lim_{k \rightarrow \infty} x_{n_k} \in S$$
3. $$S$$ is bounded
</div>

<div class="definition" markdown="1">

**Compactness:**

Let $(M, \rho)$ be a metric space with subset $K \subset M$
1. $$K$$ is called compact if any open cover of $$K$$ admits a finite subcoverr
2. K is called sequentially compact if any sequence $$\lbrace x_n \rbrace \subset K$$ admits a subsequence convergent to some $$a \in K$$
</div>

<div class="proposition" markdown="1">

**Statement:**

For any metric space compactness is equivalent to sequential compactness.
</div>

This is not true for topological spaces in general. 
Furthermore, it is not in general true that for a metric space $(M, \rho)$ 
compactness is equivalent to closedness $$+$$ boundedness. 

<div class="example" markdown="1">

**Example: Closed, Bounded, but not Compact**

Take the metric space $(\ell^2,\rho)$ which we recall was equipped with the metric
> $$\rho(x,y)$$ $$= ( \sum_{i=1}^{\infty} \vert x_i - y_i \vert^2 )^{\frac{1}{2}}$$

Consider the unit sphere $S^{\infty} \subset \ell^2,$ the set of all vectors in $\ell^2$
with distance $1$ away from the origin.
> $$S^{\infty}:= \lbrace x \in \ell^2: \rho(x,0) \rbrace = 1$$ where $$0 = (0,0,\ldots)$$

Such a subset is both closed and bounded but we will show that it is not sequentially compact. Indeed consider the sequence
> $$\begin{cases} (1,0,0,0,\ldots) \\ (0,1,0,0,\ldots) \\ (0,0,1,0,\ldots) \\ \cdots  \end{cases}$$

Clearly this sequence does not admit any convergent subsequences. Indeed, let $z_j \in \ell^2$ denote the element with a $1$ 
in its $j$-th index and $0$s otherwise, then
> $$\rho(z_j,z_i) = 2$$ $$\forall i,j \in \mathbb{N}$$

</div>

Though the Heine-Borel Theorem proposes that closedness $$+$$ boundedness is an equivalent condition to compactness 
in Euclidean spaces, it has been demonstrated that this is not the case in general metric spaces. We will need the following 
definition to generalize the result.

<div class="definition" markdown="1">

**Totally Bounded**

Given a metric space $(M, \rho),$ a set $K \subset M$ is called totally bounded if it can be covered by finitely many
balls of any fixed size, i.e.
> $$K \subset M$$ is totally bounded $$\iff$$ $$\forall \epsilon > 0$$ $$\exists x_1,\ldots,x_n \in K$$ such that $$K \subset \bigcup^n_{i=1} B_{\epsilon}(x_i)$$
</div>

<div class="proposition" markdown="1">

**Theorem:**

The followinig conditions are equivalent for any subset of a metric space.
1. Compactness (in the sense of open covers)
2. Sequential Compactness
3. Total Boundedness $$+$$ Completeness (or Closedness)
</div>

### Continuity In Metric Spaces

We recall the $\epsilon - \delta$ definition of continuity of real functions: informally that closeness of elements in the domain
imply closeness of their images in the codomain. We will generalize this notion to functions between metric spaces. 

<div class="definition" markdown="1">

**Continuity**

Given two metric spaces $(M_1, \rho_1),$ $(M_2, \rho_2),$ and a map $f: M_1 \rightarrow M_2$ then
1. $$f$$ is called continuous at $$x_0 \in M_1$$ if $$\forall \epsilon > 0 \, \exists \delta > 0$$ such that
    > $$\rho_1(x,x_0) < \delta$$ implies $$\rho_2(f(x),f(x_0)) < \epsilon$$
2. $$f$$ is called sequentially continuous if $$x_n \rightarrow x_0$$ implies $$f(x_n) \rightarrow f(x_0)$$
3. $$f$$ is said to be open if for any open subset $$U \subset M_2,$$ its preimage $$f^{-1}(U)$$ is open in $$M_1$$
4. If $$f$$ is continuous at any point of some subset $$A \subset M_1$$ then we say that $$f$$ is continuous on $$A$$

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
and minimum on $f(K$).$
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
1. $$\rho_1(x,y) = \rho_2(f(x),f(y))$$ $$$$
2. $$f$$ is bijective
</div>

### Completion of a Metric Space

<div class="definition" markdown="1">

**Completion of a Metric Space**

Given a metric space $(M', \rho),$ we say that it is the completion
of the metric space $(M, \rho)$ if 
1. $$M'$$ complete (in the sense of Cauchy sequences)
2. $$M'$$ contains $$M$$ i.e. $$M \subset M'$$
3. $$M$$ is dense in $$M'$$ i.e. $$\bar{M} = M'$$
</div>

We will prove that every metric space has a completion which is unique up to isometry.

<div class="proposition" markdown="1">

**Theorem**

Given a metric space $(M, \rho),$ 
1. There exists a completion of $$M$$ 
2. If $$M_1$$ and $$M_2$$ are two completions of M, then
    - There exists an isometry $$f: M_1 \rightarrow M_2$$ such that $$f \vert_M = \mathbb{1}$$
</div>

<div class="proof" markdown="1">

*Proof:*

**Step 1:** Define Equivalence Relation

Denote by $\tilde{M}$ the set of all Cauchy sequences in metric space $(M, \rho)$ and take $\sigma$, a 
binary relation on $\tilde{M}$ defining the following rule
> $$\lbrace x_n \rbrace \; \sigma \; \lbrace y_n \rbrace$$ $$\iff$$ $$\lim_{n \rightarrow \infty} \rho(x_n,y_n) = 0$$

**Claim 1:** $\sigma$ is an equivalence relation which partitions $\tilde{M}$ into equivalence classes.
- verify

<hr>

**Step 2:** Construct Quotient Space

Take the quotient space $M^{\star}:= \tilde{M}/_{\sigma}$ and define the following metric on $M^{\star}$
> $$(1)$$ $$\rho^{\star}(\bar{x}, \bar{y}) = \lim_{n \rightarrow \infty} \rho(x_n,y_n)$$ where $$\bar{x}, \bar{y}$$ represent 
the Cauchy sequences $$\lbrace x_n \rbrace,\lbrace y_n \rbrace$$ respectively.

**Claim 1:** Such a map, $(1)$, exists. <br>
As $$\mathbb{R}$$ is complete, it is enough to show that $$\rho(x_n,y_n)$$ is a Cauchy sequence.
- Indeed, $$\vert \rho(x_n,y_n) - \rho(x_m,y_m) \vert$$ 
- *Add and subtract term:* $$ = \vert \rho(x_n,y_n) - \rho(x_m,y_n) + \rho(x_m,y_n) - \rho(x_m,y_m) \vert$$
- *Triangle Inequality:* $$ \leq \vert \rho(x_n,y_n) - \rho(x_m,y_n) \vert + \vert \rho(x_m,y_n) - \rho(x_m,y_m) \vert$$
- *Reverse Triangle Inequality:* $$ \leq \rho(x_n,x_m) + \rho(y_n,y_m) \rightarrow 0$$

**Claim 2:** The limit in $(1)$ is independent of choice of representative. <br>
- Assume $$\lbrace x_n \rbrace \; \sigma \; \lbrace x_n' \rbrace \in [\bar{x}]$$ and $$\lbrace y_n \rbrace \; \sigma \; \lbrace y_n' \rbrace \in [\bar{y}]$$
- We want to show that $$ \vert \rho(x_n,y_n) - \rho(x_n',y_n') \vert \rightarrow 0,$$ which follows from the same argument used above. 


**Claim 3:** $(1)$ is indeed a metric on $M^{\star}$ <br>
We will only show the triangle inequality.   
- Let $$\bar{x}, \bar{y}, \bar{z} \in M^{\star}$$ be represented by the Cauchy sequences $$\lbrace x_n \rbrace, \lbrace y_n \rbrace, \lbrace z_n \rbrace \subset M$$
- As $$\rho: M \times M \rightarrow \mathbb{R}$$ is a metric it satisfies the triangle inequality $$\rho(x_n,y_n) \leq \rho(x_n,z_n) + \rho(z_n,y_n)$$
- The inequality is preserved in the limit $$\lim_{n \rightarrow \infty} \rho(x_n,y_n) \leq \lim_{n \rightarrow \infty} \rho(x_n,z_n) + \lim_{n \rightarrow \infty} \rho(z_n,y_n)$$
- And by construction of $$\rho^{\star}$$ this is exactly $$\rho^{\star}(\bar{x}, \bar{y}) \leq \rho^{\star}(\bar{x}, \bar{z}) + \rho^{\star}(\bar{y}, \bar{z})$$

<hr>

**Step 3:** Realization of $M$ in $M^{\star}$

Take $x \in M,$ we must show that this element manifests as the limit point of some class of Cauchy sequences in $M^{\star}$
- Consider the stationary sequence $$\lbrace x,x, \ldots \rbrace$$ which is by inspection
    1. A Cauchy Sequence
    2. Convergent to $$x \in M$$
- As an equivalence relation on $$\tilde{M}$$ *partitions* the space, we are guaranteed our stationary sequence represents exactly one 
equivalence class in $$M^{\star}$$
- Hence, $$M \subset M^{\star}$$

<hr>

**Step 4:** Density of $M$ in $M^{\star}$

We will show that $\bar{M} = M^{\star}:$ Take $\bar{x} \in M^{\star}$, fix $\epsilon > 0$, find Cauchy sequence, $\lbrace x_n \rbrace$ representing 
$\bar{x}$
- As $$\lbrace x_n \rbrace$$ is Cauchy $$\exists N$$ such that $$\forall n,m > N$$ we have $$\rho(x_n,x_m)$$
- Choose any $$k > N$$ and take the stationary sequence $$\lbrace x_k,x_k, \ldots \rbrace$$ and denote its equivalence class $$\hat{x} \in M^{\star}$$
- Now, $$\lim_{n \rightarrow \infty} \rho(x_n, x_k) < \epsilon$$ $$\rightarrow$$ $$\rho^{\star}(\bar{x}, \hat{x}) < \epsilon$$

<hr>

**Step 5:** Completeness of $M^{\star}$

$\ldots$

</div>

### Cantor's Construction of Real Numbers

## The Lebesgue Measure

### Construction of a Measure

The goal is to define the map $\mu: \mathcal{S} \rightarrow \mathbb{R}$ on some reasonable collection
of subsets of $\mathbb{R}^n,$ $ \mathcal{S}$ satisfying the following four properties of measure
1. *Positivity:* $$\mu > 0$$
2. *$$\sigma$$- additivity:*
3. *Normalization:* $$\mu(I^n) = 1$$ where $$I = [0,1]$$
4. *Congruency:* If $$A$$ is obtained from $$B$$ by translation or orthogonal transformation 
(i.e. if $$A,B\subset \mathbb{R}^n$$ are congruent) then $$\mu(A) = \mu(B)$$

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
1. $$ \bigcup_{r} N_r = [0,1)$$ $$ $$
2. $$ N_r \cap N_s = \emptyset$$ for all $$r \neq s$$
3. $$\mu(N_r) = \mu(N_s)$$ for all $$r,s$$

As $\lbrace N_r \rbrace^{\infty}_{r=1}$ are disjoint and $\mu$ is $\sigma$- additive
- $$\mu[0,1) = \sum^{\infty}_{r=1} \mu(N_r)$$ $$ $$

And by normalization 
- $$\sum^{\infty}_{r=1} \mu(N_r) = 1$$ $$ $$

Now consider two cases that both lead to contradiction
1. *Case:* assume that $$\forall r$$ $$\mu(N_r) = 0$$
    - But then, $$1 = 0 + 0 + \cdots = 0$$ $$\rightarrow$$ contradiction.
2. *Case:* assume that $$\forall r$$ $$\mu(N_r) = \alpha > 0$$
    - But then, $$1 = \alpha + \alpha + \cdots = \infty$$ $$\rightarrow$$ contradiction.

What remains is to show that such a family of sets $\lbrace N_r \rbrace^{\infty}_{r=1}$ indeed exists.
</div>

### Lebesgue Measure on the Plane

<div class="definition" markdown="1">

**Measure on Rectangles**

Let $X$ be any one of the following sets $[a,b],[a,b),(a,b],(a,b)$ and $Y$ any one of $[c,d],[c,d),(c,d],(c,d)$
then the set $P = X \times Y$ is called a rectangle.

In the degenerate case that either $a=b$ or $c=d$ then we say that the rectangle is *empty* and write $P = \emptyset$ 

We define the measure of a rectangle $P$ as follows:
> $$\mu(P) = \begin{cases}(b-a)(d-c), \quad \text{if} \; \text{P} \neq \emptyset \\ 0, \quad \text{if} \; \text{P} = \emptyset \end{cases}$$

</div>

<div class="proof" markdown="1">

It is clear that such a measure on the set of planar rectangles is well-defined and satisfies the four properties of measure
namely:
1. *Positivity:* $$\mu \geq 0$$ as $b>a$ and $d>c$
2. *$$\sigma$$- additivity:* If $$\lbrace P_n \rbrace^{k}_{n=1}$$ is a finite collection of disjoint rectangles we have
    - $$ \mu(\bigcup^k_{n=1} P_n) = \sum^{k}_{n=1} \mu(P_n)$$ $$ $$
3. *Normalization:* By inspection, $$\mu([0,1] \times [0,1]) = 1 $$
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

Suppose that $$A,B$$ are elementary sets, then so are
1. $$A \cap B$$ $$ $$
2. $$A \cup B$$ $$ $$
3. $$A \setminus B$$ $$ $$
4. $$A \Delta B = (A \cup B) \setminus (A \cap B)$$ where $$A \Delta B$$ is called the symmetric difference of $$A$$ and $$B$$
</div>

<div class="proof" markdown="1">

*Proof:*

First, we make an observation: if $$P,Q$$ are rectangles then $$P \cap Q$$ is also a rectangle and $$P \setminus Q$$
is elementary.

Now assume $A,B$ are elementary with representations $A = \bigcup^n_{i=1} P_i$ and $B = \bigcup^k_{j=1} Q_j$ for rectangles $P_i,Q_j$

$(1)$ First we consider their intersection: $A \cap B$
- $$A \cap B$$ $$=$$ $$ (\bigcup^n_{i=1} P_i) \bigcap (\bigcup^k_{j=1} Q_j)$$ $$=$$ $$\bigcup_{i,j} (P_i \cap Q_j)$$ 

where $$P_i \cap Q_j$$ are rectangles by observation such that $$A \cap B$$ is indeed elementary.

<hr>

**Corollary:** Let $P$ be a rectangle and $A \subset P$ an elementary set. Then, $P \setminus A$ is also elementary.

*Proof:* 

Express our elementary set as a finite disjoint union of rectangles $A = \bigcup^n_{i=1} P_i$ Now,
- $$P \setminus A = P \setminus \bigcup^n_{i=1} P_i = \bigcap^n_{i=1} (P \ P_i)$$
- By initial observation, each $$(P \ P_i)$$ is elementary 
- And so, by result $$(1)$$ $$P \setminus A$$ is elementary

<hr>

$(2)$ Next we consider their union: $A \cup B$
- Take a rectangle $$P$$ containing both $$A$$ and $$B$$
- So, $$A \cup B = P \setminus [(P \setminus A) \cap (P \setminus B)]$$ 
- $$(P \setminus A)$$ and $$(P \setminus B)$$ are elementary by collary
- In turn, $$A \cup B$$ is elementary by corollary

<hr>

$(3)$ Consider their difference: $A \setminus B$
- Again, take a rectangle $$P$$ containing both $$A$$ and $$B$$
- Now, $$A \setminus B = A \cap (P \setminus B)$$ 
- $$(P \setminus B)$$ and $$A \cap (P \setminus B)$$ are elementary by collary and $$(1)$$ respectively.

<hr>

$(4)$ Finally consider their symmetric difference: $A \Delta B$
- Write $$A \Delta B = (A \cup B) \setminus (A \cap B)$$
- $$A \Delta B$$ is elementary by $$(1),(2),(3)$$

</div>

We are now equpped to extend our measure theory to include elementary sets. For simplicity, we will initially
only consider subsets of the unit square $E = [0,1] \times [0,1]$ and then show how this assumption is easily discarded.

<div class="definition" markdown="1">

**Measure on Elementary Sets**

Let $E =  = [0,1] \times [0,1]$ an take elementary set $A \subset E$ with expression as finite union of disjoint rectangles
> $$A = \bigcup^n_{i=1} P_i$$ where $$\begin{cases} \lbrace P_i \rbrace \; \text{rectangles} \\ P_i \cap P_j = \emptyset \; i \neq j \end{cases}$$

We define the measure of $A$ as
> $$ \mu(A):= \sum^n_{i=1} \mu(P_i)$$

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
- $$A = \bigcup^n_{i=1} P_i,$$ $$\bigcup^m_{j=1} Q_j$$ $$ \quad \begin{cases} \lbrace P_i,Q_j \rbrace \; \text{rectangles} \\ P_i \cap P_l = \emptyset \; i \neq l \\ Q_j \cap Q_k = \emptyset \; j \neq k \end{cases}$$

We make the observation that
1.  $$ \sum^n_{i=1} \mu(P_i) = \sum^n_{i=1} \sum^m_{j=1} \mu(P_i \cap Q_j)$$ $$ $$
2.  $$ \sum^m_{j=1} \mu(Q_j) = \sum^m_{j=1} \sum^n_{i=1} \mu(Q_j \cap P_i)$$ $$ $$

Hence $\mu(A):= \sum^n_{i=1} \mu(P_i) = \sum^m_{j=1} \mu(Q_j)$

</div>

A measure must satisfy the properties of a measure, lets check that $\mu$ is $\sigma$-additive on elementary sets

<div class="proposition" markdown="1">

**Proposition**

The measure of an elementary set is $\sigma$-additive i.e.

Suppose $A, \lbrace A_n \rbrace^{\infty}_{n=1} \subset E$ are elementary sets with $A \subset \bigcup^{\infty}_{n=1} A_n$ then,
> $$\mu(A) \leq \sum^{\infty}_{n=1} \mu(A_n)$$
</div>

<div class="proof" markdown="1">

*Proof:*

Fix some $\epsilon > 0$

**Step 1:** Approximation of $A$ by compact subset

As an elementary set, $A$ may be expressed as the finite union of disjoint rectangles
> $$A = \bigcup^{k}_{i=1} B_i$$ where $$ \lbrace B_i \rbrace$$ is the disjoint family of rectangles

For each $B_i$ find a closed rectangle $\hat{B}_i$ such that
1. $$\hat{B}_i$ \subset B_i$$ $$$$
2. $$\mu(B_i) \leq \mu(\hat{B}_i) + \frac{\epsilon}{2k}$$ $$ $$

Put $\hat{A}:= \bigcup^{k}_{i=1} \hat{B}_i,$ then $\hat{A}$ is an elementary compact subset of $A$ with
> $$\mu(A) \leq \sum^{k}_{i=1} [\mu(\hat{B}_i) + \frac{\epsilon}{2k}]$$ $$$$
> $$\leq \sum^{k}_{i=1} \mu(\hat{B}_i) + \sum^{k}_{i=1} \frac{\epsilon}{2k} = \mu(\hat{A}) + \frac{\epsilon}{2}$$

**Step 2:** Approximation of $\lbrace A_n \rbrace$ by open superset

For each $A_n$ find an elementary set $\mathring{A}_n$ such that
1. $$A_n \subset \mathring{A}_n$$ $$ $$
2. $$\mathring{A}_n$$ is open
3. $$\mu(\mathring{A}_n) \leq \mu(A_n) + \frac{\epsilon}{2^{n+1}}
 
</div>