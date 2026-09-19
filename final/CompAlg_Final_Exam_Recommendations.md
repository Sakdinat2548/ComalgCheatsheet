## Final Exam Instructions (Computer Algebra, SCI19 3112)

**Source:** CompAlg_final_recommendations.pdf

**Content Type: Core Formula**
**Content Text:**
Exam logistics: Phones and tablets are not allowed; calculators are allowed and even recommended. Each student may bring one A4 sheet of notes (a cheat sheet). Programming, including in Maxima, is not required — students will not be asked to write code or pseudocode. There is no specific dress code. The exam consists of a multiple-choice section and a written section, for a total of 30 points. The course is focused on solving practical problems, so the exam will consist primarily of practical problems of varying difficulty, with a smaller number of theoretical questions; students can expect problems similar to those in quizzes and homework assignments.

**Section:** Theoretical Topics
**Content Type: Definition**
**Content Text:**
1. General requirement: basic elements of the theory of finite groups studied during the first half of the course: the definition of a group and its axioms, the order of a group and the order of an element, generators, and Lagrange's theorem.
2. Euler's totient function and Euler's totient theorem. The difference between Euler's totient theorem and Fermat's little theorem.
3. Applications of modular arithmetic to cryptography and understanding of the basic ideas. Correctness of an encryption algorithm viewed as a bijective mapping.
4. Standard (rectangular) and polar forms of a complex number, the real and imaginary parts of a complex number, and the complex plane. Understanding the geometry of transformations of complex numbers.
5. Understanding complex numbers as multiplicative and additive groups. Understanding the basic groups $C^{+}$, $C^{*}$, $C_n^{+}$, and $C_n^{*}$. Generators of these groups and their relations as subgroups.
6. The multiplicative property of complex numbers and its use for complex numbers of unit length.
7. Complex roots of unity: their basic properties (including their group structure) and applications. Primitive roots of unity. Understanding the geometric nature of transformations of roots of unity.
8. The isomorphism between the multiplicative group $C_n^{*}$ of complex roots of unity and the additive modular group $\mathbb{Z}_n^{+}$. Understanding of the basic ideas.
9. The statement of the Fundamental Theorem of Algebra concerning the roots of polynomials with complex coefficients. The number of roots of a polynomial over $\mathbb{C}$.
10. Two representations of polynomials: by their coefficients and by their values. How many points are needed to convert correctly from one representation to the other. The proposition specifying how many points are needed to multiply two polynomials and correctly recover the result in coefficient representation.
11. General understanding of the Fast Fourier Transform (FFT) and the Inverse Fast Fourier Transform (IFFT). Ability to determine the number of evaluation points used by a given algorithm. Zero-padding of polynomials in coefficient representation.
12. The efficiency of polynomial multiplication algorithms in coefficient and value representations, and the efficiency of FFT/IFFT, using Big-O notation.
13. Understanding the idea of fast multiplication of large integers using FFT/IFFT.
14. The concept of a field and an algebraically closed field.
15. Polynomial divisibility and factorization theorems.
16. Overdetermined systems of polynomial equations and properties of the GCD.
17. Understanding the purpose of the resultant at a basic level.

**Section:** Topics for the Practical Problems
**Content Type: Worked Example/Proof**
**Content Text:**
1. Computing Euler's totient function for prime and composite numbers. (In practice, only for relatively small numbers.)
2. Applying Euler's totient theorem to compute large powers modulo $n$.
3. Encrypting a message using simple algorithms based on addition modulo $n$ and exponentiation modulo $n$.
4. Practical computations with complex numbers. Conversion between standard (rectangular) and polar representations. Identifying a complex number with a two-dimensional vector and performing vector addition/subtraction. Basic operations: addition and subtraction, multiplication and division of complex numbers, finding the (multiplicative) inverse of a complex number, complex conjugation, and finding the modulus (length) of a complex number. Euler's and De Moivre's formulas. Powers and roots of a complex number. Basic ability to work with the trigonometric functions $\sin$ and $\cos$, including understanding of their periodicity.
5. The ability to graphically represent a complex number given in standard or polar form. The ability to write a complex number in standard or polar form from a given graphical representation.
6. Finding complex roots of unity. Ability to use the standard relations between them. Efficiently evaluating polynomials at roots of unity using these relations.
7. Ability to establish, or at least verify, the isomorphism between the groups $C_n^{*}$ and $\mathbb{Z}_n^{+}$, or to determine that no such isomorphism exists for a given pair of groups.
8. Ability to sketch a polynomial approximately or read its values from a given graph. Graphical multiplication of functions (polynomials) at a given set of points.
9. Direct and inverse conversion between the two representations (by coefficients and by values) of the same polynomial.
10. Multiplication of polynomials in value representation and representation of the result in coefficient form.
11. Fast multiplication of small polynomials using FFT/IFFT.
12. Fast multiplication of large natural numbers using polynomials.
13. Computing the GCD of polynomials and synthetic division.
14. Testing overdetermined systems for consistency and solving them using the GCD.
