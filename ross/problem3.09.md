## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.9
- Difficulty (1–5): 3

---

## Problem Statement

Urn A: 2 white, 4 red  
Urn B: 8 white, 4 red  
Urn C: 1 white, 3 red  

One ball is selected from each urn.  
Find \( P(\text{ball from A is white} \mid \text{exactly 2 white balls are selected}) \).

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability with Bayes' Theorem.

- What is random vs fixed?  
  Random: color of ball from each urn. Fixed: urn compositions.

- What is the smallest useful variable definition?  
  \(W_A\): A's ball white, \(W_B\): B's ball white, \(W_C\): C's ball white.  
  \(E\): exactly 2 white balls total.

---

## My First Attempt

We want \(P(W_A \mid E)\).  

By Bayes:  
\[
P(W_A \mid E) = \frac{P(E \mid W_A) P(W_A)}{P(E)}
\]

- \(P(W_A) = \frac{2}{6} = \frac13\)  
- \(P(E \mid W_A) = P(\text{exactly 1 of B or C white}) = P(W_B \cap R_C) + P(R_B \cap W_C)\)  
  = \( \frac{2}{3} \cdot \frac{3}{4} + \frac{1}{3} \cdot \frac{1}{4} = \frac12 + \frac{1}{12} = \frac{7}{12} \)  

- \(P(E) = P(W_A, W_B, R_C) + P(W_A, R_B, W_C) + P(R_A, W_B, W_C)\)  
  = \(\frac13 \cdot \frac23 \cdot \frac34 + \frac13 \cdot \frac13 \cdot \frac14 + \frac23 \cdot \frac23 \cdot \frac14\)  
  = \(\frac{6}{36} + \frac{1}{36} + \frac{4}{36} = \frac{11}{36}\)

Thus:  
\[
P(W_A \mid E) = \frac{ \frac{7}{12} \cdot \frac13 }{ \frac{11}{36} } = \frac{ \frac{7}{36} }{ \frac{11}{36} } = \frac{7}{11}
\]

---

## Solution Strategy

- Step 1: Identify \(P(W_A), P(W_B), P(W_C)\) from urn compositions.
- Step 2: Compute \(P(E \mid W_A)\) = probability exactly 1 more white in B and C total given A is white.
- Step 3: Compute \(P(E)\) (total probability of exactly 2 whites).
- Step 4: Apply Bayes' Theorem.

Why this works: Bayes' theorem directly conditions on \(E\), which is a global event over all three draws.

---

## Full Solution

Let \(W_A\) = white from A, similarly \(W_B, W_C\), and \(R_X = \overline{W_X}\).  

Given compositions:  
\(P(W_A) = \frac{2}{6} = \frac13 \), \(P(W_B) = \frac{8}{12} = \frac23\), \(P(W_C) = \frac14\)  
\(P(R_A) = \frac23\), \(P(R_B) = \frac13\), \(P(R_C) = \frac34\)

We want \(P(W_A \mid E)\) where \(E\) = exactly 2 whites total.

By Bayes:
\[
P(W_A \mid E) = \frac{P(E \mid W_A)P(W_A)}{P(E)}
\]

**Compute \(P(E \mid W_A)\):**  
Given \(W_A\), we need exactly one white among B and C:
\[
P(E \mid W_A) = P(W_B, R_C) + P(R_B, W_C) = \frac23 \cdot \frac34 + \frac13 \cdot \frac14 = \frac12 + \frac{1}{12} = \frac{7}{12}
\]

**Compute \(P(W_A)\):**  
\[
P(W_A) = \frac13
\]

**Compute \(P(E)\):**  
Exactly 2 whites can happen in 3 disjoint ways:
1. A white, B white, C red: \( \frac13 \cdot \frac23 \cdot \frac34 = \frac{6}{36} = \frac16 \)
2. A white, B red, C white: \( \frac13 \cdot \frac13 \cdot \frac14 = \frac{1}{36} \)
3. A red, B white, C white: \( \frac23 \cdot \frac23 \cdot \frac14 = \frac{4}{36} = \frac19 \)

Sum: \(\frac{6}{36} + \frac{1}{36} + \frac{4}{36} = \frac{11}{36}\)

**Apply Bayes:**
\[
P(W_A \mid E) = \frac{ \frac{7}{12} \cdot \frac13 }{ \frac{11}{36} } = \frac{ \frac{7}{36} }{ \frac{11}{36} } = \frac{7}{11}
\]

---

## Final Answer

\[
\boxed{\frac{7}{11}}
\]

---

## Pattern Recognition

- Pattern type: Conditional probability with "given exactly k successes" — use Bayes or count favorable cases in reduced sample space.
- Key trick: Compute \(P(E)\) using disjoint cases (three ways to get exactly 2 whites).
- Similar problems: Urn problems with conditional "given total count"; e.g., Ross 3.8, 3.10.

---

## Key Insight (1–2 lines)

When "given exactly 2 whites from 3 independent draws," fixing \(W_A\) forces exactly 1 white in {B, C}, making the posterior ratio clean.

---

## Mistakes / Lessons

- What I got wrong: Nothing here — correctly set up Bayes.
- What I will remember:  
  \(P(E \mid W_A)\) is not \(P(E)\); computing \(P(E)\) requires partitioning by which urn(s) have whites.

Tags: probability, bayes-theorem, conditional-probability, urns
