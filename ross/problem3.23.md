## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: 3.23
- Difficulty (1–5): 2

---

## Problem Statement

A red die, a blue die, and a yellow die (all six-sided) are rolled. Let \( R, B, Y \) denote the numbers on red, blue, yellow respectively. Find:

a. \(P(\text{no two dice land on same number})\)
b. \(P(B < Y < R \mid \text{all faces distinct})\)
c. \(P(B < Y < R)\)

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  Probability with dice + ordering conditions.
- What is random vs fixed?  
  Outcomes \((R,B,Y)\) each from \(\{1,\dots,6\}\) equally likely.
- What is the smallest useful variable definition?  
  The three dice outcomes as an ordered triple.

---

## My First Attempt

Part (a) — counting: total outcomes \(6^3 = 216\), number with all distinct = \( \binom{6}{3} \cdot 3! = 20 \cdot 6 = 120\), so \( \frac{120}{216} = \frac{5}{9} \).

Part (b) — given all distinct: there are \(3!\) permutations of the three distinct numbers, only 1 has \(B<Y<R\), so \( \frac{1}{6} \).

Part (c) — unconditional: I originally just multiplied parts a and b by total probability law without thinking about it, but it made sense because if there’s a tie, \(B<Y<R\) is impossible.

---

## Solution Strategy
- Step 1: Count total outcomes for all distinct in part a.
- Step 2: Use symmetry for conditional probability in part b.
- Step 3: Use law of total probability with “all distinct” as partition for part c.

Why this works: Because \(B<Y<R\) can only happen when all distinct, so conditioning on that event captures all favorable cases.

---

## Full Solution

a) Outcomes: \(6^3 = 216\).  
Choose 3 distinct numbers: \(\binom{6}{3} = 20\) sets.  
Assign permutations: \(3! = 6\) ways.  
Favorable: \(20 \times 6 = 120\).  
\[
P(\text{all distinct}) = \frac{120}{216} = \frac{5}{9}.
\]

b) Given all distinct, the 3 numbers (say \(a<b<c\) in value order) are randomly permuted among the 3 dice. Only 1 of \(3! = 6\) permutations has \(B<Y<R\).  
\[
P(B<Y<R \mid \text{all distinct}) = \frac{1}{6}.
\]

c) The event \(B<Y<R\) implies all distinct (since strict inequalities across 3 dice).  
Use law of total probability:

\[
P(B<Y<R) = P(B<Y<R \mid \text{all distinct})\, P(\text{all distinct})
\]
\[
= \frac{1}{6} \times \frac{5}{9} = \frac{5}{54}.
\]

---

## Final Answer

\[
\boxed{\frac{5}{9}, \ \frac{1}{6}, \ \frac{5}{54}}
\]

---

## Pattern Recognition
- Pattern type: Dice ordering with symmetry / “random permutation of distinct values”.
- Key trick: Condition on all distinct, use symmetry to deduce conditional probability = \(1/n!\).
- Similar problems: Birthday problem arrangements, card orderings, random permutations of ranks.

---

## Key Insight (1–2 lines)

\(B<Y<R\) can only happen if all three dice show different values. So unconditional probability = P(all distinct) × 1/(3!) by symmetry among permutations of the distinct ordered triple.

---

## Mistakes / Lessons
- What I got wrong: At first I might have tried a direct count from scratch instead of using total probability and symmetry.
- What I will remember: For “all distinct” + strict ordering among labeled items → probability = 1/(n!) after factoring out all distinct condition.

Tags: `probability`, `dice`, `law-of-total-probability`, `order-statistics`, `symmetry`
