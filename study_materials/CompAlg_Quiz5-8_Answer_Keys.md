## Quiz 5: Totient Function and Encoding — Answer Key

**Source:** quiz05_ans.pdf (Computer Algebra)

### Worked Example/Proof — Solutions

**1. Euler totient function**

(a) (0.5 points) $\phi(16) = \# \{1,3,5,7,9,11,13,15\} = 8.$

(b) (0.5 points) $\phi(17) = 17 - 1 = 16.$

**2. (3 points) Compute $3^{347} \pmod{14}$**

$$\phi(14) = \# \{1,3,5,9,11,13\} = 6.$$
$$[3^{347}]_{14} = [3^{57\cdot 6} + 5]_{14} = [3]_{14}^{5} = [5]_{14}.$$

**3. Encryption of the word BY**

(a) (1 point) The Caesar cipher: $(21, 18)$ or $(V,S)$.

(b) (2 points)
$$([1]_{29}^{5},[24]_{29}^{5}) = ([1]_{29},[7]_{29})\rightarrow (\mathbb{B},\mathbb{H})$$

(c) (1 point)
$$b d\equiv 1\quad (\mathrm{mod}\ p - 1)$$

By definition, there is some $n \in \mathbb{N}_{0}$ such that
$$b d = (p - 1)n + 1.$$

Then,
$$5d = 28n + 1,$$
$$d = \frac{28n + 1}{5}\in [1,28]\subset \mathbb{N}.$$

We try $n = 0,1,2,3,\ldots$ etc. For $n = 3$, one gets $d = b^{- 1} = 5^{- 1} = 17$.

---

## Quiz 6: Complex Numbers and Finite Groups — Answer Key

**Source:** quiz06_ans.pdf (Computer Algebra)

### Worked Example/Proof — Solutions

**1.** For $z_{1} = 1 + i$, $z_{2} = 2 - 3i$:

(a) (0.5 points) $z_{1} + z_{2} = 3 - 2i$, $z_{1} - z_{2} = -1 + 4i$.

(b) (0.5 points) $z_{1}z_{2} = 5 - i$.

(c) (0.5 points) $\overline{z}_{1}\overline{z}_{2} = 5 + i$.

(d) (0.5 points) $|z_{1}|\cdot |z_{2}| = \sqrt{2}\sqrt{13} = \sqrt{26}$.

(e) (1 point) $\frac{z_{1}}{z_{2}} = \frac{z_{1}\overline{z}_{2}}{|z_{2}|^{2}} = \frac{-1 + 5i}{13}$.

**2.** For $z_{1} = i$, $z_{2} = 3 + 2i$, $z_{3} = -5 - i$:

(a) (0.5 points) (Figure is trivial: draw the corresponding vectors)
$$z_{1}\simeq (0,1),\qquad z_{2}\simeq (3,2),\qquad z_{3}\simeq (-5, - 1).$$

(b) (1 point) (Figure is trivial: draw the corresponding vector)
$$z_{1} + z_{2} + z_{3} = -2 + 2i\simeq (-2,2).$$

**3.** For $z_{1} = \frac{1}{2} e^{\frac{\pi}{4} i}$, $z_{2} = 3e^{\frac{3\pi}{4} i}$:

(a) (0.5 points)
$$w = z_{1}z_{2} = \frac{3}{2} e^{i\pi} = -\frac{3}{2}.$$

(b) (1 point) (The figure is straightforward: draw a vector of length $1 / 2$ at an angle of $\pi /4$ for $z_{1}$; similarly for $z_{2}$ and $w$.)

**4.** For $z = 2e^{\frac{\pi}{3} i}$:

(a) (1 point)
$$z = 2\left(\cos \frac{\pi}{3} +i\sin \frac{\pi}{3}\right) = 1 + \sqrt{3} i.$$

(b) (1 point)
$$z^{3} = 8(\cos \pi +i\sin \pi) = 8e^{i\pi} = -8.$$

(c) (2 points)
$$(\sqrt{z})_{1} = \sqrt{2} e^{i\pi /6},\qquad (\sqrt{z})_{2} = \sqrt{2} e^{i\pi /6} = \sqrt{2} e^{\left(\frac{i\pi}{6} -2\pi\right)i} = \sqrt{2} e^{-i5\pi /6}.$$

Equivalently, by de Moivre's formula,
$$(\sqrt{z})_{1} = \frac{\sqrt{3}}{\sqrt{2}} +\frac{i}{\sqrt{2}},\qquad (\sqrt{z})_{2} = -\frac{\sqrt{3}}{\sqrt{2}} -\frac{i}{\sqrt{2}}.$$

**5.** Let
$$\omega_{+} = \frac{-1 + \sqrt{3}i}{2},\qquad \omega_{-} = \frac{-1 - \sqrt{3}i}{2}.$$

(a) (2 points) The multiplication table is

> **[Note: The PDF text layer contains a garbled table string `<table>*1ω+ω-11ω+ω-ω+ω+ω-1ω-ω-1ω+</table>`. The table below is reconstructed from the algebraic context (cyclic group of order 3 with $\omega_+^2=\omega_-$, $\omega_-^2=\omega_+$, $\omega_+\omega_-=1$). Please verify against the original PDF.]**

| $*$ | $1$ | $\omega_{+}$ | $\omega_{-}$ |
|---|---|---|---|
| $1$ | $1$ | $\omega_{+}$ | $\omega_{-}$ |
| $\omega_{+}$ | $\omega_{+}$ | $\omega_{-}$ | $1$ |
| $\omega_{-}$ | $\omega_{-}$ | $1$ | $\omega_{+}$ |

Thus, $\mathbb{C}_{3}$ is closed under multiplication.

(b) (1 point)
$$\mathbb{C}_{3}^{*}\cong A = (\mathbb{Z}_{3}, + ) = \{[0]_{3},[1]_{3},[2]_{3}\}.$$

Brute-force solution: construct the addition table modulo 3 and compare it with the multiplication table (see above) of $\mathbb{C}_{3}^{*}$. It can be seen that the two tables have the same structure. In fact, the tables coincide under the correspondence
$$1\mapsto [0]_{3},\qquad \omega_{+}\mapsto [1]_{3},\qquad \omega_{-}\mapsto [2]_{3}.$$

Thus, this correspondence establishes an isomorphism (equivalence) between the two groups.

Take
$$\omega_{+}\mapsto [1]_{3}.$$

Then
$$\omega_{+}^{2} = \omega_{+}*\omega_{+} = \omega_{-}\quad \mapsto \quad [1]_{3} + [1]_{3} = [2]_{3},$$
$$\omega_{+}^{3} = \omega_{+}*\omega_{+}*\omega_{+} = 1\quad \mapsto \quad [1]_{3} + [1]_{3} + [1]_{3} = [0]_{3},$$

and so on. In this way, the entire addition table modulo 3 can be obtained from the multiplication table of $\mathbb{C}_{3}$. Thus, the two tables have the same structure, which demonstrates that the groups are isomorphic (equivalent).

(c) (1 point) The generators are
$$\mathrm{Gen}(\mathbb{C}_{3}^{*}) = \{\omega_{+},\omega_{-}\},$$
$$\mathrm{Gen}(\mathbb{Z}_{3}^{+}) = \{[1]_{3},[2]_{3}\}.$$

(It is sufficient to specify at least one generator for each set.)

---

## Quiz 7: Two Representations of Polynomials — Answer Key

**Source:** quiz07_ans.pdf (Computer Algebra)

### Worked Example/Proof — Solutions

**1.** For $\omega_{8} = \frac{1 + i}{\sqrt{2}} = e^{\frac{2\pi i}{8}} = e^{\frac{\pi i}{4}}$:

(a) (0.5 points) $\boxed{\omega_{8}^{4} = -1}$ by $\omega_{n}^{n / 2} = -1$.

(b) (0.5 points) $\boxed{\omega_{8}^{8} = 1}$ by $\omega_{n}^{n} = 1$.

(c) (1 point)
$$\omega_{8}^{-5} = \omega_{8}^{-4}\omega_{8}^{-1} = (\omega_{8}^{4})^{-1}\omega_{8}^{-1} = (-1)^{-1}\cdot \overline{\omega_{8}} = (-1)\cdot \frac{1 - i}{\sqrt{2}} = \frac{-1 + i}{\sqrt{2}} = -\overline{\omega_{8}}$$

(d) (1 point)
$$\omega_{16}^{4} = (\omega_{16}^{2})^{2} = (\omega_{8})^{2} = \left(e^{\frac{\pi i}{4}}\right)^{2} = e^{\frac{\pi i}{2}} = \boxed{i}$$

(Here we can also use $(\omega_{8})^{2} = \omega_{4} = i$, or just find $\omega_{8}^{2}$ by direct calculations.)

**2. (2 points) Evaluate $p(x) = x^4 - 3x^3 + x^2 - 2x - 1$ at $x = \omega_{4}$**

$$\begin{array}{r l} p(\omega_{4}) &= \omega_{4}^{4} - 3\omega_{4}^{3} + \omega_{4}^{2} - 2\omega_{4} - 1\\ &= 1 - 3\omega_{4}^{2}\omega_{4} + \omega_{4}^{2} - 2\omega_{4} - 1 = 1 - 3(-1)\omega_{4} + (-1) - 2\omega_{4} - 1\\ &= \omega_{4} - 1 = \sqrt{(\omega_{4}^{2}) - 1} = \sqrt{-1} -1 = \boxed{i - 1}. \end{array}$$

Actually, $\omega_{2}$ is not needed here. One can use $\omega_{4}^{2} = \omega_{2}$ though.

**3.** Consider $f(x) = 1 - x$, $g(x) = 2 + x$.

(a) (1 point) At the points $x_{0} = -2$ and $x_{1} = 0$, we obtain
$$f(-2) = 1 - (-2) = 3,\qquad f(0) = 1,$$
$$g(-2) = 2 + (-2) = 0,\qquad g(0) = 2.$$

Therefore, the value representations are
$$\boxed{f(x):\{(-2,3),(0,1)\}},\qquad g(x):\{(-2,0),(0,2)\}.$$

(b) (2 points) Since the product $h(x) = f(x)g(x)$ is a quadratic polynomial, three distinct evaluation points are sufficient. We add $x_{2} = 1$. For $f$ and $g$, we have
$$f(1) = 1 - 1 = 0,\qquad g(1) = 2 + 1 = 3.$$

Thus, the extended value representations are
$$f(x):\{(-2,3),(0,1),(1,0)\},$$
and
$$g(x):\{(-2,0),(0,2),(1,3)\}.$$

Multiplying the corresponding values pointwise gives
$$h(x):\{(-2,3,0),(0,1,2),(1,0,3)\} = \{(-2,0),(0,2),(1,0)\}.$$

Thus, the value representation of the product is
$$\boxed{h(x):\{(-2,0),(0,2),(1,0)\}}.$$

For clarity, all the results of the computations are summarized in the following table.

> **[Note: The PDF text layer says "summarized in the following table" but the table itself is not present in the extracted text. Verify against original PDF.]**

(c) (3 points) We need to find $c_{0},c_{1}$, and $c_{2}$:
$$h(x) = c_0 + c_1x + c_2x^2.$$

From the value representation
$$h(-2) = 0,\qquad h(0) = 2,\qquad h(1) = 0,$$
we obtain
$$c_0 - 2c_1 + 4c_2 = 0,$$
$$c_0 = 2,$$
$$c_0 + c_1 + c_2 = 0.$$

From $c_{0} = 2$, we have
$$c_1 + c_2 = -2,$$
$$-2c_1 + 4c_2 = -2.$$

Solving these two equations yields
$$c_{1} = -1,\qquad c_{2} = -1.$$

Therefore, the coefficient representation of $h(x)$ is
$$\boxed{(2, - 1, - 1)}\qquad \Leftrightarrow \qquad h(x) = 2 - x - x^2.$$

**4. (3 points) Graphical multiplication**

This is the simplest pointwise multiplication of two functions $f$ and $g$. For each point $x_{i}$, we find approximate values of $f(x_{i})$ and $g(x_{i})$ from the graph. Then we construct a new point $(x_{i}, f(x_{i}) \cdot g(x_{i}))$. Finally, we connect all the points with a smooth curve. The approximate result is shown in the graph below by the red curve.

[Diagram: Figure showing two curves on $x \in [-1.5, 1.5]$, $y \in [-8, 10]$ — a solid curve forming a gentle downward-opening arc, and a dashed curve that dips and rises steeply, with six crosses marked on the $x$-axis at roughly $x = -1.3, -1, -0.5, 0, 1, 1.3$. The product curve (red) is plotted through the pointwise products of the two curves at these evaluation points.]

---

## Quiz 8: FFT / IFFT — Answer Key

**Source:** quiz08_ans(1).pdf (Computer Algebra)

### Worked Example/Proof — Solutions

**1.** Consider $p(x) = a_0+a_1x+a_2x^2+\cdots+a_{n-1}x^{n-1}$.

(a) (0.5 points) $n$ points.

(b) (0.5 points) No. If $n - 1 = 16$, then the polynomial has 17 coefficients. However, the base-2 FFT requires the number of points to be a power of two. So this problem requires some modifications to apply FFT.

(c) (0.5 points) The polynomial $p(x)$ has degree at most $n - 1$, so
$$\deg \big(p(x)^2\big)\leqslant 2(n - 1) = 2n - 2.$$
Therefore, $\boxed{2n - 1}$ distinct points are sufficient.

**2.** Consider $p(x) = 1-2x+3x^2-4x^3+\cdots-8x^7$.

(a) (1 point) Separate the even and odd powers:
$$p(x) = (1 + 3x^{2} + 5x^{4} + 7x^{6}) + (-2x - 4x^{3} - 6x^{5} - 8x^{7}).$$

Hence,
$$p(x) = p_{e}(x^{2}) + xp_{o}(x^{2}),$$
where
$$\boxed{p_{e}(y) = 1 + 3y + 5y^{2} + 7y^{3}}$$
and
$$\boxed{p_{o}(y) = -2 - 4y - 6y^{2} - 8y^{3}}.$$

(b) (1 point) We decompose $p_{e}$ and $p_{o}$ in the same way:
$$p_{e}(x) = p_{e e}(x^{2}) + x p_{e o}(x^{2}),$$
$$p_{o}(x) = p_{o e}(x^{2}) + x p_{o o}(x^{2}).$$

For $p_{e}$:
$$1 + 3x + 5x^{2} + 7x^{3} = (1 + 5x^{2}) + x(3 + 7x^{2}),$$
so
$$\boxed{p_{e e}(y) = 1 + 5y,\qquad p_{e o}(y) = 3 + 7y.}$$

Similarly,
$$-2 - 4x - 6x^{2} - 8x^{3} = (-2 - 6x^{2}) + x(-4 - 8x^{2}),$$
so
$$\boxed{p_{o e}(y) = -2 - 6y,\qquad p_{o o}(y) = -4 - 8y.}$$

(c) (0.5 points) The original polynomial has 8 coefficients. At each step, the polynomial is split into two polynomials of half the size:
$$8\longrightarrow 4\longrightarrow 2\longrightarrow 1.$$
Thus, the binary recursion tree has depth
$$\boxed{\log_{2}8 = 3}.$$

**3. (4 points) Represent $q(x) = 1 - x^{2} + 4x^{3}$ in value form using the FFT**

We have
$$q(x) = 1 - x^{2} + 4x^{3}.$$

To apply the FFT, we first pad the coefficient list to a power-of-two length. Since $q$ has 4 coefficients, no padding is necessary.

Separate the even and odd parts:
$$q(x) = q_{e}(x^{2}) + xq_{o}(x^{2}),$$
where
$$q_{e}(y) = 1 - y,\qquad q_{o}(y) = 4y.$$

The 4th roots of unity are
$$\omega_{4}^{0} = 1,\qquad \omega_{4}^{1} = i,\qquad \omega_{4}^{2} = -1,\qquad \omega_{4}^{3} = -i.$$

We first evaluate $q_{e}$ and $q_{o}$ at the 2nd roots of unity, $1$ and $-1$:

> **[Note: The PDF text layer has a blank gap here where the evaluation table should be. Verify against original PDF.]**

Using the butterfly formulas:
$$q(\omega_{4}^{0}) = q_{e}(1) + \omega_{4}^{0}q_{o}(1) = 0 + 4 = 4,$$
$$q(\omega_{4}^{2}) = q_{e}(1) - \omega_{4}^{0}q_{o}(1) = 0 - 4 = -4,$$
$$q(\omega_{4}^{1}) = q_{e}(-1) + \omega_{4}^{1}q_{o}(-1) = 2 - 4i,$$
$$q(\omega_{4}^{3}) = q_{e}(-1) - \omega_{4}^{1}q_{o}(-1) = 2 + 4i.$$

Therefore, the value representation is
$$\boxed{\left\{\left(1,4\right),\left(i,2 - 4i\right),\left(-1, - 4\right),\left(-i,2 + 4i\right)\right\}}.$$

**4. (4 points) IFFT recovery of coefficients**

We are given
$$y_{0} = -1,\qquad y_{1} = i,\qquad y_{2} = 1,\qquad y_{3} = 2.$$

For the 4-point IFFT,
$$a_{j} = \frac{1}{4}\sum_{k = 0}^{3}y_{k}\omega_{4}^{-jk},\qquad j = 0,1,2,3,$$
where
$$\omega_{4} = i.$$

For $a_{0}$:
$$a_{0} = \frac{1}{4} (y_{0} + y_{1} + y_{2} + y_{3})$$
$$= \frac{1}{4} (-1 + i + 1 + 2)$$
$$= \frac{2 + i}{4}.$$

For $a_{1}$:
$$a_{1} = \frac{1}{4}\left(y_{0} + y_{1}\omega_{4}^{-1} + y_{2}\omega_{4}^{-2} + y_{3}\omega_{4}^{-3}\right)$$
$$= \frac{1}{4}\left(-1 + i(-i) + 1(-1) + 2i\right)$$
$$= \frac{-1 + 2i}{4}.$$

For $a_{2}$:
$$a_{2} = \frac{1}{4}\left(y_{0} + y_{1}\omega_{4}^{-2} + y_{2}\omega_{4}^{-4} + y_{3}\omega_{4}^{-6}\right)$$
$$= \frac{1}{4}\left(-1 - i + 1 - 2\right)$$
$$= \frac{-2 - i}{4}.$$

Therefore,
$$\boxed{\left(a_{0},a_{1},a_{2}\right) = \left(\frac{2 + i}{4},\frac{-1 + 2i}{4},\frac{-2 - i}{4}\right)}.$$

**5. (2 extra points) Recover $a_{3}$**

For completeness, we can also recover $a_{3}$:
$$a_{3} = \frac{1}{4}\left(y_{0} + y_{1}\omega_{4}^{-3} + y_{2}\omega_{4}^{-6} + y_{3}\omega_{4}^{-9}\right)$$
$$= \frac{1}{4}\left(-1 + i(i) + 1(-1) + 2(-i)\right)$$
$$= \frac{1}{4}\left(-3 - 2i\right).$$

$$a_3 = -\frac{3 + 2i}{4}.$$

The polynomial in coefficient representation is
$$\boxed{p(x) = \frac{2 + i}{4} +\frac{-1 + 2i}{4} x + \frac{-2 - i}{4} x^2 -\frac{3 + 2i}{4} x^3}.$$
