## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.17
- Difficulty (1–5): 2

---

## Problem Statement

Ninety-eight percent of all babies survive delivery. However, 15 percent of all births involve Cesarean (C) sections, and when a C section is performed, the baby survives 96 percent of the time. If a randomly chosen pregnant woman does not have a C section, what is the probability that her baby survives?

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability / law of total probability.

- What is random vs fixed?  
  Random: type of delivery (C-section or not), baby survival outcome.  
  Fixed: given percentages.

- What is the smallest useful variable definition?  
  \(S\): baby survives, \(C\): C-section.

---

## My First Attempt

I used the law of total probability:  
\(P(S) = P(S \mid C)P(C) + P(S \mid C^c)P(C^c)\)  
Then solved for \(P(S \mid C^c)\).

---

## Solution Strategy

- Step 1: Identify known probabilities: \(P(S) = 0.98\), \(P(C) = 0.15\), \(P(S \mid C) = 0.96\).
- Step 2: Apply total probability: \(P(S) = P(S \mid C)P(C) + P(S \mid C^c)P(C^c)\).
- Step 3: Solve for \(P(S \mid C^c)\).

Why this works: The total probability of survival is a weighted average of survival given C-section and survival given no C-section.

---

## Full Solution

Let \(S\) = baby survives, \(C\) = C-section.

Given:  
\(P(S) = 0.98\)  
\(P(C) = 0.15 \Rightarrow P(C^c) = 0.85\)  
\(P(S \mid C) = 0.96\)

By the law of total probability:
\[
P(S) = P(S \mid C)P(C) + P(S \mid C^c)P(C^c)
\]
\[
0.98 = 0.96 \times 0.15 + P(S \mid C^c) \times 0.85
\]
\[
0.98 = 0.144 + 0.85 \times P(S \mid C^c)
\]
\[
0.98 - 0.144 = 0.85 \times P(S \mid C^c)
\]
\[
0.836 = 0.85 \times P(S \mid C^c)
\]
\[
P(S \mid C^c) = \frac{0.836}{0.85} = \frac{836}{850} = \frac{418}{425}
\]

---

## Final Answer

\[
\boxed{\frac{418}{425}} \quad (\text{about } 98.35\%)
\]

---

## Pattern Recognition

- Pattern type: Law of total probability, solving for a conditional probability.
- Key trick: Use total probability to set up equation, then solve for the unknown conditional.
- Similar problems: Medical testing (sensitivity/specificity), two-step processes with partial information.

---

## Key Insight (1–2 lines)

When given \(P(S)\), \(P(C)\), and \(P(S \mid C)\), you can find \(P(S \mid C^c)\) by solving the total probability equation. No Bayes needed here — just algebra.

---

## Mistakes / Lessons

- What I got wrong: Nothing — straightforward application of total probability.
- What I will remember:  
  Total probability is a weighted average; if one weight and one conditional are unknown, solve for it directly.

Tags: probability, total-probability, conditional-probability, medical-statistics
