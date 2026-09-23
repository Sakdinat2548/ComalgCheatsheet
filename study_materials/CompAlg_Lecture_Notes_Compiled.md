## Lecture 1: Introduction to Computer Algebra

**Source:** CompAlg_-_all.pdf, Lecture 1

**Content Type: Definition**
**Content Text:**
Computer Algebra emphasizes symbolic computation rather than numerical methods: before attempting to obtain a numerical answer, one should first try to simplify or transform the problem by manipulating the quantities involved as symbols, according to a prescribed set of rules.

**Content Type: Definition**
**Content Text:**
The term "algebra" in Computer Algebra is closely related to abstract algebra and, to a lesser extent, algebraic geometry. Polynomials and systems of polynomial equations occupy a central position in computer algebra. The solution sets of such systems define algebraic varieties, which in simple cases can be visualized as collections of separate points, curves, or surfaces.

**Content Type: Theorem/Property**
**Content Text:**
Unlike numerical analysis, computer algebra seeks exact solutions whenever possible, attempting to preserve exact symbolic information rather than replacing it with numerical approximations at an early stage.

**Content Type: Definition**
**Content Text:**
Methods from functional programming have traditionally played an important role in symbolic computation, as have data structures such as lists and trees. Lisp was one of the earliest (functional) programming languages designed for symbolic manipulation of lists; although no longer widely used itself, it has profoundly influenced later systems such as Scheme, Reduce, Maxima, and, to some extent, Maple, all of which reflect ideas from the Lisp tradition.

---

## Lecture 2: Computer Representation of Integers and Floating-Point Numbers

**Source:** CompAlg_-_all.pdf, Lecture 2

**Content Type: Definition**
**Content Text:**
The normalized IEEE 754 representation of a floating-point number stores the sign, exponent, and fraction (mantissa) explicitly.

**Content Type: Theorem/Property**
**Content Text:**
Standard floating-point numbers are generally unsuitable for exact computations: since many real numbers cannot be represented exactly, rounding errors are unavoidable and may accumulate during computations.

**Content Type: Core Formula**
**Content Text:**
Multiplication and division by 2 in the binary system correspond to shifting the bits of an integer to the left or right (bit-shift operators, often << and >>). For floating-point numbers, the same effect is achieved by adjusting the exponent (shifting the binary point).

**Content Type: Definition**
**Content Text:**
The two floating-point formats used most frequently in practice are single precision (float, 32 bits) and double precision (double, 64 bits).

---

## Lecture 3: Signed Integers, Exact Arithmetic, GCD

**Source:** CompAlg_-_all.pdf, Lecture 3

**Content Type: Core Formula**
**Content Text:**
$$(-1)^s (1.f) \cdot 2^e$$
(Value formula for the normalized IEEE 754 representation, triple $(s, f, e)$.) There is no triple $(s,f,e)$ that yields the value 0 via this formula; IEEE 754 instead interprets the special bit patterns with the smallest exponent as positive zero ($+0$) and negative zero ($-0$).

**Content Type: Definition**
**Content Text:**
Negative integers are stored using the two's complement representation, allowing signed integers to occupy the range $-2^{n-1} \ldots 2^{n-1}-1$. The most significant bit indicates the sign (0 for nonnegative, 1 for negative).

**Content Type: Worked Example/Proof**
**Content Text:**
Two-step algorithm to recover the decimal value of a negative integer in two's complement form: 1) invert (flip) all bits; 2) add the binary number 1. The resulting binary number is then converted to decimal and assigned a negative sign.

**Content Type: Definition**
**Content Text:**
A fraction $\frac{p}{q}$ is stored as a pair $(p,q)$. It is convenient to store fractions in reduced form, i.e., $(p,q)$ with $\gcd(p,q)=1$. Any fraction $\frac{a}{b}$ can be reduced by computing $g = \gcd(a,b)$ and replacing it with $\left(\frac{a}{g}, \frac{b}{g}\right)$.

**Content Type: Theorem/Property**
**Content Text:**
The GCD of two integers is precisely the last nonzero remainder in the sequence of divisions
$$a = bq_0 + r_0,$$
$$b = r_0 q_1 + r_1,$$
$$r_0 = r_1 q_2 + r_2,$$
$$r_1 = r_2 q_3 + r_3, \ldots$$

**Content Type: Core Formula**
**Content Text:**
Integer division $a = bq + r$ gives rise to the remainder operator $a \bmod b = r$, which appears in the standard definition of the GCD.

---

## Lecture 4: Irrational Numbers and Arbitrary-Precision Arithmetic

**Source:** CompAlg_-_all.pdf, Lecture 4

**Content Type: Definition**
**Content Text:**
Computer algebra systems (CAS) typically treat irrational numbers as symbolic objects rather than numerical values, simplifying expressions containing them using symbolic rewrite rules whenever possible. Floating-point numbers are "contagious": once an expression contains a floating-point value, a CAS will usually evaluate the entire expression numerically rather than symbolically.

**Content Type: Core Formula**
**Content Text:**
A standard 64-bit integer (int) can store positive numbers up to approximately $2^{63} \approx 10^{19}$.

**Content Type: Definition**
**Content Text:**
Arbitrary-precision integers (big integers): a number is represented as a list (or array) of digits in some fixed base $B$. Each array element stores one digit in base $B$ and must lie in the range $0 \ldots B-1$. A decimal integer of $d$ digits requires $\lceil d/3 \rceil$ array elements when $B = 10^3$.

**Content Type: Theorem/Property**
**Content Text:**
The schoolbook multiplication algorithm for arbitrary-precision integers has time complexity $O(n^2)$, where $n$ is the number of digits. Faster algorithms exist, including methods based on the Fast Fourier Transform (FFT), which reduce integer multiplication to polynomial multiplication.

**Content Type: Theorem/Property**
**Content Text:**
By the Fundamental Theorem of Arithmetic, every positive integer has a unique decomposition into prime factors. If the prime factorizations of two integers are known, their product can be computed by adding the corresponding exponents. No polynomial-time algorithm for integer factorization is currently known.

---

## Lecture 5: Constructing Expression Trees

**Source:** CompAlg_-_all.pdf, Lecture 5

**Content Type: Definition**
**Content Text:**
In computer algebra systems, symbolic expressions are represented as expression trees. The internal nodes represent operators, while the leaves represent operands (variables, constants, or other atomic symbols). A unary operator has one operand; a binary operator has two operands.

**Content Type: Definition**
**Content Text:**
Binary operators are usually written in infix notation, $a \circ b$. Unary operators are most commonly written in prefix notation, e.g., $-a$, or "not $x$".

**Content Type: Worked Example/Proof**
**Content Text:**
When constructing an expression tree, the first step is to identify the operator with the lowest precedence; this operator becomes the root of the (sub)tree, and the procedure is applied recursively to the remaining subexpressions. For $a - b - c$, since subtraction is left-associative, the expression is interpreted as $(a-b)-c$, rather than $a-(b-c)$. Parentheses are introduced only to clarify order of evaluation and are not represented explicitly in the expression tree.

---

## Lecture 6: Traversal and Transformations of Expression Trees

**Source:** CompAlg_-_all.pdf, Lecture 6

**Content Type: Definition**
**Content Text:**
Three standard notations for operators: prefix, infix, and postfix. Infix is standard in mathematics; prefix and postfix are more common in programming languages. Postfix is convenient for stack-based evaluation; prefix is suitable for operators with more than two operands.

**Content Type: Definition**
**Content Text:**
Three standard depth-first search (DFS) traversal orders for trees: pre-order, in-order, post-order. Printing the nodes of an expression tree during these traversals produces the corresponding expression in prefix, infix, or postfix notation, respectively.

**Content Type: Worked Example/Proof**
**Content Text:**
Expressions in prefix or postfix notation can be converted into equivalent binary-expression trees and written in infix notation:
$$(+\ 1\ 2\ 3) \longrightarrow (+\ (+\ 1\ 2)\ 3) \longrightarrow 1+2+3,$$
$$(1\ 2\ 3\ +) \longrightarrow ((1\ 2\ +)\ 3\ +) \longrightarrow 1+2+3.$$

**Content Type: Definition**
**Content Text:**
The simplest type of expression-tree transformation is substitution, $S \to S'$, where a given symbol or expression $S$ is replaced by another symbol or expression $S'$.

**Content Type: Core Formula**
**Content Text:**
Expansion applies distributive laws such as
$$a*(b+c) = a*b + a*c, \qquad (b+c)*a = b*a + c*a.$$

**Content Type: Worked Example/Proof**
**Content Text:**
During substitutions, expressions are often rewritten in prefix notation treating operators as having multiple operands, e.g.,
$$a*(b+c+d) \longrightarrow (*\ a\ (+\ b\ c\ d)).$$

---

## Lecture 7: Transformations of Expression Trees (Continued)

**Source:** CompAlg_-_all.pdf, Lecture 7

**Content Type: Core Formula**
**Content Text:**
Distributivity of multiplication over addition:
$$(a_1 + \cdots + a_n)*b = a_1*b + \cdots + a_n*b.$$
Distributivity of exponentiation over multiplication:
$$(a_1 * \cdots * a_n)^p = a_1^p * \cdots * a_n^p.$$
Analogous distributive laws for union/intersection in set theory:
$$(A_1 \cup \cdots \cup A_n) \cap B = (A_1 \cap B) \cup \cdots \cup (A_n \cap B),$$
$$(A_1 \cap \cdots \cap A_n) \cup B = (A_1 \cup B) \cap \cdots \cap (A_n \cup B).$$

**Content Type: Worked Example/Proof**
**Content Text:**
Not every identity that resembles a distributive law is valid; for example,
$$\ln(a_1 * \cdots * a_n) \neq \ln(a_1) * \cdots * \ln(a_n).$$

**Content Type: Definition**
**Content Text:**
Simplification may be viewed as the repeated application of rewrite rules, each specifying how a particular expression pattern should be transformed into an equivalent but simpler one, applied during a bottom-up traversal of the expression tree (smallest subexpressions first) until no further simplifications are possible.

---

## Lecture 8: Getting Started with Programming in Maxima

**Source:** CompAlg_-_all.pdf, Lecture 8

**Content Type: Definition**
**Content Text:**
Useful built-in Maxima functions introduced: expand, factor, ratsimp, trigsimp, subst, solve, makelist, sum, prod, lhs, rhs, float, among others. Predefined constants: %i, %e, %pi. The special symbol % refers to the result of the previous computation. The quote operator ' placed before an expression prevents Maxima from evaluating it immediately.

---

## Lecture 9: More Maxima Practice. Modular Arithmetic

**Source:** CompAlg_-_all.pdf, Lecture 9

**Content Type: Definition**
**Content Text:**
Modular arithmetic: comparing two integers modulo a given number leads to the concept of congruence (illustrated by arithmetic modulo 12 as on a clock).

---

## Lecture 10: Modular Arithmetic (Continued)

**Source:** CompAlg_-_all.pdf, Lecture 10

**Content Type: Theorem/Property**
**Content Text:**
Congruence is an equivalence relation, whose equivalence classes are called residue classes. All elements of the same residue class are equivalent, so one may freely replace a given integer by any other representative of its residue class.

**Content Type: Theorem/Property**
**Content Text:**
The sum of two residue classes equals the residue class of the sum, and the product of two residue classes equals the residue class of the product (these operations are well defined). Arithmetic operations modulo $n$ can be performed using any convenient representatives of the corresponding residue classes.

**Content Type: Definition**
**Content Text:**
Two common notations for modular arithmetic computations: residue classes ($[\cdots]_n$) or congruence relations ($\equiv$).

---

## Lecture 11: Multiplicative Inverses Modulo n

**Source:** CompAlg_-_all.pdf, Lecture 11

**Content Type: Core Formula**
**Content Text:**
$$[a]_n + [b]_n = [a+b]_n, \qquad [a]_n \cdot [b]_n = [a\cdot b]_n, \qquad [a^p]_n = ([a]_n)^p,\ p \in \mathbb{N}.$$

**Content Type: Definition**
**Content Text:**
There are exactly $n$ distinct residue classes modulo $n$, represented by $[0]_n, [1]_n, \ldots, [n-1]_n$. The set of residue classes modulo $n$ is denoted $\mathbb{Z}_n = \{[0]_n, [1]_n, \ldots, [n-1]_n\}$.

**Content Type: Definition**
**Content Text:**
Residue classes of polynomials modulo a polynomial: for integers, $[a]_n = a + n\mathbb{Z} = \{a+nk \mid k \in \mathbb{Z}\}$. Similarly, for polynomials,
$$[p(x)]_{q(x)} = p(x) + q(x)\mathbb{Z}[x] = \{p(x) + q(x)w(x) \mid w(x) \in \mathbb{Z}[x]\},$$
where $\mathbb{Z}[x]$ is the ring of all polynomials with integer coefficients.

**Content Type: Theorem/Property**
**Content Text:**
Isomorphisms of polynomial residue-class structures:
$$\{p(x) + x\mathbb{Z}[x] \mid p(x) \in \mathbb{Z}[x]\} \cong \mathbb{Z},$$
$$\{p(x) + (x^2+1)\mathbb{Z}[x] \mid p(x) \in \mathbb{Z}[x]\} \cong \mathbb{Z}x + \mathbb{Z}.$$

**Content Type: Worked Example/Proof**
**Content Text:**
Addition and multiplication tables modulo $n$ were constructed for $n = 2, 3, 4, 5$. In the addition table, every row is obtained from the first row by a cyclic shift. In the multiplication table, every nonzero row contains $[1]_n$ whenever $n$ is prime; when $n$ is composite, at least one row never contains $[1]_n$.

**Content Type: Definition**
**Content Text:**
If $a \cdot b \equiv 1 \pmod{n}$, then $b$ is called the multiplicative inverse of $a$ modulo $n$, denoted $b = a^{-1}$. When $n$ is prime, every nonzero residue class has a multiplicative inverse; when $n$ is composite, at least one nonzero residue class has no inverse.

**Content Type: Definition**
**Content Text:**
Zero divisors (divisors of zero): nonzero residue classes $[a]_n, [b]_n$ such that $[a]_n \cdot [b]_n = [0]_n$. Their presence implies not every nonzero element has a multiplicative inverse.

**Content Type: Theorem/Property**
**Content Text:**
Fermat's Little Theorem (observed pattern): $a^{p-1} \equiv 1 \pmod{p}$ for prime $p$ and $1 \leqslant a < p$.

---

## Lecture 12: Introduction to Groups

**Source:** CompAlg_-_all.pdf, Lecture 12

**Content Type: Definition**
**Content Text:**
Two integers $a$ and $b$ are coprime if $\gcd(a,b) = 1$.

**Content Type: Theorem/Property**
**Content Text:**
A residue class $[a]_n$ has a multiplicative inverse if and only if $a$ and $n$ are coprime. The proof is based on Bézout's identity.

**Content Type: Definition**
**Content Text:**
The additive inverse of a residue class $[a]_n$ is $[-a]_n$, since $[a]_n + [-a]_n = [0]_n$.

**Content Type: Definition**
**Content Text:**
A group is a set equipped with a single binary operation satisfying four axioms: closure, the existence of an identity element, associativity, and the existence of inverses. A group is denoted by a pair $(S, \circ)$. Groups whose operation is written as addition are called additive groups; those written as multiplication are called multiplicative groups.

**Content Type: Worked Example/Proof**
**Content Text:**
$(\mathbb{Z}, +)$ is an additive group. The integers with multiplication, and the natural numbers with addition, are not groups (one or more group axioms fail). An equilateral triangle admits six symmetries (rotations and reflections), which form a group under composition.

**Content Type: Definition**
**Content Text:**
$$\mathbb{Z}_n^{*} = \left(\mathbb{Z}_n \setminus \{[0]_n\}, *_n\right) = \left(\{[1]_n, [2]_n, \ldots, [n-1]_n\}, *_n\right),$$
where $*_n$ denotes multiplication modulo $n$.

**Content Type: Theorem/Property**
**Content Text:**
$\mathbb{Z}_n^{*}$ is a multiplicative group if and only if $n$ is prime. Consequently, $\mathbb{Z}_2, \mathbb{Z}_3, \mathbb{Z}_5, \mathbb{Z}_7, \mathbb{Z}_{11}, \ldots$ give rise to multiplicative groups, whereas $\mathbb{Z}_4, \mathbb{Z}_6, \mathbb{Z}_8, \mathbb{Z}_9$, etc., do not.

---

## Lecture 13: Fermat's Little Theorem

**Source:** CompAlg_-_all.pdf, Lecture 13

**Content Type: Definition**
**Content Text:**
A finite group is a group with a finite number of elements. A group $G$ is cyclic if it can be generated by a single element (a generator); every element of $G$ can be expressed as an integer power of that element.

**Content Type: Definition**
**Content Text:**
The order of an element $g$, denoted $\mathrm{ord}(g)$, is the smallest positive integer $n$ such that $g^n = e$ (the identity element); if no such $n$ exists, $\mathrm{ord}(g) = \infty$. The order of a finite group $G$, denoted $|G|$, is the number of elements in $G$.

**Content Type: Theorem/Property**
**Content Text:**
Lagrange's Theorem: the order of every element of a finite group divides the order of the group.

**Content Type: Theorem/Property**
**Content Text:**
Fermat's Little Theorem (FLT): $a^{p-1} \equiv 1 \pmod p$, where $p$ is prime and $p \nmid a$. In residue-class notation: $[a^{p-1}]_p = [a]_p^{p-1} = [1]_p$. FLT is obtained by applying Lagrange's theorem to the multiplicative group of nonzero residue classes modulo a prime.

---

## Lecture 14: Euler's Totient Theorem and Applications

**Source:** CompAlg_-_all.pdf, Lecture 14

**Content Type: Theorem/Property**
**Content Text:**
Euler's Totient Theorem generalizes Fermat's Little Theorem to arbitrary positive integers (both prime and composite moduli), using the Euler totient function.

**Content Type: Worked Example/Proof**
**Content Text:**
Simple applications of modular arithmetic to encryption were considered, including the Caesar cipher and power-based encryption, along with standard Maxima functions for modular arithmetic.

---

## Lecture 15: Final Remarks on Encryption. Complex Numbers

**Source:** CompAlg_-_all.pdf, Lecture 15

**Content Type: Definition**
**Content Text:**
A correct encryption algorithm should be bijective: if $E: A \to \tilde{A}$ is encryption and $D: \tilde{A} \to A$ is decryption, then $D(E(x)) = x$ and $E(D(y)) = y$ for all $x \in A$, $y \in \tilde{A}$.

**Content Type: Definition**
**Content Text:**
A many-to-one mapping sends two or more symbols of the original alphabet to the same symbol of the encrypted alphabet; if it covers the entire target alphabet, it is a surjective mapping.

**Content Type: Theorem/Property**
**Content Text:**
$(\mathbb{C}, +)$ and $(\mathbb{C}\setminus\{0\}, *)$ form the additive and multiplicative groups of complex numbers, respectively.

---

## Lecture 16: Complex Numbers in the Context of Groups

**Source:** CompAlg_-_all.pdf, Lecture 16

**Content Type: Definition**
**Content Text:**
A subgroup is a group whose underlying set is a subset of the original set and which is closed under the group operation.

**Content Type: Worked Example/Proof**
**Content Text:**
Finite subgroups of $C^{*} = (\mathbb{C}\setminus\{0\}, *)$:
$$C_4^{*} = (\{1,-1,-i,i\}, *), \qquad C_8^{*} = \left(\left\{1,-1,-i,i,\tfrac{1+i}{\sqrt2},\tfrac{-1+i}{\sqrt2},\tfrac{1-i}{\sqrt2},\tfrac{-1-i}{\sqrt2}\right\}, *\right).$$
$i$ is a generator of $C_4^{*}$; $(1+i)/\sqrt2$ is a generator of $C_8^{*}$.

**Content Type: Core Formula**
**Content Text:**
Euler's formula: $re^{i\theta} = r(\cos\theta + i\sin\theta)$.
De Moivre's formula: $z^n = (re^{i\theta})^n = r^n(\cos(n\theta) + i\sin(n\theta))$.

**Content Type: Core Formula**
**Content Text:**
The $n$th roots of $z = re^{i\theta}$ are
$$\sqrt[n]{r}\left(\cos\left(\frac{\theta+2\pi k}{n}\right) + i\sin\left(\frac{\theta+2\pi k}{n}\right)\right), \qquad k = 0, 1, \ldots, n-1.$$

**Content Type: Theorem/Property**
**Content Text:**
Multiplicative property of the modulus: $|z_1|\cdot|z_2| = |z_1 \cdot z_2|$, $z_1, z_2 \in \mathbb{C}$. Complex numbers of unit length form a multiplicative subgroup of $C^{*}$: $\{z \in \mathbb{C} : |z| = 1\}$; multiplication by such a number corresponds to a rotation along the unit circle.

---

## Lecture 17: Complex Numbers in the Context of Groups (Continued)

**Source:** CompAlg_-_all.pdf, Lecture 17

**Content Type: Core Formula**
**Content Text:**
For $z_1 = r_1 e^{i\theta_1}$, $z_2 = r_2 e^{i\theta_2}$: $z_1 z_2 = r_1 r_2 e^{i(\theta_1+\theta_2)}$.

**Content Type: Definition**
**Content Text:**
$\omega_n = e^{2\pi i/n}$; its powers generate all $n$th roots of unity, the solutions of $z^n - 1 = 0$. $\omega_n$ is called a primitive $n$th root of unity, a generator of $C_n^{*} = \left(\{e^{2k\pi i/n} \mid k = 0,\ldots,n-1\}, *\right)$.

**Content Type: Theorem/Property**
**Content Text:**
Isomorphism: $C_n^{*} \cong \mathbb{Z}_n^{+}$, via $\omega_n^k \mapsto [k]_n$, since $\omega_n^k \omega_n^\ell = \omega_n^{k+\ell} \leftrightarrow [k+\ell]_n = [k]_n + [\ell]_n$.

**Content Type: Worked Example/Proof**
**Content Text:**
Example with $\mathbb{Z}_4^{+} = \{[0]_4,[1]_4,[2]_4,[3]_4\}$ and $\omega_4 = e^{2\pi i/4} = i$, powers $[1, i, -1, -i]$. The correspondence $[0]_4 \leftrightarrow 1$, $[1]_4 \leftrightarrow i$, $[2]_4 \leftrightarrow -1$, $[3]_4 \leftrightarrow -i$ shows $[1]_4+[2]_4=[3]_4 \leftrightarrow i\cdot(-1) = -i$, and $[3]_4+[2]_4=[1]_4 \leftrightarrow (-i)(-1) = i$. As a simple exercise, compare the group tables of $C_4^{*}$ and $\mathbb{Z}_4^{+}$, given below, and verify that they have the same structure:

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

---

## Lecture 18: Two Representations of Polynomials

**Source:** CompAlg_-_all.pdf, Lecture 18

**Content Type: Worked Example/Proof**
**Content Text:**
The integer 5 is prime in $\mathbb{Z}$ but not in $\mathbb{Z}[i]$ (Gaussian integers), since $5 = (2-i)(2+i)$.

**Content Type: Core Formula**
**Content Text:**
Properties of $n$th roots of unity for even $n$ ($\omega_n = e^{2\pi i/n}$):
$$\omega_n^{n/2} = -1, \quad \omega_n^2 = \omega_{n/2}, \quad \omega_n^n = 1, \quad \omega_n^{-1} = \overline{\omega_n},$$
and consequently
$$\omega_n^{k+n/2} = -\omega_n^k, \quad \omega_n^{2k} = \omega_{n/2}^k, \quad \omega_n^{n-k} = \omega_n^{-k}, \quad \omega_n^{-k} = \overline{\omega_n^k}.$$
The last two of these properties actually hold for any $n \in \mathbb{N}$, but attention is restricted to even $n$ for the purposes of this course.

**Content Type: Definition**
**Content Text:**
Coefficient representation: $p(x) = a_0 + a_1 x + \cdots + a_n x^n$, represented by $(a_0, a_1, \ldots, a_n)$.

**Content Type: Core Formula**
**Content Text:**
For $f(x) = a_0+\cdots+a_nx^n$ and $g(x)=b_0+\cdots+b_nx^n$, their product is $f(x)g(x) = \sum_{k=0}^{2n} c_k x^k$, where $c_k = \sum_{i+j=k,\ 0\le i,j\le n} a_i b_j$. Computing all coefficients directly requires $O(n^2)$ operations.

**Content Type: Definition**
**Content Text:**
Value representation: a polynomial of degree at most $n$ is uniquely represented by its values at $n+1$ distinct points $\{(x_0,y_0),\ldots,(x_n,y_n)\}$, $y_i = p(x_i)$.

**Content Type: Theorem/Property**
**Content Text:**
If the points $x_0,\ldots,x_n$ are distinct, the determinant of the corresponding linear system (the Vandermonde determinant) is nonzero, guaranteeing a unique solution $(a_0,\ldots,a_n)$.

**Content Type: Core Formula**
**Content Text:**
In value representation, pointwise multiplication gives the product: $h(x_i) = f(x_i)g(x_i) = y_i\tilde y_i$, requiring only $O(m)$ operations. For two polynomials of degree at most $n$, their product has degree at most $2n$, requiring at least $2n+1$ distinct evaluation points to recover.

**Content Type: Theorem/Property**
**Content Text:**
Fundamental Theorem of Algebra (FTA): every nonconstant polynomial of degree $n$ with complex coefficients has exactly $n$ roots in $\mathbb{C}$, counted with multiplicities.

**Content Type: Worked Example/Proof**
**Content Text:**
$x^2+1=0$ has no real solutions but has roots $x=i$ and $x=-i$ over $\mathbb{C}$. $(x-1)^2 = x^2-2x+1=0$ has $x=1$ as a root of multiplicity two.

---

## Lecture 19: Polynomials and Roots of Unity

**Source:** CompAlg_-_all.pdf, Lecture 19

**Content Type: Core Formula**
**Content Text:**
$$\sqrt{i} = \frac{1+i}{\sqrt2}, \qquad \sqrt{-i} = \frac{-1+i}{\sqrt2}.$$

**Content Type: Worked Example/Proof**
**Content Text:**
Find $p(x) = 3x^3 - 2x^2 + 2 + x^8$ at $x=\omega_4$, given $\omega_2=-1$:
$$p(\omega_4) = 3\omega_4^3 - 2\omega_4^2 + 2 + \omega_4^8 = 3(-1)\omega_4 -2(-1)+2+1 = -3\omega_4+5 = -3\sqrt{\omega_4^2}+5 = -3\sqrt{-1}+5 = 5-3i.$$

**Content Type: Theorem/Property**
**Content Text:**
Proposition: Let $f$ and $g$ be polynomials of degree $n$. Then their product $h=fg$ has degree $2n$; recovering the coefficients of $h$ from its value representation requires $2n+1$ values at distinct points. More generally, if $\deg f = n$ and $\deg g = m$, then $n+m+1$ distinct evaluation points suffice.

**Content Type: Worked Example/Proof**
**Content Text:**
For $f(x)=1+2x+3x^2$, $g(x)=4+5x$, padding gives $g(x) = 4+5x+0x^2$; both have coefficient lists of length three, and the product (degree at most 4) requires 5 distinct evaluation points.

---

## Lecture 20: FFT and Inverse FFT (IFFT)

**Source:** CompAlg_-_all.pdf, Lecture 20

**Content Type: Core Formula**
**Content Text:**
Even/odd decomposition: $p(x) = p_{\text{even}}(x^2) + x\,p_{\text{odd}}(x^2)$.

**Content Type: Core Formula**
**Content Text:**
Butterfly formula:
$$p(\omega_n^k) = p_{\text{even}}(\omega_n^{2k}) + \omega_n^k\, p_{\text{odd}}(\omega_n^{2k}),$$
$$p(\omega_n^{k+n/2}) = p_{\text{even}}(\omega_n^{2k}) - \omega_n^k\, p_{\text{odd}}(\omega_n^{2k}), \qquad k = 0,\ldots, \frac{n}{2}-1.$$
This converts the coefficient representation of a polynomial with $n$ coefficients into its value representation in $O(n\ln n)$ operations, provided $n$ is a power of two.

**Content Type: Worked Example/Proof**
**Content Text:**
For $f(x)=a_0+a_1x+a_2x^2+a_3x^3$, $g(x)=b_0+b_1x+b_2x^2+b_3x^3$ ($n=4$ coefficients each), the product can have degree up to 6, hence up to 7 coefficients, requiring at least 7 evaluation points; since 7 is not a power of two, the next power of two, $8$, is chosen as the FFT size. In general, for $n$ coefficients, $N_{\mathrm{FFT}} \geqslant 2n-1$ (smallest power of two satisfying this).

**Content Type: Core Formula**
**Content Text:**
Fast polynomial multiplication pipeline:
$$\text{coefficients} \xrightarrow{\text{FFT}} \text{values} \xrightarrow{\text{pointwise multiplication}} \text{values of the product} \xrightarrow{\text{IFFT}} \text{coefficients}.$$

**Content Type: Core Formula**
**Content Text:**
IFFT coefficient formula:
$$a_j = \frac{1}{n}\sum_{k=0}^{n-1} y_k (\omega_n^{-j})^k, \qquad j = 0, \ldots, n-1.$$

---

## Lecture 21: FFT and Inverse FFT (Completed)

**Source:** CompAlg_-_all.pdf, Lecture 21

**Content Type: Theorem/Property**
**Content Text:**
Using substantially more evaluation points than the degree of a polynomial requires does not cause any problem when recovering the coefficient representation, provided the values correspond to distinct points of the same polynomial.

**Content Type: Theorem/Property**
**Content Text:**
The recursive even–odd decomposition of the FFT forms a binary tree of nested FFT computations with depth $O(\log n)$, and each level performs $O(n)$ butterfly operations, giving overall complexity $O(n)\cdot O(\log n) = O(n\log n)$. The IFFT has the same complexity, $O(n\log n)$.

**Content Type: Worked Example/Proof**
**Content Text:**
Fast integer multiplication via FFT: represent integers as polynomials whose coefficients are digits in a chosen base $B$ (e.g., $B=10$: $325 \to p(x) = 5+2x+3x^2$, since $p(10)=5+2\cdot10+3\cdot10^2=325$). Steps: (1) represent integers as polynomials; (2) FFT to value representation; (3) pointwise multiply in $O(n)$; (4) IFFT back to coefficients; (5) evaluate at $x=B$ after carrying coefficients into the range $[0,B-1]$.

**Content Type: Worked Example/Proof**
**Content Text:**
Carrying example: in base 10, coefficient list $[2,15,7]$ is converted to $[2,5,8]$, since $15 = 5+1\cdot10$ contributes digit 5 and carry 1, giving $7+1=8$. The polynomial $2+15x+7x^2$ represents the integer $2+5\cdot10+8\cdot10^2=825$.

**Content Type: Theorem/Property**
**Content Text:**
The overall complexity of polynomial multiplication using the FFT is $O(n\log n)$, since the $O(n)$ pointwise multiplication step does not dominate.

**Content Type: Definition**
**Content Text:**
The FFT has many applications beyond polynomial multiplication, and is widely used in signal processing — for example, in the analysis of audio, images, and other digital signals. There are also various modifications and variants of the FFT designed for specific applications, though the basic FFT algorithm studied in this course is sufficient for its purposes.

---

## Lecture 22: Introduction to Polynomial Systems

**Source:** CompAlg_-_all.pdf, Lecture 22

**Content Type: Definition**
**Content Text:**
A field is a set closed under addition, subtraction, multiplication, and division by a nonzero element (division by zero not allowed). $\mathbb{Q}, \mathbb{R}, \mathbb{C}$ are fields; $\mathbb{Z}$ and $\mathbb{N}$ are not, since in $\mathbb{N}$ subtraction may produce an integer outside the set of natural numbers, while in $\mathbb{Z}$ division of two integers may produce a rational number outside $\mathbb{Z}$.

**Content Type: Definition**
**Content Text:**
Polynomials in one variable $x$ are considered over a field $K$ (typically $K=\mathbb{R}$ or $K=\mathbb{C}$). A root of a polynomial $f(x) \in K[x]$ is an element $a \in K$ such that $f(a)=0$. It is easy to see that a polynomial does not necessarily have a root in an arbitrary field, which makes algebraically closed fields particularly important.

**Content Type: Definition**
**Content Text:**
A field $K$ is algebraically closed if every polynomial in $K[x]$ of degree at least 1 has at least one root in $K$.

**Content Type: Theorem/Property**
**Content Text:**
Fundamental Theorem of Algebra (FTA): $\mathbb{C}$ is an algebraically closed field. Equivalently, every polynomial in $\mathbb{C}[x]$ of degree at least 1 has at least one root in $\mathbb{C}$.

**Content Type: Theorem/Property**
**Content Text:**
Factor Theorem: Let $a \in K$ and $f(x) \in K[x]$. Then $a$ is a root of $f(x)$ if and only if $x-a$ divides $f(x)$; equivalently, there exists $q(x) \in K[x]$ such that $f(x) = (x-a)q(x)$.

**Content Type: Theorem/Property**
**Content Text:**
Factorization over $\mathbb{C}$: every polynomial $f(x) = a_n x^n + a_{n-1}x^{n-1} + \cdots + a_0 \in \mathbb{C}[x]$ of degree $n \geqslant 1$ has exactly $n$ roots in $\mathbb{C}$ and can be written as
$$f(x) = a_n(x-x_1)(x-x_2)\cdots(x-x_n),$$
where $x_1,\ldots,x_n \in \mathbb{C}$ are its roots (not necessarily distinct; repeated roots are called multiple roots).

**Content Type: Definition**
**Content Text:**
The GCD of two polynomials is defined analogously to the GCD for integers, but is unique only up to multiplication by a nonzero constant; the GCD with leading coefficient 1 is called monic. At each step of the polynomial Euclidean algorithm, polynomial division (e.g., synthetic division) is performed.

**Content Type: Worked Example/Proof**
**Content Text:**
An inconsistent overdetermined system: $x-1=0,\ x+1=0$. A consistent system: $x-1=0,\ ax-a=0\ (a\neq0)$.

**Content Type: Worked Example/Proof**
**Content Text:**
For the system
$$x^3-6x^2+11x-6=0, \qquad x^4-8x^3+17x^2+2x-24=0,$$
$$\gcd(x^4-8x^3+17x^2+2x-24,\ x^3-6x^2+11x-6) = x^2-5x+6 = h(x),$$
with roots $x_1=2$, $x_2=3$, so $h(x)=(x-2)(x-3)$; these are also solutions of the original system.

**Content Type: Theorem/Property**
**Content Text:**
Property of the GCD: Let $h=\gcd(f,g)$, $f,g\in\mathbb{C}[x]$ nonzero. If $\deg h = 0$, then $f$ and $g$ have no common roots and the system $f(x)=0,\ g(x)=0$ is inconsistent. If $\deg h \geqslant 1$, the roots of $h$ are precisely the common roots of $f$ and $g$.

**Content Type: Definition**
**Content Text:**
For a two-variable system $f(x,y)=0,\ g(x,y)=0$, the resultant is a construction based on a special determinant providing an algebraic condition for two polynomials to have a common root; it can be used to eliminate one variable in multi-variable systems.
