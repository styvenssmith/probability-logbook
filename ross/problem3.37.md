## Source
- Book / Platform:Sheldon Ross
- Chapter / Problem #: 3.37
- Difficulty (1–5): 1

---

## Problem Statement

With probability 0.6, the present was hidden by mom; with probability 0.4, it was hidden by dad.  
When mom hides the present, she hides it upstairs 70% of the time and downstairs 30% of the time.  
Dad is equally likely to hide it upstairs or downstairs.

a. What is the probability that the present is upstairs?  
b. Given that it is downstairs, what is the probability it was hidden by dad?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Law of total probability and Bayes’ theorem.

- **What is random vs fixed?**  
  Random: who hid the present (Mom/Dad), and location (upstairs/downstairs).  
  Fixed: probabilities of location given parent.

- **What is the smallest useful variable definition?**  
  \( M \) = hidden by mom, \( D \) = hidden by dad, \( U \) = upstairs, \( L \) = downstairs.

---

## My First Attempt

Given:
\[
P(M) = 0.6,\quad P(D) = 0.4
\]
\[
P(U \mid M) = 0.7,\quad P(L \mid M) = 0.3
\]
\[
P(U \mid D) = 0.5,\quad P(L \mid D) = 0.5
\]

a. \( P(U) = P(U \mid M)P(M) + P(U \mid D)P(D) \)  
\( = 0.7 \times 0.6 + 0.5 \times 0.4 = 0.42 + 0.20 = 0.62 \)

b. \( P(D \mid L) = \frac{P(L \mid D)P(D)}{P(L)} \)  
First \( P(L) = 1 - 0.62 = 0.38 \), or compute directly:  
\( P(L) = 0.3 \times 0.6 + 0.5 \times 0.4 = 0.18 + 0.20 = 0.38 \).  

So \( P(D \mid L) = \frac{0.5 \times 0.4}{0.38} = \frac{0.20}{0.38} = \frac{10}{19} \).

---

## Solution Strategy
- **Step 1:** Write down all given probabilities.
- **Step 2:** Use law of total probability to find \( P(U) \) and \( P(L) \).
- **Step 3:** Use Bayes’ theorem to find \( P(D \mid L) \).

Why this works: Straightforward two-stage probability tree.

---

## Full Solution

**a.**  
\[
P(U) = 0.7 \times 0.6 + 0.5 \times 0.4 = 0.42 + 0.20 = 0.62
\]

**b.**  
\[
P(L) = 0.3 \times 0.6 + 0.5 \times 0.4 = 0.18 + 0.20 = 0.38
\]
\[
P(D \mid L) = \frac{P(L \mid D)P(D)}{P(L)} = \frac{0.5 \times 0.4}{0.38} = \frac{0.20}{0.38} = \frac{10}{19}
\]

---

## Final Answer

a. \( 0.62 \)  
b. \( \frac{10}{19} \)

---

## Pattern Recognition
- **Pattern type:** Total probability + Bayes
- **Key trick:** Compute \( P(L) \) either as \( 1 - P(U) \) or directly from given data
- **Similar problems:** Any two-stage random process (e.g., factory machines producing defective items)

---

## Key Insight (1–2 lines)

Knowing location updates the probability of who hid it — Bayes’ theorem inverts the conditioning.

---

## Mistakes / Lessons
- **What I got wrong:** Nothing — straightforward.
- **What I will remember:** Always compute the marginal probability of the evidence first.

Tags: `#bayes` `#total-probability`
