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

Recall the cartesian product of sets $A$ and $B$
> $$A \times B = \{ (a,b): \quad a \in A \, b \in B \}$$

We will see that the cartesian product of sets is the most general binary relation between them.

<div class="definition" markdown="1">

**Definition: Binary Relation**

Given $A, B$ any subset $\sigma \subset A \times B$ is called a binary relation. We denote an element of binary relation $\sigma$ with $(a,b) \in \sigma,$ or we may equivalently write $a \sigma b$
- In the case that $$A = B,$$ we say that $\sigma \subset A \times A$ is a binary relation on A.
</div>

In general a binary relation between sets $A$ and $B$ specifies a map from $A$ to $B$ if it is transitive. 
- i.e. $$\sigma \subset A \times B$$ is a map $$\iff \begin{cases} a \sigma b \\ b \sigma c \end{cases} \implies a \sigma c$$

<div class="example" markdown="1">

**Examples: Binary Relation**

Some instructive examples of binary relations:
1. Let $$A$$ be the set of all straight lines in the plane, we define $$\sigma \subset A \times A$$ such that 
    > $$a \sigma b \iff a \parallel b$$
2. Again, let $$A$$ be the set of all straight lines in the plane
    > This time we define $$\sigma \subset A \times A$$ such that $$a \sigma b \iff a \perp b$$
3. Let $$A_m = \mathbb{Z}$$ the set of all integer numbers with $$m$$ some fixed integer, we define $$\sigma \subset A \times A$$ such that 
    > $$a \sigma b \iff a \equiv b \; mod \; m \iff \exists k \in \mathbb{Z}$$ such that $$a-b = km$$
4. Let $$X$$ be any set and put $$A = 	\mathcal{P}(X)$$ the set of all subsets of $$X,$$ we define $$\sigma \subset A \times A$$ such that 
    >  $$a \sigma b \iff a \subset b$$ where $$a,b \subset X$$
5. Let $$A = \mathbb{R}$$ and $$B = \mathbb{C},$$ we define $$\sigma \subset A \times B$$ such that,
    >  $$t \sigma z \iff$$ $$z = e^{it}$$
</div>

*Properties of Binary Relations:*
1. $$\sigma \subset A \times A$$ is called **reflexive** if $$\forall a \in A$$ we have $$a \sigma a$$
    - $$1,3,4$$ are reflexive relations, $$2,5$$ are not.
2. $$\sigma \subset A \times A$$ is called **transitive** if $$\forall a,b,c \in A$$ if $$a \sigma b$$ and $$b \sigma c$$ then $$a \sigma c$$
    - $$1,3,4$$ are transitive relations, $$2,5$$ are not.
3. $$\sigma \subset A \times A$$ is called **symmetric** if $$\forall a,b \in A$$ if $$a \sigma b$$ then $$b \sigma a$$
    - $$1,2,3$$ are symmetric relations $$4,5$$ are not.
4. $$\sigma \subset A \times A$$ is called **anti-symmetric** if $$\forall a,b \in A$$ if $$a \sigma b$$ and $$b \sigma a$$ then it must be the case that $$a = b$$
    - Only $4$ is an anti-symmetric relation.
5. $$\sigma \subset A \times A$$ is called an **equivalence relation** if it is at once reflexive, transitive and symmetric.
    - $$1,3$$ are equivalence relations, $$2,4,5$$ are not.
6. $$\sigma \subset A \times A$$ is called a **partial order** if it is at once reflexive, transitive, and anti-symmetric 
    - Only $4$ is a partial order.

<div class="example" markdown="1">

**Statement on Equivalence Relations**

Let $\sigma$ be an equivalence relation on $A,$ then $\sigma$ *partitions* $A,$ i.e. denote by $\sigma_x$ the set of all elements from $A$ equivalent to $x$ ($y \in \sigma_x \iff y \sigma x$)
1. $$\forall x \in A$$ there exists a unique $$\sigma_x$$ such that $$x \in \sigma_x$$
2. $$\forall x,y \in A$$ either $$\sigma_x = \sigma_y$$ or $$\sigma_x \cap \sigma_y = \emptyset$$
3. $$ \bigcup_{x \in A}$$ $$= A$$
</div>

### Algebraic Operations

An algebraic operation on a set is any map from the cartesian product of a set with itself to the set.

<div class="definition" markdown="1">

**Definition: Algebraic Operation**

Given $A$ we call a map $\phi: A \times A \rightarrow A$ an algebraic operation
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

## Fields

Simply, a field is a set on which algebraic operations behave as they do on $$\mathbb{R}$$ and $$\mathbb{Q}$$

<div class="definition" markdown="1">

**Definition: Field**

A set $$\mathbb{F},$$ containing at least the two elements $$\mathbb{1}, \mathbb{0}$$, is called a **field** if it is equipped with two field (algebraic) operations, $$+$$ and $$\cdot,$$ satisfying the following conditions:
1. Conditions on addition operation $$+: \quad$$ $$\forall a,b,c \in \mathbb{F}$$ 
    1. *Associativity:* $$a + (b+c) = (a+b) + c$$
    2. *Additive Identity:* $$a + \mathbb{0} = \mathbb{0} + a = a$$
    3. *Additive Inverse:* For all $$a$$ there exists a unique $$b$$ such that $$a+b = b+a = \mathbb{0}$$
    4. *Commutativity:* $$a+b = b+a$$
2. Conditions on multiplicative operation $$+: \quad$$ $$\forall a,b,c \in \mathbb{F}$$ 
    1. *Associativity:* $$a \cdot (b \cdot c) = (a \cdot b) \cdot c$$
    2. *Multplicative Identity:* $$a \cdot \mathbb{1} = \mathbb{1} \cdot a = a$$
    3. *Multplicative Inverse:* For all $$a \neq 0$$ there exists a unique $$b$$ such that $$a \cdot b = b \cdot a = \mathbb{1}$$
    4. *Commutativity:* $$a \cdot b = b \cdot a$ $
3. Conditions between $$+$$ and $$\cdot: \quad$$ $$\forall a,b,c \in \mathbb{F}$$ 
    1. *Right Distributivity* $$(a+b) \cdot c = a \cdot c + b \cdot c$$
    2. *Left Distributivity* $$c \cdot (a+b) = c \cdot a + c \cdot b$$
</div>

<div class="example" markdown="1">

We say that $\mathcal{S} \subset \mathcal{F}$ is a **subfield** of the field $\mathcal{F}$ if it is a field in its own right with the field operations of $\mathcal{F}.$

**Examples: Fields**

Some instructive examples and non-examples of fields:
1. $$\mathbb{Q},\mathbb{R},\mathbb{C}$$ are fields
2. $$\mathbb{Z}$$ is not a field
3. The set of rational functions over $$\mathbb{R},$$ $$X = \{ \frac{a_0 + a_1x + \cdots + a_n x^n}{b_0 + b_1x + \cdots + b_m x^m} \}$$ with $$a_i, b_j \in \mathbb{R}$$ is a field.
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

The canonical example of an ordered field is the real numbers. We will introduce the notions of order-completeness and the archimedian property
which provide sufficient condtitions for a field isomorphism to $\mathbb{R}.$

**Fundamental Concepts from Analysis**

Assume $(\mathbb{F}, \leq)$ is an ordered field with $A \subset \mathbb{F}$
1. $$A$$ is called bounded from above with *upper bound* $$\alpha$$ if
    > $$\exists \alpha \in \mathbb{F}$$ such that $$\forall x \in A$$ $$x \leq \alpha$$
2.  $$A$$ is called bounded from below with *lower bound* $$\beta$$ if
    > $$\exists \beta \in \mathbb{F}$$ such that $$\forall x \in A$$ $$ \beta \leq x$$
3. An element $$\gamma \in \mathbb{F}$$ is called a *supremum* for $$A$$ if
    1. $$\gamma$$ is an upper bound for $$A$$
    2. If $$\gamma^'$$ is also an upper bound for $$A$$ then $$\gamma \leq \gamma^',$$ i.e. $$\gamma$$ is the least upper bound for $$A$$
4. An element $$\delta \in \mathbb{F}$$ is called a *infimum* for $$A$$ if
    1. $$\delta$$ is an lower bound for $$A$$
    2. If $$\delta^'$$ is also an lower bound for $$A$$ then $$\delta^' \leq \delta,$$ i.e. $$\delta$$ is the greatest lower bound for $$A$$

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
    - Indeed, put $$A:= \{ x \in \mathbb{Q}: \quad x^2 < 2 \}$$ which has supremum $$\sqrt{2} \notin \mathbb{Q}$$
</div>

The Archimedian property is very nicely described by Euclid himself. In Book $\romannumeral 5$ of Euclid's Elements we read
<blockquote>
        Magnitudes are said to have a ratio to one another which can, when multiplied, exceed one another.
</blockquote>

<div class="definition" markdown="1">

**Archimedian Property**

We say that an ordered field $$(\mathbb{F}, <)$$ is Archimedian if 
> $$\forall a,b \in \mathbb{F}$$ with $$a < b$$ $$\exists n \in \mathbb{N}$$ such that $$b < na $$
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

Now, take the set $A: = \{ na \}_{n \in \mathbb{N}},$ by negation of the Archimedian property this set is bounded above by $b \in \mathbb{F}.$

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
> $$0 \cdot i < i \cdot i $$ $$\rightarrow$$ $$0 < -1,$$ contradiction. 

Case $1:$ Assume that $i < 0$ 

Then, $0 < -i$ and by the axioms of ordered fields 
> $$0 \cdot -i < -i \cdot -i $$ $$\rightarrow$$ $$0 < -1,$$ again a contradiction. 
</div>

## Metric Spaces

**Fundamental Concepts from Topology in $\mathbb{R}$**

Given $a \in \mathbb{R}$ we denote by $N_{\epsilon}(a) = \{x \in \mathbb{R}: a - \epsilon < x < a + \epsilon \}$ the *$\epsilon-$ 
neighborhood* of $a$ and by $N^{*}_{\epsilon}(a) = N_{\epsilon}(a) \ \{ a \}$ the *deleted $\epsilon-$ 
neighborhood* of $a.$

**Terminology:** take $A \subset \mathbb{R}$ 
1. $$a \in A$$ is called an *interior point* of $$A$$ if $$\exists \epsilon > 0$$ such that $$N_{\epsilon}(a) \subset A$$
    - We denote the union of all interior points with $$int(A)$$ and call this set the *interior* of $$A$$
2. $$b \in A$$ is called a *boundary point* of $$A$$ if $$\forall \epsilon > 0$$ the neighborhood $$N_{\epsilon}(a)$$ has nonempty intersection with both $$A$$ and its complement $$A^{C}$$ i.e. if  $$N_{\epsilon}(a) \cap A \neq \emptyset$$ $$\land$$ $$N_{\epsilon}(a) \cap A^{C} \neq \emptyset$$
    - We denote the union of all boundaary points with $$\partial(A)$$ and call this set the *boundary* of $$A$$
3. $$c \in A$$ is called an *accumulation point* of $$A$$ if  $$\forall \epsilon > 0$$ the deleted neighborhood of $$c$$ 
has nonempty intersection with $$A$$ i.e. if $$N^{*}_{\epsilon}(c) \cap A \neq \emptyset$$
4. $$d \in A$$ iscalled an *isolated point* of $$A$$ if $$\exists \epsilon > 0$$ such that $$N_{\epsilon}(d) \cap A = \{ d \}$$
5. The union of of accumulation points and isolated points constitute a set called the limit points of $$A$$
6. We define the closure of $$A$$ as the union of $$A$$ and the limit points of $$A$$.
    - The closure of $$A$$ is often denoted by $$\bar{A} = A \cup \{ limit points of A \}$$

1. $$A$$ is called *open* if $$A = int(A)$$
2. In turn we say that $$A$$ is *closed* if $$A^{C}$$ is open
3. $$A$$ is said to be *compact* if it is both bounded and closed

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
2. Consider $$M = \mathbb{R}^n$$ where $$\mathbb{R}^n := \{ (x_1,x_2, \ldots, x_n): \quad x_i \in \mathbb{R} \forall i \}$$ and define the $$p-$$ metric
    > $$\rho(x,y)_p =$$ $$(\sum_{i=1}^{n} \vert x_i - y_i \vert^p)^{\frac{1}{p}}$$ 
3. Take $$M = C([a,b],\mathbb{R})$$ the space of real-valued, continuous functions defined over the interval $$[a,b] \subset \mathbb{R}$$ and define the supremum metric
    > $$\rho(f,g) =$$ $$\sup_{x \in [a,b]} \vert f(x) - g(x) \vert$$
4. Again, take $$M = C([a,b],\mathbb{R})$$ but this time define the integral metric
    > $$\rho(f,g) =$$ $$\int_a^b \vert f(x) - g(x) \vert dx$$ 
5. Consider $$M = \ell^2 := \{(x_1,x_2,\ldots): \quad \sum_{i=1}^{\infty} \vert x_i \vert^2 < \infty \} equipped with the euclidean metric
    > $$\rho(x,y) =$$ $$( \sum_{i=1}^{\infty} \vert x_i - y_i \vert^2 )^{\frac{1}{2}}
</div>
