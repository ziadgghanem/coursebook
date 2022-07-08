---
previewWebRootPath: \coursebook
layout: post
title: 'Lebesgue Integration'
---

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