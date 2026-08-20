# Computer Algebra – Compiled Lecture Notes (Definitions, Theorems, Formulas, Examples)

## Lecture 1: Introduction to Computer Algebra

**Definition:**
Content Text: Computer Algebra emphasizes symbolic computation rather than numerical methods. Before attempting to obtain a numerical answer, one should first try to simplify or transform the problem by manipulating the quantities involved as symbols, according to a prescribed set of rules.

**Definition:**
Content Text: The solution sets of systems of polynomial equations define algebraic varieties, which in simple cases can be visualized as collections of separate points, curves, or surfaces.
$$\text{Var}(x,y,z) = \{(x_1,y_1,z_1), (x_2,y_2,z_2), \dots\}$$

**Core Formula (Basic arithmetic rules used for symbolic rearrangement):**
Content Text:
$$(1)\ a+b = b+a$$
$$(2)\ a = 1\cdot a = a \cdot 1$$
$$(3)\ a\cdot(b+c) = a\cdot b + a\cdot c$$
$$(4)\ (b+c)\cdot a = b\cdot a + c\cdot a$$

**Worked Example (Symbolic mindset vs numerical mindset):**
Content Text:
$$8\cdot 3 + 4 + 8$$
Numerical approach: $8\cdot 3 + 12 = 24+12 = 36$
Symbolic approach:
$$8\cdot3+4+8 = 8\cdot3+8+4 = 8\cdot3+8\cdot1+4 = 8\cdot(3+1)+4 = 8\cdot4+1\cdot4 = (8+1)\cdot4$$

**Worked Example (rule-based rearrangement):**
Content Text:
$$a\cdot b + c + a = a\cdot b + (c+a\cdot 1) = a\cdot b + a\cdot 1 + c = a\cdot(b+1)+c$$

**Definition (Algebra structures hierarchy):**
Content Text: [Diagram: Hierarchy diagram showing Algebra branching into Groups, Fields, Rings, Polynomials, and other structures]

**Definition (Algebraic varieties from linear/nonlinear systems):**
Content Text:
- Linear equation $ax+by+c=0$: solution set is a line.
- $ax+by+cz+d=0$: solution set is a plane.
- $ax^2+by=c$: solution set is a parabola-type curve, $y = \tilde{a}x^2+\tilde{c}$.
- $ax^2+by^3+cz^2+d=0$: solution set is a surface.
[Diagram: Various graphs showing lines, planes, parabolas, and surfaces representing solution sets]

**Theorem/Property (Local linear approximation of nonlinear systems):**
Content Text: It is not always a good idea to linearize (approximate) nonlinear equations, especially near a singularity. Around a regular point $A$, one can use the approximation $\tilde{a}x+\tilde{b}y+\tilde{c}z+\tilde{d}=0$.
[Diagram: Surface with a singularity point and a smooth region being approximated by a plane]

**Worked Example (System of two polynomial equations — solving by substitution):**
Content Text: Solve:
$$x+y=1,\qquad x+y^2=5$$
$$F_1 = x+y-1=0,\qquad F_2 = x+y^2-5=0$$
From $y=1-x$:
$$x+(1-x)^2-5=0 \implies x^2-9x-4=0$$
$$x_{1,2} = \frac{9\pm\sqrt{81+16}}{2} = \frac{9\pm\sqrt{97}}{2} \approx 9.5,\ -0.5$$
$$\text{Var}(x,y) = \{(9.5,-8.5), (-0.5, 1.5)\}$$

**Definition (Course Structure — Steps):**
Content Text:
- Step 1: Formulate a problem (e.g., find exact solutions of a system of polynomials; find solutions of a linear system; find a way to multiply numbers fast).
- Step 2: Study theory and develop an algorithm (e.g., resultants for polynomials, Gröbner bases, Fast Fourier Transform).
- Step 3: Write a program using symbolic computation software (e.g., Maxima).
- Step 3′: Analyze the results.
[Diagram: Cycle diagram — Problem → Algorithm → Software → back to Problem]

**Definition (Signed integer representation, naive sign-bit approach):**
Content Text: 1st bit used for sign: $1^{st}=1 \Rightarrow$ "−"; $1^{st}=0 \Rightarrow$ "+". In 3 bits we can store $-3,-2,-1,0,1,2,3$ (with two representations of zero — noted as a "bad idea").

**Core Formula (General division algorithm):**
Content Text:
$$a \div b \implies a = b\cdot q + r$$
where $a$ = dividend, $b$ = divisor, $q$ = quotient, $r$ = remainder.
Python: `q = a // b`, `r = a % b`.

**Worked Example (Decimal to binary conversion — integer part):**
Content Text:
$$21_{10} = a_0\cdot2^0+a_1\cdot2^1+a_2\cdot2^2+a_3\cdot2^3+a_4\cdot2^4+a_5\cdot2^5+\dots$$
$$21 = 1+4+16 \implies a_0=1,a_1=0,a_2=1,a_3=0,a_4=1,a_5\dots=0$$
$$21_{10} = 10101_2$$

**Worked Example (Repeated division method):**
Content Text:
$$21\div2 \implies 21=2\cdot10+1$$
$$10\div2 \implies 10=2\cdot5+0$$
$$5\div2 \implies 5=2\cdot2+1$$
$$2\div2 \implies 2=2\cdot1+0$$
$$1\div2 \implies 1=2\cdot0+1$$
Reading remainders bottom-to-top: $21_{10}=10101_2$

**Worked Example:**
Content Text: $33_{10} \Rightarrow ?_2$
$$33\div2=16 r1,\ 16\div2=8 r0,\ 8\div2=4 r0,\ 4\div2=2 r0,\ 2\div2=1 r0,\ 1\div2=0 r1$$
$$33_{10}=100001_2$$

**Worked Example:**
Content Text: $17_{10}\Rightarrow?_2$
$$17\div2=8 r1,\ 8\div2=4 r0,\ 4\div2=2 r0,\ 2\div2=1 r0,\ 1\div2=0 r1$$
$$17_{10}=10001_2$$

**Worked Example (Decimal to binary — fractional part):**
Content Text: $0.123_{10}\to x_2$ (illustration with decimal expansion of fraction using place values, e.g. $0.1\cdot10^{-1}+2\cdot10^{-2}+3\cdot10^{-3}$).
Also: $0.10110_2 \Rightarrow 1\cdot2^{-1}+0\cdot2^{-2}+1\cdot2^{-3}+1\cdot2^{-4}+0\cdot2^{-5} = \frac{1}{2}+\frac{1}{8}+\frac{1}{16} = \frac{11}{16} \approx 0.6875_{10}$

---

## Lecture 2: Computer Representation of Integers and Floating-Point Numbers

**Definition:**
Content Text: The IEEE 754 normalized representation of floating-point numbers stores the sign, exponent, and fraction (mantissa) explicitly. Standard floating-point numbers are generally unsuitable for exact computations because rounding errors accumulate.

**Theorem/Property:**
Content Text: Multiplication and division by 2 in binary correspond to left/right bit shifts of an integer. For floating-point numbers, the same effect is achieved by adjusting the exponent (shifting the binary point). Programming languages provide bit-shift operators `<<` and `>>`.

**Definition:**
Content Text: The two most common floating-point formats are single precision (`float`, 32 bits) and double precision (`double`, 64 bits).

**Worked Example (Binary to decimal conversion):**
Content Text:
$$1011_2 = 1\cdot2^3+0\cdot2^2+1\cdot2^1+1\cdot2^0 = 8+0+2+1 = 11_{10}$$

**Worked Example (Decimal to binary — integer, using division):**
Content Text:
$$26\div2=13 r0,\ 13\div2=6 r1,\ 6\div2=3 r0,\ 3\div2=1 r1,\ 1\div2=0 r1$$
$$26_{10}=11010_2$$

**Worked Example:**
Content Text:
$$205\div2=102 r1,\ 102\div2=51 r0,\ 51\div2=25 r1,\ 25\div2=12 r1,\ 12\div2=6 r0,\ 6\div2=3 r0,\ 3\div2=1 r1,\ 1\div2=0 r1$$
$$205_{10}=11001101_2$$

**Worked Example (Binary fraction to decimal):**
Content Text:
$$0.1011_2 = 1\cdot2^{-1}+0\cdot2^{-2}+1\cdot2^{-3}+1\cdot2^{-4} = \frac12+0+\frac18+\frac{1}{16} = \frac{11}{16} \approx 0.6875_{10}$$

**Worked Example (Decimal fraction to binary via multiply-by-2 method):**
Content Text: $0.6875_{10}\Rightarrow x_2$
$$0.6875\times2=1.375 \to 1$$
$$0.375\times2=0.75 \to 0$$
$$0.75\times2=1.5 \to 1$$
$$0.5\times2=1.0 \to 1$$
$$0.6875_{10}=0.1011_2$$

**Core Formula (Multiplication/division by 2, shifting):**
Content Text:
$$101_2\times2 = 1010_2 \text{ (shift left)}$$
$$101_2\div2 = 0101_2 \text{ (shift right)}$$

**Worked Example (Decimal number with integer and fractional parts to binary):**
Content Text: $21.09375_{10}\Rightarrow x_2$
Integer part: $21_{10}=10101_2$
Fractional part:
$$0.09375\times2=0.1875\to0$$
$$0.1875\times2=0.375\to0$$
$$0.375\times2=0.75\to0$$
$$0.75\times2=1.5\to1$$
$$0.5\times2=1.0\to1$$
$$0.09375_{10}\approx0.00011_2$$
Check: $0\cdot2^{-1}+0\cdot2^{-2}+0\cdot2^{-3}+1\cdot2^{-4}+1\cdot2^{-5} = \frac{1}{16}+\frac{1}{32} = \frac{3}{32} \approx 0.09375$

**Worked Example:**
Content Text: $0.1_{10} = 0.(0011)_2$ (repeating binary fraction — periodic).

**Theorem/Property (Finite memory truncation error):**
Content Text: With finite bits (e.g., 8 bits), $0.1_{10}$ cannot be represented exactly in binary; truncating causes $0.09375 \neq 0.1$. With 16 bits, the approximation improves: $\approx 0.0997924805 \approx 0.1$.

**Worked Example (Rounding error in addition):**
Content Text:
$$0.1_{10}+0.2_{10}=0.3_{10} \text{ (exact decimal)}$$
$$(0.00011)_2 + (0.0011\ldots)_2 = 0.3000\ldots04_{10} \text{ (binary rounding error)}$$

**Core Formula (IEEE 754 Standard):**
Content Text:
$$(-1)^s (1.f)_2 \cdot 2^e$$
where $s$ = sign, $f$ = fraction (mantissa), $e$ = exponent.

**Worked Example:**
Content Text: For decimal numbers (illustrative, not IEEE754-compliant since base 10):
$$-123.456 = (-1)^1\cdot(1.23456)_{10}\cdot10^2 \Rightarrow (s,f,e)=(1,23456,2)$$
$$0.00567 = (-1)^0\cdot(5.670\ldots)_{10}\cdot10^{-3} \Rightarrow (s,f,e)=(0,5.670,-3)$$

**Worked Example (Full IEEE754 conversion):**
Content Text: $21.09375_{10} = 10101.00011_2$
$$(-1)^0(10101.00011)_2\cdot2^0 = (-1)^0(1.010100011)_2\cdot2^4$$
$$(s,f,e) = (0, 010100011, 4)$$

**Worked Example:**
Content Text: $-101.00110011$
$$(-1)^1(1.0100110011)_2\cdot2^2$$
$$(s,f,e) = (1, 0100110011, 2)$$

**Core Formula (Float/double bit layout):**
Content Text:

| | s (sign) | e (exponent) | f (fraction) |
|---|---|---|---|
| float | 1 bit | 8 bits | 23 bits |
| double | 1 bit | 11 bits | 52 bits |

For float: exponent range is $2^8-1=255$ possible values, interpreted as $-128\ldots127$, giving range $2^{-128}\ldots2^{127}$.
[Diagram: Bit layout of a float showing sign bit, 8 exponent bits, 23 fraction bits]

---

## Lecture 3: Signed Integers, Exact Arithmetic, GCD

**Theorem/Property (Zero in IEEE 754):**
Content Text: There is no triple $(s,f,e)$ that yields the value $0$ via $(-1)^s(1.f)_2 2^e$, since $1.f \neq 0$. IEEE 754 reserves the bit patterns with minimum exponent (e.g., $e=-128$ for 8-bit exponent) to represent positive zero $(+0)$ and negative zero $(-0)$ as special cases.
$$(-1)^0(1.0)_2 2^{-127} \to \text{"positive 0"}$$
$$(-1)^1(1.0)_2 2^{-127} \to \text{"negative 0"}$$

**Definition (Two's complement representation):**
Content Text: Negative integers are stored using two's complement notation, allowing signed integers to occupy the range:
$$-2^{n-1} \ldots 2^{n-1}-1$$
The most significant bit indicates sign (0 = nonnegative, 1 = negative).

**Core Formula (Two-step transformation to negate a number):**
Content Text:
1. Invert (flip) all bits ($1\to0$, $0\to1$).
2. Add binary $1$.
The result is then converted to decimal and assigned a negative sign.

**Worked Example:**
Content Text: Represent $-2_{10}$ using 2 bits, from $10_2$ (unsigned interpretation of 2):
$$10 \xrightarrow{\text{flip}} 01,\quad 01+01 = 10_2 = 2_{10} \Rightarrow -2_{10}$$

**Worked Example (n=4 bits, converting two patterns using the 2-step algorithm):**
Content Text:
(a) $1000_2$: flip $\to 0111$, $+0001 \to 1000_2=8_{10} \Rightarrow -8_{10}$ (minimum representable value)
(b) $1111_2$: flip $\to 0000$, $+0001 \to 0001_2=1_{10} \Rightarrow -1_{10}$

**Theorem/Property (n-bit signed integer range):**
Content Text: For $n$ bits we can represent numbers in the range:
$$-2^{n-1} \ldots 2^{n-1}-1$$

**Worked Example (Bits needed for a given negative number):**
Content Text: To represent $-200_{10}$: since $2^7=128$ (not enough) and $2^8=256$ (enough), we need $-2^8=-2^{n-1}\Rightarrow n=9$. So 9 bits are required.

**Definition (Exact fraction representation):**
Content Text: A fraction $\frac{p}{q}$ is stored as a pair $(p,q)$, with $p$ the numerator, $q$ the denominator, ideally in reduced form with $\gcd(p,q)=1$.

**Core Formula (Fraction arithmetic as pairs):**
Content Text:
$$\frac{p_1}{q_1}\pm\frac{p_2}{q_2} \Rightarrow (p_1q_2\pm q_1p_2,\ q_1q_2)$$
$$\frac{p_1}{q_1}\cdot\frac{p_2}{q_2} = \frac{p_1p_2}{q_1q_2} \Rightarrow (p_1p_2,\ q_1q_2)$$

**Worked Example:**
Content Text:
$$\frac46+\frac{2}{12} \Rightarrow (4,6)+(2,12) = (4\cdot12+6\cdot2,\ 6\cdot12) = (60,72)$$
Simplify using GCD: $(60,72)=(12\cdot5,12\cdot6)=(5,6)$, i.e. $\frac{5}{6}$.

**Definition (Reduced fraction):**
Content Text: A fraction $\frac{p}{q}$ is represented as the pair $\left(\frac{p}{g},\frac{q}{g}\right)$, where $g=\gcd(p,q)$. Equivalently, fraction $\frac{a}{b}$ is defined as $(a,b)$ such that $\gcd(a,b)=1$.

**Worked Example:**
Content Text: $\frac{6}{12}$: $g=\gcd(6,12)=6$, so $\left(\frac{6}{6},\frac{12}{6}\right)=(1,2)$.

**Theorem/Property (Euclid's algorithm to find GCD):**
Content Text:
$$\gcd(a,b) = \begin{cases} a & \text{if } b=0 \\ \gcd(b,\ a \bmod b) & \text{if } b\neq0\end{cases}$$

**Worked Example:**
Content Text: $\gcd(126,84)$:
$$126=84\cdot1+42 \Rightarrow \gcd(84,42)$$
$$84=42\cdot2+0 \Rightarrow \gcd(42,0)=42$$

**Worked Example:**
Content Text: $\gcd(125,100)$:
$$125=100\cdot1+25 \Rightarrow \gcd(100,25)$$
$$100=25\cdot4+0 \Rightarrow \gcd(25,0)=25$$
Reduced fraction: $\left(\frac{125}{25},\frac{100}{25}\right)=(5,4)$

**Theorem/Property (GCD is the last nonzero remainder — proof sketch):**
Content Text: Given
$$a=bq+r,\quad b=rq_1+r_1,\quad r=r_1q_2+r_2,\quad r_1=r_2q_3+r_3,\ldots$$
continuing until some remainder is zero, one shows by substitution that if $r_2=0$: $a=r_1\tilde{q}$, so $r_1$ divides $a$ (and similarly $b$), and $r_1$ is the GCD of $a$ and $b$. In general, the GCD equals the last nonzero remainder in the sequence of divisions.

**Worked Example/Proof:**
Content Text: $\gcd(144,60)$:
$$144=60\cdot2+24$$
$$60=24\cdot2+12$$
$$24=12\cdot2+0$$
Last nonzero remainder is $12=\gcd(144,60)$. Verification: $\left(\frac{144}{12},\frac{60}{12}\right)=(12,5)$, and $\gcd(12,5)=1$. ✓

---

## Lecture 4: Irrational Numbers and Arbitrary-Precision Arithmetic

**Definition:**
Content Text: Irrational numbers cannot be represented exactly as fractions $\frac{p}{q}$ ($p\in\mathbb{Z}$, $q\in\mathbb{N}$), so computer algebra systems (CAS) treat them as symbolic objects and simplify using rewrite rules rather than evaluating numerically.

**Theorem/Property:**
Content Text: Any rational number $\frac{p}{q}$ has either a finite decimal representation or an infinite periodic one. Irrational numbers such as $\sqrt2,\sqrt3,\sqrt5,\pi,e$ have infinite, non-periodic decimal expansions.

**Worked Example:**
Content Text: Finite: $0.5$, $0.012345$. Periodic: $\frac13=0.333\ldots=0.(3)$; $\frac{9}{11}=0.818181\ldots=0.(81)$.

**Core Formula (Rewrite rule for simplifying radicals):**
Content Text:
$$\sqrt{k^2\cdot a} = k\cdot\sqrt{a}$$

**Worked Example:**
Content Text:
$$\sqrt8 = \sqrt{2^2\cdot2} = 2\sqrt2$$

**Definition (Floating-point "contagion"):**
Content Text: CAS preserve irrational numbers symbolically ("as is") unless a floating-point value appears in the expression, in which case the whole expression is evaluated numerically. E.g., in Maxima: `sqrt(2)` → `sqrt(2)`, but `sqrt(2.0)` → `1.41421...`.

**Definition (Arbitrary-Precision Numbers, APN):**
Content Text: Given $n$ bits, the representable integer range is $-2^{n-1}\ldots2^{n-1}-1$. For $n=64$: max $\approx 2^{63}\approx9.2234\times10^{18}$. To perform exact computations with larger integers, represent a number as a list (array) of digits in a fixed base $B$; each element lies in the range $0\ldots B-1$.

**Core Formula (Positional representation with base $B$):**
Content Text:
$$x = d_0\cdot B^0 + d_1\cdot B^1 + d_2\cdot B^2 + \cdots$$

**Worked Example:**
Content Text: $1{,}234{,}567{,}890$ with $B=10^3$:
$$= 890\cdot(10^3)^0+567\cdot(10^3)^1+234\cdot(10^3)^2+1\cdot(10^3)^3$$
List representation: $[890, 567, 234, 1]$

**Theorem/Property (Complexity of arithmetic on APNs):**
Content Text: Addition/subtraction on big integers is $O(n)$; the "schoolbook" multiplication algorithm is $O(n^2)$. Fast multiplication (e.g., via FFT) reduces integer multiplication to polynomial multiplication with complexity $O(n\log n)$.

**Worked Example (Addition of large integers as lists):**
Content Text: $x=1{,}234{,}567$, $y=987{,}654$, base $=10^3$:
$$[x]=[567,234,1],\quad [y]=[654,987,0]$$
$$567+654=1221 \to 221,\ \text{carry }1$$
$$234+987+1=1222 \to 222,\ \text{carry }1$$
$$1+0+1=2 \to 2,\ \text{carry }0$$
$$[x+y]=[221,222,2] \Rightarrow 2{,}222{,}221_{10}$$
Check: $1234567+987654=2222221$.

**Worked Example:**
Content Text: $x=654321$, $y=4567890$, base=1000:
$$[x]=[321,654,0],\quad[y]=[890,567,4]$$
$$321+890=1211\to211,\ \text{carry }1$$
$$654+567+1=1222\to222,\ \text{carry }1$$
$$0+4+1=5\to5$$
$$[x+y]=[211,222,5] = 5{,}222{,}211_{10}$$

**Worked Example (Different base):**
Content Text: $x=3601$, $y=125$, base $=60$:
$$[x]=[1,0,1]_{60}\ (\text{i.e. } 3601=1\cdot1+0\cdot60+1\cdot3600),\quad[y]=[5,2,0]_{60}$$
$$1+5=6,\quad0+2=2,\quad1+0=1$$
$$[x+y]=[6,2,1] \Rightarrow 6+2\cdot60+1\cdot3600=3726$$
Check: $3601+125=3726$. ✓

**Worked Example (Multiplication complexity comparison):**
Content Text: For $x=123$, $y=456$ ($n=3$ digits each): schoolbook multiplication requires $3\times3=9$ multiplications plus 3 additions, giving product $56{,}088$, complexity $O(n^2)$.

**Definition (Prime factorization representation):**
Content Text: By the Fundamental Theorem of Arithmetic, every positive integer has a unique decomposition into prime factors. If factorizations of two integers are known, their product is computed by adding corresponding exponents. Drawback: factorization of large integers is computationally expensive; no polynomial-time factorization algorithm is known.

**Theorem/Property (Prime Number Theorem, informal statement):**
Content Text: If we have $N$ numbers from $1$ to $N$, there are approximately $\ln N$... (asymptotically $N/\ln N$) prime numbers between $1$ and $N$.

**Worked Example:**
Content Text:
$$12=2\cdot2\cdot3=2^2\cdot3$$
$$75=3\cdot5^2$$
$$41=41^1$$
$$121=11^2$$
$$360=2^3\cdot3^2\cdot5^1$$

**Worked Example (Multiplying via prime factorization):**
Content Text: $75=3^1\cdot5^2$ as $[(2,0),(3,1),(5,2)]$; $360=2^3\cdot3^2\cdot5^1$ as $[(2,3),(3,2),(5,1)]$.
$$75\cdot360 = 2^3\cdot3^{1+2}\cdot5^{2+1} = 2^3\cdot3^3\cdot5^3$$

**Worked Example:**
Content Text: $x=25=5^2$, $y=36=2^2\cdot3^2$:
$$25\times36 = 2^2\cdot3^2\cdot5^2 \text{ or } [(2,2),(3,2),(5,2)]$$

---

## Lecture 5: Constructing Expression Trees

**Definition:**
Content Text: In CAS, symbolic expressions are represented as expression trees. Internal nodes represent operators; leaves represent operands (variables, constants, atomic symbols). A unary operator has one operand; a binary operator has two operands.

**Definition (Notations):**
Content Text: Binary operators are usually written in infix notation: $a\circ b$. Unary operators are commonly written in prefix notation, e.g. $-a$ or $\text{not } x$.

**Theorem/Property (Constructing an expression tree):**
Content Text: Identify the operator with lowest precedence; this becomes the root (or root of the subtree). Apply the same procedure recursively to remaining subexpressions. Associativity must be considered when the same operator repeats, e.g. $a-b-c$ is left-associative: $(a-b)-c$, not $a-(b-c)$.

**Worked Example (Expression tree for $a+b\cdot c+d^2$):**
Content Text: In-order DFS traversal of the tree yields $a+b*c+d^{\wedge}2$.
[Diagram: Tree with root "+", left leaf a, right subtree "+" containing "*" (b,c) and "^" (d,2)]

**Definition (Operator arity types):**
Content Text:
1. Binary operator: $a+b$ — 1st operand, operator, 2nd operand.
2. Unary operator: $-x$ — operator, operand.
3. Ternary operator (e.g. C/Java `?:`): `cond ? value1 : value2` — condition, value if true, value if false.

**Definition (Operator precedence):**
Content Text: Priority ordering (low to high): $+,- \prec *,\div \prec \wedge$ (power).

**Worked Example:**
Content Text: $a*b^3*c+d\div e$ — construct expression tree by choosing lowest-priority operator first ($+$), then $*$ and $\div$ on each side, then $\wedge$.
[Diagram: Full binary expression tree for $a*b^3*c+d\div e$]

**Definition (Left- and right-associative operators):**
Content Text:
- Left-associative: for $n\geq2$, $a_1\circ a_2\circ\cdots\circ a_n = (((a_1\circ a_2)\circ a_3)\circ\cdots\circ a_n)$
- Right-associative: for $n\geq2$, $a_1\circ a_2\circ\cdots\circ a_n = a_1\circ(a_2\circ(\cdots\circ(a_{n-1}\circ a_n)\cdots))$

**Worked Example:**
Content Text: Subtraction is left-associative: $1-2-3 = (1-2)-3=-4 \neq 1-(2-3)=2$.
Addition is both left and right associative: $1+2+3=(1+2)+3=1+(2+3)$.
Power is right-associative: $2^{3^2} = 2^{(3^2)}=2^9=512 \neq (2^3)^2=64$.

**Worked Example:**
Content Text: $a^{b^c}-d^e-f^g*k$
Rewriting: $a\wedge(b\wedge c) - d\wedge e - (f\wedge g)*k$. Since $-$ is left-associative: $(a\wedge(b\wedge c)-d\wedge e)-(f\wedge g)*k$.
[Diagram: Resulting binary expression tree]

**Worked Example (custom operators with priority/associativity):**
Content Text: $a\Box b\Box c \Diamond d\circ e\Box f\circ g \Diamond h$, where $\circ$ (right-assoc, lowest priority), $\Box$ (left-assoc, middle priority), $\Diamond$ (right-assoc, highest priority).
Result: $(a\Box b)\Box c \Diamond \left(\left((d\circ e)\Box(f\circ g)\right)\Diamond h\right)$
[Diagram: Full resulting expression tree with root $\Diamond$]

---

## Lecture 6: Traversal and Transformations of Expression Trees

**Definition (Three standard notations):**
Content Text: Prefix ($+ab$), Infix ($a+b$), Postfix ($ab+$). Infix is standard in mathematics; prefix/postfix are common in programming languages. Postfix suits stack-based evaluation; prefix suits operators with more than two operands.

**Definition (DFS traversal orders):**
Content Text: Pre-order, in-order, post-order. Printing nodes during these traversals produces prefix, infix, or postfix notation respectively.

**Worked Example (Multi-operand operator conversions):**
Content Text:
$$(+\ 1\ 2\ 3) \to (+\ (+\ 1\ 2)\ 3) \to 1+2+3$$
$$(1\ 2\ 3\ +) \to ((1\ 2\ +)\ 3\ +) \to 1+2+3$$

**Definition (Substitution transformation):**
Content Text: $S \to S'$, where a given symbol or expression $S$ is replaced by another symbol/expression $S'$.

**Core Formula (Distributive/Expansion transformation):**
Content Text:
$$a*(b+c+d) \to (*\ a\ (+\ b\ c\ d))$$
$$a*(b+c) = a*b+a*c$$

**Worked Example (Lisp prefix notation and trees):**
Content Text:
$$(\div\ (*\ (+\ a\ b)\ (\div\ c\ d))\ (+\ e\ (-\ f\ g)))$$
[Diagram: Full binary tree constructed from the nested Lisp-style prefix expression]

**Definition (Handling unary subtrees for DFS):**
Content Text: To apply in-order DFS uniformly, unary subtrees are converted to binary by adding an empty node (NULL): a single-child node becomes a two-child node with one child NULL.

**Worked Example:**
Content Text: $-1+x$: root "+", left child unary "−1" (converted to "−" with children NULL and 1), right child x.
$f(x)$: root "f", children x and NULL.

**Theorem/Property (In-order DFS algorithm):**
Content Text:
1. Convert all subtrees to binary subtrees by adding NULL if needed.
2. Visit each node applying a function $V$; define $V(\text{NULL})$ to do nothing.
3. Starting from the root: apply DFS to the left node, apply $V$ to the root, apply DFS to the right node.

**Worked Example:**
Content Text: Tree for $(a+b)*(c\div d)+(e+(f-g))$: DFS printout: $a+b*c\div d+e+f-g$ — but subtrees are calculated first: $((a+b)*(c\div d))+(e+(f-g))$.

**Worked Example (parse tree → infix expression):**
Content Text: Parse the tree with in-order DFS and write the expression in infix form:
$$*(÷(a,b), +(c, +(d, *(e,f))))$$
resulting infix expression to be derived by the student. [Diagram: expression tree with root *, left subtree ÷(a,b), right subtree containing nested + and * nodes with c,d,e,f]

**Worked Example (Simplify then verify via DFS):**
Content Text: Tree for $x-1$ simplified to $x+(-1)$:
In-order DFS of original: $x-1$. Check: $x+(-1)=x-1$. ✓

**Worked Example (Lisp internal representation in Maxima):**
Content Text:
```
expr: a+b;
:lisp $expr
> ((MPLUS SIMP) $A $B)
```

**Definition (Substitution example on trees):**
Content Text: Substitution defined as: symbol or expression → expression to substitute, e.g. $a\to c+\sin(d)$. Applying this substitution within a larger tree replaces every occurrence of node $a$ with the subtree for $c+\sin(d)$; this can be represented efficiently as a DAG.

**Worked Example:**
Content Text: Given tree $T = a*b*((a*b)*(a*b))$:
1. Parse: $(a*b)*((a*b)*(a*b))$
2. Substitute $a*b\to w$: subtree $a*b$ replaced by $w$.
3. Resulting expression: $w*(w*w)$
Check: $w*(w*w)\big|_{w=a*b} = (a*b)*((a*b)*(a*b))$ ✓

**Core Formula (Expansion / Distributive rule as a general transformation):**
Content Text:
$$(+\ R_1\ R_2\ R_3\ \ldots\ R_n) = R_1+R_2+R_3+\cdots+R_n$$
Rule for expanding $L*(R_1+R_2+\cdots+R_n) \to L*R_1+L*R_2+\cdots+L*R_n$, assuming $+$ can have any finite number of operands.

**Worked Example (Full expansion and DFS check):**
Content Text: Given $T_1$ with structure $(7*(1+(2+3))-9)+(5*(6+7))$, after transforming binary $+$ into $n$-ary $+$ and applying distribution:
$$\text{DFS}(T_1): (7*(1+(2+3))-9)+(5*(6+7))$$
$$\text{DFS}(T_3): (((7*1)+(7*2)+(7*3))-9)+((5*6)+(5*7))$$
Rule used: $(+\ a\ b\ c)\to a+b+c$. Both traversals checked to be equal (verifying the transformation preserves meaning).

---

## Lecture 7: Transformations of Expression Trees (Continued)

**Core Formula (Distributivity examples across mathematics):**
Content Text:
$$(a_1+\cdots+a_n)*b = a_1*b+\cdots+a_n*b$$
$$(a_1*\cdots*a_n)^p = a_1^p*\cdots*a_n^p$$
$$(A_1\cup\cdots\cup A_n)\cap B = (A_1\cap B)\cup\cdots\cup(A_n\cap B)$$
$$(A_1\cap\cdots\cap A_n)\cup B = (A_1\cup B)\cap\cdots\cap(A_n\cup B)$$

**Theorem/Property (Caveat about false "distributive-looking" identities):**
Content Text:
$$\ln(a_1*\cdots*a_n) \neq \ln(a_1)*\cdots*\ln(a_n)$$
Some identities can be transformed into distributive form via substitution (e.g. $*\to+$), but such transformations are usually handled by simplification rules rather than expansion rules.

**Definition (Rewrite rules):**
Content Text: Simplification may be viewed as repeated application of rewrite rules, each specifying how a particular expression pattern is transformed into an equivalent, simpler one. During bottom-up traversal, rules are applied first to smallest subexpressions, then progressively to larger subtrees, until no further simplification is possible.

**Core Formula (Sign transformation for prefix multi-operand $+$):**
Content Text:
$$(-\ a_1\ (-\ a_2\ (-\ldots))) \to (-\ a_1\ a_2\ \ldots\ a_n) \quad\text{(for right-associativity)}$$
$$-a \Rightarrow 0-a$$

**Worked Example (Expansion as distribution, general form):**
Content Text:
$$(a_1+a_2+\cdots+a_n)*m \to m*a_1+m*a_2+\cdots+m*a_n$$
$$(a_1\cdot a_2\cdots a_n)^p \to a_1^p*a_2^p*\cdots*a_n^p$$

**Worked Example (Distributive expansion of set expression):**
Content Text: Expand $(A_1\cap A_2\cap\cdots\cap A_n)\cup B$ using the distributive law:
$$(A_1\cap A_2\cap\cdots\cap A_n)\cup B = (A_1\cup B)\cap(A_2\cup B)\cap\cdots\cap(A_n\cup B)$$
Prefix: $(\cap\ (\cup\ A_1\ B)\ (\cup\ A_2\ B)\ \ldots\ (\cup\ A_n\ B))$

**Worked Example (Applying log rule with type constraints):**
Content Text:
$$\ln(a_1\cdot a_2\cdots a_n) = \ln a_1+\ln a_2+\cdots+\ln a_n$$
Expressed as tree transformation: apply expansion to $\ln(a_1\cdots a_n)$ treating $\ln$ as op1 and $*$ as op2, then substitute $\cdot\to+$:
$$\text{Substitute}\left(\cdot\to+,\ \text{Expand}(\ln(a_1\cdot\ldots\cdot a_n))\right),\quad \text{where op}_1=\ln,\ \text{op}_2=*$$

**Theorem/Property (Rewrite rules require type annotations):**
Content Text: A rewrite rule cannot be applied to arbitrary symbols; types must be specified.
Notation: `symbol :: type`, e.g. `5 :: integer`, `true :: bool`, `+ :: arithm_operator`, `x :: variable`.
$$\ln(a::\text{variable} \cdot ::\text{arith\_op}\ b::\text{variable}) = \ln(a::\text{variable}) +::\text{arith\_op}\ \ln(b::\text{variable})$$

**Worked Example (Rule with type restriction, GCD reduction):**
Content Text:
$$\frac{p::\text{integer}}{q::\text{integer}} \Rightarrow \frac{p/g}{q/g},\quad g=\gcd(p,q),\ q\neq0$$

**Worked Example (Set-distributive rule with type restriction):**
Content Text: $A\cup(B\cap C) \neq (A\cup B)\cap(A\cup B)$ in general (invalid rule as written); correctly, with $A,B,C::\text{set}$:
$$A::\text{set}\ \cup\ (B::\text{set}\cap C::\text{set}) \Rightarrow (A\cup B)\cap(A\cup C)$$

**Core Formula (Combining like terms):**
Content Text:
$$x^2+x+1+2x+3+5x^2 = 6x^2+3x+4$$

**Worked Example (Substitution and sorting to combine like terms):**
Content Text:
$$(a+b)^2+2(a+c+b)$$
Substitute $a+b\to t$: naively gives $t^2+2(a+c+b)$, but requires sorting so the substitution matches: $(a+b)^2+2(a+b+c) \xrightarrow{a+b\to t} t^2+2(t+c)$

**Worked Example (Rule-based term evaluation for like-term combination):**
Content Text: $1\cdot x^2 + 1\cdot x + 1 + 2\cdot x + 3 + 5\cdot x^2$: group terms by depth/structure (num on left, variable on right for depth 1; num on left, $x^2$ on right for depth 2; plain numbers separately). Numeric terms $1+3$ combine via rule:
$$\text{num}_1*\text{var} + \text{num}_2*\text{var} = \text{evaluate}(\text{num}_1+\text{num}_2)*\text{var}$$

---

## Lecture 8: Getting Started with Programming in Maxima

**Definition:**
Content Text: This lecture covered Maxima built-in functions including `expand`, `factor`, `ratsimp`, `trigsimp`, `subst`, `solve`, `makelist`, `sum`, `prod`, `lhs`, `rhs`, `float`. Predefined constants: `%i`, `%e`, `%pi`. The special symbol `%` refers to the result of the previous computation. The quote operator `'` prevents Maxima from evaluating an expression immediately.

*(No further mathematical formulas, theorems, or worked numerical examples were extracted from this lecture; it was primarily a hands-on programming session.)*

---

## Lecture 9: More Maxima Practice. Modular Arithmetic

**Definition (Modular arithmetic, informal — clock analogy):**
Content Text: Modular arithmetic modulo 12 is exemplified by reading a clock. Generalized to an arbitrary modulus, comparing two integers modulo a given number leads to the concept of congruence.

**Worked Example (Clock arithmetic mod 12):**
Content Text:
$$11+5=16 \equiv 4\!:\!00 \pmod{12}$$
$$7+8=15_{\circledcirc}=3_{\circledcirc}$$
$$11+3=14_{\circledcirc}=2_{\circledcirc}$$
$$11+20=31_{\circledcirc}=19_{\circledcirc}=7_{\circledcirc}\quad(\text{subtract }12\text{ repeatedly})$$
$$11+1000=1011_{\circledcirc}=3_{\circledcirc}\quad(1011-12\cdot84=3)$$
$$9+12345 = 9+12345-12348=6_{\circledcirc}\quad(12\cdot1029=12348)$$

**Definition (Modulus and reduction range):**
Content Text: For the clock, subtract 12 repeatedly until the number lies in $[0,12)$; $12_{\circledcirc}=0_{\circledcirc}$. $12$ is the modulus; calculations "modulo 12".

**Definition (Congruence notation):**
Content Text:
$$15\equiv3\pmod{12}$$
$$14\equiv2\pmod{12}$$
$$1011\equiv3\pmod{12}$$
$$12345\equiv6\pmod{12}$$
We say "15 is congruent to 3 modulo 12" or "15 is 3 modulo 12".

**Worked Example:**
Content Text:
$$15\equiv4\pmod{11}\quad[0,11)$$
$$23\equiv3\pmod5\quad(23-5\cdot4=3)$$
$$1234\equiv2\pmod8$$

---

## Lecture 10: Modular Arithmetic (Continued)

**Definition (Congruence, formal):**
Content Text:
$$a\equiv b\pmod n \iff a+k\cdot n=b \text{ for some integer } k\in\mathbb{Z},\quad \mathbb{Z}=\{0,\pm1,\pm2,\ldots\}$$

**Worked Example:**
Content Text: $23\equiv11\pmod{12}$: $23+(-1)\cdot12=11$ ✓ ($23-12=11$).

**Worked Example (Homework exercises on congruence):**
Content Text:
(a) $143\equiv x\pmod{13}$: $143-11\cdot13=0 \Rightarrow 143\equiv0\pmod{13}$
(b) $12345\equiv x\pmod{11}$: $12345-1122\cdot11=3 \Rightarrow 12345\equiv3\pmod{11}$
(c) $54321\equiv x\pmod7$: result $\equiv1\pmod7$

**Worked Example (Finding modulus n given a congruence):**
Content Text:
(a) $24\equiv0\pmod n$: solutions include $n=8$ ($24-3\cdot8=0$) and $n=2$ ($24-12\cdot2=0$).
(b) $15\equiv1\pmod n$: choose $n$ such that $15-k\cdot n=1$.

**Definition (Congruence via equal remainders):**
Content Text: Numbers $a$ and $b$ are congruent modulo $n$ if they have the same remainder after division by $n$:
$$a=k_1 n+r,\quad b=k_2 n+r\quad (0\leq r<n)$$

**Worked Example:**
Content Text: $16\equiv8\pmod2$: $16\div2=8\ r0$; $8\div2=4\ r0$; same remainder $0$ ⟹ congruent.

**Worked Example:**
Content Text: Is $25\equiv75\pmod8$? $25=3\cdot8+1$, $75=k_2\cdot8+1 \Rightarrow k_2=74/8=9.25$, not an integer ⟹ $25\not\equiv75\pmod8$.

**Worked Example:**
Content Text: $25\equiv75\pmod5$: $25=5\cdot5+0$, $75=15\cdot5+0$, same remainder ⟹ $25\equiv75\pmod5$. ✓

**Worked Example:**
Content Text: $11\equiv5\pmod3$: $11=3\cdot3+2$, $5=1\cdot3+2$ ⟹ congruent.

**Worked Example:**
Content Text: $23\equiv13\pmod7$? $23=3\cdot7+2$, $13=1\cdot7+6$ — different remainders ⟹ $23\not\equiv13\pmod7$.

**Worked Example (Negative number congruence):**
Content Text: $-5\equiv x\pmod7$, $x\in[0,7)$: $-5+1\cdot7=2 \Rightarrow -5\equiv2\pmod7$.
$-1234\equiv x\pmod9$: $-1234+138\cdot9=8 \Rightarrow -1234\equiv8\pmod9$.

**Theorem/Property (Divisibility criterion for congruence):**
Content Text: $a\equiv b\pmod n \iff n\mid(a-b)$.
Derivation: $a=k_1n+r$, $b=k_2n+r \Rightarrow a-b=n(k_1-k_2)$.
Notation: $a\mid b$ means "$a$ divides $b$"; $a\nmid b$ means "$a$ does not divide $b$".

**Worked Example:**
Content Text: $23\equiv13\pmod7$? $23-13=10$; $7\nmid10 \Rightarrow 23\not\equiv13\pmod7$.

**Definition (Equivalence class / residue class):**
Content Text: Given representative $a$ and modulus $n$:
$$[a]_n = \{a+nx \mid x\in\mathbb{Z}\}$$
E.g. $3+2\mathbb{Z} = [3]_2 = \{3+2x\mid x\in\mathbb{Z}\} = \{\ldots,-1,1,3,5,7,\ldots\}$.

**Theorem/Property (Congruence is an equivalence relation):**
Content Text: To show $\equiv_n$ is an equivalence relation, prove three properties:
1. Reflexivity: $a\equiv a\pmod n$ (since $a-a=0=n\cdot0$).
2. Symmetry: $a\equiv b\pmod n \Rightarrow b\equiv a\pmod n$.
3. Transitivity: $a\equiv b\pmod n$ and $b\equiv c\pmod n \Rightarrow a\equiv c\pmod n$.

**Theorem/Property (Well-definedness of modular addition/multiplication):**
Content Text: The sum of two residue classes equals the residue class of the sum, and the product of two residue classes equals the residue class of the product:
$$[a]_n+[b]_n=[a+b]_n$$
$$[a]_n\cdot[b]_n=[a\cdot b]_n$$

**Worked Example/Proof (Well-definedness — sketch):**
Content Text: If $[a]_n=[a']_n$ and $[b]_n=[b']_n$, i.e., $a\equiv a'\pmod n$ and $b\equiv b'\pmod n$, then $a'=a+kn$, $b'=b+\ell n$ for integers $k,\ell$.
For the sum: $(a'+b')-(a+b) = n(k+\ell) \Rightarrow n\mid(a'+b')-(a+b) \Rightarrow a'+b'\equiv a+b\pmod n$.
For the product: $a'b' = (a+kn)(b+\ell n) = ab+n(a\ell+bk+k\ell n) \Rightarrow n\mid(a'b'-ab) \Rightarrow a'b'\equiv ab\pmod n$.
This shows both operations do not depend on the choice of representative.

**Worked Example:**
Content Text: mod 5: $[26]_5+[17]_5 = [1]_5+[2]_5 = [3]_5$, since $[26]_5=\{\ldots,26,21,16,11,6,1,-4,\ldots\}$ and $[17]_5=\{\ldots,17,12,7,2,-3,\ldots\}$.
$$[26]_5\cdot[17]_5=[1]_5\cdot[2]_5=[2]_5$$

**Worked Example:**
Content Text:
(a) $[7]_3+[11]_3 = [1]_3+[2]_3 = [3]_3 = [0]_3$
(b) $[7]_3\cdot[11]_3 = [1]_3\cdot[2]_3 = [2]_3$

**Worked Example:**
Content Text: $[7]_3+[11]_3 = [7+11]_3 = [0]_3$. Verification: $7\bmod3+11\bmod3 \equiv (7+11)\bmod3 \equiv 0\pmod3$.

**Worked Example:**
Content Text: $[5]_3+[125]_3 = [2]_3+[3\cdot40+5]_3 = [2]_3+[5]_3 = [2]_3+[2]_3=[4]_3=[1]_3$
$$[5]_3\cdot[125]_3 = [2]_3\cdot[5]_3 = [2\cdot5]_3=[10]_3=[1]_3$$

## Lecture 11: Multiplicative Inverses Modulo n

**Core Formula (Residue class addition and multiplication):**
Source: CompAlg_-_Lecture_11_-_combined.pdf, Section 1
Content Text:
$$[a]_n+[b]_n=[a+b]_n$$
$$[a]_n\cdot[b]_n=[a\cdot b]_n$$
From the second identity:
$$[a^p]_n=([a]_n)^p,\quad p\in\mathbb{N}$$

**Definition (Residue classes modulo n):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: There are exactly $n$ distinct residue classes modulo $n$, usually represented by the integers $[0]_n,[1]_n,\ldots,[n-1]_n$. The set of residue classes modulo $n$ is denoted
$$\mathbb{Z}_n=\{[0]_n,[1]_n,\ldots,[n-1]_n\}$$
When the modulus is clear, the subscript is often omitted: $[0],[1],\ldots,[n-1]$.

**Definition (Residue classes of polynomials modulo a polynomial):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: For integers, $[a]_n=a+n\mathbb{Z}=\{a+nk\mid k\in\mathbb{Z}\}$, $a=0,1,2,\ldots,n-1$. Analogously for polynomials:
$$[p(x)]_{q(x)}=p(x)+q(x)\mathbb{Z}[x]=\{p(x)+q(x)w(x)\mid w(x)\in\mathbb{Z}[x]\}$$
where $\mathbb{Z}[x]$ denotes the set (ring) of all polynomials of finite degree with integer coefficients; $p(x)$ and $q(x)$ are fixed polynomials in $\mathbb{Z}[x]$, while $w(x)$ ranges over all polynomials in $\mathbb{Z}[x]$.

**Theorem/Property (Isomorphisms of polynomial residue structures):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text:
$$\{p(x)+x\mathbb{Z}[x]\mid p(x)\in\mathbb{Z}[x]\}\cong\mathbb{Z}$$
$$\{p(x)+(x^2+1)\mathbb{Z}[x]\mid p(x)\in\mathbb{Z}[x]\}\cong\mathbb{Z}x+\mathbb{Z}$$
The symbol $\cong$ indicates the corresponding structures are isomorphic (a one-to-one correspondence exists that preserves algebraic operations). The latter structure is isomorphic to the set of complex numbers with integer real and imaginary parts. Polynomial residue classes allow replacing complicated algebraic structures by simpler equivalent ones — a central theme of modern algebra.

**Worked Example (Reducing a polynomial modulo $x^2+1$):**
Source: CompAlg_-_Lecture_11_-_combined.pdf, handwritten notes p.2
Content Text:
$$[(x^5+3x^4-2x+7)]_{x^2+1} = [(x^5+3x^4-2x+7)+(x^2+1)\ell(x)]_{x^2+1}$$
Step-by-step polynomial division reduction (repeatedly subtracting multiples of $(x^2+1)$ to lower the degree):
$$= [3x^4-2x+7-x^3+(x^2+1)\ell_1(x)]_{x^2+1} = \cdots = [-x^3-2x^2-2x+7+(x^2+1)\ell_2(x)]_{x^2+1}$$
$$= [-2x^2-x+7+(x^2+1)\ell_3(x)]_{x^2+1} = [-x+7+2]_{x^2+1} = [9-x]_{x^2+1} = [x^5+3x^4-2x+7]_{x^2+1}$$
Any class will be of the form $[ax+b]_{x^2+1}$, where $a,b\in\mathbb{Z}$.

**Worked Example (Reducing modulo $x$):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text:
$$[x^2+5x-11]_x = [(x^2+5x-11)+x(-x+\lambda_1(x))]_x = [(5x-11)+x\lambda_1(x)]_x = [-11]_x$$

**Theorem/Property (Applications of residue class reduction):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: Any polynomial can be reduced to an integer number:
$$\{[p(x)]_x\} \cong \mathbb{Z}, \qquad \{[p(x)]_{x^2+1}\} \cong \mathbb{Z}x+\mathbb{Z}$$
Applications: Galois theory (checking if higher-order polynomials have solutions); cryptography and computational number theory.

**Theorem/Property (Congruence compatibility with addition/multiplication):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: If $a\equiv b\pmod n$ and $c\equiv d\pmod n$, then:
1. $a+c\equiv b+d\pmod n$
2. $a\cdot c\equiv b\cdot d\pmod n$
Equivalently: $[a]_n+[c]_n=[b]_n+[d]_n$ and $[a]_n[c]_n=[b]_n[d]_n$.

**Worked Example:**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text:
$$[5]_7+[9]_7=[5+9]_7=[14]_7=[0]_7$$
$$[5]_7[9]_7=[5\cdot9]_7=[45]_7=[45-6\cdot7]_7=[3]_7$$
$$[x^2+5x-11]_x=[-11]_x,\qquad [x^5-3x^3+8]_x=[8]_x$$
$$[(x^2+5x-11)(x^5-3x^3+8)]_x=[x^2+5x-11]_x[x^5-3x^3+8]_x=[-11]_x[8]_x=[-11\cdot8]_x=[-88]_x$$

**Core Formula (Power of a residue class):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text:
$$[a^p]_n=[a\cdot a\cdots a]_n=[a]_n\cdot[a]_n\cdots[a]_n=([a]_n)^p,\quad p\in\mathbb{N}$$

**Worked Example:**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text:
$$[7]_5^8=[5{,}764{,}801]_5$$
$$([7]_5)^8=([2]_5)^8=[2^8]_5=[256]_5=[255+1]_5=[1]_5$$

**Worked Example/Proof (Exercise, 1 point):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text:
$$[13]_{10}^6, \qquad [(x^2+5x-11)^3]_x = ([(x^2+5x-11)_x])^3 = ([-11]_x)^3=[-11^3]_x=[-1331]_x$$

**Worked Example/Proof (Exercise, 1.5 points):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: Given $[x^5+3x^4-2x+7]_{x^2+1}=[9-x]_{x^2+1}$, compute $[(x^5+3x^4-2x+7)^2]_{x^2+1}$:
$$=\left([(x^5+3x^4-2x+7)]_{x^2+1}\right)^2=([9-x]_{x^2+1})^2=[(9-x)^2]_{x^2+1}=[(81-18x+x^2)]_{x^2+1}$$
using $(a+b)^2=a^2+2ab+b^2$:
$$=[(81-18x+x^2)+(-1)(x^2+1)]_{x^2+1}=[81-18x+x^2-x^2-1]_{x^2+1}=[80-18x]_{x^2+1}$$

**Definition (Addition and multiplication tables modulo n):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: Using modular arithmetic, addition and multiplication tables mod $n$ were constructed for $n=2,3,4,5$.
[Diagram: Addition table $+_2$ for $\mathbb{Z}_2=\{[0]_2,[1]_2\}$: $[0]+[0]=[0]$, $[0]+[1]=[1]$, $[1]+[1]=[0]$. Multiplication table $*_2$: $[0][0]=[0]$, $[0][1]=[0]$, $[1][1]=[1]$.]
[Diagram: Addition table $+_3$ and multiplication table $*_3$ for $\mathbb{Z}_3=\{[0],[1],[2]\}$.]
[Diagram: Addition table $+_4$ and multiplication table $*_4$ for $\mathbb{Z}_4=\{0,1,2,3\}$; row for $2$ in $*_4$ does not contain $1$.]
[Diagram: Addition table $+_5$ and multiplication table $*_5$ for $\mathbb{Z}_5=\{0,1,2,3,4\}$; every nonzero row of $*_5$ contains $1$ (cyclic group).]

**Theorem/Property (Prime vs composite pattern in multiplication tables):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: In the addition table, every row is a cyclic shift of the first row. In the multiplication table, every nonzero row contains the entry $[1]_n$ whenever $n$ is prime. When $n$ is composite, there is always at least one row in which $[1]_n$ never appears. $n=2,3,5$ are prime; $n=4$ is not prime (row for $2$ lacks $1$).

**Definition (Multiplicative inverse modulo n):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: Every nonzero rational (or real) number $a$ has a multiplicative inverse $a^{-1}=\frac{1}{a}$ since $a\cdot\frac{1}{a}=1$. Analogously, if
$$a\cdot b\equiv1\pmod n$$
then $b$ is called the multiplicative inverse of $a$ modulo $n$, denoted $b=a^{-1}$. We write:
$$a\cdot a^{-1}\equiv1\pmod n,\qquad a^{-1}\cdot a\equiv1\pmod n$$

**Theorem/Property (Existence of inverses and zero divisors):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: From the multiplication tables: when $n$ is prime, every nonzero residue class possesses a multiplicative inverse. When $n$ is composite, at least one nonzero residue class has no inverse. In the composite case, nonzero residue classes may exist whose product is zero:
$$[a]_n\cdot[b]_n=[0]_n$$
Such elements $[a]_n,[b]_n$ are called zero divisors (divisors of zero). Their presence implies not every nonzero element has a multiplicative inverse.

**Worked Example (Multiplicative inverses mod 2, 3, 5, 4):**
Source: CompAlg_-_Lecture_11_-_combined.pdf, handwritten notes p.6
Content Text:
Mod 2: $[1]_2[1]_2=[1]_2 \iff 1\cdot1\equiv1\pmod2$, so $1^{-1}=1$.
Mod 3: $[1]_3[1]_3=[1]_3$, $[2]_3[2]_3=[4]_3=[1]_3 \Rightarrow 1^{-1}\equiv1\pmod3$, $2^{-1}\equiv2\pmod3$.
Mod 5: $[1]_5[1]_5=[1]_5$, $[2]_5[3]_5=[1]_5$, $[3]_5[2]_5=[1]_5$, $[4]_5[4]_5=[1]_5 \Rightarrow 1^{-1}=1,\ 2^{-1}=3,\ 3^{-1}=2,\ 4^{-1}=4$.
Mod 4: $[1]_4[1]_4=[1]_4 \Rightarrow 1^{-1}=1$; $[3]_4[3]_4=[1]_4 \Rightarrow 3^{-1}=3$; $2^{-1}$ does not exist (marked ✗); $[2]_4$ is a divisor of $0$.

**Theorem/Property (Fermat's Little Theorem, first observation):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: By computing examples, for prime $p$:
$$a^{p-1}\equiv1\pmod p \quad\text{whenever } 1\leq a<p$$
This pattern is known as Fermat's Little Theorem. It holds for every prime $p$ and every integer $a$ not divisible by $p$ (proved later).

**Worked Example (Observation leading to FLT):**
Source: CompAlg_-_Lecture_11_-_combined.pdf, handwritten notes p.7
Content Text:
$$2^2\equiv1\pmod3,\qquad2^4\equiv1\pmod5,\qquad2^6\equiv1\pmod7$$
$$2^{p-1}\equiv1\pmod p,\quad p\text{ prime}$$
$$3^6\equiv1\pmod7 \quad(729=104\cdot7+1)$$
$$a^{p-1}\equiv1\pmod p,\quad p\text{ is prime},\quad\gcd(a,p)=1 \quad\text{(FLT)}$$

**Definition (Fermat's Last Theorem — remark, distinguished from FLT):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: Fermat's Last Theorem (FLT — different from Little Theorem): $x^n+y^n=z^n$, $n\in\mathbb{N}$, $x,y,z\in\mathbb{Z}$ (topic of Diophantine equations). The course studies the Little theorem, not the Last theorem.

**Definition (Groups, introduced informally via symmetry):**
Source: CompAlg_-_Lecture_11_-_combined.pdf
Content Text: Groups are fundamental structures closely related to symmetry. A symmetry is a transformation that leaves an object unchanged. Example: symmetries of an equilateral triangle (rotations and reflections/flips) leave it unchanged.
[Diagram: Equilateral triangle $ABC$ under rotations of $120°$, $-120°/240°$, and flips (reflections) about each median, illustrating symmetry transformations.]

---

## Lecture 12: Introduction to Groups

**Theorem/Property (Behavior of $\mathbb{Z}_n$ depending on primality):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: The residue class systems $\mathbb{Z}_n=\{[0]_n,[1]_n,\ldots,[n-1]_n\}$ behave differently depending on whether $n$ is prime or composite. When $n$ is composite, some residue classes may be zero divisors or may have no multiplicative inverses.

**Definition (Coprime integers):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: Two integers $a$ and $b$ are called coprime if
$$\gcd(a,b)=1$$

**Theorem (Coprime criterion for multiplicative inverse):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: A residue class $[a]_n$ has a multiplicative inverse if and only if $a$ and $n$ are coprime. The proof is based on Bézout's identity.
Handwritten restatement: number $m$ has a multiplicative inverse ("coprime") modulo $n$ if and only if $\gcd(n,m)=1$.

**Worked Example (Coprimality checks):**
Source: CompAlg_-_Lecture_12_-_combined.pdf, handwritten notes p.3
Content Text:
$$\gcd(2,7)=1 \Rightarrow \text{coprime}$$
$$\gcd(3,9)=3 \Rightarrow \text{not coprime} \quad(9=3\cdot3)$$
$$\gcd(12,16)=4 \Rightarrow \text{not coprime}$$
Multiplicative inverses modulo 25: $\gcd(2,25)=1$ ✓ (has inverse); $\gcd(5,25)=5$ ✗ (no inverse); numbers checked $1,2,3,4$ (✓), $5,10$ (✗ — no inverse for compound/non-coprime numbers).

**Worked Example (Multiplicative inverses modulo 17):**
Source: CompAlg_-_Lecture_12_-_combined.pdf, handwritten notes p.4
Content Text:
$$\gcd(1,17)=1,\ \gcd(2,17)=1,\ \gcd(3,17)=1,\ \ldots,\ \gcd(16,17)=1$$
For every number from $1$ to $16$ modulo $17$, we have multiplicative inverses.
Importance: for prime numbers (modular), we can construct multiplicative groups.

**Definition (Additive inverse modulo n):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: The additive inverse of a residue class $[a]_n$ is the residue class $[-a]_n$, since
$$[a]_n+[-a]_n=[0]_n$$
Because additive inverses always exist modulo $n$, additive structures are relatively straightforward.
General definition: if $a+b=0$ then $b$ is the additive inverse, denoted $b=-a$. Example: $2+(-2)=0 \Rightarrow$ additive inverse of $2$ is $-2$, for $\mathbb{Z}$.
Modular version: if $[a]_n+[b]_n=[0]_n$ then $b$ is the additive inverse mod $n$, denoted $[-a]_n$.

**Worked Example (Additive inverses):**
Source: CompAlg_-_Lecture_12_-_combined.pdf, handwritten notes p.2
Content Text:
$$[1]_3+[2]_3=[0]_3 \quad(\text{additive inverse of }1\text{ is }[-1]_3=[2]_3)$$
$$[3]_4+[1]_4=[0]_4 \quad([-1]_4=[3]_4,\ [-3]_4=[1]_4)$$
Exercise (1 point), mod 6, find all pairs of additive inverses:
$$[3]_6+[3]_6=[0]_6 \quad([-3]_6=[3]_6)$$
$$[4]_6+[2]_6=[0]_6 \quad([-4]_6=[2]_6,\ [-2]_6=[4]_6)$$
Observation: mod 4 and mod 6 have zero divisors; mod 2, 3, 5 have no zero divisors. 4 and 6 are compound (non-prime); 2, 3, 5 are prime.

**Definition (Group):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: A group is a set equipped with a single binary operation satisfying four axioms: closure, existence of an identity element, associativity, and existence of inverses. Denoted $(S,\circ)$, consisting of the underlying set $S$ together with its binary operation $\circ$. Groups whose operation is written as addition are called additive groups; those whose operation is written as multiplication are called multiplicative groups.

**Theorem/Property (Group axioms, formal):**
Source: CompAlg_-_Lecture_12_-_combined.pdf, handwritten notes p.4
Content Text:
1. Closure: if $G$ is a group, $a,b\in G \Rightarrow a\circ b\in G$.
2. Identity element: there exists a unique element $e$ (identity) for which $e\circ a=a\circ e=a$ for each $a\in G$.
3. Associativity: for any $a,b,c\in G$: $(a\circ b)\circ c=a\circ(b\circ c)$.
4. Inverse: for any $a\in G$ there exists an element $a^{-1}$ such that $a\circ a^{-1}=e$ and $a^{-1}\circ a=e$.

**Worked Example ($(\mathbb{Z},+)$ is an additive group):**
Source: CompAlg_-_Lecture_12_-_combined.pdf, handwritten notes p.5
Content Text:
1. $a,b\in\mathbb{Z} \Rightarrow a+b\in\mathbb{Z}$
2. Identity element is $0$: $0+a=a+0=a$, $e=0$
3. $(a+b)+c=a+(b+c)$, $a,b,c\in\mathbb{Z}$
4. Inverse for $a$ is $(-a)$: $a+(-a)=0$, $(-a)+a=0$

**Worked Example/Proof ($(\mathbb{Z},\cdot)$ is not a group):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text:
1. $a,b\in\mathbb{Z}\Rightarrow a\cdot b\in\mathbb{Z}$
2. Identity is $e=1$: $1\cdot a=a\cdot1=a$, $a\in\mathbb{Z}$
3. $(a\cdot b)\cdot c=a\cdot(b\cdot c)$ ✓
4. Inverse: consider $a=2\in\mathbb{Z}$: $a\cdot a^{-1}=e \Rightarrow 2\cdot2^{-1}=1 \Rightarrow 2^{-1}=\frac12\notin\mathbb{Z}$. Property 4 (inverse) fails $\Rightarrow (\mathbb{Z},\cdot)$ is not a group.

**Worked Example/Proof ($(\mathbb{N},+)$ is not a group):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: $\mathbb{N}=\{1,2,3,4,\ldots\}$. Inverse: $e=0$, $a+(-a)=0$, e.g. $2+(-2)=0$, but $-2\notin\mathbb{N} \Rightarrow$ not a group.

**Worked Example (Symmetries of an equilateral triangle as a group):**
Source: CompAlg_-_Lecture_12_-_combined.pdf, handwritten notes p.6–7
Content Text: An equilateral triangle admits six symmetries (rotations and reflections) forming a group under composition. Transformations: $r$ (rotate $120°$), $r^2$ (rotate $240°$, two rotations), $\ell_1,\ell_2,\ell_3$ (reflections/flips), $e$ (identity, rotate $0°$).
$$T=\{r,r^2,\ell_1,\ell_2,\ell_3,e\}$$
$a\circ b$ means: apply transformation $b$, then $a$.
[Diagram: Triangle $ABC$ transformed by $r$, $r^2$, $\ell_1$, $\ell_2$, $\ell_3$, and $e$, showing resulting vertex positions for each transformation.]
Example compositions:
$$r\circ r=r^2$$
$$\ell_3\circ\ell_1=r^2$$
$$\ell_2\circ\ell_1=r$$
$$\ell_3\circ\ell_2=r\ (\text{verified})$$
This forms the group of transformations of the equilateral triangle.

**Worked Example ($\mathbb{Z}_n^*$ as multiplicative group of nonzero residue classes):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: Removing the zero residue class from $\mathbb{Z}_n$ gives:
$$\mathbb{Z}_n^*=\left(\mathbb{Z}_n\setminus\{[0]_n\},*_n\right)=\left(\{[1]_n,[2]_n,\ldots,[n-1]_n\},*_n\right)$$
where $*_n$ denotes multiplication modulo $n$ (also denoted $(\mathbb{Z}/n\mathbb{Z})^\times$ or $(\mathbb{Z}/n\mathbb{Z})^*$).

**Theorem/Property ($\mathbb{Z}_n^*$ is a group iff n is prime):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: Every nonzero residue class possesses a multiplicative inverse precisely when $n$ is prime. Consequently, $\mathbb{Z}_n^*$ is a multiplicative group if and only if $n$ is prime. Thus $\mathbb{Z}_2,\mathbb{Z}_3,\mathbb{Z}_5,\mathbb{Z}_7,\mathbb{Z}_{11},\ldots$ give rise to multiplicative groups, whereas $\mathbb{Z}_4,\mathbb{Z}_6,\mathbb{Z}_8,\mathbb{Z}_9$, etc., do not.

**Worked Example ($\mathbb{Z}_3^*$ verified as a group):**
Source: CompAlg_-_Lecture_12_-_combined.pdf, handwritten notes p.7–8
Content Text: $\mathbb{Z}_3=\{[0],[1],[2]\}$, $\mathbb{Z}_3^*=\{[1],[2]\}$ with operation $*_3$.
1. Closure under $*_3$: $[1]_3[2]_3=[2]_3$, $[1]_3[1]_3=[1]_3$, $[2]_3[2]_3=[1]_3$
2. Identity: $e=[1]_3$; $[1]_3\cdot e=[1]_3$, $[2]_3\cdot e=[2]_3$
3. Associativity: $([a]_3\cdot[b]_3)\cdot[c]_3=[a]_3\cdot([b]_3\cdot[c]_3)$ (using $[a\cdot b]_n=[a]_n[b]_n$)
4. Inverse: $1^{-1}=1$, $2^{-1}=2\pmod3$

**Worked Example ($\mathbb{Z}_5^*$ verified as a group):**
Source: CompAlg_-_Lecture_12_-_combined.pdf
Content Text: $\mathbb{Z}_5^*=\{[1],[2],[3],[4]\}$. Closure ✓, identity $[1]_5$ trivial, associativity ✓, inverses: $1^{-1}=1$, $2^{-1}=3$, $3^{-1}=2$, $4^{-1}=4$.

---

## Lecture 13: Fermat's Little Theorem

**Definition (Finite group):**
Source: CompAlg_-_Lecture_13_-_combined.pdf
Content Text: If a group has a finite number of elements, it is called a finite group. The groups arising in modular arithmetic are finite. The order (or cardinality) of a group $G$ is the number of its elements, denoted $|G|$. If the group is infinite, $|G|=\infty$; if $|G|<\infty$, $G$ is a finite group.

**Definition (Cyclic group and generator):**
Source: CompAlg_-_Lecture_13_-_combined.pdf
Content Text: A group $G$ is called cyclic if it can be generated by a single element; that is, every element of $G$ can be expressed as an integer power of one particular element. Such an element is called a generator of the group.

**Definition (Order of an element):**
Source: CompAlg_-_Lecture_13_-_combined.pdf
Content Text: In the multiplicative setting, the power $g^n$ of an element $g\in G$ is the product of $n$ copies of $g$. The order of an element $g$, denoted $\mathrm{ord}(g)$, is the smallest positive integer $n$ such that
$$g^n=e$$
where $e$ is the identity element of the group. If no such positive integer exists, $\mathrm{ord}(g)=\infty$.
Alternate handwritten phrasing: number $m$ is called the order of an element $g\in G$ if $g^m=e$, denoted $\mathrm{ord}(g)=m$.

**Core Formula (Power of an element in a group):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.4
Content Text: For $(S,\circ)$, power $n$ of element $g\in S$ is:
$$g^n=\underbrace{g\circ g\circ g\circ\cdots\circ g}_{n\text{ terms}}$$
Related: $[a^p]_n=([a]_n)^p$.

**Theorem (Lagrange's Theorem):**
Source: CompAlg_-_Lecture_13_-_combined.pdf
Content Text: Let $G$ be a finite group. For any element $g\in G$,
$$\mathrm{ord}(g) \mid |G|$$
i.e., the order of every element of a finite group divides the order of the group.

**Theorem/Property (Corollary from Lagrange's Theorem):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.9
Content Text: $\mathrm{ord}(g)$ divides $|G|$ means there exists $m\in\mathbb{N}$ such that $|G|=m\cdot\mathrm{ord}(g)$. Then for $g\in G$:
$$g^{|G|}=g^{m\cdot\mathrm{ord}(g)}=(g^{\mathrm{ord}(g)})^m=e^m=e$$
Corollary:
$$g^{|G|}=e$$

**Theorem (Fermat's Little Theorem, derived from Lagrange):**
Source: CompAlg_-_Lecture_13_-_combined.pdf
Content Text: By applying Lagrange's theorem to the multiplicative group of nonzero residue classes modulo a prime number, we obtain Fermat's Little Theorem (FLT):
$$a^{p-1}\equiv1\pmod p$$
where $p$ is prime and $p\nmid a$ ($p$ does not divide $a$). In terms of residue classes:
$$[a^{p-1}]_p=[a]_p^{p-1}=[1]_p$$
FLT is useful for simplifying very large powers modulo a prime by replacing a large exponent with a much smaller one.
Derivation via group theory: consider $\mathbb{Z}_p^*=(\{[1],\ldots,[p-1]\},*)$, $p$ prime, $|\mathbb{Z}_p^*|=p-1$. For any $g\in\mathbb{Z}_p^*$: $g^{p-1}=e=[1]_p$, i.e. $g^{p-1}\equiv1\pmod p$. By definition $g^{p-1}=p\cdot n+1$ for some $n\in\mathbb{Z}$ (remainder $1$). ($a$ and $p$ are coprime.)

**Worked Example ($\mathbb{Z}_5$ as additive and multiplicative groups):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.1–3
Content Text: $\mathbb{Z}_5=\{[0],[1],[2],[3],[4]\}$, with operations $+,*$.
Additive group $G_{\mathbb{Z}_5}=(\mathbb{Z}_5,+)$: closure $[a]_5+[b]_5=[a+b]_5\in\mathbb{Z}_5$ ✓; identity $e=[0]_5$; associativity (not needed to re-derive); inverse: for $[a]_5$, $[-a]_5$ is the inverse since $[a]_5+[-a]_5=[0]_5$. $G_{\mathbb{Z}_5}$ is an additive group.
Multiplicative group $G_{\mathbb{Z}_5}^*=(\mathbb{Z}_5,*)$: closure $[a]*[b]=[a*b]\in\mathbb{Z}_5$; identity $e=[1]_5$; for $[a]=[0]$: $[0]*b=b*[0]=[0]\neq e$, so $[0]$ has no inverse.

**Worked Example ($\mathbb{Z}_5^*$ multiplicative group, full verification):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.3
Content Text: $\mathbb{Z}_5^*=\{[1],[2],[3],[4]\}$ (also denoted $(\mathbb{Z}/5\mathbb{Z})^*$).
[Diagram: Multiplication table for $\mathbb{Z}_5^*$: rows/columns $1,2,3,4$; e.g. $2*3=1$, $2*4=3$, $3*3=4$, $4*4=1$.]
From the multiplication table, each element has an inverse: $1^{-1}=1$, $2^{-1}=3$, $3^{-1}=2$, $4^{-1}=4$. $\mathbb{Z}_5^*$ is a (multiplicative) group.
Recall Theorem: in $\mathbb{Z}_n^*$ each element has a multiplicative inverse if and only if $n$ is prime.

**Worked Example (Checking which structures are groups):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.3
Content Text: $(\mathbb{Z}_2,+)$ — group ✓; $(\mathbb{Z}_4,+)$ — group ✓; $(\mathbb{Z}_5,*)$ — group ✓; $(\mathbb{Z}_6,*)$ — not a group (6 is not prime); $(\mathbb{Z}_{11},*)$ — group, etc.

**Worked Example (Symmetry group of the triangle as a finite group):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.4
Content Text: $r\Rightarrow$ rotate $120°$, $r^2\Rightarrow$ rotate $240°$, $e\Rightarrow$ rotate $0°$, $\ell_1,\ell_2,\ell_3\Rightarrow$ reflections.
$$S_6=(\{\ell_1,\ell_2,\ell_3,e,r,r^2\},\circ), \quad |S_6|=6 \text{ — finite group}$$
$\mathbb{Q}$ (rational numbers): $|\mathbb{Q}|=\infty$ — infinite group.
Remark: for modular arithmetics, $\mathbb{Z}_n^+=(\mathbb{Z}_n,+)$ has $|\mathbb{Z}_n^+|=n$; $\mathbb{Z}_n^*=(\mathbb{Z}_n,*)$ has $|\mathbb{Z}_n^*|=n-1$ when $n$ is prime — always finite groups.

**Worked Example (Order of elements — additive and multiplicative $\mathbb{Z}_5$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.4–5
Content Text: $\mathbb{Z}_5^+=(\mathbb{Z}_5,+)$. Let $g=[3]_5$:
$$g^4=[3]_5+[3]_5+[3]_5+[3]_5=[3+3+3+3]_5=[12]_5=[2]_5$$
$\mathbb{Z}_5^*$: let $g=[3]_5$:
$$g^4=[3]\cdot[3]\cdot[3]\cdot[2]=[3\cdot3\cdot3\cdot3]_5=[81]_5=[5\cdot16+1]_5=[1]_5$$
Let $g=[2]_5$:
$$g^4=[2]\cdot[2]\cdot[2]\cdot[2]=[16]=[3]\cdots=[1]$$
Let $g=[1]_5 \Rightarrow g^1=[1]$.
Let $g=[4]_5$: $g^x=[1]_5$ for $x=2$ since $[4\cdot4]_5=[16]_5=[1]_5$ (1 point exercise).

**Worked Example (Order of elements in $\mathbb{Z}_7^+$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.5
Content Text: Let $g=[2]_7$: $g^x=[1]_7$ for $x=3$ since $[2\cdot2\cdot2]_7=[8]_7=[1]_7$.
Let $g=[3]_7=[1]_7$? computed as $3^6=729=[104\cdot7+1]_7=[1]_7$, $x=6$.

**Worked Example (Order of elements in $\mathbb{Z}_4^+$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.6
Content Text: $\mathbb{Z}_4^+=(\{[0],[1],[2],[3]\},+)$, $|\mathbb{Z}_4^+|=4$.
$$\mathrm{ord}[1]=4 \quad(\text{check: } [1]^x=\underbrace{[1]+\cdots+[1]}_{x\text{ times}}=[1+1+1+1]=[4]=[0])$$
$$\mathrm{ord}[2]=2 \quad(\text{check: } [2]+[2]=[2+2]=[4]=[0])$$
$$\mathrm{ord}[3]=4,\qquad \mathrm{ord}[0]=1 \quad(1\text{ point})$$
Lagrange's theorem check: $\mathrm{ord}[3]=4\mid4$; $\mathrm{ord}[0]=1\mid4$; $\mathrm{ord}[2]=2\mid4$.
$[3]+[3]=[6]=[2]$ (not yet identity), $[3]+[3]+[3]=[9]=[1]$ (not yet), $[3]+[3]+[3]+[3]=[12]=[0]$ ✓.

**Worked Example (Order of elements in $\mathbb{Z}_{11}^*$ and $\mathbb{Z}_3^*$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.6
Content Text: $\mathbb{Z}_{11}^*$, $e=[1]$: $\mathrm{ord}[1]=1$; computing $2\cdot2\cdot2\cdot2\cdot2=32=[16]$ (not yet identity, illustrating a step toward finding order).
$\mathbb{Z}_3^*=(\{[1],[2]\},*)$: $\mathrm{ord}(1)=1$, $\mathrm{ord}(2)=2$ since $[2][2]=[4]=[1]$.

**Worked Example (Cyclic group verification, $\mathbb{Z}_3^*$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.7
Content Text: $\mathbb{Z}_3^*=(\{[1],[2]\},*)$. Let $g=[1]$: $[1][1]=[1]$, $[1][1][1]=[1]$ (does not generate all elements). Let $g=[2]$: $[2][2]=[1]$, $[2][2][2]=[8]=[2]$, $[2][2][2][2]=[16]=[1]$, $[2^5]=[32]=[2]$; powers of $[2]$ cycle through $\{[2]\Rightarrow[1],\ [2]\Rightarrow[2]\}$ — $g=[2]$ is a generator of $\mathbb{Z}_3^*$, so $\mathbb{Z}_3^*$ is cyclic.

**Worked Example (Cyclic group verification, $\mathbb{Z}_3^+$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.7
Content Text: $\mathbb{Z}_3^+=(\{[0],[1],[2]\},+)$. Let $g=[1]$: $[1]+[1]=[2]$, $[1]+[1]+[1]=[3]=[0]$; powers cycle $[1]\Rightarrow[1]$, $[1]\Rightarrow[2]$, $[1]\Rightarrow[0]$. $[1]$ is a generator for $\mathbb{Z}_3^+$.
Remark: $[1]_n$ is a generator for any additive group $\mathbb{Z}_n^+$.

**Worked Example (Cyclic group verification, $\mathbb{Z}_5^*$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.8
Content Text: $\mathbb{Z}_5^*=(\{[1],[2],[3],[4]\},*)$. $g=[1]$ — no (doesn't generate all). $g=[2]$: $[2][2]=[4]$, $[2][2][2]=[8]=[3]$, $[2^4]=[16]=[1]$; powers of $[2]$ hit $[2],[4],[3],[1]$ — all elements. So $g=[2]$ is a generator for the multiplicative group $\mathbb{Z}_5^*$.

**Worked Example (Lagrange's theorem verification for $\mathbb{Z}_3^*$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.8
Content Text: $\mathbb{Z}_3^*=(\{[1],[2]\},*)$: $\mathrm{ord}(1)=1$, $\mathrm{ord}(2)=2$; $|\mathbb{Z}_3^*|=2$. Check: $\mathrm{ord}(1)=1$ divides $2$; $\mathrm{ord}(2)=2$ divides $2$.
Homework: check Lagrange's theorem for $\mathbb{Z}_5^*$.

**Worked Example/Proof (Problem: possible orders of elements of $\mathbb{Z}_{16}^+$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.8
Content Text: Find all possible orders of elements of $(\mathbb{Z}_{16},+)$, $|\mathbb{Z}_{16}|=16$. Since $\mathrm{ord}(g)\mid16$: possible orders $\in\{16,8,2,1,4\}$. Note: $\mathbb{Z}_{16}^+\ni g^3\neq e=[0]_{16}$ (illustrating that not every candidate exponent gives the identity).

**Worked Example/Proof (Applying FLT to simplify $123^{123}\bmod7$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.10
Content Text: Compute $123^{123}\pmod7$ using $a^{p-1}\equiv1\pmod p$.
$$123=6\cdot20+3$$
$$123^{123}\equiv123^{6\cdot20}\cdot123^3\equiv(123^6)^{20}\cdot123^3\equiv(123^{p-1})^{20}\cdot123^3\pmod7$$
$$\equiv(123^{20})^6\cdot123^3\equiv1\cdot123^3\equiv123^3\pmod7$$
In residue-class notation:
$$[123^{123}]_7=[123^{6\cdot20+3}]_7=[(123^{20})^6\cdot123^3]_7=[(123^{20})^6]_7\cdot[123^3]_7=1\cdot[123]_7^3=[123]_7^3$$
$$[123]_7=[17\cdot7+4]_7=[4]_7 \Rightarrow [123]_7^3=[4]_7^3=[4^3]_7=[64]_7=[63+1]_7=[1]_7$$

**Worked Example/Proof (Applying FLT to simplify $4569^{4569}\bmod11$):**
Source: CompAlg_-_Lecture_13_-_combined.pdf, handwritten notes p.11
Content Text: Compute $4569^{4569}\pmod{11}$.
$$[4569]_{11}=[415\cdot11+4]_{11}=[4]_{11}$$
$$[4]_{11}^{4569}=[4^{4569}]_{11}=[4^{10\cdot456+9}]_{11}=[(4^{456})^{10}\cdot4^9]_{11}$$
Using $4^{10}\equiv1\pmod{11}$ (FLT, since $10=p-1$ for $p=11$):
$$=[(4^{10})^{456}]_{11}\cdot[4^9]_{11}=[1]_{11}[4^9]_{11}=[4^9]_{11}=[4^{2+7}]_{11}=[4^2\cdot4^7]_{11}$$
$$=[16]_{11}\cdot[4^7]_{11}=[5]_{11}\cdot[4^{2+2+2+1}]_{11}=[5]_{11}\cdot[16\cdot16\cdot16\cdot4]_{11}=[5]_{11}[16]_{11}[16]_{11}[16]_{11}[4]_{11}$$
$$=[5]_{11}[5]_{11}[5]_{11}[5]_{11}[4]_{11}=[5^4]_{11}[4]_{11}=([5^2]_{11})^2[4]_{11}=([25]_{11})^2[4]_{11}=([3]_{11})^2[4]_{11}=[9\cdot4]_{11}=[36]_{11}=[3]_{11}$$
$$[4569^{4569}]_{11}=[3]_{11}$$
