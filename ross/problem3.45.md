## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 45
- Difficulty (1–5): 2

---

## Problem Statement

There are 3 coins in a box.  
- One is two-headed (always heads).  
- One is fair (P(H) = 0.5).  
- One is biased (P(H) = 0.75).  

A coin is selected at random and flipped. It shows heads.  
What is the probability that it was the two-headed coin?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Conditional probability / Bayes’ theorem.
- What is random vs fixed?  
  → Random: which coin is chosen, then the flip outcome. Fixed: coin properties.
- What is the smallest useful variable definition?  
  Let \( C_1 \) = choose two-headed coin, \( C_2 \) = choose fair coin, \( C_3 \) = choose biased coin.  
  Let \( H \) = flip shows heads.

---

## My First Attempt

P(C1) = P(C2) = P(C3) = 1/3.  
P(H|C1) = 1, P(H|C2) = 0.5, P(H|C3) = 0.75.  
We want P(C1|H). Use Bayes.

---

## Solution Strategy
- Step 1: Compute P(H) using law of total probability.
- Step 2: Apply Bayes’ theorem to find P(C1|H).

Why this works: The events C1, C2, C3 form a partition of the sample space.

---

## Full Solution

**Step 1 – Law of total probability for P(H):**  
\[
P(H) = P(H|C_1)P(C_1) + P(H|C_2)P(C_2) + P(H|C_3)P(C_3)
\]
\[
P(H) = (1)\left(\frac{1}{3}\right) + (0.5)\left(\frac{1}{3}\right) + (0.75)\left(\frac{1}{3}\right)
\]
\[
P(H) = \frac{1}{3}(1 + 0.5 + 0.75) = \frac{1}{3}(2.25) = 0.75 = \frac{3}{4}
\]

**Step 2 – Bayes’ theorem:**  
\[
P(C_1|H) = \frac{P(H|C_1)P(C_1)}{P(H)}
\]
\[
P(C_1|H) = \frac{1 \cdot \frac{1}{3}}{\frac{3}{4}} = \frac{1}{3} \cdot \frac{4}{3} = \frac{4}{9}
\]

---

## Final Answer

\[
\boxed{\frac{4}{9}}
\]

---

## Pattern Recognition
- Pattern type: Bayes’ theorem with equally likely priors.
- Key trick: Recognize that P(H) is a weighted average of the three conditional probabilities.
- Similar problems: Any “which box/die/coin” problem where you observe an outcome and infer the source.

---

## Key Insight (1–2 lines)

Even though the two-headed coin always gives heads, its prior probability is only 1/3, so P(H) = 3/4 is high enough that P(C1|H) is only 4/9.

---

## Mistakes / Lessons
- What I got wrong: Nothing here – clean calculation.
- What I will remember: Always compute total probability P(H) first when applying Bayes.

Tags: Bayes' theorem, law of total probability, conditional probability, coins
