## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.12
- Difficulty (1–5): 2

---

## Problem Statement

Suppose distinct values are written on each of 3 cards, which are then randomly given the designations \( A \), \( B \), and \( C \). Given that card A’s value is less than card B’s value, find the probability it is also less than card C’s value.

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability with random permutations.

- What is random vs fixed?  
  Random: assignment of distinct values to positions A, B, C. Fixed: the set of 3 distinct values (relative order matters, actual numbers don't).

- What is the smallest useful variable definition?  
  Represent values as 1, 2, 3 (smallest to largest). Each permutation of (1,2,3) assigned to (A,B,C) equally likely (3! = 6 outcomes).

---

## My First Attempt

I thought: the probability that A is smaller than both B and C given A < B is just the probability A is the smallest given A < B, maybe 1/3.  
I mistakenly computed joint probability \(P(A<B \text{ and } A<C) = 1/3\) and forgot to divide by \(P(A<B)\).

---

## Solution Strategy

- Step 1: List all 6 permutations of {1,2,3} for (A,B,C).
- Step 2: Identify which satisfy \(A < B\).
- Step 3: Among those, count how many satisfy \(A < C\).
- Step 4: Compute conditional probability = (favorable count)/(total given count).

Why this works: Finite equiprobable sample space, direct enumeration.

---

## Full Solution

Let values be 1 < 2 < 3.  
All permutations of (A,B,C) equally likely (6 total).

List permutations (value of A, value of B, value of C):

1. (1,2,3)  
2. (1,3,2)  
3. (2,1,3)  
4. (2,3,1)  
5. (3,1,2)  
6. (3,2,1)

**Given \(A < B\)** (event we condition on):  
Check each:

1. 1<2 ✅  
2. 1<3 ✅  
3. 2<1 ❌  
4. 2<3 ✅  
5. 3<1 ❌  
6. 3<2 ❌

So outcomes with \(A<B\): #1, #2, #4 → 3 outcomes.

**Now check \(A < C\) among these:**

#1: (1,2,3): A=1, C=3 → 1<3 ✅  
#2: (1,3,2): A=1, C=2 → 1<2 ✅  
#4: (2,3,1): A=2, C=1 → 2<1 ❌

Favorable outcomes: #1, #2 → 2 outcomes.

Thus:
\[
P(A < C \mid A < B) = \frac{2}{3}
\]

---

## Final Answer

\[
\boxed{\frac{2}{3}}
\]

---

## Pattern Recognition

- Pattern type: Conditional probability, symmetry in permutations.
- Key trick: Instead of complex formulas, list all possibilities in small sample space.
- Similar problems: "Given A precedes B in a random permutation, find probability A precedes C."

---

## Key Insight (1–2 lines)

Don't confuse joint probability \(P(A<B \text{ and } A<C)\) with conditional \(P(A<C \mid A<B)\). Always divide by \(P(A<B)\) when computing conditional.

---

## Mistakes / Lessons

- What I got wrong: Computed joint = 1/3 and stopped; forgot to divide by \(P(A<B) = 1/2\).
- What I will remember:  
  \(P(X \mid Y) = P(X \cap Y)/P(Y)\), not just \(P(X \cap Y)\).

Tags: probability, conditional-probability, permutations, symmetry
