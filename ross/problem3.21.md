## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.21
- Difficulty (1–5): 1

---

## Problem Statement

Fifty-two percent of the students at a certain college are females. Five percent of the students in this college are majoring in computer science. Two percent of the students are women majoring in computer science. If a student is selected at random, find the conditional probability that  

a. the student is female given that the student is majoring in computer science;  
b. the student is majoring in computer science given that the student is female.

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability directly from the definition.

- What is random vs fixed?  
  Random: gender and major. Fixed: given percentages (probabilities).

- What is the smallest useful variable definition?  
  \(F\): female, \(C\): computer science major.

---

## My First Attempt

I used the definition \(P(A \mid B) = P(A \cap B) / P(B)\) for both parts.

---

## Solution Strategy

- Step 1: Identify \(P(F)\), \(P(C)\), and \(P(F \cap C)\) from the problem statement.
- Step 2: For (a), use \(P(F \mid C) = P(F \cap C) / P(C)\).
- Step 3: For (b), use \(P(C \mid F) = P(F \cap C) / P(F)\).

Why this works: Direct application of conditional probability definition.

---

## Full Solution

Let \(F\) = female, \(C\) = computer science major.

Given:  
\(P(F) = 0.52\)  
\(P(C) = 0.05\)  
\(P(F \cap C) = 0.02\)

**Part (a):**  
\[
P(F \mid C) = \frac{P(F \cap C)}{P(C)} = \frac{0.02}{0.05} = 0.4
\]

**Part (b):**  
\[
P(C \mid F) = \frac{P(F \cap C)}{P(F)} = \frac{0.02}{0.52} = \frac{2}{52} = \frac{1}{26} \approx 0.03846
\]

---

## Final Answer

\[
\text{(a) } \boxed{0.4}, \quad \text{(b) } \boxed{\frac{1}{26}} \; (\approx 0.03846)
\]

---

## Pattern Recognition

- Pattern type: Basic conditional probability.
- Key trick: Use \(P(A \cap B)\) directly — no Bayes needed if intersection already given.
- Similar problems: Any contingency table with two binary variables where joint and marginals are given.

---

## Key Insight (1–2 lines)

When the joint probability \(P(A \cap B)\) is given directly, conditional probabilities are just ratios of joint to marginal.

---

## Mistakes / Lessons

- What I got wrong: Nothing — straightforward.
- What I will remember:  
  Always check if the joint probability is given before setting up Bayes’ theorem. Sometimes it's simpler.

Tags: probability, conditional-probability, intersection, gender, major
