---
layout: post
title: 'Scratch Notes'
---

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
