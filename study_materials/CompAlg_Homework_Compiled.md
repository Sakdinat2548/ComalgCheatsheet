## Source: Homework 01 (Lecture 2)

**Question 1:** Represent each of the following integer divisions in the form $a = b \cdot q + r$, where $0 \leqslant r < b$:
$$13 \div 4, \quad 512 \div 27, \quad 1023 \div 17.$$
That is, determine the corresponding quotient $q$ and remainder $r$ in each case.

**Question 2:** Convert the following numbers from decimal to binary and then back from binary to decimal:
$$0.5, \quad 0.0017, \quad 3.14159.$$

**Question 3:** Express the following binary numbers in the normalized form
$$(-1)^s (1.f) 2^{e}:$$
$$101.0011001, \quad -0.0000101101101, \quad -1010101.0010.$$
How should the number $0$ be represented in this notation?

**Question 4:** The floating-point representation discussed in the lecture was slightly simplified. A more realistic representation is
$$(-1)^s (1.f) 2^{E - \text{bias}},$$
where the exponent is stored using a bias variable.

Assume that $\text{bias} = 24$, $E \geqslant 0$, and that a floating-point number occupies 16 bits, allocated as follows:
- 1 bit for the sign $s$,
- 5 bits for the positive part of the exponent $E$,
- 10 bits for the fraction $f$.

Determine:
a) the largest representable number;
b) the smallest representable number;
c) the smallest positive representable number;
d) the largest negative representable number.

**Question 5:** Many programming languages use bit-shift operations to perform efficient multiplication and division by powers of two. For example, Python and C++ provide the operators `<<` and `>>`, which shift the bits of an integer to the left or right.

Verify on examples that
$$x \ll 1 == x * 2$$
and
$$x \gg 1 == x \,//\, 2$$
(Here `//` denotes the integer division operator in Python.)

More generally,
$$x \ll k == x * 2^k$$
and
$$x \gg k == x \,//\, 2^k$$

You may use the binary numbers such as $100110_2$ or $1011011_2$ as examples.

*Remark.* The shift operators `<<` and `>>` are typically defined only for integer types. They are generally not available for floating-point numbers, since IEEE 754 floating-point values are stored using separate sign, exponent, and fraction fields rather than as a simple binary integer. Multiplication or division by powers of two is instead performed by adjusting the exponent.

**Question 6:** Suppose decimal shift operators, denoted by $\ll_{10}$ and $\gg_{10}$, were defined analogously for decimal numbers.

a) Determine the results of the following operations:
$$123456 \ll_{10} 1, \quad 123456 \gg_{10} 1, \quad 123456 \gg_{10} 4.$$

b) Will the operator $\gg_{10}$ behave in the same way for odd integers?

c) Propose a general definition of the decimal shift operators $x \ll_{10} k$ and $x \gg_{10} k$.

---

## Source: Homework 02 (Lecture 3)

*Note: Homework assignments are optional but strongly recommended. Completing them will significantly improve your understanding of the material.*

**Question 1:** Determine the minimum number of bits required to represent each of the following integers using the representation (two's complement representation) discussed in the lecture:
$$-300, \quad -2000000000, \quad -1030.$$
*Hint: For large numbers, it is convenient to use the base-2 logarithm.*

**Question 2:** In the lecture we learned how to convert the binary representation of a negative integer into its decimal representation. Now try performing the reverse conversion.

Find the binary representations of the following integers:
$$-5, \quad -17, \quad -62.$$
Use 7-bit two's complement representation.

**Question 3:** Compute the following greatest common divisors using the standard Euclidean algorithm:
$$\gcd(3,1), \quad \gcd(48,18), \quad \gcd(144,60).$$

**Question 4:** Consider the sequence of equations arising in the Euclidean algorithm for a pair of integers $(a,b)$:
$$a = bq_0 + r_0,$$
$$b = r_0 q_1 + r_1,$$
$$r_0 = r_1 q_2 + r_2,$$
$$r_1 = r_2 q_3 + r_3,$$
$$\ldots$$

Substitute the expressions for $b$, $r_0$, and $r_1$ into the first equation. Then assume that
$$r_0 r_1 r_2 \neq 0, \quad r_3 = 0,$$
and show that
$$r_2 \mid a,$$
that is, $r_2$ is a divisor of $a$.

Think, does this alone prove that $\gcd(a,b) = r_2$?

---

## Source: Homework 03 (Lecture 4)

**Question 1:** What output would a typical computer algebra system (CAS) produce for the following expressions?
a) $\ln(2) + \ln(3)$
b) $\ln(2) + \ln(3.0)$

It is advisable for students to check this in Maxima or a similar CAS.

**Question 2:** Recall that every rational number can be represented either as a terminating decimal or as an infinite repeating decimal. Students may have encountered the following algorithm in school for converting a repeating decimal into a fraction.

*Algorithm.* Let
$$x = 0.a_1 a_2 \cdots a_n,$$
where $a_1 a_2 \cdots a_n$ is the repeating block.

a) Form the integer $A = a_1 a_2 \cdots a_n$.
b) Write the denominator as $10^n - 1$, that is, the number consisting of $n$ nines.
c) Compute $x = \dfrac{A}{10^n - 1}$.
d) Reduce the fraction to lowest terms (using GCD).

Use this algorithm to convert the following repeating decimals into fractions:
$$0.(3), \quad 0.(81), \quad 0.(538461).$$

*Note: Since this exercise involves several tedious GCD computations, you may use a calculator or a computer algebra system such as Maxima.*

**Question 3:** Consider the integers
$$x = 1034856, \quad y = 98357.$$
Represent them as arrays using base $B$, and compute their sum for each of the following bases:
a) $B = 1000$,
b) $B = 2^8$,
c) $B = 10^8$.

Convert the array representations of the computed sum back to decimal notation and verify that it agrees with the result of ordinary decimal addition.

**Question 4:** Think about how subtraction can be performed for integers represented as arrays (for example, using the base $B = 1000$). Using array representation, compute the difference of the two integers from the previous exercise.

---

## Source: Homework 04 (Lecture 5)

**Question 1:** Determine whether each of the following operators is left-associative, right-associative, or both.

a) The assignment operator in programming languages:
$$a = b = c.$$

b) The remainder (modulo) operator:
$$a \% b \% c$$
or
$$a \bmod b \bmod c.$$

c) The bitwise left shift operator:
$$a \ll b \ll c.$$

d) Matrix multiplication:
$$A \cdot B \cdot C.$$

**Question 2:** Using the standard precedence and associativity rules for arithmetic operators, construct the corresponding binary expression trees for the following expressions.

a)
$$-1 - a \cdot b - c \cdot \sqrt{d - \dfrac{e}{f}^{g}}$$

b)
$$\dfrac{x^2 - 2 \cdot x - 1}{x + 3 \cdot \ln x}$$

c)
$$f(g(x-1)) + h(k(x \div y \div z))$$

**Question 3:** Suppose the binary operators have the following precedence ($\odot$ has the highest priority):
$$\circ < \bullet < \odot,$$
where the operators $\circ$ and $\bullet$ are left-associative, while $\odot$ is right-associative.

Construct the expression tree corresponding to
$$a \circ b \bullet c \bullet d \circ e \odot f \odot g.$$

---

## Source: Homework 05 (Lecture 6)

**Question 1:** *(Expression tree from prefix notation)*
The following expression is written in Lisp-style prefix notation using only binary operators:
$$(\ast\ (+\ a\ b)\ (-\ (\div\ c\ d)\ (\wedge\ e\ f))).$$

a) Construct the corresponding binary expression tree.
b) Traverse the tree using an in-order DFS traversal and list the visited nodes.
c) Write the resulting mathematical expression in standard infix notation.

**Question 2:** *(Comparing expression trees)*
The two expression trees below are claimed to represent equivalent expressions.

[Image: Tree A — a binary expression tree with root $*$, left child $+(a,b)$, right child $+(c,d)$]

[Image: Tree B — a binary expression tree with root $+$, combining nodes $*(a,c)$, $*(a,d)$, and a subtree $+(*(b,c), *(b,d))$]

a) Traverse each tree using an in-order DFS traversal.
b) Write the corresponding mathematical expression.
c) Determine whether the two expressions are equivalent. If they are, justify your answer using standard algebraic identities.

**Question 3:** *(Substitution)*
Consider the expression
$$(a+b)^2 + c \cdot (a+b)$$
and the substitution
$$a + b \longrightarrow t.$$

a) Draw the expression tree before substitution.
b) Draw the expression tree after substitution.
c) Traverse the trees using in-order DFS and write both mathematical expressions.

**Question 4:** *(Expansion)*
Consider the expression
$$(a+b) \cdot (c+d+e).$$

a) Draw its expression tree.
b) Apply the Expand transformation in two steps:
   i. $(a+b)\cdot c + (a+b) \cdot d + (a+b) \cdot e$
   ii. $a\cdot c + b \cdot c + a \cdot d + b \cdot d + a \cdot e + b \cdot e$.
c) Draw the resulting expression trees corresponding to each step.

**Question 5:** *(Investigating expression trees in Maxima)*
Using Maxima and the command
```
:lisp $expr
```
investigate the internal representation of the expression
```
expr : (x^2-2*x+1)/(x+ln(x));
```

a) Compute the expression in Maxima.
b) Display its internal Lisp representation.
c) Identify the root operator.
d) Determine the left and right operands of the root.
e) Continue recursively until the complete expression tree has been reconstructed.

---

## Source: Homework 06 (Lecture 8)

*Students are strongly encouraged to master the basics of symbolic computation and programming in Maxima as early as possible.*

*Since we do not have sufficient time to study Maxima in detail during the course, students are advised to read Section 2.2 of the lecture notes and/or consult the official Maxima documentation on programming. Students with prior programming experience should be able to master the fundamentals of the language fairly quickly.*

*Students are also encouraged to complete the introductory programming exercises, Programming Tasks 2.1–2.21 (see Section 2.2.2 of the lecture notes), independently.*

(No individually numbered problems in this homework — it consists of directed reading and Programming Tasks 2.1–2.21 referenced from the lecture notes.)

---

## Source: Homework 07 (Lecture 9)

**Section i. Practice with Maxima**

Study how the functions `mygcd`, `int_to_big`, `big_to_int`, and `big_add` work (see the end of Section 2.2.2, Basic Programming Exercises in Maxima of the lecture notes). Try to reproduce these implementations independently in Maxima.

You may also improve some of these implementations or rewrite them recursively. Complete Programming Tasks 2.23, 2.24, and 2.25. If you have enough time, also try to solve the more advanced Programming Tasks 2.26–2.29.

*Note: If you have not yet completed the previous homework assignment containing the introductory programming exercises, it is recommended that you start with that assignment and then return to the present one.*

**Section ii. Modular Arithmetic**

**Question 1:** Find $x$ in each of the following congruences:
a) $143 \equiv x \pmod{13}$,
b) $12345 \equiv x \pmod{11}$,
c) $54321 \equiv x \pmod{7}$.

**Question 2:** Determine possible values of $n$ such that:
a) $24 \equiv 0 \pmod{n}$,
b) $15 \equiv 1 \pmod{n}$,
c) $124 \equiv 4 \pmod{n}$.

---

## Source: Homework 08 (Lecture 10)

*Working through the following problems will help students gain confidence in performing modular arithmetic and in translating between the two most common notational conventions: residue classes (i.e., equivalence classes) and congruences.*

**Question 1:** For each of the following residue classes (i.e., equivalence classes), describe the set $[a]_n$ and list at least five of its elements (including both positive and negative integers).
a) $[2]_5$
b) $[4]_7$
c) $[-3]_8$

**Question 2:** Rewrite each of the following statements in the equivalent notation.

a) Express the following equations involving residue classes as congruences:
$$[8]_{11} + [9]_{11} = [6]_{11},$$
$$[4]_7 \cdot [5]_7 = [6]_7.$$

b) Express the following congruences using residue classes:
$$17 + 9 \equiv 2 \pmod{8},$$
$$6 \cdot 8 \equiv 3 \pmod{5}.$$

*Hint: For example, $[2]_5 + [4]_5 = [1]_5$, is equivalent to $2 + 4 \equiv 1 \pmod{5}$.*

**Question 3:** Using the fact that addition and multiplication of residue classes are well defined, i.e.,
$$[a]_n + [b]_n = [a+b]_n, \quad \text{and} \quad [a]_n \cdot [b]_n = [a \cdot b]_n,$$
compute the following:
a) $[123]_{17} + [245]_{17}$
b) $[391]_{23} \cdot [457]_{23}$
c) $([156]_{11} + [247]_{11}) \cdot [83]_{11}$
d) $[312]_{15} \cdot ([184]_{15} + [257]_{15})$

**Question 4:** Solve problems similar to those in the previous exercise, but this time use congruence notation ("$\equiv$" and "mod") instead of residue classes.

That is, compute:
a) $4 + 8 \pmod{9}$
b) $7 \cdot 11 \pmod{13}$
c) $(2+4) \cdot 3 \pmod{5}$
d) $5 \cdot (6+7) \pmod{8}$

*Hint: For example, $4 + 6 \equiv 10 \equiv 1 \pmod{9}$.*

---

## Source: Homework 09 (Lecture 12)

*The following exercises will help students become familiar with the concept of a group. Recall that a group must satisfy four axioms: closure, the existence of an identity element, associativity, and the existence of an inverse for every element.*

**Question 1:** Determine whether the set of rational numbers $\mathbb{Q}$ forms a group
- under addition, $(\mathbb{Q}, +)$;
- under multiplication, $(\mathbb{Q}, *)$.

**Question 2:** Determine whether
$$\mathbb{Z}_4 = \{[0]_4, [1]_4, [2]_4, [3]_4\}$$
forms a group under addition, i.e., whether $(\mathbb{Z}_4, +)$ is a group.

**Question 3:** Determine whether
$$\mathbb{Z}_4^* = \{[1]_4, [2]_4, [3]_4\}$$
forms a group under multiplication, i.e., whether $(\mathbb{Z}_4^*, *)$ is a group.

**Question 4:** [Image: Figure 1 — an equilateral triangle $ABC$ with altitudes $\ell_1$ (through $B$), $\ell_2$ (through $A$), $\ell_3$ (through $C$), and arrows illustrating rotations $r$ (120°), $r^2$ (240°), and $e$ (360°)]

Figure 1 shows an equilateral triangle $ABC$ together with the following six transformations:
- $e$ — the identity transformation (a rotation by $0°$ or $360°$);
- $r$ — a rotation by $120°$ clockwise;
- $r^2$ — a rotation by $240°$ clockwise (or by $120°$ counterclockwise);
- $\ell_1$ — reflection across the altitude passing through vertex $B$;
- $\ell_2$ — reflection across the altitude passing through vertex $A$;
- $\ell_3$ — reflection across the altitude passing through vertex $C$.

We define multiplication of these transformations by successive application: $b \cdot a$ means that $a$ is applied first and then $b$. Thus, transformations are composed from right to left. For example, $r^2 \cdot \ell_1$ means that we first reflect the triangle across the altitude passing through vertex $B$, and then rotate it by $240°$ clockwise.

Complete the following multiplication table.

| $\cdot$ | $e$ | $r$ | $r^2$ | $\ell_1$ | $\ell_2$ | $\ell_3$ |
|---|---|---|---|---|---|---|
| $e$ |  |  |  |  |  |  |
| $r$ |  |  |  |  |  |  |
| $r^2$ |  |  |  |  |  |  |
| $\ell_1$ |  |  |  |  |  |  |
| $\ell_2$ |  |  |  |  |  |  |
| $\ell_3$ |  |  |  |  |  |  |

Then verify that these six transformations form a group (this group is called $D_3$, the dihedral group of order 6). In particular, use the table to find the inverse of each transformation. The closure, associativity, and identity properties are immediate from the construction (check it!).

---

## Source: Homework 10 (Lecture 13)

*(Finite Groups and FLT)*

*The following exercises concern finite groups and applications of Fermat's Little Theorem (FLT).*

**Question 1:** Consider the additive group of residue classes $\mathbb{Z}_8$. Determine the order of the group, i.e., $|\mathbb{Z}_8|$. What are the orders of the elements $[1]_8$, $[2]_8$, and $[7]_8$? Give a generator of the group.

**Question 2:** For which of the following values of $n$ can a multiplicative group be defined on the set $\mathbb{Z}_n$?
$$3, 5, 10, 13, 15, 17.$$
For each value of $n$ for which such a multiplicative group exists:
a) Determine the order of the group.
b) Using Lagrange's theorem, list all possible orders of its elements.

**Question 3:** Consider the multiplicative group $\mathbb{Z}_{24}^*$. Using Lagrange's theorem, determine for which positive integers $x$ the equation
$$[a]^x = [1],$$
cannot hold for any $a = 2, \ldots, 23$.

**Question 4:** Find at least one generator of the multiplicative group $\mathbb{Z}_{13}^*$.

**Question 5:** In which of the following cases can FLT not be applied directly, and why?
$$19^6 \pmod{7}, \quad 21^6 \pmod{7}, \quad 11^8 \pmod{9}.$$

**Question 6:** Compute the following powers modulo the given numbers using FLT:
$$19^6 \pmod{7},$$
$$19^{68} \pmod{7},$$
$$271^{24} \pmod{11},$$
$$290^{293} \pmod{23}.$$

*Hint: If FLT is applicable to a problem involving $a^b \pmod{p}$, or equivalently $[a^b]_p$, express the exponent as $b = (p-1)q + c$, $0 \leqslant c < p-1$. Then*
$$[a^{(p-1)q+c}]_p = [a^{(p-1)q} \cdot a^c]_p = [a^{(p-1)q}]_p \cdot [a^c]_p = ([a^{p-1}]_p)^q \cdot [a^c]_p = [1]_p^q \cdot [a^c]_p = [a^c]_p = ([a]_p)^c.$$
*If $a$ and $c$ are sufficiently small, the remaining expression can then be evaluated using standard modular arithmetic.*

**Question 7:** Simplify the following expressions without using FLT (use standard modular arithmetic):
$$[16^4]_7, \quad [10^{100}]_9, \quad [23^2]_9, \quad [42^1]_{12},$$

*Hint: You may use identities such as*
$$[a^{2n}]_m = ([a^2]_m)^n,$$
*and*
$$[a^{2n+1}]_m = [a^{2n} \cdot a]_m = ([a^2]_m)^n \cdot [a]_m.$$

---

## Source: Homework 11 (Lecture 15)

*(Complex Numbers)*

*In many situations, complex numbers can conveniently be identified with two-dimensional vectors. In this course, we adopt a geometric perspective. This homework is intended to develop geometric intuition about complex numbers and their basic operations.*

**Question 1:** Plot the two complex numbers on the complex plane and approximately construct their sum geometrically. Then calculate the sum and verify that it is consistent with your construction.

a) $-2 + 4i$ and $-3 - 7i$

b) $-2 - i$ and $2 + i$

c) $1 - 2i$ and $1 + 2i$

**Question 2:** Find $|z|^2$ using the identity $|z|^2 = z\bar{z}$, if

a) $z = -2 - 3i$

b) $z = 4i$

c) $\bar{z} = 4i$

**Question 3:** Find $z_1/z_2$ and plot the vectors corresponding to $z_1$, $z_2$, and their quotient on the complex plane, if

a) $z_1 = 2 + 6i$, $z_2 = 2$

b) $z_1 = 1 + 6i$, $z_2 = 1 - 6i$

c) $z_1 = 3 + 4i$, $z_2 = 1 - 6i$

**Question 4:** Associate the complex numbers
$$z_1 = a + bi, \qquad z_2 = c + di$$
with the two-dimensional vectors
$$u = (a, b), \qquad v = (c, d).$$

a) What is the difference between the product of the complex numbers $z_1 z_2$ and the dot product of the vectors $u \cdot v$?

b) Find $|z_1 z_2|^2$ and $(u \cdot v)^2$ in general, and for some particular choices of $a, b, c, d$. In which cases do these two quantities coincide?

**Question 5:** Determine whether the set of complex numbers of the form
$$2a + 7bi, \qquad a, b \in \mathbb{Z},$$
forms an additive group.

**Question 6:** Determine whether the set of complex numbers of the form
$$3a + 3bi, \qquad a, b \in \mathbb{Z}, \ ab \neq 0,$$
forms a multiplicative group.

---

## Source: Homework 12 (Lecture 16)

*(Complex Numbers II)*

*Multiplication of complex numbers has an interesting group structure. These exercises are intended to explore the group properties of complex numbers and to develop geometric intuition.*

**Question 1:** Similar to as we did in the lecture, show that the set
$$\{1, -1\}$$
forms a multiplicative group. Plot its elements on the complex plane. Which element is a generator of the group? Verify that this group is a subgroup of the larger multiplicative group
$$(\{1, -1, i, -i\}, *).$$

**Question 2:** Repeat the same analysis for the set
$$\{i, -i\}.$$
What goes wrong in this case?

**Question 3:** Verify the multiplicative property,
$$|z_1| \cdot |z_2| = |z_1 \cdot z_2|,$$
for
$$z_1 = \frac{1+i}{\sqrt{2}}, \qquad z_2 = \frac{1-i}{\sqrt{2}}.$$
Find the length of each number separately and then the length of their product.

**Question 4:** Consider the group
$$C_8^{*} = \left(\left\{\underbrace{1}_{z_1}, \underbrace{-1}_{z_2}, \underbrace{-i}_{z_3}, \underbrace{i}_{z_4}, \underbrace{\frac{1+i}{\sqrt2}}_{z_5}, \underbrace{\frac{-1+i}{\sqrt2}}_{z_6}, \underbrace{\frac{1-i}{\sqrt2}}_{z_7}, \underbrace{\frac{-1-i}{\sqrt2}}_{z_8}\right\}, *\right).$$
Determine which elements of the set are obtained from the products $z_2 z_5$, $z_5 z_7$, $z_6 z_8$.

**Question 5:** Using the formula for division of complex numbers, find the multiplicative inverse of
$$z = \frac{-1-i}{\sqrt2}.$$

**Question 6:** Using Euler's formula, express the following complex numbers in standard (rectangular) form. Then sketch the corresponding numbers (i.e., the corresponding vectors) on the complex plane:
$$8e^{\frac{\pi}{3}i}, \qquad 11e^{\frac{3\pi}{2}i}.$$

**Question 7:** Using de Moivre's formula, find the following roots of complex numbers and sketch them on the complex plane:
$$\left(e^{i\frac{\pi}{2}}\right)^{1/3}, \qquad \left(e^{i\frac{\pi}{4}}\right)^{1/2}.$$

---

## Source: Homework 13 (Lecture 17)

*(Roots of Unity)*

*The roots of unity form an important subgroup of the multiplicative group of complex numbers and play a central role in many applications, including the Fast Fourier Transform (FFT). The purpose of this homework is to develop an understanding of the algebraic structure of this group, its generators, and its connection with modular arithmetic.*

**Question 1:** Recall that the $n$th roots of unity are the complex roots of the equation
$$z^n - 1 = 0.$$
How many distinct complex $n$th roots of unity are there?

**Question 2:** The number
$$\omega_n = e^{\frac{2\pi i}{n}}$$
is called a primitive $n$th root of unity. Verify that $\omega_n$ is a generator of the multiplicative group of all $n$th roots of unity. In other words, show that all $n$th roots of unity are obtained as successive powers
$$\omega_n^0, \omega_n^1, \ldots, \omega_n^{n-1},$$
after which the sequence repeats cyclically.

**Question 3:** Two groups $G_1$ and $G_2$ are called isomorphic ($G_1 \cong G_2$) if they have the same structure.[^1] For finite groups, isomorphic groups necessarily have the same number of elements.

Verify that the multiplicative group $C_4^{*}$ of all fourth roots of unity is isomorphic to the additive group $\mathbb{Z}_4^{+}$ of residue classes modulo 4, by comparing the following group tables:

| $*$ | $1$ | $i$ | $-1$ | $-i$ |
|---|---|---|---|---|
| $1$ | $1$ | $i$ | $-1$ | $-i$ |
| $i$ | $i$ | $-1$ | $-i$ | $1$ |
| $-1$ | $-1$ | $-i$ | $1$ | $i$ |
| $-i$ | $-i$ | $1$ | $i$ | $-1$ |

| $+_4$ | $[0]$ | $[1]$ | $[2]$ | $[3]$ |
|---|---|---|---|---|
| $[0]$ | $[0]$ | $[1]$ | $[2]$ | $[3]$ |
| $[1]$ | $[1]$ | $[2]$ | $[3]$ | $[0]$ |
| $[2]$ | $[2]$ | $[3]$ | $[0]$ | $[1]$ |
| $[3]$ | $[3]$ | $[0]$ | $[1]$ | $[2]$ |

[^1]: More precisely, two groups are isomorphic if there exists a bijection between their elements that preserves the group operation.

**Question 4:** Using the following addition table modulo 5,

| $+_5$ | $[0]$ | $[1]$ | $[2]$ | $[3]$ | $[4]$ |
|---|---|---|---|---|---|
| $[0]$ | $[0]$ | $[1]$ | $[2]$ | $[3]$ | $[4]$ |
| $[1]$ | $[1]$ | $[2]$ | $[3]$ | $[4]$ | $[0]$ |
| $[2]$ | $[2]$ | $[3]$ | $[4]$ | $[0]$ | $[1]$ |
| $[3]$ | $[3]$ | $[4]$ | $[0]$ | $[1]$ | $[2]$ |
| $[4]$ | $[4]$ | $[0]$ | $[1]$ | $[2]$ | $[3]$ |

fill in the multiplication table for the group $C_5^{*}$ of all fifth roots of unity given below. Use the isomorphism between the two groups by corresponding their generators and their powers:
$$\omega_5 = e^{\frac{2\pi i}{5}} \longleftrightarrow [1]_5, \qquad \omega_5^2 = \omega_5 * \omega_5 = e^{\frac{4\pi i}{5}} \longleftrightarrow [1]_5 + [1]_5 = [2]_5,$$
and similarly for the remaining powers of the generators.

| $*$ | $1$ | $\omega_5$ | $\omega_5^2$ | $\omega_5^3$ | $\omega_5^4$ |
|---|---|---|---|---|---|
| $1$ |  |  |  |  |  |
| $\omega_5$ |  |  |  |  |  |
| $\omega_5^2$ |  |  |  |  |  |
| $\omega_5^3$ |  |  |  |  |  |
| $\omega_5^4$ |  |  |  |  |  |

**Question 5:** Verify that every root of the equation
$$z^{2^m} - 1 = 0, \qquad m \in \mathbb{N},$$
is also a root of the equation
$$(z^{2^m})^2 - 1 = 0.$$
Conclude that
$$C_{2^m}^{*} \subset C_{2^{m+1}}^{*},$$
that is, the $2^m$th roots of unity form a subgroup of the $2^{m+1}$th roots of unity.

---

## Source: Homework 14 (Lecture 20)

*(FFT/IFFT)*

*This homework is intended as a useful supplement to the lectures on FFT and inverse FFT (IFFT).*

**Question 1:** For the polynomial
$$f(x) = 2 + 3x + 5x^3,$$
write down the butterfly formulas and perform the FFT. As a result, write the polynomial in value representation.
*Hint: First determine which root of unity you will need.*

**Question 2:** Suppose that two values of a polynomial are given:
$$\{(1, 1), (-1, 1+i)\}.$$
Explain why $x_0 = 1$ and $x_1 = -1$. Using the IFFT formulas, recover the coefficient representation of the polynomial. The coefficients may turn out to be complex; this is perfectly normal.

**Question 3:** Consider the number
$$5678 = 8 + 7\cdot 10 + 6 \cdot 10^2 + 5 \cdot 10^3.$$
Try to represent it as a polynomial $q(x)$ of degree three in the variable $x$. Compute $q(10)$ and $q(2)$.

*The following problems are useful for developing a better understanding of the structure of the FFT algorithm.*

**Question 4:** Let us briefly recall some basic facts about algorithms. Suppose that a problem is repeatedly divided into subproblems, so that the resulting structure can be represented as a binary tree with $n$ leaves.

a) What is the depth of this tree?

b) What is the complexity of the corresponding algorithm if the main computations are performed at the bottom (last) level? Assume that the computations at the intermediate levels take constant time. Give the complexity using Big-O notation.

c) What is the complexity of the corresponding algorithm if additional computations proportional to $n$ are performed at each level of the tree?

**Question 5:** Consider the cubic polynomial
$$p(x) = a_0 + a_1 x + a_2 x^2 + a_3 x^3.$$
Suppose that its values at the points $\omega_4^0, \omega_4^1, \omega_4^2, \omega_4^3$ are already known and are denoted by $y_0, y_1, y_2, y_3$, respectively. The coefficients can be recovered using the IFFT formulas with 4th roots of unity:
$$a_0 = \frac{1}{4}(y_0 + y_1 + y_2 + y_3),$$
$$a_1 = \frac{1}{4}(y_0 + y_1\omega_4^{-1} + y_2\omega_4^{-2} + y_3\omega_4^{-3}),$$
$$\ldots$$
$$a_3 = \frac{1}{4}(y_0 + y_1\omega_4^{-3} + y_2\omega_4^{-6} + y_3\omega_4^{-9}).$$

a) Recover the coefficient $a_2$ in a similar way.

b) Simplify the resulting expressions for the coefficients using the standard properties of roots of unity.

c) Substitute the resulting formulas for the coefficients into $p(\omega_4)$ and compute the result, taking into account that $\omega_4 = i$. If everything has been done correctly, you should obtain the known value of the polynomial at $\omega_4$.

**Question 6:** We use the FFT to transform the polynomial
$$p(x) = a_0 + a_1 x + \cdots + a_{n-1}x^{n-1},$$
where $n = 32$. Thus, we need the 32nd roots of unity and will work with $\omega_{32}$.

a) Write the polynomial as a sum of its even and odd parts, and write down the corresponding polynomials.

b) Write the butterfly formulas for the first few powers of the roots of unity, for example, for $\omega^0, \omega^{16}$ and $\omega^1, \omega^{17}$.

c) The even and odd parts in the formulas above have degree 15. Now split each of them again into its even and odd parts. How many polynomials do you obtain in total? Try to understand how many times each of them is used in the original FFT algorithm for $\omega_{32}$.

**Question 7:** Read the derivation of the IFFT formulas in the lecture notes, Section 4.6, and try to reproduce and understand the main steps of the derivation.

---

## Source: Homework 15 (Lecture 22)

*(Introduction to Polynomial Systems)*

*This homework is intended to reinforce some basic concepts related to polynomials.*

**Question 1:** Show that the equation
$$x^4 + 16 = 0$$
has no real roots. According to the Fundamental Theorem of Algebra, how many roots does it have over $\mathbb{C}$? Try to find at least two roots of this equation. They can be guessed or found using the standard theory for extracting complex roots.

**Question 2:** Suppose that
$$h(x) = 4x^2 + 12x - 7$$
is the GCD of two polynomials. Give the corresponding monic GCD.

**Question 3:** Verify that
$$\gcd(x^4 - 8x^3 + 17x^2 + 2x - 24,\ x^3 - 6x^2 + 11x - 6) = x^2 - 5x + 6.$$

**Question 4:** Determine whether the following system is consistent. If it is, find all of its roots:
$$\begin{cases} x^2 - 11x + 30 = 0, \\ x^3 - 10x^2 + 27x - 18 = 0. \end{cases}$$
