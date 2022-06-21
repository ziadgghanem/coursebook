---
layout: post
title: 'Complex Analysis'
---

<blockquote>
        The object of mathematics is the honor of the human spirit.
        <footer>Jacobi</footer>
</blockquote>

<hr>

A mathematical result must first be appreciated according to its aesthetics and only after for any practical application. As in all things, an aesthetic result cuts to the heart of things using only as much as is necessary to make its point.  

# 1. The Complex Numbers

The set of complex numbers consists of all $z = a + ib$ with $a,b \in \mathbb{R}$ where the imaginary number, $i$, is defined as a solution of the equation $i^2 = -1$
> $$\mathbb{C} := \lbrace z = a + ib \; : \; a,b \in \mathbb{R} \rbrace $$

Every complex number $z = a + ib$ has a one-to-one and onto correspondence with the point on the plane $(a,b)$. We call the plane in which complex numbers are represented in this way, the complex plane.

We define two projections $Re: \mathbb{C} \rightarrow \mathbb{R}$, $Im: \mathbb{C} \rightarrow \mathbb{R}$ onto the real and imaginary parts of the complex number $z = a + ib$
> $$Re(z) = a \quad Im(z) = b$$ $$$$

The equality of two complex numbers  $z = a + ib$,  $w = c + id$ is the respective equality of their real and imaginary parts.
> $$ (a + ib) = (c + id) \quad \iff \quad a = c \; \land \; b = d$$ $$$$

The addition of two complex numbers is the sum of their real and imaginary parts.
> $$ (a + ib) + (c + id) = a + c + i (b + d)$$ $$$$

The multiplication of two complex numbers follows naturally from the product of binomials and the fact that $i^2 = -1$
> $$ (a + ib)(c + id) = ac + iad + ibc + i^2bd = (a - bd) + i(ad + bc)$$ $$$$

The set of complex numbers $\mathbb{C}$ together with its addition and multiplication operations is a field, and so both operations come with the properties of commutivaty, associativity, distributivity along with neutral elements, $(0,0)$ for addition and $(1,0)$ for multiplication, and inverses for all elements with respect to both operations except for $(0,0)$ with respect to multiplication.

For any $z = a + ib$, its additive inverse is called the opposite of $z$ and has the obvious form $-z = -a - ib$ such that $z + (-z)= 0$

For any $z = a + ib$, with $a,b$ not simultaneously equal to $0$, its multiplicative inverse is given by
> $$z^{-1} = \frac{a}{a^2 + b^2} - \frac{b}{a^2 + b^2}$$ $$$$

The complex conjugate $\overline{z}$ a the complex number $z = a+ib$ is defined $\overline{z} = a - ib$ and is the geometric reflection of a point across the real axis on the complex plane. The product of a complex number with its conjugate is the sum of the square of its real part with the square of its imaginary part.
> $$(a + ib)(a - ib) = (a^2 + b^2) + i(ab - ab) = a^2 + b^2$$

<div class="proposition" markdown="1">

**Proposition 1.01:**  Properties of the Conjugate

The complex conjugate has the following properties
1. $$ \overline{i} = - i$$ $$$$
2. If $$Im(z) = 0$$ then $$\overline{z} = z$$
3. $$\overline{z_1 + z_2} = \overline{z_1} + \overline{z_2}$$ $$$$
4. $$\overline{z_1 z_2} = \overline{z_1} \overline{z_2}$$ $$$$
5. $$\overline{\overline{z}} = z$$ $$$$
6. $$Re(z) = \frac{z + \overline{z}}{2}$$  $$$$
7. $$Im(z) = \frac{z - \overline{z}}{2i}$$ $$$$

</div>

The quotient of two complex numbers may be calculated by multiplying both numerator and denominator with the complex conjugate of the demonimator
> $$\frac{a + ib}{c + id} = \frac{a + ib}{c + id} \frac{c - id}{c - id} = \frac{(ac + bd) + i(bc - ad)}{c^2 + d^2}$$

The modulus $\vert z \vert$ of a complex number $z = a + ib$ is the length of the corresponding vector $(a,b)$ in the complex plane i.e. $\vert z \vert =  \sqrt{a^2 + b^2}$. The following modulus identites are useful
- $$\vert z \vert = \sqrt{z \overline{z}} = \sqrt{Re(z)^2 + Im(z)^2}$$ $$$$
- $$\vert z \vert^2 = z \overline{z} = Re(z)^2 + Im(z)^2$$ $$$$
- $$\frac{1}{z} = \frac{\overline{z}}{\vert z \vert^2} = {\overline{z}}{Re(z)^2 + Im(z)^2}$$ $$$$

<div class="proposition" markdown="1">

**Proposition 1.01:**  Properties of the Modulus

The complex conjugate has the following properties
1. $$ \overline{i} = - i$$ $$$$
2. If $$Im(z) = 0$$ then $$\overline{z} = z$$
3. $$\overline{z_1 + z_2} = \overline{z_1} + \overline{z_2}$$ $$$$
4. $$\overline{z_1 z_2} = \overline{z_1} \overline{z_2}$$ $$$$
5. $$\overline{\overline{z}} = z$$ $$$$
6. $$Re(z) = \frac{z + \overline{z}}{2}$$  $$$$
7. $$Im(z) = \frac{z - \overline{z}}{2i}$$ $$$$

</div>

# 7. Calculus of Residues

## 7.1 The Residue

The basis of our discussion will be Cauchy's General Integral Formula, which states: Given a function $f$ analytic in a region $\Omega$, then for every cycle $\gamma$ that is homologous to zero in $\Omega$, 
> $$n(\gamma, a)f(a) = \frac{1}{2 \pi i} \int\limits_{\gamma} \frac{f(z)}{z-a}dz$$ $$$$

Now suppose we lose the assumption of analyticity in $\Omega$ and for the moment assume that $f$ is analytic in $\Omega$ except for a set of isolated singularities $\lbrace a_1, \ldots, a_n, \ldots \rbrace$. Recall that if $a$ is an isolated singularity of $f(z)$ then there exists a deleted neighborhood of $a$ where $f(z)$ is analytic.
- In the case that $$f(z)$$ has isolated singularity $$a \in C$$, then we have a neighborhood $0 < \vert z-a \vert < \delta$ in which $$f(z)$$ is analytic.
- In the case that $$f(z)$$ has isolated singularity $$a = \infty$$, then we have a neighborhood $R < \vert z \vert < \infty$ in which $$f(z)$$ is analytic.

<div class="definition" markdown="1">

**Definition:** Residue at an isolated singularity

The residue of $f(z)$ at an isolated singularity $a$ is defined with respect to an annular neighborhood $0 < \vert z-a \vert < \delta$ inside which $f(z)$ is analytic
> $$Res_{z=a}f(z) =  \frac{1}{2 \pi i} \int\limits_{c} f(z)dz$$ $$$$

where c is a positively oriented circle $\vert z-a \vert = r$ with $0 < r < \delta$.
</div>

<div class="proposition" markdown="1">

**Theorem 7.01:** Residue Theorem

Let $f(z)$ be analytic in a region $\Omega$, except for at isolated singularities $\lbrace a_j \rbrace$, and $\gamma$ a cycle homologous to zero in $\Omega$ and not passing through any $a_j$ then

The residue of $f(z)$ at an isolated singularity $a$ is defined with respect to an annular neighborhood $0 < \vert z-a \vert < \delta$ inside which $f(z)$ is analytic
> $$ \frac{1}{2 \pi i} \int\limits_{c} f(z)dz = \sum_{j}{n(\gamma, a_j) Res_{z = a_j}f(z)}$$ $$$$

In the case that $\gamma$ is simple we have $n(\gamma, a_j) = \begin{cases} 0 \\ 1 \end{cases}$ such that
> $$ \frac{1}{2 \pi i} \int\limits_{c} f(z)dz = \sum_{j}{Res_{z = a_j}f(z)}$$ $$$$

</div>

In the neighborhood of an isolated singularity a complex function $f(z)$ has a Laurent series representation in some annulus $0 < \vert z - a \vert < R$
> $$f(z) = \cdots + \frac{c_{-3}}{(z-a)^3} + \frac{c_{-2}}{(z-a)^2} + \frac{c_{-1}}{(z-a)} + c_0 + c_1(z-a) + c_2(z-a)^2 + \cdots$$ $$$$

<div class="proposition" markdown="1">

**Proposition 7.02:** 

The residue of $f(z)$ at an isolated singularity $a$ coincides with the coefficient of $\frac{1}{(z-a)}$ in its Lauent expansion about $a$, i.e.
> $$Res_{z = a}f(z) = c_{-1}$$ $$$$

</div>

<div class="proof" markdown="1">

**Proposition 7.02:** 

The residue of $f(z)$ at an isolated singularity $a$ coincides with the coefficient of $\frac{1}{(z-a)}$ in its Lauent expansion about $a$, i.e.
> $$Res_{z = a}f(z) = c_{-1}$$ $$$$

</div>

## 7.2 Calculation of Residues at Isolated Singularity

**i. Calculation of residue at a removeable singular point.** <br>
Let $z_0$ be a finite removeable singular point of the function $f(z)$, then the Laurent expansion of $f$ about $z_0$ has no principle part such that $Res_{z = z_0}f(z) = 0$.
- *Remark:* the residue of a function at a finite point $z_0$ may only be nonzero if $z_0$ is a pole or an essential singular point.

<hr>

**ii. Calculation of residue at a simple pole.** <br>
Let $z_0$ be a finite simple pole of the function $f(z)$, then its Laurent series expansion about $z_0$ must be of the form 
> $$f(z) =  \frac{c_{-1}}{(z-z_0)} + c_0 + c_1(z-z_0) + c_2(z-z_0)^2 + \cdots$$ $$$$

such that $f(z)(z-z_0) = c_{-1} + c_0(z-z_0)+ c_1(z-z_0)^2 + c_2(z-z_0)^3 + \cdots$ and so as we pass to the limit $z \rightarrow z_0$
> $$Res_{z = z_0} f(z) = c_{-1} = \lim_{z \rightarrow z_0}f(z)(z-z_0)$$ $$$$

<div class="example" markdown="1">

**Example:**  Find the residues of the function $f(z) = \frac{1}{z^2 + 1}$ at its finite singular points

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

First we must find the singular points of the function
> $$f(z) = \frac{1}{z^2 + 1} = \frac{1}{(z+i)(z-i)}$$ $$$$

We find that $f(z)$ has singular points at $z_1 = i$, $z_2 = -i$ and we notice that both are simple poles and so we may calculate the residues of $f$ at each as follows
> $$Res_{z = i} \frac{1}{(z+i)(z-i)} = \lim_{z \rightarrow i}{\frac{1}{(z+i)(z-i)}(z-i)} = \frac{1}{2i}$$ $$$$
> $$Res_{z = -i} \frac{1}{(z+i)(z-i)} = \lim_{z \rightarrow -i}{\frac{1}{(z+i)(z-i)}(z+i)} = \frac{-1}{2i}$$ $$$$

</details>
</div>

**ii.i Calculation of residue at a simple pole (Special Case).** <br>
Let $z_0$ be a finite simple pole of the function $f(z)$, which can be represented as the quoteint of two analytic functions $f(z) = \frac{g(z)}{h(z)}$ where $g(z_0) \neq 0$ and $h(z)$ such that $z_0$ is a zero of order one then we have
> $$Res_{z = z_0} f(z) = \lim_{z \rightarrow z_0}\frac{g(z)}{h(z)}(z-z_0) = \frac{g(z)}{\frac{h(z) - h(z_0)}{z-z_0}}$$ $$$$

And hence, we obtain the formula
> $$Res_{z = z_0} \frac{g(z)}{h(z)} = \frac{g(z_0)}{h'(z_0)}$$ $$$$


<div class="example" markdown="1">

**Example:**  Find the residues of the function $f(z) = \cot(z)$ at $z_0 = 0$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

First we note that $f(z) = \cot(z) = \frac{\cos(z)}{\sin(z)}$ indeed has a singular point at $z = 0$, furthermore $\cos(0) \neq 0$ and $\sin(z)$ has a zero of the first order at $z=0$ so
> $$Res_{z = 0} cot(z) = \frac{\cos(0)}{\sin'(0)} = \frac{\cos(0)}{\cos(0)} = 1$$ $$$$

</details>

**Example:**  Find the residues of the function $f(z) = \frac{1}{sinz}$ at each of its isolated singularities.

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

$f(z)$ has simple poles at the points $z_k = k \pi$ for all $k \in \mathbb{Z}$ and so
> $$Res_{z = z_k} \frac{1}{sinz} = \frac{1)}{\sin'(k \pi)} = \frac{1}{\cos(k \pi)} = (-1)^k$$ $$$$
</details>
</div>

**iii Calculation of residue at a multiple pole.** <br>
Let $z_0$ be a multiple pole of the function $f(z)$, then its Laurent series expansion about $z_0$ must be of the form 
> $$f(z) = \frac{c_{-n}}{(z-z_0)^n} + \frac{c_{-n+1}}{(z-z_0)^{n-1}} + \cdots + \frac{c_{-1}}{(z-z_0)} + c_0 + c_1(z-z_0) + \cdots$$ $$$$

such that $f(z)(z-z_0)^n = c_{-n} + c_{-n+1}(z-z_0) + \cdots c_{-1}(z-z_0)^{n-1} +  c_0(z-z_0)^n + \cdots$ and so as we pass to the limit $z \rightarrow z_0$. If we differentiate this equation $(n-1)$ times we obtain
> $$\frac{d^{n-1}}{dz^{n-1}}[f(z)(z-z_0)^n] = c_{-1}(n-1)! + c_0 n! (z-z_0) + \cdots$$ $$$$

Hence, if we pass to the limit $z \rightarrow z_0$ and divide by the factorial factor on $c_{-1}$ we obtain
> $$Res_{z = z_0} f(z) = c_{-1} = \frac{1}{(n-1)!}\lim_{z \rightarrow z_0}\frac{d^{n-1}}[f(z)(z-z_0)]$$ $$$$

<div class="example" markdown="1">

**Example:**  Find the residues of the function $f(z) = \frac{1}{(z^2 + 1)^3}$ at $z_0 = -i$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

First we note that $f(z) = \frac{1}{(z^2 + 1)^3} = \frac{1}{(z-i)^3(z+i)^3}$ has a pole of order $3$ at $z_0 = -i$
so will need to calculate two derivatives
> $$[\frac{1}{(z-i)^3(z+i)^3}(z+i)^3]'' = [\frac{1}{(z-i)^3]'' = [\frac{-3}{(z-i)^4]' = \frac{12}{(z-i)^5

Now we can directly calculate the residue
> $$Res_{z = -i} f(z) =  \frac{1}{2}\lim_{z \rightarrow -i}[\frac{12}{(z-i)^5] = \frac{1}{2} \frac{12}{(-2i)^5 = \frac{3i}{2^4}$$ $$$$

</details>
</div>

**iv Calculation of residue at an essential singular point.** <br>
In order to calculate the residue of $f(z)$ at an essential singular point $z_0$ is is necessary to determine the coefficient $c_{-1}$ in its Laurent series about the singularity. 

<div class="example" markdown="1">

**Example:**  Find the residues of the function $f(z) = e^{\frac{1}{z}}$ at $z_0 = 0$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

$f(z)$ has an essential singularity at $z=0$ so we must examine its Laurent series about this point
> $$e^{\frac{1}{z}} = 1 + \frac{1}{z} + \frac{1}{2 !} \frac{1}{z^2} + \cdots $$ $$$$

And so by observation $c_{-1} = 1$
> $$Res_{z = 0} f(z) = 1$$ $$$$

</details>
</div>

### Residues at Infinity

**v Calculation of residue at an infinite removeable singularity,** <b4>
Let $z_0 = \infty$ be a removeable singulaar point of the function $f(z)$, the expansion of its Laurent series about $\infty$ will have the form
> $$f(z) = c_0 + \frac{c_{-1}}{z} + \frac{c_{-2}}{z^2} + \cdots$$ $$\tag{v}$$

Such that the residue can be obtained $c_{-1} = \lim_{z \rightarrow \infty}[(f(z) - c_0) \cdot z]$ and if we put $f(\infty) = \lim_{z \rightarrow \infty}f(z) = c_0$ we have a formula for the residue
> $$Res_{z = \infty}f(z) = \lim_{z \rightarrow \infty}[f(\infty) - f(z)] \cdot z$$ $$$$

In particular, if $z = \infty$ is a zero fo $f(z)$, i.e. if $c_0 = 0$ in the Laurent expansion, the formula can be simplified
> $$Res_{z = \infty}f(z) = \lim_{z \rightarrow \infty}[-z f(z)]$$ $$\tag{v.1}$$

<div class="example" markdown="1">

**Example:**  Find the residue of the function $f(z) = \frac{z+2}{z^2 - 2z + 3}$ at $z_0 = \infty$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

We note that $z_0 = \infty$ is a removeable singularity of $f(z)$ such that $\lim_{z \rightarrow \infty}f(z) = 0$ and so by $v.i$
> $$Res_{z = \infty}f(z) = - \lim_{z \rightarrow \infty}\frac{z(z+2)}{z^2 - 2z + 3} = -1$$ $$$$
</details>

**Example:**  Find the residue of the function $f(z) = \frac{z+2}{(z+1)^2(z-3)}$ at $z_0 = \infty$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

Again, $z_0 = \infty$ is a removeable singularity of $f(z)$ and $\lim_{z \rightarrow \infty}f(z) = 0$ so by $v.i$
> $$Res_{z = \infty}f(z) = - \lim_{z \rightarrow \infty}\frac{z(z+2)}{(z+1)^2(z-3)} = 0$$ $$$$
</details>

**Example:**  Find the residue of the function $f(z) = \frac{3z^2 + z}{z^2 + z - 4}$ at $z_0 = \infty$

<details>
<summary><i style="font-size:150%;">Solution</i></summary>

Now, $z_0 = \infty$ is a removeable singularity of $f(z)$ but this time, $\lim_{z \rightarrow \infty}f(z) = 3$ so by $v.i$
> $$Res_{z = \infty}f(z) = \lim_{z \rightarrow \infty}(3 - \frac{3z^2 + z}{z^2 + z - 4}) \cdot z$$ $$= \lim_{z \rightarrow \infty}(\frac{3z^2 + 3z - 12}{z^2 + z - 4} - \frac{3z^2 + z}{z^2 + z - 4}) \cdot z = \lim_{z \rightarrow \infty} \frac{(2z - 12)z}{z^2 + z - 4} = 2$$ 
</details>

</div>


<div class="proposition" markdown="1">

**Theorem**

If a function $f(z)$ is analytic on the extended complex plane except for finitely many isolated singular points then the sum of all its residues, including its residue at infinity is zero.

Let $\lbrace a_1, \ldots, a_n \rbrace$ be the finite isolated singular points of $f(z)$ then
> $$ Res_{z = \infty}f(z) = - \sum_{k =1}^{n} Res_{z = a_k}f(z) $$ $$$$

</div>
