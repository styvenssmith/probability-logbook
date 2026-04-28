## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 53
- Difficulty (1–5): 1

---

## Problem Statement

A worker has asked her supervisor for a letter of recommendation for a new job. She estimates that there is an 80 percent chance that she will get the job if she receives a strong recommendation, a 40 percent chance if she receives a moderately good recommendation, and a 10 percent chance if she receives a weak recommendation. She further estimates that the probabilities that the recommendation will be strong, moderate, and weak are 0.7, 0.2, and 0.1, respectively.

a. How certain is she that she will receive the new job offer?  
b. Given that she does receive the offer, how likely should she feel that she received a strong recommendation? a moderate recommendation? a weak recommendation?  
c. Given that she does not receive the job offer, how likely should she feel that she received a strong recommendation? a moderate recommendation? a weak recommendation?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Law of total probability + Bayes’ theorem.

- What is random vs fixed?  
  → Random: type of recommendation, then job offer outcome. Fixed: given probabilities.

- What is the smallest useful variable definition?  
  Let \( S, M, W \) = strong, moderate, weak recommendation.  
  Let \( J \) = receives job offer.

---

## My First Attempt

Straightforward plug-and-chug:  
- Part (a): \( P(J) = \sum P(J \mid \text{type}) P(\text{type}) \)  
- Part (b): \( P(\text{type} \mid J) = P(J \mid \text{type}) P(\text{type}) / P(J) \)  
- Part (c): similar with \( J^c \)

---

## Solution Strategy
- Step 1: Compute \( P(J) \) using total probability.
- Step 2: Use Bayes to find posterior probabilities given \( J \).
- Step 3: Use Bayes to find posterior probabilities given \( J^c \).

Why this works: Recommendation type partitions the sample space; job offer probability depends only on recommendation type.

---

## Full Solution

**Given:**  
\( P(S) = 0.7,\; P(M) = 0.2,\; P(W) = 0.1 \)  
\( P(J \mid S) = 0.8,\; P(J \mid M) = 0.4,\; P(J \mid W) = 0.1 \)  
Thus \( P(J^c \mid S) = 0.2,\; P(J^c \mid M) = 0.6,\; P(J^c \mid W) = 0.9 \)

---

### a. Probability of receiving job offer

\[
P(J) = (0.8)(0.7) + (0.4)(0.2) + (0.1)(0.1)
\]
\[
= 0.56 + 0.08 + 0.01 = 0.65
\]

---

### b. Given job offer, probability of each recommendation type

\[
P(S \mid J) = \frac{0.8 \times 0.7}{0.65} = \frac{0.56}{0.65} \approx 0.86154
\]
\[
P(M \mid J) = \frac{0.4 \times 0.2}{0.65} = \frac{0.08}{0.65} \approx 0.12308
\]
\[
P(W \mid J) = \frac{0.1 \times 0.1}{0.65} = \frac{0.01}{0.65} \approx 0.01538
\]

---

### c. Given no job offer, probability of each recommendation type

\( P(J^c) = 1 - 0.65 = 0.35 \)

\[
P(S \mid J^c) = \frac{0.2 \times 0.7}{0.35} = \frac{0.14}{0.35} = 0.4
\]
\[
P(M \mid J^c) = \frac{0.6 \times 0.2}{0.35} = \frac{0.12}{0.35} \approx 0.34286
\]
\[
P(W \mid J^c) = \frac{0.9 \times 0.1}{0.35} = \frac{0.09}{0.35} \approx 0.25714
\]

---

## Final Answer

**a.** \( \boxed{0.65} \)

**b.** \( \boxed{0.8615,\ 0.1231,\ 0.0154} \) (S, M, W respectively)

**c.** \( \boxed{0.4,\ 0.3429,\ 0.2571} \) (S, M, W respectively)

---

## Pattern Recognition
- Pattern type: Three-state Bayes with binary observation (job offer or not).
- Key trick: Compute \( P(J) \) first, then \( P(J^c) = 1 - P(J) \).
- Similar problems: Insurance risk classes (3.52), medical testing (3.51).

---

## Key Insight (1–2 lines)

The posterior probabilities shift dramatically: given job offer, strong recommendation is very likely; given no offer, weak recommendation becomes much more plausible.

---

## Mistakes / Lessons
- What I got wrong: Nothing — straightforward.
- What I will remember: For Bayes with multiple categories, just compute numerator for each and divide by same denominator.

Tags: law of total probability, Bayes' theorem, recommendation letter, job offer
