---
layout: post
title: 'Local Properties of Analytic Functions'
---

## 6.1 Removeable Singularities

<div class="proposition" markdown="1">

**Theorem 6.01:** Analytic Extension

Suppose that $f(z)$ is analytic in a region $\Omega$ except perhaps at the point $b \in \Omega$. A necessary and sufficient condition that there exists an analytic function in all of $\Omega$ which coincides with $f(z)$ on $\Omega \setminus b$ is that
> $$\lim_{z \rightarrow b}(z-b)f(z)= 0$$ $$$$

The extension of $f(z)$ onto $\Omega$ is unique.
</div>


<div class="definition" markdown="1">

**Definition:** Removeable Singularity

If a function $f$ is analytic on some deleted neighborhood of $b \in \mathbb{C}$, $0 < \vert z-b \vert < \delta$, and if  $\lim_{z \rightarrow b}(z-b)f(z)= 0$ then we call $b$ a **removeable singularity** of $f$.
</div>

<div class="proposition" markdown="1">

**Theorem 6.02:** Taylor's Theorem

If $f(z)$ is analytic in a region $\Omega \ni a$ then it has the following expansion
> $$f(z) = f(a) + f'(a)(z-a) + \frac{f''(a)}{2 !}(z-a)^2 + \cdots + \frac{f^{(n-1)}(a)}{(n-1)!}(z-a)^{n-1} + f_n(z)(z-a)^n$$ $$$$

where $f_n(z)$ is analytic in $\Omega$
</div>

<div class="example" markdown="1">

**Example:** 

Does there exist a function $f$, analytic in the punctured plane $C^* := \mathbb{C} \setminus 0$ such that 
> $$\forall_{z \in \mathbb{C} \setminus 0} \; \vert f(z) \vert \geq \frac{1}{\sqrt{\vert z \vert}}$$ $$$$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

Suppose such a function exists, as $f$ is strictly non-zero on $C^*$ then the function $g(z) = \frac{1}{f(z)}$ is also analytic on 
$C^*$ and satisfies its own inequality $\vert g(z) \vert \geq \sqrt{\vert z \vert}$. In particular $g$ is bounded on the punctured open ball $z \; : \; 0 < \vert z \vert < 1$ and hence has a removeable singularity at $0$. By the theorem on analytic extensions $g$ extends as an analytic function over all of $\mathbb{C}$. Fix $a \in \mathbb{C}$, $R > \vert a \vert$, and take $\gamma_R$ the circle of radius $R$ centered at $0$, then by Cauchy's Differential Formula
> $$g'(z) = \frac{1}{2 \pi i} \int\limits_{\gamma_R} \frac{g(z)}{(z-a)^2}dz$$ $$$$

Using Cauchy's estimate and the inequaltiy $\vert g(z) \vert \geq \sqrt{\vert z \vert}$ we obtain the upper bound
> $$\vert g'(z) \vert \leq \frac{1}{2 \pi} 2 \pi R \frac{\sqrt{R}}{(R - \vert a \vert)^2}$$ $$$$

Which tends to zero as $R \rightarrow \infty$ such that $g' \equiv 0$. So the function $g$, and therefore also function $f$, must be constant maps. However, this contradicts the initial assumption that $\vert f(z) \vert \geq \frac{1}{\sqrt{\vert z \vert}}$
</details>

</div>