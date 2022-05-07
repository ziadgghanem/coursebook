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


> **Definition(Algebra):**  

Let $V$ be a vector space over a field $K$ (either $\mathbb{R}$ or $\mathbb{C}$). We equip $V$ with an additional operation $*: V \times V \rightarrow V$ satisfying the properties $\forall x,y,z \in V$ and $\forall \alpha, \beta \in K:$

1. (Right Distributivity) $$(\alpha x + \beta y) * z = \alpha(x*z) + \beta(y*z)$$
2. (Left Distributivity) $$z * (\alpha a + \beta b) = \alpha(z*x) + \beta(z*y)$$

Then we say that $V$ is an algebra over the field $K$ or we may call $V$ a K-algebra and write $(V, *)$.  
In essence, an Algebra is a vector space with an additional operator that is bilinear. 

We will consider three classes of algebras, $(A, *)$ is called: <label for="reasonable_algebras" class="margin-toggle">&#8853;</label><input type="checkbox" id="reasonable_algebras" class="margin-toggle"/><span class="marginnote">For our purposes, an algebra satisfying atleast one of the above properties will be called *reasonable*.</span> 
1. Commutative if $$a*b = b*a \quad \forall a,b \in A$$
2. Associative if $$(a*b)*c = a*(b*c) \quad \forall a,b,c \in A$$
3. Unital if $$\exists e \in A$$ st $$\forall a \in A a*e=e*a=a$$


> ***Examples***  
1. $$(\mathbb{C}, \cdot)$$ The complex numbers with standard complex multiplication is *commutative,* *associative* and *unital*
2. $$(\bar{\mathbb{C}}, *)$$ The complex numbers with the following multiplication: $$\forall z_1, z_2 \in \mathbb{C} \quad z_1 * z_2 = \bar{z_1} * \bar{z_2}$$ is *commutative,* *associative* but *not unital*
3. $$(\mathbb{R} \bigoplus \mathbb{R}, *)$$ with the following multiplication: $$ \forall u = (u_1, u_2) v = (v_1, v_2) \quad u*v = (u_1v_1, u_2,v_2)$$ is *commutative,* *associative* and *unital*
4. $$(M(n,K), \cdot)$$ The group of $$n \times n$$ matrices with entries from field $$K$$ with the usual matrix multiplication. is *associative,* *unital* but *not commutative*
5. $$((C[a,b], K),*)$$ The space of functions continous over the interval $$[a,b] \subset K$$ with the usual function multiplication $$f*g = f(x) \cdot g(x) \, \forall x \in [a,b]$$ is *commutative,* *associative* and *unital*

If the underlying vector space $A$ is finite-dimensional then we say $(A,*)$ is a finite dimensional algebra.


> **Explicit Construction of Algebras from Vector Spaces** 

Given an n-dimensional vector space $A$ one might want to define a multiplication $*$ on this space to construct an algebra $$(A,*).$$ This can be achieved as follows:

1. Take a basis $$\{e_1, \ldots , e_n \}$$
2. Fix indices $$i,j$$ from $$1:n$$ and put 
    - $$e_j * e_i := \sum_{k=1}^n \alpha_{i \, j}^{k} e_{k} = \alpha_{i \, j}^{1} e_{1} + \cdots + \alpha_{i \, j}^{n} e_{n}$$ 
where $$\alpha_{i \, j}^{k}$$ are chosen from our field.
3. In general we will need to specify $$n^3$$ coefficients $$\alpha_{i \, j}^{k} \in K$$ in order to define a particular multiplication over $$A$$.
4. If, in particular, we wanted to define a *commutative* multiplication then $$\forall i,j,k \quad \alpha_{i \, j}^{k}= \alpha_{j \, i}^{k}$$


> ***Example***  

Take $$\mathbb{C}$$ and define the usual complex multiplication $$*$$ using the above strategy. 

We have the standard basis $e_1 = (1,0), e_2 = (0,1)$. As complex multiplication is *commutative* it is sufficient to define six coefficients: $ \begin{pmatrix} \alpha_{1} & \alpha_{2} & \alpha_{3}\\\ \beta_{1} & \beta_{2} & \beta_{3} \end{pmatrix}$ 
$$= \begin{pmatrix} 1 & 0 & -1\\\ 0 & 1 & 0 \end{pmatrix}$$
1. $$e_1 * e_1 = \alpha_{1}e_1 + \beta_{1}e_2 = e_1$$ $$\iff$$ $$(1,0)*(1,0) = (1,0) $$ $$\iff$$ $$1 \cdot 1 = 1$$
2. $$e_1 * e_2 = \alpha_{2}e_1 + \beta_{2}e_2 = e_2$$ $$\iff$$ $$(1,0)*(0,1) = (0,1) $$ $$\iff$$ $$1 \cdot i = i$$
3. $$e_2 * e_2 = \alpha_{3}e_1 + \beta_{3}e_2 = -e_1$$ $$\iff$$ $$(0,1)*(0,1) = (-1,0) $$ $$\iff$$ $$i \cdot i = -1$$

So for $x = (x_1, x_2), y = (y_1, y_2) \in \mathbb{C}$ we have the expected product
- $$ (x_1, x_2)*(y_1, y_2)$$ $$ = (\alpha_{1}x_1y_1 + \alpha_{3}x_2y_2 , \beta_{2}x_1y_2 + \beta_{2}x_2y_2) = (x_1y_1 - x_2y_2, x_1y_2 + x_2y_2)$$


> **Definition: Left Multiplication Matrix, norm, trace** 

Given an algebra $(A,*)$ take a fixed element $x \in A.$ We define the so-called *left multiplication matrix,* $J_A(x): A \rightarrow A,$ as $J_A(x) \cdot y := x * y$ In addition, we define:
1. The *norm of A:* $$ \quad \gamma_2 := \det J_A(x)$$
2. The *trace of A:* $$\quad \gamma_1 := \operatorname{Tr} J_A(x)$$




> ***Example***

Take $(\mathbb{C}, \cdot)$ the complex numbers with their usual multiplication. For any, $z_1 = (x_1,y_1), z_2 = (x_2,y_2),$ we should have $z_1 \cdot z_2 = (x_1 x_2 - y_1 y_2, x_1 y_2 + x_2 y_1)$ The appropriate left multiplication matrix is: $J_A(z_1) = \begin{pmatrix}x_1 & -y_1\\\ y_1 & x_1\end{pmatrix}$ with norm  $\gamma_2 = \det (J_A(x)) = x_1^2 + y_1^2 = \lVert z_1 {\rVert}_{2}^2$ and trace $ \gamma_1 = \operatorname{Tr} J_A(x) = 2x_1$

To confirm we take $J_A(z_1)z_2 = \begin{pmatrix}x_1 & -y_1\\\ y_1 & x_1\end{pmatrix} \begin{pmatrix}x_2 \\\ y_2 \end{pmatrix} = \begin{pmatrix}x_1 x_2 - y_1 y_2 \\\ x_1 y_2 + x_2 y_1 \end{pmatrix} = z_1 \cdot z_2$


**Table Of Classification for**

| $N$         | Price     | # In stock |
|--------------|-----------|------------|
| Juicy Apples | 1.99      | *7*        |
| Bananas      | **1.89**  | 5234       |

Theorem