## Source
- Book / Platform:Sheldon Ross
- Chapter / Problem #: 3.35
- Difficulty (1–5): 1

---

## Problem Statement

On rainy days, Joe is late to work with probability 0.3; on nonrainy days, he is late with probability 0.1.  
With probability 0.7, it will rain tomorrow.

a. Find the probability that Joe is early tomorrow.  
b. Given that Joe was early, what is the conditional probability that it rained?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Total probability + Bayes’ theorem.

- **What is random vs fixed?**  
  Random: rain (binary) and lateness (binary).  
  Fixed: probabilities of lateness given rain, and rain prior.

- **What is the smallest useful variable definition?**  
  \( R = \text{rain} \), \( L = \text{late} \), \( E = \text{early} = L^c \).

---

## My First Attempt

Given \( P(R) = 0.7 \),  
\( P(L \mid R) = 0.3 \implies P(E \mid R) = 0.7 \)  
\( P(L \mid R^c) = 0.1 \implies P(E \mid R^c) = 0.9 \)

Part (a): \( P(E) = P(E|R)P(R) + P(E|R^c)P(R^c) \)  
= \( 0.7\cdot 0.7 + 0.9\cdot 0.3 = 0.49 + 0.27 = 0.76 \)

Part (b): \( P(R \mid E) = \frac{P(E|R)P(R)}{P(E)} = \frac{0.49}{0.76} = \frac{49}{76} \)

---

## Solution Strategy
- **Step 1:** Identify conditional probabilities of being early given rain status.
- **Step 2:** Apply law of total probability to find \( P(E) \).
- **Step 3:** Apply Bayes’ theorem to find \( P(R \mid E) \).

Why this works: Straightforward application of basic probability laws.

---

## Full Solution

\[
P(E) = P(E|R)P(R) + P(E|R^c)P(R^c) 
= 0.7 \times 0.7 \;+\; 0.9 \times 0.3
\]
\[
= 0.49 + 0.27 = 0.76
\]

\[
P(R \mid E) = \frac{P(E|R)P(R)}{P(E)} 
= \frac{0.7 \times 0.7}{0.76} = \frac{0.49}{0.76}
\]
\[
= \frac{49}{76} \approx 0.6447
\]

---

## Final Answer

a. \( 0.76 \)  
b. \( \frac{49}{76} \)

---

## Pattern Recognition
- **Pattern type:** Binary conditioning (rain/no rain) → binary outcome (late/early)
- **Key trick:** Always compute \( P(\text{early}) = 1 - P(\text{late}) \) from given data
- **Similar problems:** Any "test accuracy" or "disease screening" with prior and conditional probabilities

---

## Key Insight (1–2 lines)

Given two possible "states of nature" (rain, no rain) and two possible observations (late, early), use total probability and Bayes' theorem mechanically.

---

## Mistakes / Lessons
- **What I got wrong:** Nothing — this is straightforward.
- **What I will remember:** Always check which event you are conditioning on; here “given early” is the reverse of “given rain” in a Bayes setup.

Tags: `#bayes` `#total-probability` `#simple`
