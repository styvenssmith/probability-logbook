## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.13
- Difficulty (1–5): 3

---

## Problem Statement

A student takes up to 3 actuarial exams sequentially in summer:  
June (exam 1), July (exam 2 if pass June), September (exam 3 if pass July).  
Given:  
\(P(\text{pass exam 1}) = 0.9\)  
\(P(\text{pass exam 2} \mid \text{pass exam 1}) = 0.8\)  
\(P(\text{pass exam 3} \mid \text{pass exams 1 and 2}) = 0.7\)  

(a) Probability passes all three.  
(b) Given she did **not** pass all three, probability she failed the second exam.

---

## Key Observations (DO BEFORE SOLVING)

- Type: Sequential conditional probability, tree diagram, law of total probability.
- Random: pass/fail each exam given previous passed.
- Fixed: given probabilities.
- Smallest event definitions: \(F_1, F_2, F_3\) = pass exam 1,2,3.

---

## My First Attempt

I computed part (a) correctly.  
For part (b), I initially thought maybe \(P(\text{fail second} \mid T^c) = \frac{P(F_2^c)}{1 - P(T)}\) directly, but forgot to check if \(F_2^c \subset T^c\) — it is, yes, so that formula works. Actually my mistake was checking if failing second equals failing third (they are disjoint).  

---

## Solution Strategy

- Step 1: Compute \(P(T) = P(F_1 \cap F_2 \cap F_3) = 0.9 \times 0.8 \times 0.7\).
- Step 2: Event \(E\) = fail second exam.  
  Ways: fail first OR pass first and fail second.  
  \(P(E) = P(F_1^c) + P(F_1 \cap F_2^c)\)
- Step 3: \(E \subset T^c\) because failing second ⇒ cannot pass all three.  
  So \(E \cap T^c = E\).  
  Thus \(P(E \mid T^c) = P(E)/P(T^c)\).

Why this works: The only way not to pass all three but still pass second is pass first and second and fail third. That case is excluded from \(E\). So \(E\) = failing second is a subset of \(T^c\).

---

## Full Solution

**Part (a):**  
\[
P(T) = 0.9 \times 0.8 \times 0.7 = 0.504
\]

**Part (b):**  
\[
P(T^c) = 1 - 0.504 = 0.496
\]

Fail second exam (\(E\)):  
\[
P(F_1^c) = 0.1
\]
\[
P(F_1 \cap F_2^c) = 0.9 \times 0.2 = 0.18
\]
\[
P(E) = 0.1 + 0.18 = 0.28
\]

Since \(E \subset T^c\):  
\[
P(E \mid T^c) = \frac{0.28}{0.496} = \frac{35}{62}
\]

---

## Final Answer

\[
\text{(a) } \boxed{0.504}, \quad \text{(b) } \boxed{\frac{35}{62}}
\]

---

## Pattern Recognition

- Pattern type: Sequential conditional probability.
- Key trick: Realizing \(F_2^c\) (fail second) ⊂ \(T^c\) (not all three passed) simplifies numerator.
- Similar problems: Anything with "given not all events occurred" where "fail early" events are subset.

---

## Key Insight (1–2 lines)

In sequential exams: Failing second exam = fail first OR pass first and fail second.  
That event is a subset of “not pass all three.”

---

## Mistakes / Lessons

- What I got wrong: Initially thought about “failing second = failing third” — that’s wrong.  
  Failing third ⇒ pass second ⇒ cannot fail second. They are disjoint.

- What I will remember:  
  Fail second and fail third are **mutually exclusive** in sequential pass/fail with no retakes. One implies the other did *not* happen. Not the same event. But for Bayes-type “given not all three passed,” fail second is a subset of that condition.

Tags: probability, conditional-probability, sequential-events, actuarial-exams
