---
layout: post
title: 'Planar Degree Theory'
---

<blockquote>
        Mathematicians are a kind of Frenchmen. Whenever you say anything or talk to them, they translate it into their own language, and right away it is something completely different.
        <footer>Goethe</footer>
</blockquote>

<hr>

### algebras and the existence of bounded/periodic solutions to dynamical systems 

---
**Definition(Algebra):**  Let $V$ be a vector space over a field $K$ (either $\mathbb{R}$ or $\mathbb{C}$). We equip $V$ with an additional operation $*: V \times V \rightarrow V$ satisfying the properties $\forall x,y,z \in V$ and $\forall \alpha, \beta \in K:$

1. (Right Distributivity) $$(\alpha x + \beta y) * z = \alpha(x*z) + \beta(y*z)$$
2. (Left Distributivity) $$z * (\alpha a + \beta b) = \alpha(z*x) + \beta(z*y)$$

Then we say that $V$ is an algebra over the field $K$ or we may call $V$ a K-algebra and write $(V, *)$.  
In essence, an Algebra is a vector space with an additional operator that is bilinear. 
---

We will consider three classes of algebras, $(A, *)$ is called: <label for="reasonable_algebras" class="margin-toggle">&#8853;</label><input type="checkbox" id="reasonable_algebras" class="margin-toggle"/><span class="marginnote">For our purposes, an algebra satisfying atleast one of the above properties will be called *reasonable*.</span> 
1. Commutative if $$a*b = b*a \quad \forall a,b \in A$$
2. Associative if $$(a*b)*c = a*(b*c) \quad \forall a,b,c \in A$$
3. Unital if $$\exists e \in A$$ st $$\forall a \in A a*e=e*a=a$$

***Examples***
1. $$(\mathbb{C}, \cdot)$$ The complex numbers with standard complex multiplication is *commutative,* *associative* and *unital*
2. $$(\bar{\mathbb{C}}, *)$$ The complex numbers with the following multiplication: $$\forall z_1, z_2 \in \mathbb{C} \quad z_1 * z_2 = \bar{z_1} * \bar{z_2}$$ is *commutative,* *associative* but *not unital*
3. $$(\mathbb{R} \bigoplus \mathbb{R}, *)$$ with the following multiplication: $$ \forall u = (u_1, u_2) v = (v_1, v_2) \quad u*v = (u_1v_1, u_2,v_2)$$ is *commutative,* *associative* and *unital*
4. $$(M(n,K), \cdot)$$ The group of $$n \times n$$ matrices with entries from field $$K$$ with the usual matrix multiplication. is *associative,* *unital* but *not commutative*
5. $$((C[a,b], K),*)$$ The space of functions continous over the interval $$[a,b] \subset K$$ with the usual function multiplication $$f*g = f(x) \cdot g(x) \, \forall x \in [a,b]$$ is *commutative,* *associative* and *unital*

If the underlying vector space $A$ is finite-dimensional then we say $(A,*)$ is a finite dimensional algebra.

**Construction of Algebras from Vector Spaces** 

Given an n-dimensional vector space $A$ one might want to define a multiplication $*$ on this space to construct an algebra $$(A,*).$$ This can be achieved as follows:

1. Take a basis $$\{e_1, \ldots , e_n \}$$
2. Fix indices $$i,j$$ from $$1:n$$ and put 
    - $$e_j * e_i := \sum_{k=1}^n \alpha_{i \, j}^{k} e_{k} = \alpha_{i \, j}^{1} e_{1} + \cdots + \alpha_{i \, j}^{n} e_{n}$$ 
where $$\alpha_{i \, j}^{k}$$ are chosen from our field.
3. In general we will need to specify $$n^3$$ coefficients $$\alpha_{i \, j}^{k} \in K$$ in order to define a particular multiplication over $$A$$.
4. If, in particular, we wanted to define a *commutative* multiplication then $$\forall i,j,k \quad \alpha_{i \, j}^{k}= \alpha_{j \, i}^{k}$$

