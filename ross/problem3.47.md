## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 47
- Difficulty (1–5): 2

---

## Problem Statement

There is a 30% chance that A can fix her busted computer. If A cannot, then there is a 40% chance that her friend B can fix it.

a. Find the probability it will be fixed by either A or B.  
b. If it is fixed, what is the probability it will be fixed by B.

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Sequential events / conditional probability / total probability / Bayes.

- What is random vs fixed?  
  → Random: whether A can fix it, then whether B can fix it if A fails. Fixed: given probabilities.

- What is the smallest useful variable definition?  
  Let \( A \) = event “A fixes computer”  
  Let \( B \) = event “B fixes computer”  
  Given: \( P(A) = 0.30 \), \( P(B \mid A^c) = 0.40 \).  
  Also, \( A \) and \( B \) are mutually exclusive (B only tries if A fails).

---

## My First Attempt

Initially I thought \( P(B) = 0.40 \), but that’s wrong — that’s \( P(B \mid A^c) \), not \( P(B) \).  
Must use \( P(B) = P(B \mid A^c) P(A^c) \).

---

## Solution Strategy
- Step 1: Compute \( P(B) = P(B \mid A^c) P(A^c) \).
- Step 2: \( P(\text{fixed}) = P(A \cup B) = P(A) + P(B) \) (mutual exclusivity).
- Step 3: Use Bayes / conditional probability for \( P(B \mid \text{fixed}) \).

Why this works: B only operates if A fails, so the two events are naturally sequential and disjoint.

---

## Full Solution

**Given:**
\[
P(A) = 0.30,\quad P(A^c) = 0.70
\]
\[
P(B \mid A^c) = 0.40
\]

**a. Find \( P(A \cup B) \)**  

First, \( P(B) = P(B \mid A^c) P(A^c) = 0.40 \times 0.70 = 0.28 \).  

Mutually exclusive: \( A \cap B = \varnothing \) (if A fixes it, B never tries).  

So:
\[
P(A \cup B) = P(A) + P(B) = 0.30 + 0.28 = 0.58
\]

**b. Find \( P(B \mid A \cup B) \)**  

\[
P(B \mid \text{fixed}) = \frac{P(B)}{P(\text{fixed})} = \frac{0.28}{0.58}
\]
\[
= \frac{28}{58} = \frac{14}{29} \approx 0.4828
\]

---

## Final Answer

a. \( \boxed{0.58} \)  
b. \( \boxed{\frac{14}{29}} \) (≈ 0.4828)

---

## Pattern Recognition
- Pattern type: Sequential probabilities, mutual exclusivity.
- Key trick: \( P(B) \neq P(B \mid A^c) \); must multiply by \( P(A^c) \).
- Similar problems: Any “try A first, then B if A fails” system (reliability, medical tests with second opinion, etc.).

---

## Key Insight (1–2 lines)

B’s overall probability = probability A fails × probability B succeeds given A fails.  
Then part (b) is just \( P(B) / P(\text{fixed}) \).

---

## Mistakes / Lessons
- What I got wrong: Initially read \( P(B \mid A^c) = 0.40 \) as \( P(B) = 0.40 \).  
- What I will remember: \( P(B) = P(B \mid A^c) P(A^c) \) when B only matters after A fails.

Tags: conditional probability, total probability, mutual exclusivity, sequential events
