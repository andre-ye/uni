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
4. Additive identity or zero element: there is an element $$O_R$$ in $$R$$ such that $$a + O_R = a$$ for all $$a \in R$$
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
3. Zero element: $$0_R \in S$$
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

### 3.3: Isomorphisms and Homomorphisms
- Consider the subset $$S = \{0, 2, 4, 6, 8\}$$ of $$\mathbb{Z}_{10}$$. $$S$$ is essentially the same as the field $$\mathbb{Z}_5$$, except for the labels on the elements.
- That is, $$S$$ is isomorphic to $$\mathbb{Z}_5$$.
- Isomorphic rings are rings with the same structure, in that addition and multiplication tables are equivalent when relabelled.
- Relabing: every element of $$R$$ is paired with a unique element of $$S$$. 
- There is a function $$f: R \to S$$ which assigns each $$r$$ to a new label $$f(r) \in S$$.
- Properties of $$f$$:
  - Distinct elements of $$R$$ must get distinct new labels: if $$r \neq r'$$ in $$R$$, then $$f(r) \neq f(r')$$ in $$S$$. (Injective)
  - Every element of $$S$$ must be the label of some element in $$R$$: for each $$s \in S$$, there is an $$r \in R$$ such that $$f(r) = s$$. (Surjective)
- The function $$f$$ is a bijection.
- If $$a + b = c$$ in $$R$$, then $$f(a) + f(b) = f(c)$$ in $$S$$. And $$f(a + b) = f(c)$$. Therefore, $$f(a + b) + f(a) + f(b)$$.

**Definition.**
A ring $$R$$ is isomorphic to a ring $$S$$ is there is a function $$f: R \to S$$ such that
1. $$f$$ is injective,
2. $$f$$ is surjective,
3. $$f(a + b) = f(a) + f(b)$$ and $$f(ab) = f(a) f(b)$$ for all $$a, b \in R$$,

**Example.**
The field $$K$$ of all matrices of the form $$\begin{pmatrix} a & b \\ -b & a \end{pmatrix}$$ is ismomorphic to the field $$\mathbb{C}$$.
Let $$f: K \to \mathbb{C}$$ be defined as follows:
$$f(\begin{pmatrix} a & b \\ -b & a \end{pmatrix}) = a + bi$$
We will first show that $$f$$ is injective. Suppose $$f(\begin{pmatrix} a & b \\ -b & a \end{pmatrix}) = f(\begin{pmatrix} c & d \\ -d & c \end{pmatrix})$$. Then $$a + bi = c + di$$. Therefore, $$a = c$$ and $$b = d$$. Therefore, $$\begin{pmatrix} a & b \\ -b & a \end{pmatrix} = \begin{pmatrix} c & d \\ -d & c \end{pmatrix}$$. Therefore, $$f$$ is injective.
We will next show that $$f$$ is surjective. Let $$a + bi$$ be any element of $$\mathbb{C}$$. Then $$f(\begin{pmatrix} a & b \\ -b & a \end{pmatrix}) = a + bi$$. Therefore, $$f$$ is surjective.
Finally, we will show that $$f$$ preserves addition and multiplication. Let $$\begin{pmatrix} a & b \\ -b & a \end{pmatrix}, \begin{pmatrix} c & d \\ -d & c \end{pmatrix}$$ be any elements of $$K$$. Then $$f(\begin{pmatrix} a & b \\ -b & a \end{pmatrix} + \begin{pmatrix} c & d \\ -d & c \end{pmatrix}) = f(\begin{pmatrix} a + c & b + d \\ -(b + d) & a + c \end{pmatrix}) = a + c + (b + d)i = (a + bi) + (c + di) = f(\begin{pmatrix} a & b \\ -b & a \end{pmatrix}) + f(\begin{pmatrix} c & d \\ -d & c \end{pmatrix})$$. Therefore, $$f$$ preserves addition. Similarly, $$f$$ preserves multiplication. Therefore, $$f$$ is an isomorphism.

You can even relabel the elements of a ring such that the ring is ismorphic to itself.
For example, $$f : \mathbb{C} \to \mathbb{C}$$ where $$f(a + bi) = a - bi$$.

Isomorphisms are intuitively symmetric.
But the definition of an isomorphism is not necessarily symmetric.
Requires a function from $$R$$ onto $$S$$ but not vice versa.
Yet, $$f$$ is a bijective function of sets, which means the inverse exists.
Therefore ismorphism is symmetric.

**Definition.**
Let $$R, S$$ be rings. A function $$f : R \to S$$ is a homomorphism if 
$$f(a + b) = f(a) + f(b)$$ and $$f(ab) = f(a) f(b)$$ for all $$a, b \in R$$.

- Every isomorphism is a homomorphism.
- However a homomorphism may fail to be injective or surjective.

**Example.**
The zero map $$z : R \to S$$, $$z(r) = 0_S$$ is a homomorphism.
The function $$f: \mathbb{Z} \to \mathbb{Z}_6$$, $$f(a) = [a]$$ is a homomorphism.

**Theorem 3.10.**
Let $$f : R \to S$$ be a homomorphism of rings.
Then
1. Identity preservation: $$f(0_R) = 0_S$$
2. Negation preservation: $$f(-a) = -f(a)$$
3. Subtrative cancellation: $$f(a - b) = f(a) - f(b)$$
If $$R$$ is a ring with identity and $$f$$ is surjective, then
4. $$S$$ is a ring with identity $$f(1_R)$$.
5. Whenever $$u$$ is a unit in $$R$$, then $$f(u)$$ is a unit in $$S$$ and $$f(u)^{-1} = f(u^{-1})$$.

**Corollary 3.11.**
If $$f : R \to S$$ is a homomorphism of rings, then the image of $$f$$ is a subring of $$S$$.

How to show that there is no possible function from one ring to another?
Proceed indirectly.
Assume that there is a contradiction which exists, and show a contradiction.
Alternatively, isomorphisms should preserve features such as zero elements, units, or identities.
For instance, we know that $$\mathbb{Q}, \mathbb{R}$$ are not isomorphic to $$\mathbb{Z}$$ because every nonzero element in $$\mathbb{Q}, \mathbb{R}$$ is a unit, but not in $$\mathbb{Z}$$.

- No commutative ring can be isomorphic to a noncommutative ring.

---

## Chapter 4: Arithmetic in $$F[x]$$

### 4.1: Polynomial Arithmetic and the Division Algorithm
- A polynomial with coefficients in $$R$$ is an expression of the form $$a_0 + a_1 x + a_2 x^2 + ... + a_n x^n$$, where $$n$$ is a nonnegative integer and the $$a_i$$ are elements of $$R$$.
- What is $$x$$? What does it mean to multiply $$x$$ by a ring element? Is $$x \in R$$?
- Polynomials are coefficients in a ring $$R$$, which are elements of a larger ring containing both $$R$$ and the special element $$x$$ if not in $$R$$

**Theorem 4.1.**
If $$R$$ is a ring, then there exists a ring $$T$$ containing an element $$x$$ that is not in $$R$$ and has these properties:
1. $$R$$ is a subring of $$T$$
2. $$xa = ax$$ for every $$a \in R$$
3. The set $$R[x]$$ of all elements of $$T$$ of the form $$a_0 + a_1 x + a_2 x^2 + ... + a_n x^n$$ for $$n \ge 0$$ and $$a_i \in R$$ is a subring of $$T$$ that contains $$R$$.
4. The representation of elements is unique.
5. $$a_0 + a_1 x + a_2 x^2 + ... + a_n x^n = 0_R$$ iff $$\forall i : a_i = 0_R$$.

- Elements of $$R[x]$$ are polynomials with coefficients in $$R$$ and the elements $$a_i$$ are coefficients
- $$x$$ is an indeterminate
- The ring $$T$$ is not necessarily commutative, but rather that $$x$$ is commutative with every element in $$R$$
- Examples
  - $$\mathbb{Z}[x], \mathbb{Q}[x], \mathbb{R}[x]$$ are all familiar rings
  - $$4 - 6x + 4x^3 \in E[x]$$, $$E$$ ring of even integers. The polynomial $$x$$ is not in $$E[x]$$ becuase it cannot be written with even coefficients.

Polynomial Arithmetic
- Rules for adding and multiplying polynomials follow from the fact that $$R[x]$$ is ar ing.
- Polynomial addition and multiplication

$$\sum_{i=0}^n a_i x^i + \sum_{i=0}^m b_i x^i = \sum_{i=0}^k (a_i + b_i) x^i$$

$$\sum_{i=0}^n a_i x^i \cdot \sum_{i=0}^m b_i x^i = \sum_{i=0}^{n+m} \left( \sum_{j=0}^i a_{j} b_{i-j} \right)x^i$$

- If $$R$$ is commutative, then so is $$R[x]$$
- If $$1_R \in R$$, then $$1_R$$ is the multiplicative identity of $$R[x]$$.
- $$a_n$$ is the leading coefficient of $$f(x)$$
- Degree is the largest exponent of $$x$$ which appears as a nonzero coeficient
- The constant polynomial does not have a degree

**Theorem 4.2.**
If $$R$$ is an integral domain and $$f(x), g(x)$$ are nonzero polynomials in $$R[x]$$, then $$\deg(f(x)g(x)) = \deg(f(x)) + \deg(g(x))$$.

**Corollary 4.3.**
If $$R$$ is an integral domain, then so is $$R[x]$$.


**Corollary 4.4.**
Let $$R$$ be a ring.
If $$f(x), g(x), f(x)g(x)$$ are nonzero in $$R[x]$$, then
$$\deg[ f(x) g(x) ] \le \deg f(x) + \deg g(x)$$.

**Corollary 4.5.**
Let $$R$$ be an integral domain and $$f(x) \in R[x]$$.
Then $$f(x)$$ is a unit in $$R[x]$$ iff $$f(x)$$ is a constant polynomial that is a unit in $$R$$.
In particular, if $$F$$ is a field, the units in $$F[x]$$ are the nonzero constants in $$F$$.

The Division Algortihm in $$F[x]$$
- What about polynomials with coefficients in a field $$F$$?

**Theorem 4.6: The Division Algorithm in $$F[x]$$.**
Let $$F$$ be a field and $$f(x), g(x) \in F[x]$$ with $$g(x) \neq 0_F$$.
Then there exist unique polynomials $$q(x)$$ and $$r(x)$$ such that $f(x) = g(x) q(x) + r(x)$$ and either $$r(x) = 0_F$$ or $$\deg r(x) < \deg g(x)$$.

### 4.2: Divisibility in $$F[x]$$
- Let $$F$$ be a field and $$a(x), b(x) \in F[x]$$ with $$b(x)$$ nonzero.
- $$b(x)$$ divides $$a(x)$$ if $$a(x) = b(x) h(x)$$ for some $$h(x) \in F[x]$$.

**Theorem 4.7.**
Let $$F$$ be a field and $$a(x), b(x) \in F[x]$$ with $$b(x)$$ nonzero.
1. If $$b(x) \vert a(x)$$, then $$cb(x) \vert a(x)$$  for each nonzero $$c \in F$$
2. Every divisor of $$a(x)$$ has degree less than or equal to $$\deg a(x)$$.

- A polynomial is monic if its leading coefficient is $$1_F$$

**Definition.**
The GCD of $$a(x)$$ and $$b(x)$$ is the monic polynomial of highest degree that divides both $$a(x)$$ and $$b(x)$$.
$$d(x)$$ is the gcd of $$a(x)$$ and $$b(x)$$, provided that $$d(x)$$ is monic and 
1. $$d(x) \vert a(x)$$ and $$d(x) \vert b(x)$$
2. If $$c(x) \vert a(x)$$ and $$c(x) \vert b(x)$$, then $$\deg c(x) \le \deg d(x)$$.

**Theorem 4.8.**
Let $$F$$ be a field and $$a(x), b(x) \in F[x]$$, both nonzero.
Then there is a unique GCD $$d(x)$$ of $$a(x)$$ and $$b(x)$$.
There are polynomials $$u(x), v(x) : d(x) = a(x) u(x) + b(x) v(x)$$.

**Theorem 4.10.**
Let $$F$$ be a field and $$a(x), b(x), c(x) \in F[x]$$.
If $$a(x) \vert b(x) c(x)$$ and $$a(x)$$ and $$b(x)$$ are relatively prime, then $$a(x) \vert c(x)$$.

### 4.3: Irreducibles and Unique Factorization
- Here, $$F$$ always denotes a field
- In $$\mathbb{Z}$$ there are only two units, $$\pm 1$$ - polynomial rings can have more units
- Elements $$a$$ in commutative rings with identity $$R$$ are associates of an element $$b \in R$$ if $$a = bu$$ for some unit $$u$$
  - In $$\mathbb{Z}$$, $$a$$ and $$b$$ are associates iff $$a = \pm b$$

$$f(x)$$ is an associate of $$g(x)$$ in $$F[x]$$ iff $$f(x) = cg(x)$$ for some nonzero $$c \in F$$

- A nonzero integer $$p$$ is prime in $$\mathbb{Z}44 if it is not $$ \pm 1$$ and its only divisors are $$\pm 1$$ and $$\pm p$$, the associates of $$p$$

**Definition.**
Let $$F$$ be a field.
A nonconstant polynomial $$p(x) \in F[x]$$ is irreducible if its only divisor are its associates and units (nonzero constant polynomials).
A nonconstant polynomial that is not irreducible is reducible.

Every polynomial of degree 1 in $$F[x]$$ is irreducible in $$F[x]$$.

**Theorem 4.11.**
Let $$F$$ be a field.
A nonzero polynomial $$f(x)$$ is reducible in $$F[x]$$ iff $$f(x)$$ can be written as the product of two polynomials of lower degree.

- Irreducibles in $$F[x]$$ have the same divisibility properties as primes in $$\mathbb{Z}$$

**Theorem 4.12.**
Let $$F$$ be a field and $$p(x)$$ be a nonconstant polynomial in $$F[x]$$.
Then the following conditions are equivalent.
1. $$p(x)$$ is irreducible
2. If $$b(x)$$ and $$c(x)$$ are polynomials such that $$p(x) \vert b(x) c(x)$$, then $$p(x) \vert b(x)$$ or $$p(x) \vert c(x)$$
3. If $$r(x)$$ and $$s(x)$$ are any polynomials such that $$p(x) = r(x) s(x)$$, then $$r(x)$$ or $$s(x)$$ is a nonzero constant polynomial.

**Corollary 4.13.**
Let $$F$$ be a field and $$p(x)$$ an irreducible polynomial in $$F[x]$$.
If $$p(x) \vert a_1(x) a_2(x) \hdots a_n(x)$$, then $$p(x)$$ divides at least one of the $$a_i(x)$$.

**Theorem 4.14.**
Let $$F$$ be a field.
Every nonconstant polynomial $$f(x)$$ in $$F[x]$$ is a product of irreducible polynomials in $$F[x]$$.
This factorization is unique, such that when ordered and relabelled, every element is an associate in the parallel factorization.

### 4.4: Polynomial Functions, Roots, and Reducibility

- What are criteria for the irreducibility of polynomials (e.g. primality testing)
- Every polynomial induces a function from $$F$$ to $$F$$
- $$R$$ is a commutative ring
- Polynomial function $$f : R \to R$$, for each $$r \in R$$, $$f(r) = a_n r^n + ... + a_2 r^2 + a_1r + a_0$$
- $$x$$ can be treated as indeterminate or determinate, and yielding different results

**Definition.**
Let $$R$$ be a commutative ring and $$f(x) \in R[x]$$.
An element $$a$$ of $$R$$ is said to be a root (or zero) of the polynomial $$f(x)$$ if $$f(a) = 0_R$$, that is, if the induced function $$f : R \to R$$ maps $$a$$ to $$0_R$$.

**Theorem 4.15.**
The Remainder Theorem.
Let $$F$$ be a field, $$f(x) \in F[x]$$, and $$a \in F$$.
The remainder when $$f(x)$$ is divided by the polynomial $$x - a$$ is $$f(a)$$.

**Theorem 4.16.**
The Factor Theorem.
Let $$F$$ be a field, $$f(x) \in F[x]$$, and $$a \in F$$. 
Then $$a$$ is a root of the polynomial $$f(x)$$ iff $$x - a$$ is a factor of $$f(x)$$ in $$F[x]$$.

**Corollary 4.17.**
Let $$F$$ be a field and $$f(x)$$ a nonzero polynomial of degree $$n$$ in $$F[x]$$.
Then $$f(x)$$ has at most $$N$$ roots in $$F$$.

**Corollary 4.18.**
Let $$F$$ be a field and $$f(x) \in F[x]$$, with $$\deg f(x) \ge 2$$.
If $$f(x)$$ is irreducible in $$F[x]$$, then $$f(x)$$ has no roots in $$F$$.

**Corollary 4.19.**
Let $$F$$ be a field and let $$f(x) \in F[x]$$ be a polynomial of degree $$2$$ or $$3$$.
Then $$f(x)$$ is irreducible in $$F[x]$$ iff $$f(x)$$ has no roots in $$F$$.

**Corollary 4.20.**
Let $$F$$ be an infinite field and $$f(x), g(x) \in F[x]$$.
Then $$f(x)$$ and $$g(x)$$ induce the same function from $$F$$ to $$F$$ iff $$f(x) = g(x)$$ in $$F[x]$$.


### 4.5: Irreducibility in $$\mathbb{Q}[x]$$

- Factoring in $$\mathbb{Q}[x]$$ can be reduced to factoring in $$\mathbb{Z}[x]$$.
- If $$f(x) \in \mathbb{Q}[x]$$, then $$cf(x)$$ has integer coefficients for some nonzero integer $$c$$.
- Factor theorem: finding first-degree factors of a polynomial in $$\mathbb{Q}[x]$$ is equivlaent to finding the roots of $$g(x) \in \mathbb{Q}$$.

**Theorem 4.21.** The Rational Root Test.
Let $$f(x) = a_n x^n + a_{n-1} x^{n-1} + \hdots + a_1 x + a_0$$ be a polynomial with integer coefficients.
If $$r \neq 0$$ and the rational number $$r/s$$ in lowest terms is a root of $$f(x)$$, then $$r \vert a_0$$ and $$s \vert a_n$$.

- If $$f(x) \in \mathbb{Q}[x]$$, then $$cf(x)$$ has integer coefficients for some nonzero integer $$c$$.

**Lemma 4.22.**
Let $$f(x), g(x), h(x) \in \mathbb{Z}[x]$$ with $$f(x) = g(x) h(x)$$.
If $$p$$ is a prime that divides every coefficient of $$h(x)$$, then either $$p$$ divides every coefficient of $$g(x)$$ or $$p$$ divides every coefficient of $$h(x)$$. 

**Theorem 4.23.**
Let $$f(x)$$ be a polynomial with integer coefficients.
Then $$f(x)$$ factors as a product of polynomials of degrees $$m$$ and $$n$$ in $$\mathbb{Q}[x]$$ iff $$f(x)$$ factors as a product of polynomials of degrees $$m$$ and $$n$$ in $$\mathbb{Z}[x]$$.

**Theorem 4.24.**
Eisenstein's Criterion.
Let $$f(x) = a_n x^n + \hdots + a_1 x + a_0$$ be a nonconstant polynomial with integer coefficients.
If there is a prime $$p$$ such that $$p$$ divides each of $$a-0, a_1, \hdots, a_{n-1}$$ but $$p$$ does not divide $$a_n$$ and $$p^2$$ does not divide $$a_0$$, then $$f(x)$$ is irreducible in $$\mathbb{Q}[x]$$.

The polynomial $$x%n + 5$$ is reducible in $$\mathbb{Q}[x]$$ for each $$n \ge 1$$.
Therefore, there are irreducible polynomials of every degree in $$\mathbb{Q}[x]$$.

If $$f(x) = a_k x^k + \hdots + a_1 x + a_0$$, $$\bar{f}(x) = [a_k] x^k + \hdots + [a_1] x + [a_0] \in \mathbb{Z}_p[x]$$.
These two polynomials will have the same degree when the leading coefficient of $$f(x)$$ is not divisible by $$p$$.

**Theorem 4.25.**
Let $$f(x) = a_k x^k + \hdots + a_1 x + a_0$$ be a polynomial with integer coefficients, and let $$p$$ be a positiv eprime that does not divide $$a_k$$. 
If $$\bar{f}(x)$$ is irreducible in $$\mathbb{Z}_p[x]$$, then $$f(x)$$ is irreducible in $$\mathbb{Q}[x]$$.

For every non-negative integer $$k$$, there are only finitely many polynomials of degree $$k$$ in $$\mathbb{Z}_p[x]$$, so in fact you can determine whether any given polynomial in $$\mathbb{Z}_p$$ is irreducible by checking a finite number of factors.

---

## Chapter 5: Congruence in $$F[x]$$ and Congruence-Class Arithmetic

- Concepts of congruence and congruence-class arithmetic carry over from $$\mathbb{Z}$$ to $$F[x]$$ with basically no changes.
- New congruence-class rings have a much richer structure than rings $$\mathbb{Z}_n$$
- Given any polynomial over any field, we can find a root of that polynomial in some larger field.

### 5.1: Congruence in $$F[x]$$ and Congruence Classes
- Basic facts about divisibility in $$\mathbb{Z}$$ support the concept of congruence in the integers.
- If $$F$$ is a field, the polynomial ring $$F[x]$$ has the same divisibility properties as $$\mathbb{Z}$$.

**Definition.**
Let $$F$$ be a field and $$f(x), g(x), p(x) \in F[x]$$ with $$p(x)$$ nonzero.
Then $$f(x)$$ is congruent to $$g(x)$$ mod $$p(x)$$, $$f(x) \equiv_{p(x)} g(x)$$, given $$p(x) \vert f(x) - g(x)$$.

**Theorem 5.1.**
Let $$F$$ be a field and $$p(x)$$ a nonzero polynomial in $$F[x]$$. Then the relation of congruence modulo $$p(x)$$ is
1. reflexive: $$f(x) \equiv_{p(x)} f(x), \forall f(x) \in F[x]$$
2. symmetric: if $$f(x) \equiv_{p(x)} g(x)$$, then $$g(x) \equiv_{p(x)} f(x)$$
3. transitive: if $$f(x) \equiv_{p(x)} g(x)$$ and $$g(x) \equiv_{p(x)} h(x)$$, then $$f(x) \equiv_{p(x)} h(x)$$

**Theorem 5.2.**
Let $$F$$ be a field and $$p(x)$$ a nonzero polynomial in $$F[x]$$.
If $$f(x) \equiv_{p(x)} g(x)$$ and $$h(x) \equiv_{p(x)} k(x)$$, then
1. $$f(x) + h(x) \equiv_{p(x)} g(x) + k(x)$$
2. $$f(x) h(x) \equiv_{p(x)} g(x) k(x)$$

**Definition.**
The congruence class / residue class of $$f(x)$$ modulo $$p(x)$$ is $$[f(x)]$$ and consists of all polynomials in $$F[x]$$ which are congruent to $$f(x)$$ modulo $$p(x)$$.

$$[f(x)] = \{ g(x) \vert g(x) \in F[x] \wedge g(x) \equiv_{p(x)} f(x) \}

Some algebra shows that

$$[f(x)] = \{ f(x) + k(x) p(x) \vert k(x) \in F[x] \}$$

**Theorem 5.3.**
$$f(x) \equiv_{p(x)} g(x)$$ iff $$[f(x)] = [g(x)]$$.

**Corollary 5.4.**
Two congruence classes modulo $$p(x)$$ are either disjoint or identical.

**Corollary 5.5.**
Let $$F$$ be a field and $$p(x)$$ a polynomial of degree $$n$$ in $$F[x]$$, and consider congruence modulo $$p(x)$$.
1. If $$f(x) \in F[x]$$ and $$r(x)$$ is the remainder when $$f(x)$$ is divided by $$p(x)$$, then $[f(x)] = [r(x)]$$.
2. Let $$S$$ be the set consisting of the zero polynomial and all the polynomials of degree less than $$n$$ in $$F[x]$$. Then every congruence class modulo $$p(x)$$ is the class of some polynomial in $$S$$, and the congruence calsses of different polynomials in $$S$$ are distinct. 

---

### 5.2: Congruence-Class Arithmetic
- 

















