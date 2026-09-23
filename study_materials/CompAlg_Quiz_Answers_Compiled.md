## Answers to Quiz 5: Totient Function and Encoding

**Source:** quiz05_ans.pdf (Computer Algebra) — Answer key for Quiz 5.

**Content Type: Worked Example/Proof**
**Content Text:**
1. (a) (0.5 points) $`\varphi(16) = \lvert \lbrace 1, 3, 5, 7, 9, 11, 13, 15 \rbrace \rvert = 8`$.
(b) (0.5 points) $`\varphi(17) = 17 - 1 = 16`$.
2. (3 points)

```math
\varphi(14) = \lvert \lbrace 1, 3, 5, 9, 11, 13 \rbrace \rvert = 6.
```

```math
[3^{347}]_{14} = [3^{57\cdot 6 + 5}]_{14} = [3]_{14}^5 = [5]_{14}.
```

3. (a) (1 point) The Caesar cipher: $`(21, 18)`$ or $`(\text{V}, \text{S})`$.
(b) (2 points)

```math
([1]_{29}^5,\ [24]_{29}^5) = ([1]_{29},\ [7]_{29}) \to (\text{B}, \text{H})
```

(c) (1 point) $`bd \equiv 1 \pmod{p-1}`$. By definition, there is some $`n \in \mathbb{N}_0`$ such that

```math
bd = (p-1)n + 1.
```

Then,

```math
5d = 28n + 1, \qquad d = \frac{28n+1}{5} \in [1, 28] \subset \mathbb{N}.
```

We try $`n = 0, 1, 2, 3, \ldots`$, etc. For $`n = 3`$, one gets $`d = b^{-1} = 5^{-1} = 17`$.

---

## Answers to Quiz 6: Complex Numbers and Finite Groups

**Source:** quiz06_ans.pdf (Computer Algebra) — Answer key for Quiz 6.

**Content Type: Worked Example/Proof**
**Content Text:**
1. (a) (0.5 points) $`z_1 + z_2 = 3 - 2i`$, $`\quad z_1 - z_2 = -1 + 4i`$.
(b) (0.5 points) $`z_1 z_2 = 5 - i`$.
(c) (0.5 points) $`z_1 z_2 = 5 + i`$ [Diagram: a complex-conjugate overline appears to be present in the original expression but is not preserved in the extracted text].
(d) (0.5 points) $`|z_1|\cdot|z_2| = \sqrt{2}\sqrt{13} = \sqrt{26}`$.
(e) (1 point)

```math
\frac{z_1}{z_2} = \frac{z_1 \overline{z_2}}{|z_2|^2} = \frac{-1 + 5i}{13}.
```

2. (a) (0.5 points) (Figure is trivial: draw the corresponding vectors)
$`z_1 \simeq (0, 1)`$, $`z_2 \simeq (3, 2)`$, $`z_3 \simeq (-5, -1)`$.
(b) (1 point) (Figure is trivial: draw the corresponding vector)
$`z_1 + z_2 + z_3 = -2 + 2i \simeq (-2, 2)`$.
3. (a) (0.5 points)

```math
w = z_1 z_2 = \frac{3}{2}e^{i\pi} = -\frac{3}{2}.
```

(b) (1 point) (The figure is straightforward: draw a vector of length $`1/2`$ at an angle of $`\pi/4`$ for $`z_1`$; similarly for $`z_2`$ and $`w`$.)
4. (a) (1 point)

```math
z = 2\left(\cos\frac{\pi}{3} + i\sin\frac{\pi}{3}\right) = 1 + \sqrt{3} i.
```

(b) (1 point)

```math
z^3 = 8(\cos\pi + i\sin\pi) = 8e^{i\pi} = -8.
```

(c) (2 points)

```math
(\sqrt{z})_1 = \sqrt{2} e^{i\pi/6}, \qquad (\sqrt{z})_2 = \sqrt{2} e^{i7\pi/6} = \sqrt{2} e^{\left(\frac{7\pi}{6} - 2\pi\right)i} = \sqrt{2} e^{-i5\pi/6}.
```

Equivalently, by de Moivre's formula,

```math
(\sqrt{z})_1 = \frac{\sqrt{3}}{\sqrt{2}} + \frac{i}{\sqrt{2}}, \qquad (\sqrt{z})_2 = -\frac{\sqrt{3}}{\sqrt{2}} - \frac{i}{\sqrt{2}}.
```

5. Let

```math
\omega_+ = \frac{-1 + \sqrt{3} i}{2}, \qquad \omega_- = \frac{-1 - \sqrt{3} i}{2}.
```

(a) (2 points) The multiplication table is

| $`*`$ | $`1`$ | $`\omega_+`$ | $`\omega_-`$ |
|---|---|---|---|
| $`1`$ | $`1`$ | $`\omega_+`$ | $`\omega_-`$ |
| $`\omega_+`$ | $`\omega_+`$ | $`\omega_-`$ | $`1`$ |
| $`\omega_-`$ | $`\omega_-`$ | $`1`$ | $`\omega_+`$ |

Thus, $`C_3`$ is closed under multiplication.
(b) (1 point)

```math
C_3^* \cong A = (\mathbb{Z}_3, +) = \lbrace [0]_3, [1]_3, [2]_3\rbrace.
```

Brute-force solution: construct the addition table modulo 3 and compare it with the multiplication table (see above) of $`C_3^*`$. It can be seen that the two tables have the same structure. In fact, the tables coincide under the correspondence

```math
1 \mapsto [0]_3, \qquad \omega_+ \mapsto [1]_3, \qquad \omega_- \mapsto [2]_3.
```

Thus, this correspondence establishes an isomorphism (equivalence) between the two groups.

More elegant solution: this correspondence is particularly easy to establish by matching the generators of the two groups, for example,

```math
\omega_+ \mapsto [1]_3.
```

Then

```math
\omega_+^2 = \omega_+ * \omega_+ = \omega_- \mapsto [1]_3 + [1]_3 = [2]_3,
```

```math
\omega_+^3 = \omega_+ * \omega_+ * \omega_+ = 1 \mapsto [1]_3 + [1]_3 + [1]_3 = [0]_3,
```

and so on. In this way, the entire addition table modulo 3 can be obtained from the multiplication table of $`C_3`$. Thus, the two tables have the same structure, which demonstrates that the groups are isomorphic (equivalent).
(c) (1 point) The generators are

```math
\text{Gen}(C_3^*) = \lbrace \omega_+, \omega_-\rbrace, \qquad \text{Gen}(\mathbb{Z}_3^+) = \lbrace [1]_3, [2]_3\rbrace.
```

(It is sufficient to specify at least one generator for each set.)

---

## Answers to Quiz 7: Two Representations of Polynomials

**Source:** quiz07_ans.pdf (Computer Algebra) — Answer key for Quiz 7.

**Content Type: Core Formula**
**Content Text:**
The following properties of complex roots of unity may be useful:

```math
\omega_n^{n/2} = -1, \qquad \omega_n^2 = \omega_{n/2}, \qquad \omega_n^n = 1, \qquad \omega_n^{-1} = \overline{\omega_n}.
```

**Content Type: Worked Example/Proof**
**Content Text:**
1. For $`\omega_8 = \dfrac{1+i}{\sqrt{2}} = e^{\frac{2\pi i}{8}} = e^{\frac{\pi i}{4}}`$:
(a) (0.5 points) $`\omega_8^4 = -1`$ by $`\omega_n^{n/2} = -1`$.
(b) (0.5 points) $`\omega_8^8 = 1`$ by $`\omega_n^n = 1`$.
(c) (1 point)

```math
\omega_8^{-5} = \omega_8^{-4}\omega_8^{-1} = (\omega_8^4)^{-1}\omega_8^{-1} = (-1)^{-1}\cdot\overline{\omega_8} = (-1)\cdot\frac{1-i}{\sqrt{2}} = \frac{-1+i}{\sqrt{2}} = -\overline{\omega_8}
```

(d) (1 point)

```math
\omega_{16}^4 = (\omega_{16}^2)^2 = (\omega_8)^2 = \left(e^{\frac{\pi i}{4}}\right)^2 = e^{\frac{\pi i}{2}} = i
```

(Here we can also use $`(\omega_8)^2 = \omega_4 = i`$, or just find $`\omega_8^2`$ by direct calculations.)
2. (2 points) Evaluate the polynomial at $`x = \omega_4`$ without evaluating $`\omega_4`$, given $`\omega_2 = -1`$:

```math
p(\omega_4) = \omega_4^4 - 3\omega_4^3 + \omega_4^2 - 2\omega_4 - 1
```

```math
= 1 - 3\omega_4^2\omega_4 + \omega_4^2 - 2\omega_4 - 1 = 1 - 3(-1)\omega_4 + (-1) - 2\omega_4 - 1
```

```math
= \omega_4 - 1 = \sqrt{\omega_4^2} - 1 = \sqrt{-1} - 1 = i - 1.
```

Actually, $`\omega_2`$ is not needed here. One can use $`\omega_4^2 = \omega_2`$ though.
3. Consider the following two polynomials (linear functions): $`f(x) = 1 - x`$, $`g(x) = 2 + x`$.
(a) (1 point) At the points $`x_0 = -2`$ and $`x_1 = 0`$, we obtain

```math
f(-2) = 1 - (-2) = 3, \qquad f(0) = 1,
```

```math
g(-2) = 2 + (-2) = 0, \qquad g(0) = 2.
```

Therefore, the value representations are

```math
f(x):\ \lbrace(-2, 3), (0, 1)\rbrace, \qquad g(x):\ \lbrace(-2, 0), (0, 2)\rbrace.
```

(b) (2 points) Since the product $`h(x) = f(x)g(x)`$ is a quadratic polynomial, three distinct evaluation points are sufficient. We add $`x_2 = 1`$. For $`f`$ and $`g`$, we have

```math
f(1) = 1 - 1 = 0, \qquad g(1) = 2 + 1 = 3.
```

Thus, the extended value representations are

```math
f(x):\ \lbrace(-2, 3), (0, 1), (1, 0)\rbrace,
```

and

```math
g(x):\ \lbrace(-2, 0), (0, 2), (1, 3)\rbrace.
```

Multiplying the corresponding values pointwise gives

```math
h(x):\ \lbrace(-2, 3\cdot 0), (0, 1\cdot 2), (1, 0\cdot 3)\rbrace = \lbrace(-2, 0), (0, 2), (1, 0)\rbrace.
```

Thus, the value representation of the product is

```math
h(x):\ \lbrace(-2, 0), (0, 2), (1, 0)\rbrace.
```

For clarity, all the results of the computations are summarized in the following table.

| $`x`$ | $`-2`$ | $`0`$ | $`1`$ |
|---|---|---|---|
| $`f(x) = 1 - x`$ | $`3`$ | $`1`$ | $`0`$ |
| $`g(x) = 2 + x`$ | $`0`$ | $`2`$ | $`3`$ |
| $`h(x) = f(x)g(x)`$ | $`0`$ | $`2`$ | $`0`$ |

(c) (3 points) We need to find $`c_0`$, $`c_1`$, and $`c_2`$:

```math
h(x) = c_0 + c_1 x + c_2 x^2.
```

From the value representation

```math
h(-2) = 0, \qquad h(0) = 2, \qquad h(1) = 0,
```

we obtain

```math
c_0 - 2c_1 + 4c_2 = 0,
```

```math
c_0 = 2,
```

```math
c_0 + c_1 + c_2 = 0.
```

From $`c_0 = 2`$, we have

```math
c_1 + c_2 = -2,
```

```math
-2c_1 + 4c_2 = -2.
```

Solving these two equations yields

```math
c_1 = -1, \qquad c_2 = -1.
```

Therefore, the coefficient representation of $`h(x)`$ is

```math
(2, -1, -1) \quad \Leftrightarrow \quad h(x) = 2 - x - x^2
```

4. (3 points) This is the simplest pointwise multiplication of two functions $`f`$ and $`g`$. For each point $`x_i`$, we find approximate values of $`f(x_i)`$ and $`g(x_i)`$ from the graph. Then we construct a new point $`(x_i, f(x_i)\cdot g(x_i))`$. Finally, we connect all the points with a smooth curve. The approximate result is shown in the graph below by the red curve.
[Diagram: Graph on $`x \in [-1.5, 1.5]`$, $`y \in [-8, 10]`$ (axis extends slightly beyond, to about $`11`$ and $`-9`$), with crosses on the $`x`$-axis marking the evaluation points (approximately $`x = -1.5, -1.25, -1, 0, 1, 1.25, 1.5`$). It shows the solid black curve $`f`$ (a gentle arc peaking near $`y \approx 2.5`$ at $`x = 0`$ and dropping below zero toward $`x = \pm 1.5`$), the dashed black curve $`g`$ (about $`4.3`$ at $`x = -1.5`$, dipping to near $`0`$ around $`x = 0`$, then rising steeply to about $`11`$ at $`x = 1.5`$), blue points marking $`f`$ and $`g`$ at the evaluation points, and the red curve for the product through the points $`(x_i, f(x_i)\cdot g(x_i))`$: approximately $`-4.5`$ at $`x = -1.5`$, crossing zero near $`x \approx -1.25`$, about $`2.3`$ at $`x = -1`$, about $`0.6`$ at $`x = 0`$, about $`3.3`$ at $`x = 1`$, crossing zero near $`x \approx 1.25`$, and about $`-9.3`$ at $`x = 1.5`$.]

---

## Answers to Quiz 8: FFT / IFFT

**Source:** quiz08_ans_1_.pdf (Computer Algebra) — Answer key for Quiz 8.

**Content Type: Worked Example/Proof**
**Content Text:**
1. (a) (0.5 points) $`n`$ points.
(b) (0.5 points) No. If $`n - 1 = 16`$, then the polynomial has $`17`$ coefficients. However, the base-2 FFT requires the number of points to be a power of two. So this problem requires some modifications to apply FFT.
(c) (0.5 points) The polynomial $`p(x)`$ has degree at most $`n-1`$, so

```math
\deg\big(p(x)^2\big) \leqslant 2(n-1) = 2n - 2.
```

Therefore, $`2n - 1`$ distinct points are sufficient.
2. (a) (1 point) Separate the even and odd powers:

```math
p(x) = (1 + 3x^2 + 5x^4 + 7x^6) + (-2x - 4x^3 - 6x^5 - 8x^7).
```

Hence,

```math
p(x) = p_e(x^2) + x p_o(x^2),
```

where

```math
p_e(y) = 1 + 3y + 5y^2 + 7y^3 \quad \text{and} \quad p_o(y) = -2 - 4y - 6y^2 - 8y^3.
```

(b) (1 point) We decompose $`p_e`$ and $`p_o`$ in the same way:

```math
p_e(x) = p_{ee}(x^2) + x p_{eo}(x^2),
```

```math
p_o(x) = p_{oe}(x^2) + x p_{oo}(x^2).
```

For $`p_e`$,

```math
1 + 3x + 5x^2 + 7x^3 = (1 + 5x^2) + x(3 + 7x^2),
```

so

```math
p_{ee}(y) = 1 + 5y, \qquad p_{eo}(y) = 3 + 7y.
```

Similarly,

```math
-2 - 4x - 6x^2 - 8x^3 = (-2 - 6x^2) + x(-4 - 8x^2),
```

so

```math
p_{oe}(y) = -2 - 6y, \qquad p_{oo}(y) = -4 - 8y.
```

Therefore,

```math
p_e(y) = p_{ee}(y^2) + y p_{eo}(y^2),
```

```math
p_o(y) = p_{oe}(y^2) + y p_{oo}(y^2).
```

(c) (0.5 points) The original polynomial has $`8`$ coefficients. At each step, the polynomial is split into two polynomials of half the size:

```math
8 \longrightarrow 4 \longrightarrow 2 \longrightarrow 1.
```

Thus, the binary recursion tree has depth

```math
\log_2 8 = 3.
```

3. (4 points) We have

```math
q(x) = 1 - x^2 + 4x^3.
```

To apply the FFT, we first pad the coefficient list to a power-of-two length. Since $`q`$ has $`4`$ coefficients, no padding is necessary.
Separate the even and odd parts:

```math
q(x) = q_e(x^2) + x q_o(x^2),
```

where

```math
q_e(y) = 1 - y, \qquad q_o(y) = 4y.
```

For the $`4`$-th roots of unity, let

```math
\omega_4^0 = 1, \quad \omega_4^1 = i, \quad \omega_4^2 = -1, \quad \omega_4^3 = -i.
```

We first evaluate $`q_e`$ and $`q_o`$ at the $`2`$-nd roots of unity, $`1`$ and $`-1`$:

```math
q_e(1) = 1 - 1 = 0, \qquad q_o(1) = 4,
```

```math
q_e(-1) = 1 - (-1) = 2, \qquad q_o(-1) = -4.
```

Using the butterfly formulas,

```math
q(\omega_4^0) = q_e(1) + \omega_4^0 q_o(1) = 0 + 4 = 4,
```

```math
q(\omega_4^2) = q_e(1) - \omega_4^0 q_o(1) = 0 - 4 = -4,
```

```math
q(\omega_4^1) = q_e(-1) + \omega_4^1 q_o(-1) = 2 - 4i,
```

```math
q(\omega_4^3) = q_e(-1) - \omega_4^1 q_o(-1) = 2 + 4i.
```

Therefore, the value representation is

```math
\lbrace(1, 4), (i, 2 - 4i), (-1, -4), (-i, 2 + 4i)\rbrace
```

4. (4 points) We are given

```math
y_0 = -1, \quad y_1 = i, \quad y_2 = 1, \quad y_3 = 2.
```

For the $`4`$-point IFFT,

```math
a_j = \frac{1}{4}\sum_{k=0}^{3} y_k \omega_4^{-jk}, \qquad j = 0, 1, 2, 3,
```

where

```math
\omega_4 = i.
```

For $`a_0`$,

```math
a_0 = \frac{1}{4}(y_0 + y_1 + y_2 + y_3) = \frac{1}{4}(-1 + i + 1 + 2) = \frac{2 + i}{4}.
```

For $`a_1`$,

```math
a_1 = \frac{1}{4}\left(y_0 + y_1\omega_4^{-1} + y_2\omega_4^{-2} + y_3\omega_4^{-3}\right) = \frac{1}{4}\left(-1 + i(-i) + 1(-1) + 2i\right) = \frac{-1 + 2i}{4}.
```

For $`a_2`$,

```math
a_2 = \frac{1}{4}\left(y_0 + y_1\omega_4^{-2} + y_2\omega_4^{-4} + y_3\omega_4^{-6}\right) = \frac{1}{4}\left(-1 - i + 1 - 2\right) = \frac{-2 - i}{4}.
```

Therefore,

```math
(a_0, a_1, a_2) = \left(\frac{2 + i}{4},\ \frac{-1 + 2i}{4},\ \frac{-2 - i}{4}\right).
```

(Extra) (2 extra points) For completeness, we can also recover $`a_3`$:

```math
a_3 = \frac{1}{4}\left(y_0 + y_1\omega_4^{-3} + y_2\omega_4^{-6} + y_3\omega_4^{-9}\right) = \frac{1}{4}\left(-1 + i(i) + 1(-1) + 2(-i)\right) = \frac{1}{4}(-3 - 2i).
```

Thus,

```math
a_3 = -\frac{3 + 2i}{4}.
```

The polynomial in coefficient representation is

```math
p(x) = \frac{2 + i}{4} + \frac{-1 + 2i}{4} x + \frac{-2 - i}{4} x^2 - \frac{3 + 2i}{4} x^3.
```
