## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.20
- Difficulty (1–5): 2

---

## Problem Statement

A total of 48 percent of the women and 37 percent of the men who took a certain "quit smoking" class remained nonsmokers for at least one year after completing the class. These people then attended a success party at the end of a year. If 62 percent of the original class was male,

a. what percentage of those attending the party were women?
b. what percentage of the original class attended the party?

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability, law of total probability, Bayes' theorem.

- What is random vs fixed?  
  Random: gender and success status. Fixed: given percentages.

- What is the smallest useful variable definition?  
  \(M\): male, \(W\): female, \(S\): successful (attended party).

---

## My First Attempt

I used total probability to find \(P(S)\) (part b), then Bayes to find \(P(W \mid S)\) (part a).

---

## Solution Strategy

- Step 1: Write given probabilities: \(P(M) = 0.62\), \(P(W) = 0.38\), \(P(S \mid W) = 0.48\), \(P(S \mid M) = 0.37\).
- Step 2: Compute \(P(S) = P(S \mid W)P(W) + P(S \mid M)P(M)\) (part b).
- Step 3: Compute \(P(W \mid S) = \frac{P(S \mid W)P(W)}{P(S)}\) (part a).

Why this works: Direct application of total probability and Bayes' theorem.

---

## Full Solution

Let \(M\) = male, \(W\) = female, \(S\) = successful (attended party).

Given:  
\(P(M) = 0.62\), \(P(W) = 0.38\)  
\(P(S \mid W) = 0.48\)  
\(P(S \mid M) = 0.37\)

**Part (b):**  
\[
P(S) = P(S \mid W)P(W) + P(S \mid M)P(M)
\]
\[
P(S) = 0.48 \times 0.38 + 0.37 \times 0.62
\]
\[
= 0.1824 + 0.2294 = 0.4118
\]
So 41.18% of the original class attended.

**Part (a):**  
\[
P(W \mid S) = \frac{P(S \mid W)P(W)}{P(S)} = \frac{0.48 \times 0.38}{0.4118}
\]
\[
= \frac{0.1824}{0.4118} \approx 0.4429
\]
So 44.29% of attendees were women.

---

## Final Answer

\[
\text{(a) } \boxed{44.29\%}, \quad \text{(b) } \boxed{41.18\%}
\]

---

## Pattern Recognition

- Pattern type: Bayes' theorem with two groups.
- Key trick: Find total success rate first, then invert conditional.
- Similar problems: Any "X% of A and Y% of B" with given group sizes.

---

## Key Insight (1–2 lines)

Total probability gives the overall success rate; Bayes then gives the proportion of successes coming from each group.

---

## Mistakes / Lessons

- What I got wrong: Nothing — straightforward.
- What I will remember:  
  When given group-specific success rates and group sizes,  
  \(P(\text{success}) = \sum P(\text{success} \mid \text{group}) P(\text{group})\).  
  Then \(P(\text{group} \mid \text{success}) = \frac{P(\text{success} \mid \text{group}) P(\text{group})}{P(\text{success})}\).

Tags: probability, bayes-theorem, total-probability, conditional-probability, smoking-cessation
