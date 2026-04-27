## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 50
- Difficulty (1–5): 2

---

## Problem Statement

Each of 2 cabinets identical in appearance has 2 drawers.  
Cabinet A contains a silver coin in each drawer, and cabinet B contains a silver coin in one of its drawers and a gold coin in the other.  

A cabinet is randomly selected, one of its drawers is opened, and a silver coin is found.  

What is the probability that there is a silver coin in the other drawer?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Conditional probability / Bayes’ theorem.

- What is random vs fixed?  
  → Random: which cabinet, then which drawer. Fixed: coin arrangement.

- What is the smallest useful variable definition?  
  \( A \) = cabinet A selected, \( B \) = cabinet B selected.  
  \( S \) = opened drawer contains silver.

---

## My First Attempt

Very straightforward:  
We want \( P(\text{other drawer silver} \mid S) \).  
Other drawer silver ⇔ cabinet A selected (since only cabinet A has both silver).  
So compute \( P(A \mid S) \) using Bayes.

---

## Solution Strategy
- Step 1: Identify that “other drawer silver” = cabinet A.
- Step 2: Compute \( P(S) \) using law of total probability.
- Step 3: Apply Bayes’ theorem to find \( P(A \mid S) \).

Why this works: The problem reduces to finding the probability the chosen cabinet was A given a silver was seen.

---

## Full Solution

**Given:**  
\( P(A) = P(B) = \frac12 \)  
\( P(S \mid A) = 1 \) (both drawers silver)  
\( P(S \mid B) = \frac12 \) (only 1 silver drawer out of 2)

**Step 1 – Total probability for \( P(S) \)**  
\[
P(S) = P(S \mid A)P(A) + P(S \mid B)P(B)
\]
\[
P(S) = (1)\left(\frac12\right) + \left(\frac12\right)\left(\frac12\right) = \frac12 + \frac14 = \frac34
\]

**Step 2 – Bayes’ theorem**  
\[
P(A \mid S) = \frac{P(S \mid A)P(A)}{P(S)} = \frac{1 \cdot \frac12}{\frac34} = \frac{1/2}{3/4} = \frac12 \times \frac43 = \frac23
\]

Thus \( P(\text{other drawer silver} \mid S) = \frac23 \).

---

## Final Answer

\[
\boxed{\frac{2}{3}}
\]

---

## Pattern Recognition
- Pattern type: Bertrand’s box paradox / conditional probability with symmetry.
- Key trick: Recognize that “other drawer silver” = “cabinet A selected” given you saw silver.
- Similar problems: Monty Hall, three prisoners, two-coin problem.

---

## Key Insight (1–2 lines)

Out of the 3 equally likely silver-drawer scenarios (A1, A2, B1), 2 have the other drawer silver → \( 2/3 \).

---

## Mistakes / Lessons
- What I got wrong: Nothing — problem is simple.
- What I will remember: Draw a quick mental table of (cabinet, drawer) pairs, count favorable scenarios.

Tags: conditional probability, Bayes' theorem, Bertrand's box
