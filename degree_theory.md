---
layout: post
title: 'Planar Degree Theory'
---

<hr>

### algebras and the existence of bounded/periodic solutions to dynamical systems 

Definition (Algebra): Let $V$ be a vector space over a field $K$ (either $\mathbb{R}$ or $\mathbb{C}$). We equip $V$ with an additional operation $*: V \times V \rightarrow V$ satisfying the properties $\forall x,y,z \in V$ and $\forall \alpha, \beta \in K:$

1. (Right Distributivity) $$(\alpha x + \beta y) * z = \alpha(x*z) + \beta(y*z)$$
2. (Left Distributivity) $$z * (\alpha a + \beta b) = \alpha(z*x) + \beta(z*y)$$

Then we say that $V$ is an algebra over the field $K$ or we may call $V$ a K-algebra and write $(V, *)$. 

In essence, an Algebra is a vector space with an additional operator that is bilinear.

We will consider three classes of algebras, $(A, *)$ is called:
1. Commutative if $$a*b = b*a \quad \forall a,b \in A$$
2. Associative if $$(a*b)*c = a*(b*c) \quad \forall a,b,c \in A$$
3. Unital if $$\exists e \in A$ st $\forall a \in A a*e=e*a=a$$

For our purposes, an algebra satisfying atleast one of the above properties will be called *reasonable*.



