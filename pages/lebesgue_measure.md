---
previewWebRootPath: \coursebook
layout: post
title: 'Lebesgue Measure'
---

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

### Rectangular Measure

<div class="definition" markdown="1">

**Measure on Rectangles**

Let $X$ be any one of the following sets 
> $$[a,b],[a,b),(a,b],(a,b)$$  $$$$

And $Y$ any one of 
> $$[c,d],[c,d),(c,d],(c,d)$$ $$$$

Then the set $P = X \times Y$ is called a **rectangle**.

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

### Elementary Measure

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

<hr>

As an elementary set, $A$ may be expressed as the finite union of disjoint rectangles
> $$A = \bigcup^{k}_{i=1} B_i$$ where $$ \lbrace B_i \rbrace$$ is the disjoint family of rectangles

For each $B_i$ find a closed rectangle $\hat{B}_i$ such that
1. $$\hat{B}_i$ \subset B_i$$ $$$$
2. $$\mu(B_i) \leq \mu(\hat{B}_i) + \frac{\epsilon}{2k}$$ $$ $$

Put $\hat{A}:= \bigcup^{k}_{i=1} \hat{B}_i,$ then 
1. $$\hat{A}$$ is an compact 
2. $$\hat{A} \subset A$$ $$ $$
3. $$\mu(A) \leq \sum^{k}_{i=1} [\mu(\hat{B}_i) + \frac{\epsilon}{2k}]$$ $$$$
    > $$\leq \sum^{k}_{i=1} \mu(\hat{B}_i) + \sum^{k}_{i=1} \frac{\epsilon}{2k} $$ $$$$
    > $$ \leq \mu(\hat{A}) + \frac{\epsilon}{2}$$ $$$$

**Step 2:** Open approximation of $\lbrace A_n \rbrace$ 

<hr>

For each $A_n$ find an elementary set $\mathring{A}_n$ such that
1. $$A_n \subset \mathring{A}_n$$ $$ $$
2. $$\mathring{A}_n$$ is open
3. $$\mu(\mathring{A}_n) \leq \mu(A_n) + \frac{\epsilon}{2^{n+1}}$$ $$ $$
 
**Step 3:** Application of Heine Borel

<hr>

We have both, $\hat{A} \subset A$ and $\bigcup^{\infty}_{n=1} A_n \subset \bigcup^{\infty}_{n=1} \mathring{A}_n$, by construction and $A \subset \bigcup^{\infty}_{n=1} A_n$ by assumption such that $\lbrace \mathring{A}_n \rbrace^{\infty}_{n=1}$ is an open cover of $\hat{A}$ i.e.
> $$\hat{A} \subset  \bigcup^{\infty}_{n=1} \mathring{A}_n$$ $$$$

As $\hat{A}$ is compact there exists a finite open subcover $\lbrace \mathring{A}_{n_1},\mathring{A}_{n_2}, \ldots, \mathring{A}_{n_s} \rbrace$ such that $\hat{A} \subset  \bigcup^{s}_{k=1} \mathring{A}_{n_k}$. As this cover is, in particular, *finite*, we have
> $$\mu(\hat{A}) \leq \sum^{s}_{k=1} \mu(\mathring{A}_{n_k})$$

Finally, as $\lbrace \mathring{A}_{n_1},\mathring{A}_{n_2}, \ldots, \mathring{A}_{n_s} \rbrace \subset \lbrace \mathring{A}_n \rbrace^{\infty}_{n=1}$ we can bound $\sum^{s}_{k=1} \mu(\mathring{A}_{n_k}) \leq \sum^{\infty}_{n=1} \mu(\mathring{A}_{n})$ such that
> $$\mu(\hat{A}) \leq \sum^{\infty}_{n=1} \mu(\mathring{A}_{n})$$

**Step 4:** Final Estimate

<hr>

In **(Step 1)** we obtained 
> $$\mu(A) \leq \mu(\hat{A}) + \frac{\epsilon}{2}$$ $$$$

In **(Step 3)** we further bound this with 
> $$\mu(A) \leq \mu(\hat{A}) + \frac{\epsilon}{2} \leq \sum^{s}_{k=1} \mu(\mathring{A}_{n_k}) + \frac{\epsilon}{2} \leq \sum^{\infty}_{n=1} \mu(\mathring{A}_{n})  + \frac{\epsilon}{2}$$

Now, using positivity of $\epsilon$ and linearity of addition,
> $$\mu(A) \leq \sum^{\infty}_{n=1}{(\mu(\mathring{A}_{n})  + \frac{\epsilon}{2^{n+1}})} + \frac{\epsilon}{2}$$ $$$$
> $$ = \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \sum^{\infty}_{n=1}{\frac{\epsilon}{2^{n+1}}} + \frac{\epsilon}{2}$$ $$$$
 > $$ = \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \frac{\epsilon}{2} + \frac{\epsilon}{2} = \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \epsilon$$ $$$$

And so, we have $\mu(A) \leq \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})} + \epsilon$. As $\epsilon>0$ was chosen arbitrarily we conclude that the measure is indeed semi-$\sigma$-additive on elementary sets
> $$\mu(A) \leq \sum^{\infty}_{n=1}{\mu(\mathring{A}_{n})}$$ $$$$

</div>

It has been demonstrated that the measure on elementary sets is semi-$\sigma$-additive. We will prove further that the measure is $\sigma$-additive on elementary sets. 

<div class="definition" markdown="1">

**Proposition:** 

The measure of elementary sets is $\sigma$-additive, i.e. if $A$ is an elementary set with $A = \bigcup_{n=1}^{\infty} A_n$ where $\lbrace A_n \rbrace_{n=1}^{\infty}$ is a disjoint family of elementary sets,then
> $$\mu(A) = \sum^{\infty}_{n=1}{\mu(A_{n})}$$ $$$$

</div>

<div class="proof" markdown="1">

*Proof:* 

We will show two inequalities, 

$(\leq) \quad$ in which we show that 
> $$\mu(A) \leq \sum^{\infty}_{n=1}{\mu(A_{n})}$$ $$$$

Indeed, as $A = \bigcup_{n=1}^{\infty} A_n$, in particular $$A \subset \bigcup_{n=1}^{\infty} A_n$, and so by $\sigma$-semi-additivity we have
> $$\mu(A) \leq \sum^{\infty}_{n=1}{\mu(A_{n})}$$ $$$$

$(\geq) \quad$ in which we show that 
> $$\mu(A) \geq \sum^{\infty}_{n=1}{\mu(A_{n})}$$ $$$$

Again we start from the assumption that $A = \bigcup_{n=1}^{\infty} A_n$, if we truncate this union at some finite number $N \in \mathbb{N}$ it must be the case that $\bigcup_{n=1}^{N} A_n \subset A$ such that
> $$\mu(A) \geq \sum^{N}_{n=1}{\mu(A_{n})}$$ $$$$

Now, as $\lim_{N \rightarrow \infty}{\sum^{N}_{n=1}{\mu(A_{n})}} = \sum^{\infty}_{n=1}{\mu(A_{n})}$ we simply take the limit as $N \rightarrow \infty$ of both sides of this inequality to obtain the desired result
> $$\mu(A) \geq \sum^{\infty}_{n=1}{\mu(A_{n})}$$ $$$$

</div>

<div class="definition" markdown="1">

**Outer Measure**

Take $A \subset E$ and denote by $\mathcal{M}$ the set of all collections of the form $\lbrace A_n \rbrace_{n=1}^{\infty}$ such that
1. $$\forall_{n} \quad$$ $$A_n \subset E$$
2. $$\forall_{n} \quad$$ $$A_n$$ is a rectangle
3. $$A \subset \bigcup_{n=1}^{\infty} A_n$$ $$$$

The outer measure of $A$ is here defined
> $$\mu^{\star}(A):= \inf_{\lbrace A_n \rbrace \in \mathcal{M}} \sum_{n=1}^{\infty}{\mu(A_n)} $$

</div>

*Remark:* it is clear that the outer measure of a rectangle must coincide with the measure constructed above. 

<div class="proposition" markdown="1">

**Properties of the Outer Measure**

1. $$\mu^{\star}$$ is correctly defined (finite) for any $$A \subset E$$
2. $$\mu^{\star}$$ is $$\sigma$$-semi-additive, i.e.
    > If $$A \subset \bigcup_{n=1}^{\infty} A_n, \; A_n \subset E \;$$ then $$\mu^{\star}(A) \leq \sum_{n=1}^{\infty} \mu^{\star}(A_n)$$

</div>

<div class="proof" markdown="1">

*Proof:*

<div class="proposition" markdown="1">

**Lemma:**

Let $\lbrace A_n \rbrace_{n=1}^{\infty} \in \mathcal{M}$ then 
> $$\forall_{\epsilon>0} \forall_{n \in \mathbb{N}} \quad \exists$$ a countable collection of rectangles $$\lbrace P_{n_k} \rbrace_{k=1}^{\infty} \in \mathcal{M}$$ such that
1. $$A_n \subset \bigcup_{k=1}^{\infty} P_{n_k}$$ $$$$
2. $$\sum_{k=1}^{\infty} \mu(P_{n_k}) \leq \mu^{\star}(A_n) + \frac{\epsilon}{2^n}$$ $$$$
</div>

Then by the **lemma**, we have the following inclusions
> $$A \subset \bigcup_{n=1}^{\infty}{A_n} \subset \bigcup_{n=1}^{\infty}{\bigcup_{k=1}^{\infty}{P_{n_k}}}$$ $$$$

And as the outer-measure of $A$ is an infimum over the set of infinite rectangular covers of $A$ we have the inequality
> $$\mu^{\star}(A) \leq \sum_{n=1}^{\infty}{\sum_{k=1}^{\infty}{\mu(P_{n_k})}}$$ $$$$
> $$ \leq \sum_{n=1}^{\infty}{(\mu^{\star}(A_n) + \frac{\epsilon}{2^n})}$$ (by the second claim of **lemma**)
> $$ = \sum_{n=1}^{\infty}{\mu^{\star}(A_n)} + \sum_{n=1}^{\frac{\epsilon}{2^n}} = \sum_{n=1}^{\infty}{\mu^{\star}(A_n)} + \epsilon$$

Since, this holds $\forall_{\epsilon>0}$ we have our result
> $$\mu^{\star}(A) \leq \sum_{n=1}^{\infty}{\mu^{\star}(A_n)}$$ $$$$
</div>

<div class="definition" markdown="1">

**Inner Measure**

Given $A \subset E$ define its inner measure as
> $$\mu_{\star}(A):= 1 - \mu^{\star}(E \setminus A)$$ $$$$

A set $A \subset E$ is called Lebesgue measurable if
>  $$\mu_{\star}(A)$$ $$=$$  $$\mu^{\star}(A)$$ 
</div>

<div class="proposition" markdown="1">

**Proposition**
> $$\mu_{\star}(A)$$ $$\leq$$  $$\mu^{\star}(A)$$
</div>

<div class="proof" markdown="1">

*Proof:*

Assume for contradiction that it is not the case, i.e. suppose
> $$\mu_{\star}(A)$$ $$>$$  $$\mu^{\star}(A)$$

Using our definition of inner measure we rewrite this inequality
> $$1 - \mu^{\star}(E \setminus A)$$ $$>$$  $$\mu^{\star}(A)$$

Rearrange terms to find
> $$\mu^{\star}(E \setminus A) + \mu^{\star}(A)$$ $$<$$ $$\mu^{\star}(E)$$

However, we have shown that the outer measure is $\sigma$-additive. Now, as $E = A + (E \setminus A)$ we have $E \subset A + (E \setminus A)$ and so by $\sigma$-additivty of the outer measure
> $$\mu^{\star}(E) \leq \mu^{\star}(E \setminus A) + \mu^{\star}(A)$$

Contradiction.
</div>

We will show that the Lebesgue measure is an extension of the measure on elementary sets. 

<div class="proposition" markdown="1">

**Proposition**

Let $A$ be an elementary set, then it is Lebesgue measurable and if $\mu_{E}$ denotes the measure on elementary sets
and $\mu$ the Lebesgue measure then
> $$\mu_{E}(A) = \mu(A)$$ $$$$
</div>

<div class="proof" markdown="1">

*Proof:*

Take $A \subset E$ elementary, we will prove that $A$ is Lebesgue measurable, i.e. that $\mu^{\star}(A) = \mu_{\star}(A)$, by demonstrating two inequalities
1. $$\mu^{\star}(A) \leq \mu(A)$$ $$$$
2. $$\mu_{\star}(A) \geq \mu(A)$$ $$$$

<hr>

$(1.):$ in which we show
> $$\mu^{\star}(A) \leq \mu(A)$$ $$$$

As $A$ is elementary it may be represented by the finite union of disjoint rectangles
> $$A = \bigcup_{i=1}^n P_i$$ where $$\forall_{i = 1,\ldots,n} \; P_i$$ is a rectangle and $$P_i \cap P_j = \emptyset$$ for $$i \neq j$$

We have already the elementary measure of $A$
> $$\mu(A) = \sum_{i=1}^n{\mu(P_i)}$$ $$$$

and the outer measure of $A$
> $$\mu^{\star}(A) = \inf_{\lbrace Q_k \rbrace_{k =1} \in \mathcal{M}}^{\infty}{\sum_{k =1}^{\infty} \mu(Q_k)}$$ $$$$

In particular, $A \subset \bigcup_{i=1}^n P_i$, such that by $\sigma$-additivity of the outer measure
> $$\mu^{\star}(A) \leq \sum_{i=1}^n{\mu^{\star}(P_i)} = \sum_{i=1}^n{\mu(P_i)}$$ $$$$

And so, we have our first inequality
> $$\mu^{\star}(A) \leq \mu(A)$$ $$$$

<hr>

$(2.):$ in which we show
> $$\mu^{\star}(A) \geq \mu(A)$$ $$$$

Choose a countable rectangular cover $$\lbrace P_n \rbrace_{n=1}^{\infty} \in \mathcal{M}$$ of $$A$$, then by the $\sigma$-additivity of the measure on elementary sets
> $$\sum_{n=1}^{\infty}{\mu(P_n)} \geq \mu(A)$$ $$$$

Consider the definition of the outer measure, as the infimum over countable rectangular covers of our set $\mu^{\star}(A) = \inf_{\lbrace Q_k \rbrace \in \mathcal{M}} \sum_{k=1}^{\infty}{\mu(Q_k)}$ it must be that
> $$\mu^{\star}(A) \geq \sum_{n=1}^{\infty}{\mu(P_n)}$$ $$$$

and hence we have our result
> $$\mu^{\star}(A) \geq \mu(A)$$ $$$$

<hr>

$(3.):$ in which we show
> $$\mu_{\star}(A) = \mu(A)$$ $$$$

By ($1.$) and ($2.$) we have $\mu^{\star}(A) = \mu(A)$ for any elementary set $A$, in particular, as $E \setminus A$, is elementary 
> $$\mu^{\star}(E \setminus A) = \mu(E \setminus A)$$ $$$$ 
> $$(\rightarrow)$$ $$1 - \mu^{\star}(E \setminus A) = 1 - \mu(E \setminus A)$$ 
> $$(\rightarrow)$$ $$\mu_{\star}(A) = \mu(A)$$ 

</div>

The **Caratheodory Theorem** gives us a criterion for the Lebesgue measurability of a set.

<div class="proposition" markdown="1">

**Theorem** (Caratheodory Theorem)

A set $A$ is Lebesgue measurable if and only if $\forall_{\epsilon > 0}$ there exists an elementary set $B \subset E$ such that
> $$\mu^{\star}(A \Deleta B) < \epsilon$$ $$$$
</div>

<div class="proof" markdown="1">

*Proof:*

We will need two lemmas to complete this proof

<div class="proposition" markdown="1">

**Lemma A** 

For any two sets $A,B \subset E$
> $$\vert \mu^{\star}(A) - \mu^{\star}(B) \vert \leq \mu^{\star}(A \Delta B)$$ $$$$
</div>

<div class="proof" markdown="1">

*Proof of Lemma A* 

Recall $A \Delta B = (A \cup B) \setminus (A \cap B)$ such that $A \subset B \cup (A \Delta B)$ and now by $\sigma$-additivity of the outer measure
> $$\mu^{\star}(A) \leq \mu^{\star}(B) + \mu^{\star}(A \Delta B)$$
> Hence, $$\mu^{\star}(A) - \mu^{\star}(B) \leq \mu^{\star}(A \Delta B) \tag{\star}$$

Likewise we have $B \subset A \cup (A \Delta B)$ and obtain the analagous result
> Hence, $$\mu^{\star}(B) - \mu^{\star}(A) \leq \mu^{\star}(A \Delta B) \tag{\star \star}$$

Now consider the case when $\mu^{\star}(A) \geq \mu^{\star}(B)$, then by $\star$ we have
> $$\mu^{\star}(A) - \mu^{\star}(B) = \vert \mu^{\star}(A) - \mu^{\star}(B) \vert \ leq \mu^{\star}(A \Delta B)$$

Suppose, on the otherhand, that $\mu^{\star}(A) \leq \mu^{\star}(B)$ then by $\star \star$ we have
> $$\mu^{\star}(B) - \mu^{\star}(A) = \vert \mu^{\star}(A) - \mu^{\star}(B) \vert \ leq \mu^{\star}(A \Delta B)$$
</div>

<div class="proposition" markdown="1">

**Lemma B** 

For any two sets $A,B \subset E$
> $$A \Delta B = (E \setminus A) \Delta (E \setminus B)$$ $$$$
</div>

<div class="proof" markdown="1">

*Proof of Lemma B* 

We must recall De Morgan's Laws
1. $$(A \cup B)^c = A^c \cap B^c$$
2. $$(A \cap B)^c = A^c \cup B^c$$


Starting from the definition of symmetric difference 
> $$\cdots$$
</div>

**Proof of Sufficiency**

**Proof of Necessity**

</div>


<div class="proposition" markdown="1">

**Theorem** 

If $A_1, \ldot, A_n \subset E$ are measurable sets then so are
1. $$\bigcup_{i=1}^n{A_n}$$ $$$$
2. $$\bigcap_{i=1}^n{A_n}$$ $$$$
3. $$A_i \setminus A_j$$ $$$$
4. $$A_j \Delta A_j$$ $$$$
</div>

<div class="proof" markdown="1">

*Proof* 

<hr>

$(1.)$ In which we prove
> $$\bigcup_{i=1}^n{A_n}$$ $$$$

It is enough to prove that the union of two measurable sets is again measurable and then by induction extend it to any finite union. Take measurable sets $A_1,A_2$ then by Caratheodory $\forall_{\epsilon > 0} \; \exists B_1,B_2$, elementary sets, such that
- $$\mu^{\star}(A_1 \Delta B_1) < \frac{\epsilon}{2},$$ and $$\mu^{\star}(A_2 \Delta B_2) < \frac{\epsilon}{2},$$ 

$\cdots$
</div>


<div class="proposition" markdown="1">

**Theorem** 

Assume that $A_1,A_2$ are measurable with $A_1 \cap A_2 = \emptyset$ then
> $$\mu(A_1 \cup A_2) = \mu(A_1) + \mu(A_2)$$ $$$$

This result extends, by induction, to any finite disjoint family of measurable sets, let us call this property **finite additivity** of the Lebesgue measure.
</div>

<div class="proof" markdown="1">

*Proof* 

$\cdots$
</div>


<div class="proposition" markdown="1">

**Theorem** ($\sigma$-additivity of the Lebesgue Measure)

Given a countable collection of disjoint measurable sets $\lbrace A_n \rbrace_{n=1}^{\infty}$ 
> $$\mu(\bigcup_{n=1}^{\infty}{A_n}) = \sum_{n=1}^{\infty}{\mu(A_n)} $$ $$$$

</div>

<div class="proof" markdown="1">

*Proof* 

Put $A = \bigcup_{n=1}^{\infty}{A_n}$, as the countable union of measurable sets, $A$ is measurable. In particular as $A \subset \bigcup_{n=1}^{\infty}{A_n}$ we use $\sigma$-semi-additivity of the outer measure to conclude
> $$\mu^{\star}(A) \leq \sum_{n=1}^{\infty}{\mu^{\star}(A_n)}$$ $$$$

As $A$ and $A_n$ are measurable $\forall_{n}$ the outer measure coincides with the Lebesgue measure
> $$\mu(A) \leq \sum_{n=1}^{\infty}{\mu(A_n)}$$ $$$$

Conversely, $\forall_{N \in \mathbb{N}}$ we have the inclusion $\bigcup_{n=1}^{N}{A_n} \subset A$ and again by $\sigma$-semi-additivity of the outer measure and the measurability of all sets concerned
> $$\sum_{n=1}^{N}{\mu(A_n)} \leq \mu(A)$$ $$$$

Finally, as we take the limit as $N \rightarrow \infty$ the inclusion remains true such that
> $$\lim_{N \rightarrow \infty}{\sum_{n=1}^{N}{\mu(A_n)}} = \sum_{n=1}^{\infty}{\mu(A_n)} \leq \mu(A)$$

</div>

<div class="proposition" markdown="1">

**Theorem** (Continuity of the Lebesgue Measure)

Assume $\lbrace A_n \rbrace_{n=1}^{\infty}$ is a countable collection of measurable subsets of $E$ and
- $$A_1 \supset	A_2 \supset \cdots \supset A_n \supset \cdots$$ $$$$

Then,
> $$\mu(\bigcap_{n=1}^{\infty}{A_n} = \lim_{n \rightarrow \infty}{\mu(A_n)}$$ $$$$

</div>

<div class="proof" markdown="1">

*Proof* 

$\cdots$
</div>

<div class="proposition" markdown="1">

**Theorem** (Corollary to Continuity of the Lebesgue Measure)

Assume $\lbrace A_n \rbrace_{n=1}^{\infty}$ is a countable collection of measurable subsets of $E$ and
- $$A_1 \subset	A_2 \subset \cdots \subset A_n \subset \cdots$$ $$$$

Then,
> $$\mu(\bigcup_{n=1}^{\infty}{A_n} = \lim_{n \rightarrow \infty}{\mu(A_n)}$$ $$$$

Which follows directly from De Morgan's laws.
</div>

<div class="proposition" markdown="1">

**Theorem** (Completeness of the Lebesgue Measure)

Let $A \subset E$ be a measurable set such that $\mu(A) = 0$, then for any $B \subset A$ one has
1. $$B$$ is measurable
2. $$\mu(B) = 0$$ $$$$ 

</div>

<div class="proof" markdown="1">

*Proof* 

That $\mu(B) = 0$ follows from the claim that $B$ is measurable, non-negativeness of the Lebesgue measure, and semi-$\sigma$-additivity of the Lebesgue measure.

Take the set $C = \lbrace \emptyset \rbrace$, then as an *empty* rectangle, $C$ is, in particular, elementary and measurable.
Consider, the symmetric difference of $B$ and $C$
- $$B \Delta C = (B \cup C) \setminus (B \cap C)$$ 

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
1. $$A_1 \subset A \subset A_2$$ $$$$
2. $$\mu(A_2 \setminus A_1) < \epsilon$$
</div>

*Statement:* If a set is Jordan measurable, then it is Lebesgue measurable. The converse is not necessarily true.

<div class="proposition" markdown="1">

**Proposition:** Properties of Jordan Measurable Sets

If $A$ and $B$ are Jordan measurable then so are
1. $$A \cup B$$ $$$$
2. $$A \cap B$$ $$$$
3. $$A \setminus B$$ $$$$
4. $$A \Delta B$$ $$$$

</div>

<div class="proof" markdown="1">

*Proof:* (only of union)

Take $\epsilon > 0$ by definition, there exist elementary sets $A_1,A_2,B_1,B_2$ such that $A_1 \subset A \subset A_2$, $B_1 \subset B \subset B_2$ and $\mu(A_2 \setminus A_1) < \frac{\epsilon}{2}$, $\mu(B_2 \setminus B_1) < \frac{\epsilon}{2}$

As $A_1 \subset A$, $B_1 \subset B$ and $A \subset A_2$ and $B \subset B_2$ we have
> $$A_1 \cup B_1 \subset A \cup B \subset A_2 \cup B_2$$ $$$$

If $A_2,B_2$ are disjoint we have the equality
> $$(A_2 \cup B_2) \setminus (A_1 \cup B_1) = (A_2 \setminus A_1) \cup (B_2 \setminus B_1)$$ $$$$

In general, we have the inclusion
> $$(A_2 \cup B_2) \setminus (A_1 \cup B_1) \subset (A_2 \setminus A_1) \cup (B_2 \setminus B_1)$$ $$$$

And hence by semi-$\sigma$-additivity of the lebesgue measure
> $$\mu((A_2 \cup B_2) \setminus (A_1 \cup B_1)) \leq \mu((A_2 \setminus A_1) \cup (B_2 \setminus B_1)) < \epsilon$$ $$$$
</div>


<div class="definition" markdown="1">

**Definition:** Outer/Inner Jordan Measure

For $A \subset E$ we define the **outer Jordan measure** of $A$ as the infimum over the Lebesgue measure of elementary sets containing $A$
> $$\overline{\mu}(A) = \inf_{S \supset A, S \; \text{elementary}}{\mu(S)}$$ $$$$

Similarly we define the **inner Jordan measure**  of $A$ as the supremum over the Lebesgue measure of elementary sets contained in $A$
> $$\underline{\mu}(A) = \sup_{S \subset A, S \; \text{elementary}}{\mu(S)}$$ $$$$

</div>

<div class="proposition" markdown="1">

**Theorem:** 

Given $A \subset E$, $A$ is Jordan measurable if and only if 
> $$\overline{\mu}(A) = \underline{\mu}(A)$$ $$$$

</div>

<div class="proposition" markdown="1">

**Theorem:** (Crieterion of Jordan Measurability)

A set $A \subset E$, $A$ is Jordan measurable if and only if the boundary of $A$ has outer measure 0. 
> $$\mu^{\star}(\partial A) = 0$$ $$$$

</div>