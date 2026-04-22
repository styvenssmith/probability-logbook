# Problem: Example 5E, Laplace's rule of succession

## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Example 5E Laplace's rule of succession
- Difficulty (1–5): 2

---

## Problem Statement
There are $k+1$ coins in a box. When flipped, the $i$th coin will turn up heads with probability $i/k$, $i = 0, 1, \dots, k$. A coin is randomly selected from the box and is then repeatedly flipped. If the first $n$ flips all result in heads, what is the probability that the $(n+1)$st flip will do likewise?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this? Conditional probability, also using Law of total probability
- What is random vs fixed? The choice of coin is random, the probability of heads and the probability of the $i$th coin turning heads is fixed.
- What is the smallest useful variable definition? $H_n$ represents the event that all $n$ coin flips are heads.

---

## My First Attempt
I quickly realized that this was a conditional problem. After writing the conditional probability formula, $P(H_{n+1}|H_{n})$. To find $P(H_{n})$ I used the law of total probability for $H_{n}$ conditioning on which coin we are choosing to do the flips $P(H_{n}) = \sum_{i=0}^{k} P(H_{n}|C_i)P(C_i)$. From the problem statement, we know that $P(H_n|C_i) = \left(\frac{i}{k}\right)^n$, $P(C_i) = \frac{1}{k+1}$ because there are $k+1$ coins total and we are choosing one of them. I left the solution as 
$$\frac{\sum_{i=0}^{k} \left( \frac{i}{k} \right)^{n+1}}{\sum_{i=0}^{k} \left( \frac{i}{k} \right)^n}.$$

---

## Solution Strategy
- Step 1: Recognize that this is a conditional problem
- Step 2: Define the events $H_{n+1}$ and $H_{n}$ as the events that the $n$ and $n+1$ trials all end with heads.
- Step 3: Cancel the $\frac{1}{k+1}$ terms and obtain the result

Why this works:

---

## Full Solution
$$P(H_{n+1}|H_{n}) = \frac{P(H_{n+1} \cap H_{n})}{P(H_n)}$$

$$P(H_{n}) = \sum_{i=0}^{k} P(H_{n}|C_i)P(C_i)$$

$$P(H_n|C_i) = \left(\frac{i}{k}\right)^n, \quad P(C_i) = \frac{1}{k+1}$$

$$P(H_{n+1}|H_{n}) = \frac{\sum_{i=0}^{k} \left( \frac{i}{k} \right)^{n+1}}{\sum_{i=0}^{k} \left( \frac{i}{k} \right)^n}$$

Using integral approximation (Riemann sum) to get:

$$P(H_{n+1}|H_{n}) \approx \frac{n+1}{n+2}$$

---

## Final Answer
$$P(H_{n+1}|H_{n}) = \frac{\sum_{i=0}^{k} \left( \frac{i}{k} \right)^{n+1}}{\sum_{i=0}^{k} \left( \frac{i}{k} \right)^n}$$

As $k \to \infty$, this tends to $\frac{n+1}{n+2}$.

---

## Pattern Recognition
- Pattern type: Laplace's rule of succession
- Key trick: Use integral approximation for the sum (Riemann sum)
- Similar problems: Beta-Binomial conjugate prior problems

---

## Key Insight (1–2 lines)
The uniform prior over discrete probabilities $i/k$ leads to the rule of succession. The sums approximate $\int_0^1 x^{n+1} dx / \int_0^1 x^n dx = (n+1)/(n+2)$.

---

## Mistakes / Lessons
- What I got wrong: I did not remember the Riemann sum to approximate the sum using an integral
- What I will remember:
When you see a sum of the form $\frac{1}{k}\sum f\left(\frac{i}{k}\right)$, I should be thinking Riemann sum.

Tags: Laplace, rule of succession, conditional probability, law of total probability, Riemann sum