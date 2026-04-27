## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 (Conditional Probability) / Problem 44
- Difficulty (1–5): 2

---

## Problem Statement

Twelve percent of all U.S. households are in California.  
A total of 1.3 percent of all U.S. households earn more than $250,000 per year, while a total of 3.3 percent of all California households earn more than $250,000 per year.

a. What proportion of all non-California households earn more than $250,000 per year?  

b. Given that a randomly chosen U.S. household earns more than $250,000 per year, what is the probability it is a California household?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Conditional probability / Bayes’ theorem / law of total probability.
- What is random vs fixed?  
  → Random: choosing a U.S. household. Fixed: given percentages.
- What is the smallest useful variable definition?  
  \( C \) = household in California, \( H \) = income > $250K.

---

## My First Attempt

P(C) = 0.12, P(H) = 0.013, P(H | C) = 0.033.

We want P(H | C^c) and P(C | H), so I can use total probability and Bayes.

---

## Solution Strategy
- Step 1: Write law of total probability for P(H):  
  \( P(H) = P(H | C) P(C) + P(H | C^c) P(C^c) \) → solve for \( P(H | C^c) \).

- Step 2: Use Bayes’ theorem to find \( P(C | H) \).

Why this works: The only missing info is P(H | C^c), and once we have that, all probabilities for the second part are known.

---

## Full Solution

Given:  
\( P(C) = 0.12,\ P(C^c) = 0.88 \)  
\( P(H) = 0.013 \)  
\( P(H | C) = 0.033 \)

**a.** Law of total probability:  
\( 0.013 = (0.033)(0.12) + P(H | C^c)(0.88) \)  
\( 0.013 = 0.00396 + 0.88 \cdot P(H | C^c) \)  
\( 0.00904 = 0.88 \cdot P(H | C^c) \)  
\( P(H | C^c) = 0.00904 / 0.88 \approx 0.0102727 \).

**b.** Bayes’ theorem:  
\( P(C | H) = \frac{P(H | C) P(C)}{P(H)} \)  
\( = \frac{0.033 \cdot 0.12}{0.013} \)  
\( = \frac{0.00396}{0.013} \approx 0.304615 \).

---

## Final Answer

a. \( \approx 0.01027 \) (or 1.027%)  
b. \( \approx 0.3046 \) (or 30.46%)

---

## Pattern Recognition
- Pattern type: Partition + Bayes.
- Key trick: Direct substitution into the law of total probability to find the missing conditional probability.
- Similar problems: Any problem where you have P(A), P(B|A) and P(B) and are missing P(B|A^c) or P(A|B).

---

## Key Insight (1–2 lines)

Total probability fills in the missing “P(H | not C)” by splitting P(H) across the two regions (CA and not CA).

---

## Mistakes / Lessons
- What I got wrong: Nothing here. Computations straightforward.
- What I will remember: P(H) is a weighted average of P(H|C) and P(H|C^c). That alone solves (a); then Bayes for (b).

Tags: law of total probability, Bayes' theorem, conditional probability, two-event partition
