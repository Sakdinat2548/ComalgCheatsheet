## Midterm Exam Instructions
## Computer Algebra (SCI19 3112)

**Note:** Students are not allowed to use phones or tablets during the exam. Calculators are allowed and even recommended. In addition, each student may bring one A4 sheet of paper with any notes they wish to prepare (a cheat sheet).

**Note:** Programming, including programming in Maxima, is not required. Students will not be asked to write code or pseudocode during the exam.

**Note:** There is no specific dress code for the exam.

The exam will consist of a multiple-choice section and a written section, with a total of 30 points.

Since our Computer Algebra course is focused on solving practical problems, the exam will consist primarily of practical problems of varying difficulty, with a smaller number of theoretical questions. Students can expect problems similar to those encountered in quizzes and homework assignments.

Below is an approximate list of topics that may be covered on the exam. Answers to most questions can be found in the lecture notes and scans of the lectures (available on e-Learning) or in the references provided therein.

## Theoretical Topics

**1.** Standard number sets and their notation: $\mathbb{N}$, $\mathbb{Z}$, $\mathbb{Q}$, $\mathbb{R}$, and the polynomial set $\mathbb{Z}[x]$. Definitions of prime and composite numbers.

**2.** The distinction between approximate and exact computations, and the specific features of exact computation.

**3.** Understanding how integers are stored in computer memory, including the representation of negative integers using two's complement.

**4.** The structure of floating-point numbers and the normalized IEEE 754 format. Representation of zero in IEEE 754.

**5.** The Euclidean algorithm and its formulation. The definition of a rational number using the GCD.

**6.** The purpose and basic structure of arbitrary-precision integers.

**7.** A simple representation of integers using prime factorization.

**8.** The peculiarities of working with real numbers in computer algebra systems (CAS), including the idea of the "contagious" nature of real numbers.

**9.** Understanding what expression trees are and why they are used. The algorithm for constructing an expression tree from a mathematical expression.

**10.** Representation of expression trees using Lisp-style lists.

**11.** Operators, operands, associativity, and operator precedence.

**12.** Traversal and standard transformations of expression trees. The concepts of rewrite rules and substitution, and the distinction between them. Relation between expansion transformation and distributivity in mathematics.

**13.** The use of types when defining rewrite rules.

**14.** Basic concepts of modular arithmetic: congruence, residue classes (equivalence classes), and the operations of addition, multiplication, and exponentiation.

**15.** A basic understanding of the generalization of modular arithmetic to polynomials.

**16.** Multiplicative and additive inverses in modular arithmetic. The theorem characterizing the existence of a multiplicative inverse modulo $n$.

**17.** Idea of the connection between groups and symmetries.

**18.** The definition of a group and the four group axioms. Multiplicative and additive groups.

**19.** Finite and infinite groups. The order of a group and the order of an element. Cyclic groups.

**20.** The Lagrange theorem for finite groups.

**21.** The statement of Fermat's little theorem.

## Topics for the Practical Problems

**1.** Converting unsigned integers from decimal to binary and from binary to decimal.

**2.** Converting signed integers from decimal to binary and from binary to decimal.

**3.** Basic binary arithmetic: addition and multiplication of binary numbers.

**4.** Converting real (floating point) numbers between decimal and binary representations, including the normalized IEEE 754 representation.

**5.** Finding the GCD of two numbers and determining whether two numbers are relatively prime (coprime).

**6.** Working with arbitrary-precision integers in an arbitrary base, including adding them, converting them to a list representation, and converting such a representation back to a decimal number.

**7.** Determining the minimum and maximum integers, including negative integers, that can be represented using $n$ bits.

**8.** Performing prime factorization for small integers and multiplying numbers represented in prime-factorized form.

**9.** Constructing expression trees from arithmetic expressions or from general expressions with specified operator precedence and associativity.

**10.** Representing expression trees as lists using Lisp-style syntax, and converting between expression trees and their list representations.

**11.** Performing standard transformations of expression trees, including substitution, expansion, simplification, and the application of given rewrite rules.

**12.** Determining whether a rewrite rule can be applied, taking into account the types of the leaves of the expression tree.

**13.** Writing simple two- or three-line programs in Maxima or pseudocode involving lists and arithmetic operations.

**14.** Modular arithmetic: reduction modulo $n$ (i.e., finding the simplest representative of an equivalence class), addition, multiplication, and exponentiation.

**15.** Converting freely between congruence notation and residue-class (equivalence-class) notation.

**16.** Constructing addition and multiplication tables for a given modulus.

**17.** Finding multiplicative inverses, additive inverses, and zero divisors using addition and multiplication tables for a given modulus.

**18.** Polynomial modular arithmetic: reducing a polynomial to its simplest representative, computing powers of polynomials modulo a given polynomial, and understanding what the equivalence classes of polynomials modulo a polynomial represent.

**19.** Using standard theorems to determine whether an integer $m$ has a multiplicative inverse modulo $n$, and determining whether zero divisors can occur in arithmetic modulo $n$.

**20.** Determining whether a given set with a given binary operation forms a group, i.e., checking the four group axioms. Finding the identity element and inverses in a group.

**21.** Constructing a multiplication table for a given group, for example, a group arising from modular arithmetic or from a given set of geometric transformations.

**22.** Computing the order of a group element and determining whether an element is a generator of the group.

**23.** Using Lagrange's theorem for finite groups to determine the possible orders of elements of a given group.

**24.** Computing large powers of integers using Fermat's little theorem.
