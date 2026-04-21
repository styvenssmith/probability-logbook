# Problem: Example 5d

## Source
- Book / Platform:Sheldon Ross
- Chapter / Problem #:Chapter 2, example 5d
- Difficulty (1–5):3

---

## Problem Statement
At a party, there are n people all with hats. We mix the hats up and each person selects one. A match occurs if each person selects his or her own hat. We want the probability that there are no matches. Find also the probability that exactly K people get their own hats.
---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this? This is a derangement problem (all posibilities in which you lose)
- What is random vs fixed? The assignment of hats to people is random. The people and their hats are fixed
- What is the smallest useful variable definition? Pn = probability of no matches with n people 

---

## My First Attempt
On my first attempt, I used inclusion exclusion principle. The key idea that I focused on is that the complement of the union of Ai is the probability that no person gets their own hat. Where Ai represents the probability that the ith person gets their own hat. When I tried the condition approach, I first conditioned on the first person's outcome, but got stuck on whether the reduced problem was Pn-1 or Pn-2.
For the probability that k people get their own hats this was relatively straight foward. Explicitly writing out the probability the k people get their own hats we see that this is the same as (N-k)!/N!*PN-k(N-k people do not get their own hats). There are (N choose k) ways to choose the k people that get their own hats, writing this out causes cancellation, and the solution is PN-k/k!
---

## Solution Strategy
- Step 1:Condition on what the first person gets. P(first get own hat), P(first gets someone elses hat)
- Step 2: Given that the first person takes i's hat, we have n-1 people and n-1 hats
- Step 3: We now have two cases. A-> persion i takes person 1's hat (a swap). probability = 1/n-1, remaining n-2 people ->Pn-2. B-> person i does not take person 1's hat, probability n-2/n-1, this reduces to Pn-1. Then we combine

Why this works:
This is easier than the inclusion, exclusion method, we condition on the first person's outcome and correctly handle the two possible remaining cases, by splitting swap vs no swap cases.
---

## Full Solution
P1 = 0
P2 = 1/2
P3 = 1/2!-1/3!
...
Pn = sum from k = 0 (-1)^k/k!
---

## Final Answer
Pn = sum from k = 0 to n (-1)^k/k!
as n goes to infinity Pn = 1/e
---

## Pattern Recognition
- Pattern type: Deragement
- Key trick:Condition on the first person's hat, then splitting into swap and no swap cases
- Similar problems: probability of n consecutive successes before m consecutive failures, matching problem

---

## Key Insight (1–2 lines)
After we condition on the first person's hat. The remaining case is does the next person take the first person's hat, or not
---

## Mistakes / Lessons
- What I got wrong: I thought both cases reduced to Pn-2 or Pn-1 without the correct weights, I also confused the recurrence coefficients
- What I will remember:

Tags: