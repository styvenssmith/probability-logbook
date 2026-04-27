## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: 3.41 (based on Example 3a)
- Difficulty (1–5): 2

---

## Problem Statement

An insurance company believes people are either accident prone (AP) or not (NAP).  
- \( P(\text{accident in a year} \mid AP) = 0.4 \)  
- \( P(\text{accident in a year} \mid NAP) = 0.2 \)  
- \( P(AP) = 0.3 \), \( P(NAP) = 0.7 \)

Accidents in different years are independent given AP status.

Given a policyholder had no accident in the first year, what is the probability they have an accident in the second year?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Conditional probability with a hidden binary state (AP/NAP) → use law of total probability and conditional independence.

- **What is random vs fixed?**  
  Random: AP status, accidents in each year.  
  Fixed: accident probabilities given AP status.

- **What is the smallest useful variable definition?**  
  \( AP \) = accident prone, \( A_i \) = accident in year \( i \)

---

## My First Attempt

I tried to compute \( P(A_2 \mid A_1^c) \) directly but made a mistake in computing \( P(A_2 \cap A_1^c) \) — I forgot to condition on AP status first, so I might have incorrectly assumed \( A_1 \) and \( A_2 \) are independent overall.

---

## Solution Strategy
- **Step 1:** Compute \( P(A_1^c) \) using total probability over AP/NAP.
- **Step 2:** Compute \( P(A_2 \cap A_1^c) \) using total probability and conditional independence given AP status.
- **Step 3:** Divide: \( P(A_2 \mid A_1^c) = \frac{P(A_2 \cap A_1^c)}{P(A_1^c)} \).

Why this works: \( A_1 \) and \( A_2 \) are independent given AP status, but not independent overall — total probability over the hidden class accounts for this.

---

## Full Solution

**Step 1 — \( P(A_1^c) \)**
\[
P(A_1^c \mid AP) = 0.6,\quad P(A_1^c \mid NAP) = 0.8
\]
\[
P(A_1^c) = 0.6 \times 0.3 + 0.8 \times 0.7 = 0.18 + 0.56 = 0.74
\]

**Step 2 — \( P(A_2 \cap A_1^c) \)**
\[
P(A_2 \cap A_1^c \mid AP) = P(A_2 \mid AP) \cdot P(A_1^c \mid AP) = 0.4 \times 0.6 = 0.24
\]
\[
P(A_2 \cap A_1^c \mid NAP) = 0.2 \times 0.8 = 0.16
\]
\[
P(A_2 \cap A_1^c) = 0.24 \times 0.3 + 0.16 \times 0.7 = 0.072 + 0.112 = 0.184
\]

**Step 3 — Divide**
\[
P(A_2 \mid A_1^c) = \frac{0.184}{0.74} = \frac{184}{740} = \frac{92}{370} = \frac{46}{185}
\]

---

## Final Answer

\[
\boxed{\frac{46}{185}}
\]

---

## Pattern Recognition
- **Pattern type:** Bayes with hidden class and conditional independence.
- **Key trick:** Compute joint probability \( P(A_2 \cap A_1^c) \) by conditioning on hidden class first, using conditional independence within each class.
- **Similar problems:** Disease testing over time, machine failure with hidden quality state.

---

## Key Insight (1–2 lines)

Accidents in different years are independent given accident-proneness status, but not independent unconditionally — must condition on hidden class before multiplying probabilities.

---

## Mistakes / Lessons
- **What I got wrong:** Forgot to condition on \( AP \) vs \( NAP \) when computing \( P(A_2 \cap A_1^c) \); wrongly assumed \( P(A_2 \cap A_1^c) = P(A_2)P(A_1^c) \).
- **What I will remember:**  
  Whenever events are independent only given a hidden variable, use total probability over that variable first, then multiply.

Tags: `#bayes` `#conditional-independence` `#hidden-class` `#ross`
