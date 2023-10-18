---
layout: default
title: Reading Notes
parent: MATH 402
grand_parent: Mathematics
nav_order: 1
---

# Reading Notes
{: .no_toc }

MATH 402
{: .fs-6 .fw-300 }

---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

Textbook: *Abstract Algebra, an Introduction.* Thomas Hungerford. [Internet Archive link](https://archive.org/details/abstractalgebrai0003hung/page/2/mode/2up){:target="_blank"}

## Chapter 1: Arithmetic in $$\mathbb{Z}$$ Revisited
- Algebra grows out of arithmetic and depends heavily on it

### 1.2: Divisibility

> Let $$a$$ and $$b$$ be integers with $$b \neq 0$$. $$b \vert a$$ (divides $$a$$) if $$a = bc$$ for some integer $$c$$.

- An important case of division happens when the remainder is zero
- $$a$$ and $$-a$$ have the same divisors
- $$a$$ and $$b$$ are not both 0; then, their GCD exists and is unique. It is also larger than or equal to one.

**Theorem 1.2.** Let $$a$$ and $$b$$ be integers, not both zero, and let $$d$$ be their greatest common divisor. Then there exist (not necessarily unique) integers $$u$$ and $$v$$ such that $$d = au + bv$$.

Proof:
1. Let $$S$$ be the set of all linear integral combinations of $$a, b$$: $$S = \{ am + bn \vert m, n \in \mathbb{Z} \}$$
2. Find the smallest positive element of $$S$$.
    1. $$a^2 + b^2 = aa + bb$$, $$aa + bb \in S$$, $$a^2 + b^2 \ge 0$$. 
    2. $$S$$ must contain a smallest positive integer by the Well-Ordering Axiom.
    3. Let $$t = au + bv$$ be the smallest positive element of $$S$$
3. Prove that $$t = GCD(a, b)$$
    1. Prove $$t \vert a$$ and $$t \vert b$$
        1. By the Division Algorithm, $$\exists q, r \in \mathbb{Z} : a = tq + r$$, where $$0 \le r < t$$.
        2. Therefore, $$r = a - tq$$
        3. Substituting: $$r = a - (au + bv)q$$
        4. We get $$a - aqu - bvq$$ by expanding
        5. Rearranging into linear combination: $$r = a(1 - qu) + b(-vq)$$
        6. $$r \in S$$ because it is a linear combination of $$a, b$$
        7. $$r < t$$, the smallest positive element of $$S$$
        8. $$r \ge 0$$, so the only possibility is that $$r = 0$$
        9. Therefore, $$t \vert a$$. Repeat argument to show $$t \vert b$$. 
        10. $$t$$ is a common divisor of $$a$$$ and $$b$$.
    2. Prove $$c \vert a$$ and $$c \vert b$$ implies $$c \vert t$$
        1. Let $$c$$ be any common divisor of $$a$$ and $$b$$.
        2. Then $$a = ck$$ and $$b = cs$$, where $$k, s \in \mathbb{Z}$$
        3. Therefore, $$t = au + bv = (ck)u + (cs)v = c(ku + sv)$$
        4. We know from this that $$c \vert t$$ 
        5. $$c \le \vert t \vert$$: every divior of a nonzero integer $$a$$ is less than or equal to $$\vert a \vert$$
        5. However, $$t$$ is positive.
        6. Therefore, $$c \le t$$.
        7. Therefore, $$t$$ is the greatest common divisor.

**Corollary 1.3.** Let $$a$$ and $$b$$ be integers, not both 0, and let $$d$$ be a positive integer. Then $$d$$ is the greatest common divisor of $$a$$ and $$b$$ if and only if $$d$$ satisfies these conditions:
- $$d \vert a$$ and $$d \vert b$$
- $$(c \vert a \wedge c \vert b)$$ implies $$c \vert d$$

**Theorem 1.4.** If $$a \vert bc$$ and $$(a, b) = 1$$, then $$a \vert c$$.

Proof:
1. Since $$(a, b) = 1$$, $$au + bv = 1$$ for some $$u, v \in \mathbb{Z}$$
2. Multiply by $$c$$: $$acu + bcv = c$$
3. Since $$a \vert bc$$, $$bc = ar$$ for some $$r \in \mathbb{Z}$$
4. Therefore, $$c = acu + bcv = acu + (ar) v = a(cu + rv)$$
5. This shows $$a \vert c$$

### 1.3: Primes and Unique Factorization

- Every nonzero integer has four distinct divisors.
- Integers with only four divisors are important:

> An integer $$p$$ is prime if $$p \neq 0, \pm 1$$ and the only divisors of $$p$$ are $$\pm 1$$ and $$\pm p$$.

- Becuase an integer $$p$$ has the same divisors as $$-p$$, $$p$$ is prime iff $$-p$$ is prime.
- If $$p$$ and $$q$$ are prime and $$p \vert q$$, then $$p = \pm q$$

**Theorem 1.5.** Let $$p$$ be an integer with $$p \neq 0, \pm 1$$. Then $$p$$ is prime iff whenever $$p \vert ab$$, $$p \vert b$$ or $$p \vert c$$.

Proof.
1. Suppose $$p$$ is prime and $$p \vert bc$$.
    1. $$(p, b)$$ must be a positive divisor of the prime $$p$$.
    2. If $$(p, b) = \pm p$$, $$p \vert b$$
    3. If $$(p, b) = \pm 1$$, then $$p \vert c$$
2. Suppose $$p \vert bc$$ implies $$p \vert b$$ or $$p \vert c$$.
    1. ...

**Corollary 1.6.** If $$p$$ is prime and $$p \vert a_1 a_2 ... a_n$$, then $$p$$ divides at least one of $$a_i$$.

**Theorem 1.7.** Every integer $$n$$ except $$0, \pm 1$$ is the product of primes.

Proof: Let $$S$$ be the set of integers greater than 1 that are not a product of primes. Show that $$S$$ is the empty set. Since there are no integers in $$S$$, every integer greater than 1 is a product of primes.

1. Suppose $$S$$ is not empty.
2. By the Well-Ordering Principle, $$S$$ has a smallest element, call it $$n$$.
3. $$n$$ is not prime, so $$n = ab$$ for some integers $$a, b$$, where $$1 < a, b < n$$.
4. Since $$n$$ is the smallest element of $$S$$, $$a$$ and $$b$$ are not in $$S$$.
5. Therefore, $$a$$ and $$b$$ are products of primes.
6. Therefore, $$n$$ is a product of primes.
7. This contradicts the assumption that $$n$$ is not a product of primes.
8. Therefore, $$S$$ is empty.

**Theorem 1.8 (The Fundamental Theorem of Arithmetic).**  Every integer $$n$$ except $$0, \pm 1$$ is a product of primes. The prime factorization is unique:

$$(n = p_1 p_2 ... p_n) \wedge (n = q_1 q_2 ... q_n) \implies p_1 = \pm q_1, p_2 = \pm q_2, ..., p_n \pm q_n$$

Proof: 
1. Eery integer $$n$$ except $$0, \pm 1$$ is a product of primes by Theorem 1.7.
2. Suppose $$n$$ has two prime factorizations. Then,

$$n = p_1 p_2 ... p_n = q_1 q_2 ... q_n$$

3. We know that $$p_1 \vert q_1 q_2 ... q_n$$.
4. $$p$$ must divide one of the $$q$$.
5. After reordering, $$p_1 \vert q_1$$.
6. Since $$p_1$$ and $$q_1$$ are prime, $$p_1 = \pm q_1$$.
7. Therefore, replacing on the LHS: $$\pm q_1 p_2 p_3 ... p_n = q_1 q_2 q_3 ... q_n$$
8. Dividing both sides by $$q_1$$ gives $$\pm p_2 p_3 ... p_n = q_2 q_3 ... q_n$$
9. Continuing to eliminate one prime at each step, we get totaly equality.$$
10. The lengths of the prime factorizations must be equal. If they were not, then we would get something like $$ \pm p_{r+1} p_{r+2} ... p_n = 1$$
10. This is a contradiction because $$p_i = \pm 1$$ but is also prime.

**Corollary 1.9.** Every integer $$n > 1$$ can be written in only one way in the form $$n = p_1 p_2 p_3 ... p_n$$, where the $$p_i$$ are primes and $$p_1 \le p_2 \le p_3 \le ... \le p_n$$.

**Theorem 1.10.** Let $$n > 1$$. If $$n$$ has no positive prime factor less than or equal to $$\sqrt{n}$$, then $$n$$ is prime.

---

## Chapter 2: Congruence in $$\mathbb{Z}$$ and Modular Arithmetic

### 2.1: Congruence and Congruence Classes
- Congruence is a generalization of the equality relation.
- Two integers are equal if their difference is zero or a multiple of zero.
- For $$n \in \mathbb{Z}^+$$, two integers are congruent modulo $$n$$ if their difference is a multiple of $$n$$.
- **Definition:** Let $$a, b, n$$ be integers with $$n > 0$$. Then $$a$$ is congruent to $$b$$ modulo $$n$$, provided that $$n$$ divides $$a-b$$.
- Congruence has many of the same properties as standard equality.
  - Reflexivity: $$a = a$$ for every integer $$a$$
  - Symmetric: $$a = b \iff b = a$$
  - Transitive: $$a = b \wedge b = c \implies a = c$$

**Theorem 2.1.**
Let $$n$$ be a positive integer.
For all $$a, b, c \in \mathbb{Z}$$.
1. Reflexivity: $$a \equiv_n a$$
2. Symmetric: $$a \equiv_n b \implies b \equiv_n a$$
3. Transitive: $$a \equiv_n b \wedge b \equiv_n c \implies a \equiv_n c$$

**Theorem 2.2.**
If $$a \equiv_n b$$ and $$c \equiv_n d$$, then
1. Distributivity: $$a + c \equiv_n b + d$$
2. Multiplicativity: $$ac \equiv_n bd$$

**Definition.**
Let $$a$$ and $$n$$ be integers with $$n > 0$$.
The congruence class of a modulo $$n$$ is the set of all integers that are congruent to $$a$$ modulo $$n$$.
$$[ a\ ] = \{ b \vert b \in \mathbb{Z} \text{ and } b \equiv_n a \}$$
To say that $$b \equiv_n a$$ means that $$b - a = kn$$ for some integer $$k$$.
Therefore we can rewrite it as
$$[a] = \{ a + kn \vert k \in \mathbb{Z} \}$$

**Theorem 2.3.**
$$a \equiv_n c$$ iff $$[a] = [c]$$

**Corollary 2.4.**
Two congruence classes modulo $$n$$ are either disjoint or identical.

**Corollary 2.5.**
Let $$n > 1$$ be an integer and consider congruence modulo $$n$$.
1. If $$a$$ is any integer and $$r$$ is the remainder when $$a$$ is divided by $$n$$, then $$[a] = [r]$$.
2. There are exactly $$n$$ distinct congruence classes, namely, $$[0], [1], ..., [n-1]$$.

The set of all congruence classes modulo $$n$$ is $$\mathbb{Z}_n$$.
These elements are classes, not single integers.


### 2.2: Modular Arithmetic
- The finite set $$\mathbb{Z}_n$$ is closely related to the infinite set $$\mathbb{Z}$$. 
- Can we define addition and multiplication on $$\mathbb{Z}_n$$?
- The sum of classes $$[a]$$ and $$[c]$$ is $$[a] \oplus [c] = [a + c]$$
- The product of classes $$[a]$$ and $$[c]$$ is $$[a] \odot [c] = [ac]$$
- These operations do not depend on the choice of representatives from the various classes. (e.g. $$[a] = [a + kn]$$)

**Theorem 2.6.**
If $$[a] = [b]$$ and $$[c] = [d]$$ in $$\mathbb{Z}_n$$, then
$$[a + c] = [b + d]$$
and
$$[ac] = [bd]$$

**Theorem 2.7.**
For any classes $$[a]$$, $$[b]$$, $$[c]$$ in $$\mathbb{Z}_n$$, 
1. Closure for addition: $$[a] \oplus [b] \in \mathbb{Z}_n$$
2. Associativity for addition: $$[a] \oplus ([b] \oplus [c]) = ([a] \oplus [b]) \oplus [c]$$
3. Commutativity for addition: $$[a] \oplus [b] = [b] \oplus [a]$$
4. Identity for addition: $$[a] \oplus [0] = [a]$$
5. Root existence: for each $$[a]$$ in $$\mathbb{Z}_n$$, the equation $$[a] \oplus [x] = [0]$$ has a solution in $$\mathbb{Z}_n$$
6. Closure for multiplication: $$[a] \odot [b] \in \mathbb{Z}_n$$
7. Associativity for multiplication: $$[a] \odot ([b] \odot [c]) = ([a] \odot [b]) \odot [c]$$
8. Distribution with addition: $$[a] \odot ([b] \oplus [c]) = ([a] \odot [b]) \oplus ([a] \odot [c])$$
9. Commutativity for multiplication: $$[a] \odot [b] = [b] \odot [a]$$
10. Identity for multiplication: $$[a] \odot [1] = [a]$$

- For $$k \in \mathbb{Z}^+$$, $$[a]^k$$ denotes the product

$$[a]^k = [a] \odot [a] \odot ... \odot [a] , k\text{ times}$$

### 2.3: The Structure of $$\mathbb{Z}_p$$ and $$\mathbb{Z}_n$$
- New notation: uses the same symbol to represent totally different entities.
- The class notation $$[a]$$ will be replaced with $$a$$.

The structure of $$\mathbb{Z}_p$$ when $$p$$ is prime
- When $$a \neq 0$$, the equation $$ax = 1$$ has a solution in $$\mathbb{Z}$$ iff $$a = \pm 1$$.
- But $$ax = 1$$ has solutions when $$p$$ is prime for $$\mathbb{Z}_p$$

**Theorem 2.8.**
If $$p > 1$$ is an integer, the following conditions are equivalent:
1. $$p$$ is prime
2. For any $$a \neq 0$$ in $$\mathbb{Z}_p$$, the equation $$ax = 1$$ has a solution in $$\mathbb{Z}_p$$
3. Whenever $$bc = 0$$ in $$\mathbb{Z}_p$$, then $$b = 0$$ or $$c = 0$$

Proof:
1. Show that 1 implies 2. Suppose $$p$$ is prime and $$a \neq 0$$ in $$\mathbb{Z}_p$$. Then $$a \not\equiv_p 0$$. Therefore, $$p \nmid a$$. Now, $$(a, p)$$ is a positive divisor of $$p$$ and is either $$p$$ or $$1$$. Since $$(a, p)$$ also divides $$a$$ and $$p \nmid a$$, $$(a, p) = 1$$. From theorem 1.2., $$au + pv = 1$$ for some integers $$u, v$$. Hence, $$au - 1 = p(-v)$$, so $$au \equiv_p 1$$. Therefore $$[au] = [1]$$ in $$\mathbb{Z}_p$$. Therefore $$x = [u]$$ is a solution to $$ax = 1$$ in $$\mathbb{Z}_p$$.
2. Show that 2 implies 3. Suppose $$ab = 0$$ in $$\mathbb{Z}_p$$. If $$a = 0$$, there is nothing to prove. If $$a \neq 0$$, then by 2 there exists $$u \in \mathbb{Z}_p$$ such that $$au = 1$$. Then $$0 = u \cdot 0 = u(ab) = (ua)b = (au)b = 1 \cdot b = b$$. 
3. Show that 3 implies 1. Suppose $$b, c \in \mathbb{Z}$$, $$p \vert bc$$. Then $$bc \equiv_p 0$$. By 2.3, $$[b][c] = [bc] = [0]$$ in $$\mathbb{Z}_p$$. By 3, $$[b] = 0$$ or $$[c] = [0]$$. This means $$b \equiv_p 0$$ or $$c \equiv_p 0$$, or $$p \vert b$$ or $$p \vert c$$. This means $$p$$ is prime by theorem 1.5.

The Structure of $$\mathbb{Z}_n$$
- When $$n$$ is not prime, $$ax = 1$$ does not necessarily have a solution in $$\mathbb{Z}_n$$. 

**Theorem 2.9.** 
Let $$a$$ and $$n$$ be integers with $$n > 1$$.
Then the equation $$[a]x = [1]$$ has a solution in $$\mathbb{Z}_n$$ iff $$(a, n) = 1$$ in $$\mathbb{Z}$$.

Units and Zero Divisors
- An element $$a$$ in $$\mathbb{Z}_n$$ is a unit if the equation $$ax = 1$$ has a solution

**Theorem 2.10.**
Let $$a, n$$ be integers with $$n > 1$$.
Then $$[a]$$ is a unit in $$\mathbb{Z}_n$$ iff $$(a, n) = 1$$ in $$\mathbb{Z}$$.

- A nonzero element $$a$$ of $$\mathbb{Z}_n$$ is called a zero divisor if the equation $$ax = 0$$ has a noznero solution
- From 2.8. part 3, when $$p$$ is prime, there are no zero divisors in $$\mathbb{Z}_p$$


---

## Chapter 3: Rings
- High-school algebra: arithmetic of polynomials
- What are common features of arithmetic across different systems?
- Abstraction allows us to understand the real reasons for why a particular statement is true.
- Rings -- systems which share a minimal number of fundamental properties of $$\mathbb{Z}$$ and $$\mathbb{Z}_n$$.

### 3.1: Definition and Examples
A ring is a nonempty set $$R$$ equipped with two operations, addition and multiplication, which satisfy the following axioms. 
For all $$a, b, c \in R$$:
1. Closure for addition: $$a + b \in R$$
2. Associative addition: $$(a + b) + c = a + (b + c)$$
3. Commutative addition: $$a + b = b + a$$
4. Additive identity or zero element: there is an element $O_R$$ in $$R$$ such that $$a + O_R = a$$ for all $$a \in R$$
5. Additive identity or zero element: for each $$a \in R$$, the equation $$a + x = O_R$$ has a solution in $$R$$
6. Closure for multiplication: $$ab \in R$$
7. Associative multiplication: $$(ab)c = a(bc)$$
8. Distributive laws. $$a(b + c) = ab + ac$$ and $$(b + c)a = ba + ca$$

A commutative ring is a ring which additionally satisfies the axiom that for all $$a, b \in R$$, $$ab = ba$$.

A ring with identity is a ring which additionally satisfies the axiom that there is an element $$1_R$$ in $$R$$ such that $$1_R a = a = a 1_R$$ for all $$a \in R$$ (multiplicative identity).

Examples
- $$\mathbb{Z}$$ is a commutative ring with identity.
- $$\mathbb{Z}_n$$ is a commutative ring with identity.
- $$\mathbb{R}$$ is a commutative ring with identity.
- The set of odd integers with integer addition and multiplication is not a ring. The sum of two odd integers is not odd.
- The set of even integers is a commutative ring.
- $$M(\mathbb{R})$$ is the set of all $$2 \times 2$$ matrices over the real numbers. It is a ring with identity.
- $$T$$ is the set of all functions from $$\mathbb{R}\to\mathbb{R}$$. $$f + g$$ and $$fg$$ are defined by $$(f + g)(x) = f(x) + g(x)$$ and $$(fg)(x) = f(x)g(x)$$. It is a commutative ring with identity.

An integral domain is a commutative ring $$R$$ with identity $$1_R \neq 0_R$$ that satisfies this axiom:
whenever $$a, b \in \mathbb{R}$$ and $$ab = 0_R$$, then $$a = 0_R$$ or $$b = 0_R$$
(Note: $$1_R \neq 0_R$$ excludes the zero ring from integral domains.)
Contrapositive: whenever $$a, b \in \mathbb{R}$$ and $$a \neq 0_R$$ and $$b \neq 0_R$$, then $$ab \neq 0_R$$

- The ring $$\mathbb{Z}$$ of integers is an integral domain.
- The ring $$\mathbb{Z}_p$$ is an integral domain.
- The ring $$\mathbb{Z}_n$$ is not an integral domain when $$n$$ is not prime. For example, $$[2] \odot [3] = [0]$$ in $$\mathbb{Z}_6$$.
- The ring $$\mathbb{Q}$$ is an integral domain.

A field is a commutative ring $$R$$ with identity $$1_R \neq 0_R$$ which satisfies this axiom:
for each $$a \neq 0_R$$ in $$R$$, the equation $$ax = 1_R$$ has a solution in $$R$$.

- $$\mathbb{R}$$ is a field
- $$\mathbb{Z}_p$$ is a field
- $$\mathbb{C}$$ is a field
- The set of all matrices of the form $$\begin{pmatrix} a & b \\ -b & a \end{pmatrix}$$ is a field.

**Theorem 3.1.**
Let $$R$$ and $$S$$ be rings.
Define addition and multiplication on the Cartesian product $$R \times S$$ by
$$(r, s) + (r', s') = (r + r', s + s')$$
$$(r, s) \cdot (r', s') = (rr', ss')$$
Then $$R \times S$$ is a ring.
If $$R$$ and $$S$$ are both commutative, then $$R \times S$$ is commutative.
If both $$R$$ and $$S$$ have an identity, then so does $$R \times S$$.

When a subset $$S$$ of a ring $$R$$ is itself a ring under the addition and multiplication in $$R$$, $$S$$ is a subring of $$R$$.

- $$\mathbb{Z}$$ is a subring of the ring $$\mathbb{Q}$$
- $$\mathbb{Q}$$ is a subring of the ring $$\mathbb{R}$$
- $$\mathbb{Q}$$ is a subfield of $$\mathbb{R}$$
- $$\mathbb{R}$$ is a subfield of $$\mathbb{C}$$
- $$M(\mathbb{Z})$$ is a subring of $$M(\mathbb{R})$$
- The set of all continuous functions $$\mathbb{R} \to \mathbb{R}$$ is a subring of the ring of all functions from $$\mathbb{R} \to \mathbb{R}$$

Often, proving $$S$$ is a subring is easier than proving that $$S$$ is a ring.

**Theorem 3.2.**
Suppose $$R$$ is a ring and that $$S$$ is a subset of $$R$$ such that
1. $$S$$ is closed under addition
2. $$S$$ is closed under multiplication
3. $$0_R \in S$$
4. If $$a \in S$$, then the solution to the equation $$a + x = 0_R$$ is in $$S$$
Then $$S$$ is a subring of $$R$$.

- $$\{0, 3\}$$ is a subring of $$\mathbb{Z}_6$$.
- The set of all matrices with form $$\begin{pmatrix} a & 0 \\ b & c \end{pmatrix}$$ is a subring of $$M(\mathbb{R})$$.
- The set $$\{ a + b \sqrt{2} \vert a, b \in \mathbb{Z} \}$$ is a subring of $$\mathbb{R}$$.



### 3.2: Basic Properties of Rings

Arithmetic in Rings
- We cannot assume subtraction exists in an arbitrary ring

**Theorem 3.3.**
For any element $$a$$ in a ring $$R$$, the equation $$a + x = 0_R$$ has a unique solution.

- You can define negatives and subtraction: $$-a$$ is the solution to $$a + x = 0_R$$
- Since addition is commutative $$-a$$ is the unique element of $$R$$ such that $$a + (-a) = 0_R = (-a) + a$$
- Subtraction in a ring $$b-a$$ is defined as $$b+(-a)$$.

**Theorem 3.4.**
If $$a + b = a + c$$ in a ring $$R$$, then $$b = c$$.

**Theorem 3.5.**
For any elements $$a, b$$ of a ring $$R$$,
1. Multiplication of the zero element: $$a \cdot 0_R = 0_R = 0_R \cdot a$$
2. Negative of a product: $$(-a)b = -(ab) = a(-b)$$
3. Double negation: $$-(-a) = a$$
4. Distribution of negative: $$-(a + b) = (-a) + (-b)$$
5. Distribution of negative: $$-(a - b) = (-a) + b$$
6. Double negation: $$(-a)(-b) = ab$$
7. (If $$R$$ has an identity) $$(-1_R)a = -a$$

- Exponents: $$a^n = aaa \cdot a$$
- We can verify that $$a^ma^n = a^{m+n}$$ and $$(a^m)^n = a^{mn}$$
- $$na = a + a + a + ... + a$$, $$-na = (-a) + (-a) + (-a) + ... + (-a)$$
- We can give a product of an integer $$n$$ and a ring element $$a$$

**Theorem 3.6.**
Let $$S$$ be a nonempty subset of a ring $$R$$ such that
1. $$S$$ is closed under subtraction (if $$a, b \in S$$, then $$a - b \in S$$)
2. $$S$$ is closed under multiplication (if $$a, b \in S$$, then $$ab \in S$$)
Then $$S$$ is a subring of $$R$$.

Units and Zero Divisors
- An element $$a$$ in a ring $$R$$ is a unit if the equation $$au = 1_R = ua$$ has a solution in $$R$$.
- The element $$u$$ is the multiplicative inverse of $$a$$ and denoted $$a^{-1}$$
- The only units in $$\mathbb{Z}$$ are $$\pm 1$$
- Every nonzero element of a field is a unit.
- Invertible matrices are units in a matrix ring.
- An element $$a$$ in a ring $$R$$ is a zero divisor provided that $$a \neq 0_R$$ and there exists a nonzero element $$c$$ in $$R$$ such that $$ac = 0_R$$ or $$ca = 0_R$$.
- An integral domain contains no zero divisors.

**Theorem 3.7.**
Cancellation is valid in any integral domain $$R$$. 
If $$a \neq 0_R$$ and $$ab = ac$$ in $$R$$, then $$b = c$$. 

**Theorem 3.8.**
Every field $$F$$ is an integral domain.

**Theorem 3.9.**
Every finite integral domain $$R$$ is a field.


---






















