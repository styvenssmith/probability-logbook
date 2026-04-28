## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 52
- Difficulty (1–5): 1

---

## Problem Statement

Suppose that an insurance company classifies people into one of three classes: good risks, average risks, and bad risks. The company’s records indicate that the probabilities that good-, average-, and bad-risk persons will be involved in an accident over a 1-year span are, respectively, 0.05, 0.15, and 0.30. If 20 percent of the population is a good risk, 50 percent an average risk, and 30 percent a bad risk:

a. What proportion of people have accidents in a fixed year?  
b. If policyholder A had no accidents in 2012, what is the probability that he or she is a good risk?  
c. What is the probability that he or she is an average risk?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Law of total probability + Bayes’ theorem.

- What is random vs fixed?  
  → Random: risk class, then accident occurrence. Fixed: given probabilities.

- What is the smallest useful variable definition?  
  Let \( G, A, B \) = good, average, bad risk.  
  Let \( Acc \) = has an accident, \( NoAcc \) = no accident.

---

## My First Attempt

Straightforward plug-and-chug:  
- Part (a): \( P(Acc) = \sum P(Acc \mid \text{class}) P(\text{class}) \)  
- Parts (b) & (c): \( P(\text{class} \mid NoAcc) = \frac{P(NoAcc \mid \text{class}) P(\text{class})}{P(NoAcc)} \)

---

## Solution Strategy
- Step 1: Compute \( P(Acc) \) using total probability.
- Step 2: Compute \( P(NoAcc) = 1 - P(Acc) \) or directly.
- Step 3: Apply Bayes for each class given no accident.

Why this works: Risk class is a partition of the population, and accident probability depends only on class.

---

## Full Solution

**Given:**  
\( P(G) = 0.20,\; P(A) = 0.50,\; P(B) = 0.30 \)  
\( P(Acc \mid G) = 0.05,\; P(Acc \mid A) = 0.15,\; P(Acc \mid B) = 0.30 \)  
Thus \( P(NoAcc \mid G) = 0.95,\; P(NoAcc \mid A) = 0.85,\; P(NoAcc \mid B) = 0.70 \)

**a. Proportion with accidents**  
\[
P(Acc) = (0.05)(0.20) + (0.15)(0.50) + (0.30)(0.30)
\]
\[
= 0.01 + 0.075 + 0.09 = 0.175
\]

**b. \( P(G \mid NoAcc) \)**  

First \( P(NoAcc) \):  
\[
P(NoAcc) = (0.95)(0.20) + (0.85)(0.50) + (0.70)(0.30)
\]
\[
= 0.19 + 0.425 + 0.21 = 0.825
\]

Now Bayes:  
\[
P(G \mid NoAcc) = \frac{0.95 \times 0.20}{0.825} = \frac{0.19}{0.825} \approx 0.2303
\]

**c. \( P(A \mid NoAcc) \)**  
\[
P(A \mid NoAcc) = \frac{0.85 \times 0.50}{0.825} = \frac{0.425}{0.825} \approx 0.5152
\]

---

## Final Answer

a. \( \boxed{0.175} \)  
b. \( \boxed{0.2303} \)  
c. \( \boxed{0.5152} \)

---

## Pattern Recognition
- Pattern type: Three-state Bayes with binary observation (accident or not).
- Key trick: Compute \( P(NoAcc) \) directly or as \( 1 - P(Acc) \).
- Similar problems: Any problem with multiple prior categories and a binary observation.

---

## Key Insight (1–2 lines)

The posterior probabilities after “no accident” shift weight toward lower-risk classes because they have higher \( P(NoAcc \mid \text{class}) \).

---

## Mistakes / Lessons
- What I got wrong: Nothing — straightforward plug-in.
- What I will remember: For Bayes with multiple classes, just compute numerator for each and divide by same denominator \( P(NoAcc) \).

Tags: law of total probability, Bayes' theorem, risk classes, insurance
