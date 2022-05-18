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

**<u>Definition(Algebra):</u>**

Let $V$ be a vector space over a field $K$ (either $\mathbb{R}$ or $\mathbb{C}$). We equip $V$ with an additional operation $*: V \times V \rightarrow V$ satisfying the properties $\forall x,y,z \in V$ and $\forall \alpha, \beta \in K:$

1. (Right Distributivity) $$(\alpha x + \beta y) * z = \alpha(x*z) + \beta(y*z)$$
2. (Left Distributivity) $$z * (\alpha a + \beta b) = \alpha(z*x) + \beta(z*y)$$

Then we say that $V$ is an algebra over the field $K$ or we may call $V$ a K-algebra and write $(V, *)$.  
In essence, an Algebra is a vector space with an additional operator that is bilinear. 

We will consider three classes of algebras, $(A, *)$ is called: <label for="reasonable_algebras" class="margin-toggle">&#8853;</label><input type="checkbox" id="reasonable_algebras" class="margin-toggle"/><span class="marginnote">For our purposes, an algebra satisfying atleast one of the above properties will be called *reasonable*.</span> 
1. Commutative if $$a*b = b*a \quad \forall a,b \in A$$
2. Associative if $$(a*b)*c = a*(b*c) \quad \forall a,b,c \in A$$
3. Unital if $$\exists e \in A$$ st $$\forall a \in A$$ $$a*e=e*a=a$$


<div class="example" markdown="1">

**Examples: Reasonable Algebras**

1. $$(\mathbb{C}, \cdot)$$ The complex numbers with standard complex multiplication is *commutative,* *associative* and *unital*
2. $$(\bar{\mathbb{C}}, *)$$ The complex numbers with the following multiplication: $$\forall z_1, z_2 \in \mathbb{C} \quad z_1 * z_2 = \bar{z_1} * \bar{z_2}$$ is *commutative,* *associative* but *not unital*
3. $$(\mathbb{R} \bigoplus \mathbb{R}, *)$$ with the following multiplication: $$ \forall u = (u_1, u_2) v = (v_1, v_2) \quad u*v = (u_1v_1, u_2,v_2)$$ is *commutative,* *associative* and *unital*
4. $$(M(n,K), \cdot)$$ The group of $$n \times n$$ matrices with entries from field $$K$$ with the usual matrix multiplication. is *associative,* *unital* but *not commutative*
5. $$((C[a,b], K),*)$$ The space of functions continous over the interval $$[a,b] \subset K$$ with the usual function multiplication $$f*g = f(x) \cdot g(x) \, \forall x \in [a,b]$$ is *commutative,* *associative* and *unital*

</div>

If the underlying vector space $A$ is finite-dimensional then we say $(A,*)$ is a finite dimensional algebra.

---

**<u>Explicit Construction of Algebras from Vector Spaces</u>**

Given an n-dimensional vector space $A$ one might want to define a multiplication $*$ on this space to construct an algebra $$(A,*).$$ This can be achieved as follows:

1. Take a basis $$\{e_1, \ldots , e_n \}$$
2. Fix indices $$i,j$$ from $$1:n$$ and put 
    * $$e_j * e_i := \sum_{k=1}^n \alpha_{i \, j}^{k} e_{k} = \alpha_{i \, j}^{1} e_{1} + \cdots + \alpha_{i \, j}^{n} e_{n}$$ 
where $$\alpha_{i \, j}^{k}$$ are chosen from our field.
3. In general we will need to specify $$n^3$$ coefficients $$\alpha_{i \, j}^{k} \in K$$ in order to define a particular multiplication over $$A$$.
4. If, in particular, we wanted to define a *commutative* multiplication then $$\forall i,j,k \quad \alpha_{i \, j}^{k}= \alpha_{j \, i}^{k}$$


<div class="example" markdown="1">

**Example**

Take $$\mathbb{C}$$ and define the usual complex multiplication $$*$$ using the above strategy. 

We have the standard basis $e_1 = (1,0), e_2 = (0,1)$. As complex multiplication is *commutative* it is sufficient to define six coefficients: $ \begin{pmatrix} \alpha_{1} & \alpha_{2} & \alpha_{3}\\\ \beta_{1} & \beta_{2} & \beta_{3} \end{pmatrix}$ 
$$= \begin{pmatrix} 1 & 0 & -1\\\ 0 & 1 & 0 \end{pmatrix}$$
1. $$e_1 * e_1 = \alpha_{1}e_1 + \beta_{1}e_2 = e_1$$ $$\iff$$ $$(1,0)*(1,0) = (1,0) $$ $$\iff$$ $$1 \cdot 1 = 1$$
2. $$e_1 * e_2 = \alpha_{2}e_1 + \beta_{2}e_2 = e_2$$ $$\iff$$ $$(1,0)*(0,1) = (0,1) $$ $$\iff$$ $$1 \cdot i = i$$
3. $$e_2 * e_2 = \alpha_{3}e_1 + \beta_{3}e_2 = -e_1$$ $$\iff$$ $$(0,1)*(0,1) = (-1,0) $$ $$\iff$$ $$i \cdot i = -1$$

So for $x = (x_1, x_2), y = (y_1, y_2) \in \mathbb{C}$ we have the expected product
* $$ (x_1, x_2)*(y_1, y_2)$$ $$ = (\alpha_{1}x_1y_1 + \alpha_{3}x_2y_2 , \beta_{2}x_1y_2 + \beta_{2}x_2y_2) = (x_1y_1 - x_2y_2, x_1y_2 + x_2y_2)$$

</div>

**<u>Definition: Left Multiplication Matrix, norm, trace</u>**

Given a K-algebra $(A,*)$ take a fixed element $x \in A.$ We define the so-called *left multiplication matrix,* $J_A(x): A \rightarrow A,$ as $J_A(x) \cdot y := x * y$ In addition, we define:
1. The *norm* of A, $$\gamma_2: A \rightarrow K$$ 
    > $$ \quad \gamma_2(x)$$ $$:= \det J_A(x)$$
2. The *trace* of A, $$\gamma_1: A \rightarrow K$$ 
    > $$\quad \gamma_1(x)$$ $$:= \operatorname{Tr} J_A(x)$$

<div class="example" markdown="1">

**Example (the complex numbers)**

Take $(\mathbb{C}, \cdot)$ the complex numbers with their usual multiplication. For any, $z_1 = (x_1,y_1), z_2 = (x_2,y_2),$ we should have $z_1 \cdot z_2 = (x_1 x_2 - y_1 y_2, x_1 y_2 + x_2 y_1)$ The appropriate left multiplication matrix is: $J_A(z_1) = \begin{pmatrix}x_1 & -y_1\\\ y_1 & x_1\end{pmatrix}$ with norm  $\gamma_2 = \det (J_A(x)) = x_1^2 + y_1^2 = \lVert z_1 {\rVert}_{2}^2$ and trace $ \gamma_1 = \operatorname{Tr} J_A(x) = 2x_1$

To confirm we take $J_A(z_1)z_2 = \begin{pmatrix}x_1 & -y_1\\\ y_1 & x_1\end{pmatrix} \begin{pmatrix}x_2 \\\ y_2 \end{pmatrix} = \begin{pmatrix}x_1 x_2 - y_1 y_2 \\\ x_1 y_2 + x_2 y_1 \end{pmatrix} = z_1 \cdot z_2$
</div>

---

<div class="example" markdown="1">

**Example**

Take the algebra  $(\mathbb{R} \bigoplus \mathbb{R}, *)$ 
equipped with multiplication 
$(x_1,y_1)*(x_2,y_2) = (x_1 x_2, y_1 y_2)$ this algebra has
1. Left multiplication matrix:  $$J_A(z_1) = \begin{pmatrix}x_1 & 0\\\ 0 & y_1\end{pmatrix}$$ 
2. Norm: $$\gamma_2(z_1) = x_1 y_1$$
3. Trace: $$\gamma_1(z_1) = x_1 + y_1$$

</div>

<div class="proposition" markdown="1">

**<u>Theorem (Cayley-Hamilton):</u>**

Let $(A,*)$ be a 2-dimensional algebra, then $\forall x,y \in A$

> $$ x*(x*y)$$ $$= \gamma_{1}(x) (x*y) - \gamma_{2}(x) y$$ 

</div>

**<u>Corollary</u>**

If in addition $(A,*)$ is commutative, we have 

> $$x*(x*x) = x^3$$ $$= \gamma_{1}(x) x^2 - \gamma_{2}(x) x$$ 

<div class="proof" markdown="1">

**Proof (Cayley-Hamilton)** 

Consider the left multiplication matrix, $J_A(x)$, associated with a 2-dimensional algebra $(A,*).$ with characteristic polynomial $P( \lambda ) = \lambda^2 -  \operatorname{Tr}(J_A) \lambda + \det(J_A) \cdot \mathbb{1}_{2}$ We will need the following lemma:

**<u>Lemma: (square matrix as root of its own characteristic polynomial)</u>** <br>
For any $n \times n$ matrix $A$ with characteristic polynomial $P( \lambda ) = a_0 + a_1 \lambda + \cdots + a_n \lambda^n$ we have:
<label for="charpoly_annihilation" class="margin-toggle">&#8853;</label><input type="checkbox" id="charpoly_annihilation" class="margin-toggle"/><span class="marginnote">i.e. any square matrix *annihilates* its characteristic polynomial.</span> 

> $$P(A) =  a_0 + a_1 A + \cdots + a_n A^n$$ $$= 0$$

**Proof (Lemma Case: $n=2$)** <br>
Take $A =  \begin{pmatrix}a & b\\\ c & d\end{pmatrix},$ it is well known that the characteristic polynomial of a $2 \times 2$ matrix is given by: 
> $$ P( \lambda ) = \lambda^2 -  \operatorname{Tr}(A) \lambda + \det(A) \cdot \mathbb{1}_{2}$$ 

If we evaluate valuate $A$ with its characteristic polynomial we obtain:
> $$P(A) = A^2 - \operatorname{Tr}(A) A + \det(A) \cdot \mathbb{1}_{2} $$
> $$ P(A) = \begin{pmatrix}a & b\\\ c & d\end{pmatrix} \begin{pmatrix}a & b\\\ c & d\end{pmatrix} - (a+d) \begin{pmatrix}a & b\\\ c & d\end{pmatrix} + \begin{pmatrix}ad - bc & 0\\\ 0 & ad - bc\end{pmatrix} $$
> $$ = \begin{pmatrix}a^2 + bc - a^2 - ad + ad - bc & ab + bd - ab - db\\\ ca + dc - ac + dc & cb + d^2 - ad - d^2 + ad -bc \end{pmatrix} = \begin{pmatrix}0 & 0\\\ 0 & 0\end{pmatrix}$$ $$\blacksquare$$

The characteristic polynomial of the left multiplication matrix, $J_A(x)$, is
> $$P( \lambda ) = \lambda^2 -  \operatorname{Tr}(J_A) \lambda + \det(J_A) \cdot \mathbb{1}_{2}$$

By **Lemma** we have: 
> $$ P(J_A(x)) = J_A(x)^2 - \operatorname{Tr}(J_A(x)) J_A(x) + \det(J_A(x)) \cdot \mathbb{1}_{2} = 0 $$ 
> $$\rightarrow $$
> $$ J_A(x)^2 = \operatorname{Tr}(J_A(x)) J_A(x) - \det(J_A(x)) \cdot \mathbb{1}_{2}$$
> $$\rightarrow $$
> $$ J_A(x)^2 y = \operatorname{Tr}(J_A(x)) J_A(x) y - \det(J_A(x)) y = \gamma_{1}(x)(x*y) -  \gamma_{2}(x) y$$
> Note $$J_A(x) \cdot y := x * y$$ $$\rightarrow$$ $$x*(x*y) = x*(J_A(x)y) = J_A(x) J_A(x) y = J_A(x)^2 y$$ 

</div>

### Algebraic Terminology

The element $a$ in a K-algebra, $(A,*),$ $a \neq 0,$ is called **idempotent** if $a^2=a$

<div class="example" markdown="1">

**Example: (idempotence in unital algebras)**

Take any unital algebra $(A,*)$ then for the unital element $e\in A$
it is always the case that $e^2 = e$
</div>

The element $b$ in the K-algebra, $(A,*),$ $b \neq 0,$ is called **2-nilpotent** if $a^2 = 0$
<label for="multiple_2nilpotence" class="margin-toggle">&#8853;</label><input type="checkbox" id="multiple_2nilpotence" class="margin-toggle"/><span class="marginnote">If $u$ is a 2-nilpotent, then so is $\alpha u$ for all $\alpha \in K$.</span> 


<div class="example" markdown="1">

**Example: (2-nilpotence in matrix algebra)**

Consider the matrix algebra $(M(2,K), \cdot).$ Take $a = \begin{pmatrix}0 & 1\\\ 0 & 0\end{pmatrix}$ and verify that $a^2 = \begin{pmatrix}0 & 0\\\ 0 & 0\end{pmatrix}$
</div>

<div class="proposition" markdown="1">
<u>Theorem: (certainty of idempotence in algebra without 2-nilpotents)</u>

Let $(A,*)$ be an arbitrary K-algebra, assume that $A$ does not admit 2-nilpotents, then A admits atleast one idempotent.
</div>

<div class="proof" markdown="1">

**Proof:**

We will employ degree theory. Consider the map $\phi: A \rightarrow A$ given by $\phi(u) = u - u^2$ and assume, by contradiction, that $A$ admits neither 2-nilpotents nor idempotents.
<label for="consequence_idempotent" class="margin-toggle">&#8853;</label><input type="checkbox" id="consequence_idempotent" class="margin-toggle"/><span class="marginnote">As A does not admit idempotents, $\forall u \in A$ with $u \neq 0,$ $u^2 \neq u \rightarrow \phi(u) \neq 0$ such that $\phi$ is admissible on any neighborhood of $0$.</span> 

1. Near the origin, $$\phi_0(u) := u$$ is a principle part of our map with $$ind(0, \phi_0) = 1$$
2. On a sufficiently large ball $$B:=B_R(0),$$ $$\phi_{\infty}(u) := u^2,$$ an even map, is a principle part of $\phi$ such that $deg(\phi_{\infty})$ is even. 
<label for="consequence_nilpotence" class="margin-toggle">&#8853;</label><input type="checkbox" id="consequence_nilpotence" class="margin-toggle"/><span class="marginnote">We are only guaranteed admissibility of $\phi_{\infty}$ on the ball $B$ as $A$ does not admit 2-nilpotents. Indeed, suppose $v$ was a 2-nilpotent of $A,$ but then $\phi_{\infty}(u) = 0$ would have a ray solution in the direction of $v$ passing through the origin prohibiting admissibility on any ball about the origin.</span>

Homotopy equivalence is an equivalence relation, in particular it is a transitive relation, such that $ind(0, \phi_0) = ind(0, \phi_{\infty}),$ contradiction.
</div>

Let algebra $(A,*)$ be associative -or- commutative -or- both. Then $a \in A$ is called **3-nilpotent** if $a^2 \neq 0$ but $a^3 = 0$


<div class="example" markdown="1">

**Example: (3-nilpotence in matrix algebra)**

Consider the matrix algebra $(M(3,\mathbb{R}), \cdot).$ Take $a =  \begin{pmatrix}0 & 1 & 0\\\ 0 & 0 & 1\\\ 0 & 0 & 0\end{pmatrix}$ and verify that $a^2 \neq a^3 = \begin{pmatrix}0 & 0 & 0\\\ 0 & 0 & 0 \\\ 0 & 0 & 0 \end{pmatrix}$
</div>

If $(A,*)$ is a K-algebra, then $x \in A, x \neq 0$ is called a **zero-divisor** if $\exist y \in A, y \neq 0$ such that $x*y=0$ <label for="nilpotence_zdivisor" class="margin-toggle">&#8853;</label><input type="checkbox" id="nilpotence_zdivisor" class="margin-toggle"/><span class="marginnote"> Any 2-nilpotent element, $$x$$, is a zero-divisor of itself.</span>

In order to embark on the perilous, crucial passage from algebra theory to their application in the study of dynamical systems we will have to discuss special classes of algebra, the first of which is the division algebra.

$(A,*)$ is called a division algebra if it does not admit zero-divisors.

<div class="example" markdown="1">

**Example: (division algebras)**

1. $$\mathbb{C}$$ is a division algebra
2. $$\bar{\mathbb{C}}$$ is a division algebra
3. $$\mathbb{R} \bigoplus \mathbb{R}$$ is not a division algebra, take for instance $$(1,0)*(0,1) = (0,0)$$

</div>

The next class of special algebras is the so-called regular algebra.

$(A,*)$ is called a **regular** algebra if $\exists x \in A$ such that $J_A(x)$ is invertible.

On the other hand, we call an algebra $(A,*)$ **singular** if $\forall x \in A$ the matrix $J_A(x)$ is singular, i.e. $det J_A(x) = 0$. <label for="norm_singularalgebras" class="margin-toggle">&#8853;</label><input type="checkbox" id="norm_singularalgebras" class="margin-toggle"/><span class="marginnote"> As one might suspect, the norm is an important tool in the study of regular alegbras and not so for singular algebras.</span>

<div class="proposition" markdown="1">

**Proposition**
Suppose $(A,*)$ is singular, then for every element in $x \in A,$ $x$ is a zero-divisor.

</div>

<div class="proof" markdown="1">

**Proof**
Let $(A,*)$ be a singular algebra. 
* For every element, $$x \in A,$$ the left multiplication matrix $$J_A(x)$$ is singular 
> $$\rightarrow$$
* $$J_A(x)$$, has a nontrivial kernel in $$A$$
> i.e. $$\exists y \neq 0 \in A$$ with $$J_A(x)y = x * y = 0$$

Hence, $x$ is a zero divisor. $\blacksquare$
</div>

Given two algebras $(A,*)$ and $(B,\cdot)$ we call the map 
$\phi: A \rightarrow B$ a homomomorphism if it is 
structure preserving, i.e. if
> $$\forall x,y \in A \quad \phi(x*y) = \phi(x) \cdot \phi(y)$$

If, in addition, $\phi$ is invertibile, then it is an isomorphism and we say that the algebras are *isomoprhic.* Furthermore, we have the following relation
> $$x*y = \phi^{-1}[\phi(x) \cdot \phi(y)]$$

<div class="proposition" markdown="1">

**Theorem (Classification of Commutative 2-dimensional Algebras)**
All 2-dimensional commutative algebras are completely described, up to isomorphism, with six classes. They are distinguished by two invariants: number of idempotents, number of 2-nilpotents.

</div>

Notation | Number of Idempotents | Number of Nilpotents | Multiplication Table
---|---|---|---|---|---|---
$N^0_{\infty}$|  | 0 |  | $\infty$ |  | $\begin{pmatrix} 0 & 0 & 0\\\ 0 & 0 & 0 \end{pmatrix}$
$N^1_{0}$|  | 1 |  | 0 |  | $\begin{pmatrix} 1 & 0 & 1\\\ 0 & 1 & 0 \end{pmatrix}$
$N^1_{1}$|  | 1 |  | 1 |  | $\begin{pmatrix} 1 & 0 & 0\\\ 0 & 0 & 0 \end{pmatrix}$
$N^1_{2}$|  | 1 |  | 2 |  | $\begin{pmatrix} 1 & 0 & -1\\\ 0 & 0 & 0 \end{pmatrix}$
$N^0_{1}$|  | 0 |  | 1 |  | $\begin{pmatrix} 0 & 0 & 0\\\ 1 & 0 & 0 \end{pmatrix}$
$N^0_{2}$|  | 0 |  | 2 |  | $\begin{pmatrix} 0 & 0 & 0\\\ 1 & 0 & 0 \end{pmatrix}$

**<u>Definition (Rank 3-algebra):</u>**

A real commutative algebra $(A,*)$ is called rank-3 if $x^3 = \gamma_1(x) x^2 - \gamma_2(x) x$ 
<label for="column_rank" class="margin-toggle">&#8853;</label><input type="checkbox" id="column_rank" class="margin-toggle"/><span class="marginnote"> Recall that, in linear algebra, the rank of a matrix is the dimension of the vector space spanned by its columns.</span>


<div class="proposition" markdown="1">

**Theorem (First Main Theorem)**

Let $(A,*)$ be a real commutative 2-dimensional rank-3 algebra, then:
1. Regular algebra A is a division algebra iff the norm is uniformly positive definite or uniformly negative definite i.e. iff $$\gamma_2(x) > 0 \forall x \neq 0 \in A$$ or  $$\gamma_2(x) < 0 \forall x \neq 0 \in A$$
2. Regular algebra A, admits a basis of zero-divisors iff the norm is indefinite i.e. iff $$\exists x,y \neq 0$$ such that $$\gamma_2(x) > 0$$ and $$\gamma_2(y) < 0$$
3. A admits a 2-nilpotent elelment iff the norm is uniformly positive semi-definite or uniformly negative semi-definite i.e. iff $$ \gamma_2(x) \geq 0 \forall x \in A$$ and $$\exists y \neq 0$$ with $$ \gamma_2(y) = 0$$ or $\gamma_2(x) \leq 0 \forall x \in A$$ and $$\exists y \neq 0$$ with $$ \gamma_2(y) = 0$$
4. A is singular iff the norm is identically zero i.e. iff $$\gamma_2(x) \equiv 0$$

</div>

### passage between algebras and dynamical systems

Given a finite K-algebra $(A,*)$ of dimension $n$ we are interested in the quadratic differrential equation, called the Ricatti equation
> $$\dot{x} = x*x = x^2$$

Conversely, given a quadratic map $f: K^n \rightarrrow K^n,$ we will associate the algebra $(A,*)$ where $A=K^n$ and the multiplication is defined by the the polarization formula
> $$x*y = \frac{1}{2} [f(x+y) - f(x) - f(y)]

<div class="example" markdown="1">

**Example: (The Complex Numbers)**

We will show how the polarization formula retrieves the algebra associated to a quadratic map in the context of the complex numbers. Consider the map $f: \mathbb{C} \rightarrow \mathbb{C}$ 
> f(x_1,x_2) = (x^2_1 - x^2_2, x_1x_2)
<label for="complex_map" class="margin-toggle">&#8853;</label><input type="checkbox" id="complex_map" class="margin-toggle"/><span class="marginnote"> Note, for $x \in \mathbb{C},$ $x^2 = f(x)$.</span>


1. $$\mathbb{C}$$ is a division algebra
2. $$\bar{\mathbb{C}}$$ is a division algebra
3. $$\mathbb{R} \bigoplus \mathbb{R}$$ is not a division algebra, take for instance $$(1,0)*(0,1) = (0,0)$$

</div>

### formulation of Muhamadiev type results

---
**Theorem**

Consider the m-homogeneous map $P: \mathbb{R}^n \rightarrow \mathbb{R}^n$ satisfying the following properties
1. $P( \lambda x) = \lambda^m P(x)$ for all $\lambda \in \mathbb{R}$
2. if $P(x) = 0$ then x = 0
3. $ind(0,P)$ $\neq 0$
4. The system $\dot{x} = P(x)$ does not admit any bounded solutions

and $h: \mathbb{R} \times \mathbb{R}^n \rightarrow \mathbb{R}^n$ any map satisfying
1. *continuity*
2. *$\omega$ periodicity* 
    - $\exists \omega \in \mathbb{R}$ such that $h(t+\omega,x) = h(t,x)$
3. *asymptoticity* 
    - $\lim_{\vert x \vert \to \infty} \frac{h(t,x)}{\vert x \vert^m} = 0$ uniformly in t

Then the system $\dot{x} = P(x) + h(t,x)$ admits at least one periodic solution. <label for="no_perturbation" class="margin-toggle">&#8853;</label><input type="checkbox" id="no_perturbation" class="margin-toggle"/><span class="marginnote">Note: the result holds for $h \equiv	0$ as $x(t) \equiv 0$ solves $\dot{x} = P(x)$ by assumption and is trivially $\omega$ periodic.</span> 

**Termionolgy (Autonomous System)**  
Consider the system $\dot{x} = f(t,x)$ we say that $f(t,x)$ is autonomous as it depends explicitly on t. Otherwise the system is called non-autonomous
- e.g. $\dot{x}=x^2 + sin(t)$ is an autonomous system

### construction of degree theory in n-dimensions

Assume $\Omega$ is an open subset of $\mathbb{R}^n$ and $f: \Omega \rightarrow \mathbb{R}^m$ a differrentiable map. The point $x_0 \in \Omega$ is called rregular if $$





