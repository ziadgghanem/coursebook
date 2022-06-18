---
layout: post
title: 'Scratch Notes'
---
<details>
<summary><i style="font-size:150%;">Proof</i></summary>

<div class="proof" markdown="1">


</div>
</details>


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

<div class="definition" markdown="1">

**Theorem:** (Heine-Borel)

A set $A \subset \mathbb{R}^n$ is compact if and only if it is closed and bounded.

</div>

<hr>
<hr>


<div class="definition" markdown="1">

**Field**

A field is a set $F$ with two algebraic operations $(+, \cdot)$ such that
1. $$(F,+)$$ is an abelian group with identity element $$\mathbb{0}$$ i.e. the additive operation satisfies $$\forall a,b,c \in F$$
    1. *Associativity:* $$(a+b) + c = a + (b+c)$$
    2. *Commutivity:* $$a+b = b+a$$
    3. *Identity:* $$a + \mathbb{0} = \mathbb{0} + a = a \quad$$ $$\forall a \in F$$ 
    4. *Inverse:* $$\forall a \in F \exists (-a) \in F$$ such that $$a + (-a) = (-a) + a = \mathbb{0}$$
2. $$(F \setminus \mathbb{0}, \cdot)$$ is an abelian group with identity element $$\mathbb{1}$$ i.e. the multiplicative operation satisfies $$\forall (a,b,c \neq 0) \in F$$
    1. *Associativity:* $$(a \cdot b) \cdot c = a \cdot (b \cdot c)$$
    2. *Commutivity:* $$a \cdot b = b \cdot a$$
    3. *Identity:* $$a \cdot \mathbb{1} = \mathbb{1} \cdot a = a \quad$$ $$\forall a \in F$$ 
    4. *Inverse:* $$\forall a \in F \exists a^{-1} \in F$$ such that $$a \cdot a^{-1} = a^{-1} \cdot a = \mathbb{1}$$
3. Multiplication satisfies the following distributive property over addition $$\forall a,b,c \in F$$
    - $$a \cdot (b+c) = a \cdot b + a \cdot c$$
</div>

Some common examples of fields: $\mathbb{R},\mathbb{Q},\mathbb{Z_2},\mathbb{Z_3}$

We say that $S \subset F$ is a **subfield** of the field $F$ if it is a field in its own right with the field operations of $F$. e.g. $\mathbb{Q}$ is a subfield of $\mathbb{R}$

**Augmentation of a Sub-Field**

Let $S$ be any subfield of a field $F$. Suppose we were interested in the augmentation of $S$ by some element $x_0 \in F$ i.e. the smallest field containing both $S$ and the element $x_0$. Let us denote such a field with $S[x_0]$ which can be constructed as follows
> $$S[x_0] = \lbrace a + b \cdot x_0 \vert a,b \in S \rbrace

<div class="example" markdown="1">

**Augmentation of the Rationals**

Consider the rational numbers, $\mathbb{Q}$, as a subfield of the real numbers, $\mathbb{R}$. $\mathbb{Q}$.

The irrationality of $\sqrt{2}$ is ancient and contreversial mathematical knowledge (Euclids's Elements $X.117$). Let us consider the smallest field containing both $\mathbb{Q}$ and $\sqrt{2}$
> $$Q[\sqrt{2}] = \lbrace a + b \sqrt{2} \vert a,b \in \mathbb{Q} \rbrace$$

Take $z_1 = (a_1 + b_1 \sqrt{2}), z_2 = (a_2 + b_2 \sqrt{2}) \in  Q[\sqrt{2}]$ addition and multiplicative operations are naturally defined on this augmented field.
- $$z_1 + z_2 = (a_1 + b_1 \sqrt{2}) + (a_2 + b_2 \sqrt{2}) = a_1 + a_2 + (b_1 + b_2) \sqrt{2}$$
- $$z_1 \cdot z_2 = (a_1 + b_1 \sqrt{2}) (a_2 + b_2 \sqrt{2}) = a_1 a_2 + 2 b_1 b_2 + (a_1 b_2 + b_1 + a_2) \sqrt{2}$$

Such a field contains the solution of the equation $x^2 - 2 = 0$

</div>

<div class="definition" markdown="1">

**Ordered Field**

An ordered field is a field $(F,+, \cdot)$ together with a relation $<$ satisfying the following properties:
1. *trichotomy:* $$\forall a,b \in F$$ exactly one of $$a < b$$, $$a > b$$, or $$a=b$$ is true
2. *additive monotony:* $$\forall a,b,c \in F$$ if $$a<b$$ then $$a+c < b+c$$
3. *multiplicative monotony* $$\forall a,b,c > 0 \in F$$ if $$a<b$$ then $$ac < bc$$

</div>

<div class="proposition" markdown="1">

**Proposition**

In an ordered field, $(F, <)$, every square is nonnegative 
- i.e. $$\forall p \in F \quad 0 \leq p^2$$

</div>

<div class="proof" markdown="1">

*Proof:*

Take $p \in F$, if $p = 0$ then $p^2 = 0$ so assume that $p \neq 0$
- Suppose $$p > 0$$ then $$p^2 = p \cdot p > 0 \cdot p = 0$$
- Suppose $$p < 0$$ then $$(-p) > 0$$ and as before $$p^2 = (-p) \cdot (-p) > 0 \cdot (-p) = 0$$

</div>

<div class="definition" markdown="1">

**Order-Complete Fields**

An ordered field, $F$, is called order-complete if every bounded from above (or from below), non-empty subset admits a supremum (or respectively an infimum).

</div>