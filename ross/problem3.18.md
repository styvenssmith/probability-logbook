## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.18
- Difficulty (1–5): 1

---

## Problem Statement

In a certain community, 36 percent of the families own a dog and 22 percent of the families that own a dog also own a cat. In addition, 30 percent of the families own a cat. What is  

a. the probability that a randomly selected family owns both a dog and a cat?  
b. the conditional probability that a randomly selected family owns a dog given that it owns a cat?

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Basic conditional probability, intersection from conditional, then Bayes-type conditional.

- What is random vs fixed?  
  Random: dog/cat ownership status. Fixed: given percentages.

- What is the smallest useful variable definition?  
  \(D\): owns a dog, \(C\): owns a cat.

---

## My First Attempt

I used \(P(C \mid D) = P(C \cap D) / P(D)\) to find \(P(C \cap D)\), then \(P(D \mid C) = P(C \cap D) / P(C)\).

---

## Solution Strategy

- Step 1: Use \(P(C \mid D) = \frac{P(C \cap D)}{P(D)}\) to solve for \(P(C \cap D)\).
- Step 2: Use \(P(D \mid C) = \frac{P(C \cap D)}{P(C)}\) to find the second answer.

Why this works: Direct application of conditional probability definition.

---

## Full Solution

Let \(D\) = owns a dog, \(C\) = owns a cat.

Given:  
\(P(D) = 0.36\)  
\(P(C \mid D) = 0.22\)  
\(P(C) = 0.30\)

**Part (a):**

\[
P(C \cap D) = P(C \mid D) \cdot P(D) = 0.22 \times 0.36 = 0.0792
\]

**Part (b):**

\[
P(D \mid C) = \frac{P(C \cap D)}{P(C)} = \frac{0.0792}{0.30} = 0.264
\]

---

## Final Answer

\[
\text{(a) } \boxed{0.0792}, \quad \text{(b) } \boxed{0.264}
\]

---

## Pattern Recognition

- Pattern type: Two-step conditional probability.
- Key trick: Intersection from one conditional, then flip the conditional using the other marginal.
- Similar problems: Any “X% of A are B” and “Y% total are B” problems.

---

## Key Insight (1–2 lines)

You don’t need Bayes' theorem explicitly here — just the definition of conditional probability twice.

---

## Mistakes / Lessons

- What I got wrong: Nothing — straightforward.
- What I will remember:  
  When given \(P(B \mid A)\) and \(P(A)\), \(P(A \cap B) = P(B \mid A) P(A)\).  
  Then \(P(A \mid B) = P(A \cap B) / P(B)\).

Tags: probability, conditional-probability, intersection, bayes, pets
