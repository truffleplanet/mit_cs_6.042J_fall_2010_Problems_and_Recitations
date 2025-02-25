# Problem Set 1

<https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-fall-2010/resources/mit6_042jf10_assn01/>

## Problem 1

> Translate the following sentences from English to predicate logic. The domain that you are working over is X, the set of people. You may use the functions S(x), meaning that “x has been a student of 6.042,” A(x), meaning that “x has gotten an ‘A’ in 6.042,” T (x), meaning that “x is a TA of 6.042,” and E(x, y), meaning that “x and y are the same person.”

(a) There are people who have taken 6.042 and have gotten A’s in 6.042

- $\exists x \in X: (S(x) \land A(x))$

(b) All people who are 6.042 TA’s and have taken 6.042 got A’s in 6.042

- $\forall x (S(x)\land T(x)) \rightarrow A(x)$

(c) There are no people who are 6.042 TA’s who did not get A’s in 6.042.

- $\neg \exists x \in X: (T(x)\land\neg A(x))$

(d) There are at least three people who are TA’s in 6.042 and have not taken 6.042

- $|\{x \mid T(x) \land \neg S(x)\}| \geq 3$

## Problem 2

> Use a truth table to prove or disprove the following statements:

(a) ¬(P ∨ (Q ∧ R)) = (¬P ) ∧ (¬Q ∨ ¬R)

(b) ¬(P ∧ (Q ∨ R)) = ¬P ∨ (¬Q ∨ ¬R)

| P | Q | R | ¬(P ∨ (Q ∧ R))  | (¬P ) ∧ (¬Q ∨ ¬R) | ¬(P ∧ (Q ∨ R)) | ¬P ∨ (¬Q ∨ ¬R) |
| --- | --- | --- | --- | --- | --- | --- |
| T | T | T | F | F | F | F |
| T | T | F | F | F | F | T |
| T | F | T | F | F | F | T |
| T | F | F | F | F | T | T |
| F | T | T | F | F | T | T |
| F | T | F | T | T | T | T |
| F | F | T | T | T | T | T |
| F | F | F | T | T | T | T |

- We haven proven that equation (a) holds, but eqaution (b) has been disproven.

## Problem 3

> (a) For each of the following expressions, find an equivalent expression using only (not), as well as grouping parentheses to specify the order in which the operations ¬ apply. You may use A, B, and the operators any number of times.

1. $A \land B = \neg(A \barwedge B)$
2. $A \lor B = \neg A \barwedge \neg B$
3. $A \rightarrow B = A \barwedge \neg B$

| P | Q | $P \barwedge Q$ | $\neg (P\barwedge Q)$ | $P \rightarrow Q$ | $\neg P$ | $\neg Q$ | $\neg P \barwedge \neg Q$ | $P \barwedge \neg Q$ |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| T | T | F | T | T | F | F | T | T |
| T | F | T | F | F | F | T | T | F |
| F | T | T | F | T | T | F | T | T |
| F | F | T | F | T | T | T | F | T |

> (b) It is actually possible to express each of the above using only nand, without needing to use ¬. Find an equivalent expression for (A) using only nand and grouping parentheses.

### Properties

- $A \barwedge A = \neg A$
- $\neg(A\land B) = A\barwedge B$

1. $A \land B = \neg(A \barwedge B) = (A \barwedge B) \barwedge (A \barwedge B)$
2. $A\lor B = \neg(\neg A \land \neg B) = (\neg A \barwedge \neg B) = (A \barwedge A) \barwedge (B\barwedge B)$
3. $A \rightarrow B = \neg A \lor B = \neg (A\land \neg B) = A\barwedge(B\barwedge B)$

> (c)The constants true and false themselves may be expressed using only nand. Construct an expression using an arbitrary statement A and nand that evaluates to true regardless of whether A is true or false. Construct a second expression that always evaluates to false. Do not use the constants true and false themselves in your statements.

- $A \lor \neg A = \neg(\neg A\land A) = (\neg A \barwedge A) = (A \barwedge A)\barwedge A$ is always True.
- So negation of above, is always False. $((A \barwedge A) \barwedge A) \barwedge ((A \barwedge A) \barwedge A)$  is always False.
- or $A \land \neg A  = \neg(A \barwedge \neg A) = \neg(A\barwedge (A\barwedge A)) = \\ \quad(A\barwedge (A\barwedge A)) \barwedge (A\barwedge (A\barwedge A))$

## Problem 4

> You have 12 coins and a balance scale, one of which is fake. All the real coins weigh the same, but the fake coin weighs less than the rest. All the coins visually appear the same, and the diﬀerence in weight is imperceptible to your senses. In at most 3 weighings, give a strategy that detects the fake coin. (Note: the scale in this problem is a scale with two dishes, which tips toward the side that is heavier. For clarification, do an image search for “balance scale”).

- 6개 6개씩 반으로 나눠가면서 찾으면 무조건 3번 걸림.

    6:6 중 가벼운쪽 3:3, 가벼운 쪽 1:1, 나머지 1

- 5개 5개 2개로 나누고, 5, 5를 비교했을 시 동일하면, 나머지 2개를 1, 1 비교해서 2번만에 끝. 동일하지 않다면 낮은 무게를 가진 쪽의 5를 2, 2, 1개로 나눠 2, 2 비교. 이때 동일하다면 2번만에 끝, 동일하지 않다면 가벼운 쪽의 2를 1:1로 나눠 가벼운 것 찾으면 된다. 최장 3번.

## Problem 5

>Prove the following statement by proving its contrapositive: if r is irrational, then r1/5 is irrational. (Be sure to state the >contrapositive explicitly.)

Contrapositive: If $r^\frac{1}{5}$ is rational, then $r$ is rational.

If, $r^\frac{1}{5}$ is rational, then we can write it as:

$r^\frac{1}{5} = \frac {a}{b}, \quad a, b \in \mathbb{Z}$ ,  b≠0

Raising both sides to the fifth power, we get:

$r = \frac{a^5}{b^5}$

Since $a^5$ and $b^5$ are both integers, $\frac{a^5}{b^5}$ is a rational number. Thus, $r$ is rational. Since we have proven the contrapositive, it follows that the original statement is true. Therefore, if $r$ is irrational, then $r^\frac{1}{5}$ must be irrational.


## Problem 6

> Suppose that $w^2 + x^2 + y^2 = z^2$, where w, x, y, and z always denote positive integers. (Hint: It may be helpful to represent even integers as 2i and odd integers as 2j + 1, where i and j are integers) Prove the proposition: z is even if and only if w, x, and y are even. Do this by considering all the cases of w, x, y being odd or even.


if w, x and y are even, we can write them as:

$w = 2i_w, x= 2i_x, y = 2i_y, i_w, i_x, i_z \in \mathbb {Z}$

Substituting these into the equation:

$4i_w^2 + 4i_x^2 + 4i_y^2 = z^2$

Since the left-hand side is clearly divisible by 4, $z^2$ must also be divisible by 4. This implies that $z$ itself must be even(since the square of an odd number is congruent to 1 modulo 4). Therefore we can write:

$z=2i_z, i_z \in \mathbb{Z}$

An odd integer can be written as $2i +1$, and its sqaure expands as:

$(2i +1)^2 = 4(i^2 + i) +1$

This means that square of an odd number is always congruent to 1 mod 4.

Now, consider the sum $w^2 + x^2 + y^2$

- If one of $w, x, y$ is odd, then the sum is $4k + 1$ for some integer $k$.
- If two of $w, x, y$ is odd, then the sum is $4k + 2$ for some integer $k$.
- If all three are odd, then the sum is $4k+3$.

For $w^2 + x^2 + y^2 = z^2$ to hold, $z^2$ must also follow one of these forms. However, since $z^2$ must be either 0 mod 4 (if $z$ is even) or 1 mod 4(if $z$ is odd), we see that only way for $z$ to be even is if all three of $w, x, y$ are also even.

Thus, we conclude that if $z$ is even, then $w, x, y$ must be even as well.
