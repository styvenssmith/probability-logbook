# Problem: Example 5d

## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 2, example 5d
- Difficulty (1–5): 3

---

## Problem Statement
At a party, there are $n$ people all with hats. We mix the hats up and each person selects one. A match occurs if each person selects his or her own hat. We want the probability that there are no matches. Find also the probability that exactly $K$ people get their own hats.

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this? This is a derangement problem (all possibilities in which you lose)
- What is random vs fixed? The assignment of hats to people is random. The people and their hats are fixed
- What is the smallest useful variable definition? $P_n$ = probability of no matches with $n$ people

---

## My First Attempt
On my first attempt, I used inclusion exclusion principle. The key idea that I focused on is that the complement of the union of $A_i$ is the probability that no person gets their own hat. Where $A_i$ represents the probability that the $i$th person gets their own hat. When I tried the condition approach, I first conditioned on the first person's outcome, but got stuck on whether the reduced problem was $P_{n-1}$ or $P_{n-2}$.
For the probability that $k$ people get their own hats this was relatively straightforward. Explicitly writing out the probability the $k$ people get their own hats we see that this is the same as $\frac{(n-k)!}{n!} \cdot P_{n-k}$ ($n-k$ people do not get their own hats). There are $\binom{n}{k}$ ways to choose the $k$ people that get their own hats, writing this out causes cancellation, and the solution is $\frac{P_{n-k}}{k!}$.

---

## Solution Strategy
- Step 1: Condition on what the first person gets. $P(\text{first gets own hat})$, $P(\text{first gets someone else's hat})$
- Step 2: Given that the first person takes $i$'s hat, we have $n-1$ people and $n-1$ hats
- Step 3: We now have two cases. A $\to$ person $i$ takes person $1$'s hat (a swap). probability $= \frac{1}{n-1}$, remaining $n-2$ people $\to P_{n-2}$. B $\to$ person $i$ does not take person $1$'s hat, probability $\frac{n-2}{n-1}$, this reduces to $P_{n-1}$. Then we combine

Why this works:
This is easier than the inclusion-exclusion method, we condition on the first person's outcome and correctly handle the two possible remaining cases, by splitting swap vs no swap cases.

---

## Full Solution
$P_1 = 0$

$P_2 = \frac{1}{2}$

$P_3 = \frac{1}{2!} - \frac{1}{3!}$

$\vdots$

$P_n = \sum_{k=0}^{n} \frac{(-1)^k}{k!}$

---

## Final Answer
$P_n = \sum_{k=0}^{n} \frac{(-1)^k}{k!}$

as $n$ goes to infinity $P_n = \frac{1}{e}$

---

## Pattern Recognition
- Pattern type: Derangement
- Key trick: Condition on the first person's hat, then splitting into swap and no swap cases
- Similar problems: probability of $n$ consecutive successes before $m$ consecutive failures, matching problem

---

## Key Insight (1–2 lines)
After we condition on the first person's hat, the remaining case is: does the next person take the first person's hat, or not?

---

## Mistakes / Lessons
- What I got wrong: I thought both cases reduced to $P_{n-2}$ or $P_{n-1}$ without the correct weights, I also confused the recurrence coefficients
- What I will remember:

Tags: