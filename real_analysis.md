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
    - *Transitive:* comparable elements form a *chain*, $$a \leq b \, \and b \leq c \implies a \leq c$$
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
1. $$(\mathbb{Q}, \leq), (\mathbb{R}, \leq)$$ are fields
2. Any subfield of an ordered field is again ordered.
3. The field of rational functions is an ordered field.
</div>

