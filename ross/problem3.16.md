## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.16
- Difficulty (1–5): 2

---

## Problem Statement

An ectopic pregnancy is twice as likely to develop when the pregnant woman is a smoker as it is when she is a nonsmoker.  
If 32 percent of women of childbearing age are smokers, what percentage of women having ectopic pregnancies are smokers?

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability / Bayes’ theorem.

- What is random vs fixed?  
  Random: smoking status, ectopic pregnancy occurrence.  
  Fixed: given probabilities (32% smokers, relative risk 2:1).

- What is the smallest useful variable definition?  
  \(S\): smoker, \(E\): ectopic pregnancy.

---

## My First Attempt

I tried using the law of total probability:  
\(P(S) = P(S \mid E)P(E) + P(S \mid E^c)P(E^c)\) — but that’s not directly helpful.  
Better: Start with Bayes: \(P(S \mid E) = \frac{P(E \mid S)P(S)}{P(E)}\).

---

## Solution Strategy

- Step 1: Let \(x = P(E \mid N)\) where \(N = S^c\) (nonsmoker). Then \(P(E \mid S) = 2x\).
- Step 2: Use total probability to find \(P(E) = P(E \mid S)P(S) + P(E \mid N)P(N)\).
- Step 3: Plug into Bayes’ formula; \(x\) cancels.

Why this works: The unknown baseline risk \(x\) cancels, leaving a pure function of known smoking rate and relative risk.

---

## Full Solution

Let \(S\) = smoker, \(N = S^c\) = nonsmoker, \(E\) = ectopic pregnancy.

Given:  
\(P(S) = 0.32\), \(P(N) = 0.68\)  
\(P(E \mid S) = 2 \cdot P(E \mid N)\)

Let \(x = P(E \mid N)\). Then \(P(E \mid S) = 2x\).

By total probability:
\[
P(E) = P(E \mid S)P(S) + P(E \mid N)P(N) = 2x(0.32) + x(0.68) = 0.64x + 0.68x = 1.32x
\]

By Bayes’ theorem:
\[
P(S \mid E) = \frac{P(E \mid S)P(S)}{P(E)} = \frac{2x \cdot 0.32}{1.32x} = \frac{0.64}{1.32} = \frac{64}{132} = \frac{16}{33}
\]

As a percentage:
\[
\frac{16}{33} \times 100\% \approx 48.48\%
\]

---

## Final Answer

\[
\boxed{\frac{16}{33}} \quad (\text{about } 48.48\%)
\]

---

## Pattern Recognition

- Pattern type: Bayes’ theorem with relative risk.
- Key trick: Let the unknown baseline probability cancel by expressing everything in terms of it.
- Similar problems: Disease screening with given sensitivity/specificity and prevalence; "twice as likely" problems.

---

## Key Insight (1–2 lines)

When given "A is twice as likely as B", set \(P(A) = 2P(B)\) and let the baseline cancel.  
You don’t need the actual numeric risk, only the ratio.

---

## Mistakes / Lessons

- What I got wrong: Initially tried law of total probability on \(P(S)\) instead of Bayes — wrong direction.
- What I will remember:  
  "Twice as likely" means \(P(E \mid S) = 2 \cdot P(E \mid N)\).  
  In Bayes, if numerator and denominator both contain the same unknown factor, it cancels.

Tags: probability, bayes-theorem, conditional-probability, relative-risk, medical-statistics
