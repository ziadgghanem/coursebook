---
layout: post
title: 'The Complex Plane'
---

<blockquote>
        The object of mathematics is the honor of the human spirit.
        <footer>Jacobi</footer>
</blockquote>

<hr>

A mathematical result must first be appreciated according to its aesthetics and only after for any practical application. As in all things, an aesthetic result cuts to the heart of things using only as much as is necessary to make its point.  

## 1.1 Complex Numbers

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

The modulus of a complex number $z \in \CC$ has the following properties
1. $$\vert z \vert \geq 0 \; \land \; \vert z \vert \geq 0 \iff z=0$$ $$$$
2. $$\forall_{a \in \mathbb{R}} \vert az \vert = \vert a \vert \cdot \vert z \vert$$ $$$$
3. $$\vert z_1 + z_2 \vert \leq \vert z_1 \vert + \vert z_2 \vert$$ $$$$
4. $$ \vert z \vert = \vert \overline{z} \vert$$ $$$$
5. $$\vert z_1 z_2 \vert = \vert z_1 \vert \cdot \vert z_2 \vert $$ $$$$
6. $$\vert z^{-1} \vert = \frac{1}{\vert z \vert}$$ $$$$

</div>

$(\CC, \vert \cdot \vert)$ is a normed space and $\vert \cdot \vert$ induces the metric $d: \CC \times \CC \rightarrow \mathbb{R}$
> $$d(z_1,z_2) = \vert z_1 - z_2 = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}$$ $$$$

## 1.2 Polar and Exponential Form

<div class="proposition" markdown="1">

**Proposition 1.01:**  Eulers Formula

> $$e^{i \theta} = \cos{\theta} + i \sin{\theta}$$ $$$$

**Corollary 1.01:**  

> $$\cos{\theta} = \frac{e^{i \theta} + e^{- i \theta}}{2}, \; \sin{\theta} = \frac{e^{i \theta} - e^{- i \theta}}{2i} $$ $$$$


</div>

The polar form of a complex number $z$ is expressed in terms of $r:= \vert z \vert$ the modulus of $z$, and $\theta$ the argument of $z$, the angle between the positive real-axis and the vector representation of $z$
> $$z = r(\cos{\theta} + i \sin{\theta}) = r e^{i \theta}$$ $$$$

A problem arises that the argument of a complex number is multivalued, indeed it is only defined up to integer multiples of $2 \pi$

Given two complex numbers in polar form $z = r(\cos{\theta} + i \sin{\theta})$, $w =  s(\cos{\phi} + i \sin{\phi})$ we have
1. $$z \cdot w = rs(\cos{\theta + \phi} + i \sin{\theta + \phi})$$ $$$$
2. $$\frac{z}{w} = \frac{r}{s}(\cos{\theta - \phi} + i \sin{\theta - \phi}),$$ for $$w \neq 0$$

<div class="proposition" markdown="1">

**Theorem 1.01:**  De Moivre's Theorem 

$\forall_{\theta \in \mathbb{R}} \forall_{n \in \mathbb{N}}$
> $$(\cos{\theta} + i \sin{\theta})^n = \cos{n \theta} + i \sin{n \theta}$$ $$$$

**Corollary 1.01:** 

The $n$-th power of any complex number $z = r(\cos{\theta} + i \sin{\theta})$
> $$z^n = r^n(\cos{n \theta} + i \sin{n \theta})$$ $$$$

</div>