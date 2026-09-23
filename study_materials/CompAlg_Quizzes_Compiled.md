## Quiz 1: Computer Representation of Numbers

**Source:** quiz01-3.pdf (Computer Algebra) — Time: 30 minutes, Score: up to 12 points.

**Content Type: Worked Example/Proof**
**Content Text:**
1. (1 point) Express the integer division $`a \div b = 511 \div 49`$ in the form $`a = b\cdot q + r`$, where $`0 \leqslant r < b`$.
2. Convert the following decimal numbers to binary: a) (1 point) $`754_{10}`$; b) (2 points) $`0.25_{10}`$.
3. (2 points) Convert the decimal number $`0.19_{10}`$ to binary, assuming that 8 bits are used for the fractional part (mantissa).
4. (2 points) Convert the binary number $`0.1011011_2`$ to decimal.
5. (1 point) Express the binary number $`-10100.0011101_2`$ in the normalized form $`(-1)^s(1.f)_2 \cdot 2^e`$.
6. (1 point) Given the number in the normalized IEEE 754-like form $`(s,f,e) = (0, 11011011, -3)`$, express it in standard binary form (i.e., in the form $`d_1d_2\cdots d_n.d_{n+1}d_{n+2}\cdots`$, each $`d_i \in \lbrace 0,1 \rbrace`$; e.g., $`101.01101_2`$).
7. (2 points) Assuming a 5-bit two's complement representation, determine which negative integer (decimal!) is represented by $`10010_2`$.

---

## Quiz 2: Exact Arithmetic

**Source:** quiz02-1.pdf (Computer Algebra) — Time: 30 minutes, Score: up to 12 points. An equivalent Thai-language version of the quiz is included in the same file.

**Content Type: Core Formula**
**Content Text:**
Reference: the prime numbers between 1 and 100 are $`2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97`$.

**Content Type: Worked Example/Proof**
**Content Text:**
1. Compute the following greatest common divisors using Euclid's algorithm: (a) (0.5 points) $`\gcd(1,0)`$; (b) (0.5 points) $`\gcd(84,60)`$.
2. (1 point) Represent the fraction $`\dfrac{132}{154}`$ as a pair $`(p,q)`$, $`\gcd(p,q)=1`$.
3. (0.5 points) Suppose positive integers are represented in array form using the base $`B=27`$. What are the minimum and maximum possible values of an element of such an array?
4. (0.5 points) Suppose the integer $`\underbrace{120! = 6689502913449\ldots0\cdots0}_{\text{199 digits total}}`$ is represented in array form using the base $`B=1000`$. How many elements should the corresponding array contain (minimum required length)?
5. (0.5 points) Represent the integer $`7834436793`$ in array form using the base $`B=1000`$.
6. (0.5 points) Represent the integer $`7834436793`$ in array form using the base $`B=1011`$.
7. (3 points) Represent the integer $`1234`$ in array form using the base $`B=32`$.
8. (2 points) Consider the integers $`x=62549734`$, $`y=15431`$. Represent them as arrays using base $`B=1000`$, and compute their sum.
9. (1 point) Suppose the prime factorizations of the integers $`x`$ and $`y`$ are known:

```math
x = 1374144656489 = 11^4\cdot17^2\cdot41\cdot89^2, \qquad y = 37852722699 = 3\cdot11^2\cdot17\cdot41^3\cdot89.
```

Represent the product $`x\cdot y`$ as an array of pairs (prime, exponent). *Note: Include only those prime numbers that actually appear in the factorization.*
10. (2 points) Consider the integers $`x=120`$, $`y=96`$. Factor each integer into prime factors. Then represent each factorization as an array of pairs (prime, exponent). Using this representation, compute the product $`x\cdot y`$.

---

## Quiz 3: Expression Trees

**Source:** quiz03-1.pdf (Computer Algebra) — Time: 25 minutes, Score: up to 9 points. Operator priority is assumed standard in mathematics. An equivalent Thai-language version of the quiz is included in the same file.

**Content Type: Worked Example/Proof**
**Content Text:**
1. The expression $`(-\ (*\ (+\ a\ b)\ c)\ (\div\ d\ e))`$ is written in Lisp-style prefix notation.
(a) (0.5 points) Construct the corresponding binary expression tree.
(b) (0.5 points) Traverse the tree using an in-order DFS traversal and write the resulting mathematical expression in standard infix notation.

2. Two expression trees are claimed to represent equivalent expressions:
[Diagram: Tree A — root $`+`$, left child $`*`$ with leaves $`a, b`$, right child $`*`$ with leaves $`a, c`$ (representing $`a*b + a*c`$).]
[Diagram: Tree B — root $`*`$, left leaf $`a`$, right child $`+`$ with leaves $`b, c`$ (representing $`a*(b+c)`$).]
(a) (1 point) Traverse both trees using in-order DFS and write the corresponding mathematical expressions using infix form.
(b) (0.5 points) Are the expressions equivalent? Justify your answer.

3. Consider the expression $`(a+b)*f(x+y)`$. Apply the Expand transformation.
(a) (0.5 points) Draw the original expression tree.
(b) (0.5 points) Draw the expression tree after expansion.

4. Consider the expression $`(a+b)^3 + d*(a+1+b)`$ and the substitution $`a+b \to t`$.
(a) (0.5 points) Draw the expression tree before substitution.
(b) (1 point) Draw the expression tree after substitution.
*Note: Assume operator $`+`$ is left-associative.*

5. Apply the Simplify transformation 3 times to the expression $`\sin^2(x) + \cos^2(x)*\ln(e^x)`$. State the identities used.
(a) (1 point) Draw the expression tree for the original expression.
(b) (1 point) Draw the expression tree after the first simplification.
(c) (1 point) Draw the expression tree after the second simplification.
(d) (1 point) Draw the expression tree after the third simplification.

---

## Quiz 4: Modular Arithmetic

**Source:** quiz04-2.pdf (Computer Algebra) — Time: 30 minutes, Score: up to 12 points. An equivalent Thai-language version of the quiz is included in the same file.

**Content Type: Worked Example/Proof**
**Content Text:**
1. (0.5 points) How many distinct residue classes (equivalence classes) are there modulo 7? List all of them.
2. (0.5 points) Find $`x`$: $`147 \equiv x \pmod{13}`$.
3. (0.5 points) Determine all possible values of $`0 < n \leqslant 18`$ such that $`18 \equiv 0 \pmod n`$.
4. Compute the following:
(a) (0.5 points) $`[125]_{17} + [241]_{17}`$
(b) (0.5 points) $`[391]_{21} \cdot [457]_{21}`$
(c) (1 point) $`[94]_7`$
(d) (1.5 points) $`([157]_{13} + [249]_{13}) \cdot [83]_{13}`$
5. Consider integer arithmetic modulo 8.
(a) (1 point) Construct the multiplication table $`*_8`$.
(b) (1 point) Find all multiplicative inverses that exist.
(c) (1 point) Identify all zero divisors (if any).
6. Consider polynomial arithmetic for $`\mathbb{Z}[x]`$ (polynomials with integer coefficients).
(a) (1.5 points) Reduce the polynomial $`p(x) = 2x^5 - 9x^3 + 5x + 9`$ modulo $`x^3 - 1`$.
(b) (1.5 points) Using the result from the previous part, compute $`(p(x))^2`$ modulo $`x^3-1`$.
(c) (1 point) Describe the set of representatives obtained for $`\mathbb{Z}[x]`$ modulo $`x^3-1`$.

---

## Quiz 5: Totient Function and Encoding

**Source:** quiz05-1.pdf (Computer Algebra) — Time: 25 minutes, Score: up to 8 points. An equivalent Thai-language version of the quiz is included in the same file.

**Content Type: Core Formula**
**Content Text:**
Caesar cipher: $`c \equiv m + s \pmod{26}`$, where $`m`$ is the original code, $`c`$ the encrypted code, $`s`$ the secret key.
Power-based cipher: $`c \equiv m^b \pmod p`$; decryption $`m \equiv c^d \pmod p`$, where $`d`$ satisfies $`bd \equiv 1 \pmod{p-1}`$.

**Content Type: Worked Example/Proof**
**Content Text:**
1. Compute the Euler totient function: (a) (0.5 points) $`\varphi(16)`$; (b) (0.5 points) $`\varphi(17)`$.
2. (3 points) Compute $`3^{347} \pmod{14}`$ using Euler's totient theorem and the rules of modular arithmetic.
3. Using the coding table (A=0, B=1, C=2, D=3, E=4, F=5, G=6, H=7, I=8, J=9, K=10, L=11, M=12, N=13, O=14, P=15, Q=16, R=17, S=18, T=19, U=20, V=21, W=22, X=23, Y=24, Z=25), encrypt the word BY using:
(a) (1 point) The Caesar cipher with secret key $`s=20`$.
(b) (2 points) The power-based cipher with $`p=29`$, $`b=5`$.
(c) (1 point) For the previous problem, find the value of $`d`$ for the decryption formula.

---

## Quiz 6: Complex Numbers and Finite Groups

**Source:** quiz06_1_.pdf (Computer Algebra) — Time: 35 minutes, Score: up to 14 points. Calculators are allowed, but reasoning is emphasized. An equivalent Thai-language version of the quiz is included in the same file.

**Content Type: Core Formula**
**Content Text:**
Table of standard sine and cosine values:

| $`\theta`$ | $`0`$ | $`\frac{\pi}{6}`$ | $`\frac{\pi}{4}`$ | $`\frac{\pi}{3}`$ | $`\frac{\pi}{2}`$ | $`\frac{2\pi}{3}`$ | $`\frac{3\pi}{4}`$ | $`\frac{5\pi}{6}`$ | $`\pi`$ |
|---|---|---|---|---|---|---|---|---|---|
| $`\sin\theta`$ | $`0`$ | $`\frac{1}{2}`$ | $`\frac{\sqrt{2}}{2}`$ | $`\frac{\sqrt{3}}{2}`$ | $`1`$ | $`\frac{\sqrt{3}}{2}`$ | $`\frac{\sqrt{2}}{2}`$ | $`\frac{1}{2}`$ | $`0`$ |
| $`\cos\theta`$ | $`1`$ | $`\frac{\sqrt{3}}{2}`$ | $`\frac{\sqrt{2}}{2}`$ | $`\frac{1}{2}`$ | $`0`$ | $`-\frac{1}{2}`$ | $`-\frac{\sqrt{2}}{2}`$ | $`-\frac{\sqrt{3}}{2}`$ | $`-1`$ |

Trigonometric identities:

```math
\sin(x+2\pi k)=\sin x, \quad \cos(x+2\pi k)=\cos x, \quad k\in\mathbb{Z},
```

```math
\sin(-x)=-\sin(x), \quad \cos(-x)=\cos(x).
```

**Content Type: Worked Example/Proof**
**Content Text:**
1. For the complex numbers $`z_1 = 1+i`$, $`z_2 = 2-3i`$, find:
(a) (0.5 points) $`z_1+z_2`$ and $`z_1-z_2`$;
(b) (0.5 points) $`z_1z_2`$;
(c) (0.5 points) $`z_1 z_2`$ [Diagram: a complex-conjugate overline appears to be present in the original expression but is not preserved in the extracted text];
(d) (0.5 points) $`|z_1|\cdot|z_2|`$;
(e) (1 point) $`\dfrac{z_1}{z_2}`$.
2. Consider the complex numbers $`z_1 = i`$, $`z_2 = 3+2i`$, $`z_3 = -5-i`$.
(a) (0.5 points) Plot $`z_1`$, $`z_2`$, and $`z_3`$ as vectors on the complex plane (Re, Im).
(b) (1 point) Find the sum $`z_1+z_2+z_3`$ graphically.
3. Consider the following complex numbers in polar form: $`z_1 = \dfrac{1}{2}e^{\frac{\pi}{4}i}`$, $`z_2 = 3e^{\frac{3\pi}{4}i}`$.
(a) (0.5 points) Find the product $`w = z_1z_2`$ in polar form.
(b) (1 point) Plot the vectors corresponding to $`z_1`$, $`z_2`$, and $`w`$ on the complex plane (Re, Im).
4. Consider the complex number in polar form $`z = 2e^{\frac{\pi}{3}i}`$.
(a) (1 point) Using Euler's formula, express $`z`$ in standard (rectangular) form.
(b) (1 point) Using de Moivre's formula, find $`z^3`$ and express the result in standard (rectangular) form.
(c) (2 points) Using de Moivre's formula, find all square roots of $`z`$.
5. Consider the following set:

```math
C_3 = \left\lbrace 1,\ \frac{-1+\sqrt{3}\ i}{2},\ \frac{-1-\sqrt{3}\ i}{2} \right\rbrace.
```

(a) (2 points) Construct the multiplication table for the elements of $`C_3`$ and verify that the set is closed under multiplication.
(b) (1 point) For the multiplicative group $`C_3^* = (C_3, *)`$, identify an isomorphic group $`A`$ arising from modular arithmetic.
(c) (1 point) Identify the generators of the groups $`C_3^*`$ and $`A`$.

---

## Quiz 7: Two Representations of Polynomials

**Source:** quiz07-1.pdf (Computer Algebra) — Time: 35 minutes, Score: up to 14 points. An equivalent Thai-language version of the quiz is included in the same file.

**Content Type: Core Formula**
**Content Text:**
Properties of complex roots of unity:

```math
\omega_n = e^{2\pi i/n}, \quad \omega_n^{k+n/2} = -\omega_n^k, \quad \omega_n^{2k} = \omega_{n/2}^k, \quad \omega_n^{n-k} = \omega_n^{-k}, \quad \omega_n^{-k} = (\omega_n^k)^{-1} = \overline{\omega_n^k},
```

where $`k \in \mathbb{N}\cup\lbrace 0\rbrace`$. In particular, for $`k=0`$: $`\omega_n^{n/2}=-1`$, $`\omega_n^2=\omega_{n/2}`$, $`\omega_n^n=1`$, $`\omega_n^{-1}=\overline{\omega_n}`$.

**Content Type: Worked Example/Proof**
**Content Text:**
1. The eighth roots of unity can be obtained from the primitive root $`\omega_8 = \frac{1+i}{\sqrt2}`$. Using the properties of complex roots of unity, determine: (a) (0.5 points) $`\omega_8^4`$; (b) (0.5 points) $`\omega_8^8`$; (c) (1 point) $`\omega_8^{-5}`$; (d) (1 point) $`\omega_{16}^4`$.
2. (2 points) Evaluate the polynomial $`p(x) = x^4 - 3x^3 + x^2 - 2x - 1`$ at $`x=\omega_4`$ without evaluating $`\omega_4`$, given $`\omega_2 = -1`$.
3. Consider the two polynomials (linear functions) $`f(x) = 1-x`$, $`g(x) = 2+x`$.
(a) (1 point) Write their representations by values at the points $`x_0=-2`$ and $`x_1=0`$.
(b) (2 points) Extend the set of evaluation points by taking $`x_2=1`$. Write the value representations of both polynomials at the extended set of points and multiply the corresponding values to obtain the value representation of $`h(x)=f(x)g(x)`$.
(c) (3 points) Recover the coefficient representation of the polynomial $`h(x)`$.
4. (3 points) Multiply the two polynomials represented by the curves in the figure below graphically. Use at least six points for the multiplication, choosing points marked by crosses on the $`x`$-axis. Sketch an approximate graph of the product.
[Diagram: Figure showing two curves on $`x \in [-1.5, 1.5]`$, $`y \in [-8, 10]`$ — a solid curve forming a gentle downward-opening arc near $`y \approx 2`$–$`3`$ around $`x=0`$ crossing zero near $`x=\pm1.3`$, and a dashed curve that dips to about $`-1`$ near $`x=-1`$, rises through the origin, and climbs steeply to about $`9`$–$`10`$ near $`x=1.5`$ — with six crosses marked on the $`x`$-axis at roughly $`x = -1.3, -1, -0.5, 0, 1, 1.3`$ as the evaluation points for graphical multiplication.]

---

## Quiz 8: FFT / IFFT

**Source:** quiz08.pdf (Computer Algebra) — Time: 35 minutes, Score: up to 12 points. An equivalent Thai-language version of the quiz is included in the same file.

**Content Type: Core Formula**
**Content Text:**
Butterfly formula:

```math
p(\omega_n^k) = p_{\text{even}}(\omega_n^{2k}) + \omega_n^k p_{\text{odd}}(\omega_n^{2k}), \qquad p(\omega_n^{k+n/2}) = p_{\text{even}}(\omega_n^{2k}) - \omega_n^k p_{\text{odd}}(\omega_n^{2k}), \qquad k=0,\ldots,\frac{n}{2}-1.
```

Inverse FFT:

```math
a_j = \frac{1}{n}\sum_{k=0}^{n-1} y_k(\omega_n^{-j})^k, \qquad j=0,\ldots,n-1.
```

Useful properties of complex roots of unity (n even): $`\omega_n^n=1`$, $`\omega_n^{n/2}=-1`$, $`\omega_n^2=\omega_{n/2}`$, $`\omega_n^{-1}=\overline{\omega_n}`$, $`\omega_n^{-k}=\omega_n^{n-k}=(\omega_n^k)^{-1}`$.

**Content Type: Worked Example/Proof**
**Content Text:**
1. Consider $`p(x) = a_0+a_1x+a_2x^2+\cdots+a_{n-1}x^{n-1}`$.
(a) (0.5 points) How many points are required to convert this polynomial into its value representation and back?
(b) (0.5 points) Can this polynomial be used directly with the FFT algorithm if $`n-1=16`$?
(c) (0.5 points) How many points are required to convert $`(p(x))^2`$ into its value representation and recover its coefficient representation without any loss of data?
2. Consider $`p(x) = 1-2x+3x^2-4x^3+\cdots-8x^7`$.
(a) (1 point) Represent the polynomial in terms of its even and odd parts, $`p_e`$ and $`p_o`$, in a form suitable for subsequent application of the FFT.
(b) (1 point) Further decompose each of $`p_e`$ and $`p_o`$ into their even and odd parts, i.e., express them in terms of $`p_{ee}, p_{eo}, p_{oe}, p_{oo}`$.
(c) (0.5 points) What is the depth of the recursion (binary) tree obtained by repeatedly applying the butterfly formulas to this polynomial?
3. (4 points) Represent the polynomial $`q(x) = 1 - x^2 + 4x^3`$ in value form using the FFT.
4. (4 points) Given the values of a polynomial at the 4th roots of unity, $`y_0=-1`$, $`y_1=i`$, $`y_2=1`$, $`y_3=2`$, recover the first three coefficients $`(a_0, a_1, a_2)`$ of the polynomial using the IFFT.
5. (2 extra points) Recover the coefficient $`a_3`$ of the polynomial from the previous problem and write the polynomial in coefficient representation.
