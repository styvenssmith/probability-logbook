# Problem: Example 5E, Laplace's rule of succession

## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Example 5E Laplace's rule of succession
- Difficulty (1–5):2

---

## Problem Statement
There are k+1 coins in a box. When flipped, the ith coin will turn up head with probability i/k, i = 0, 1, ..., k. A coin is randomly selected from the box and is then repeatedly flipeed. If the first n flips all result in heads, what is the probability that the (n+1) flip will do likewise?
---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this? Conditional probability, also using Law of total probability
- What is random vs fixed? The choice of coin is random, the probability of heads and the probability of the ith coin turning heads is fixed.
- What is the smallest useful variable definition? Hn represents the event, that all n coin flips are head.

---

## My First Attempt
I quickly realized that this was a conditional problem. After writing the conditional probability formula, $P(H_{n+1}|H_{n})$. To find $P(H_{n})$ I used the law of total probability for $H_{n}$ conditioning on which coin we are choosing to do the flips $P(H_{n}) = \sum_{i=0}^{k} P(H_{n}|C_i)P(C_i)$. From the problem statement, we know that $P(H_n|C_i) = (\frac{i}{k})^n$, $P(C_i) = \frac{1}{k+1}$ because there are k+1 coins total and we are choosing one of them. I left the solution as $\frac{\sum_{i=0}^{k}(\frac{i/k}^{n+1})}{\sum_{i=0}^{k}(\frac{i/k}^{n})}$.
---

## Solution Strategy
- Step 1: Recognize that this is a conditional problem
- Step 2: Define the events $H_{n+1} \text{ and } H_{n}$ as the events that the n and n+1 trials all end with head.
- Step 3: Cancel the $\frac{1}{k+1}$ terms and obtain the result

Why this works:

---

## Full Solution
$P(H_{n+1}|H_{n}) = \frac{P(H_{n+1}H_{n})}{P(H_n)}$
$P(H_{n}) = \sum_{i=0}^{k} P(H_{n}|C_i)P(C_i)$
$P(H_n|C_i) = (\frac{i}{k})^n$
$P(H_{n+1}|H_{n}) = \frac{\sum_{i=0}^{k}(\frac{i/k}^{n+1})}{\sum_{i=0}^{k}(\frac{i/k}^{n})}$
Use integral approximation to get:
$P(H_{n+1}|H_{n}) = \frac{n+1}{n+2}$
---

## Final Answer
$P(H_{n+1}|H_{n}) = \frac{\sum_{i=0}^{k}(\frac{i/k}^{n+1})}{\sum_{i=0}^{k}(\frac{i/k}^{n})}$
---

## Pattern Recognition
- Pattern type:
- Key trick: Use integral approximation for the sum
- Similar problems:

---

## Key Insight (1–2 lines)

---

## Mistakes / Lessons
- What I got wrong: I did not remember the riemann sum, to approximate the sum using an integral
- What I will remember:
When you see a sum of the form $\frac{1}{k}\sum f(\frac{i}{k})$ I should be thinking riemann sum.

Tags: