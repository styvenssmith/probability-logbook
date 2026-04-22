# Problem: Example 5f, Updating information sequentially

## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Example 5f: Updating information
- Difficulty (1–5): 3

---

## Problem Statement

Suppose there are \( n \) mutually exclusive and exhaustive possible hypotheses, with initial probabilities \( P(H_i) \), \( \sum_{i=1}^n P(H_i) = 1 \). Now, if information that the event \( E \) has occurred is received, then the conditional probability that \( H_i \) is the true hypothesis is

\[
P(H_i | E) = \frac{P(E | H_i) P(H_i)}{\sum_j P(E | H_j) P(H_j)}
\]

Suppose now that we learn first that \( E_1 \) has occurred and then that \( E_2 \) has occurred. Can we compute \( P(H_i | E_1 E_2) \) by using the above formula with \( E = E_2 \) and with \( P(H_j) \) replaced by \( P(H_j | E_1) \)? That is, is it legitimate to regard \( P(H_j | E_1) \) as the prior probabilities and then use the formula to compute the posterior probabilities?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this? Sequential Bayesian updating / conditional probability
- What is random vs fixed? The hypothesis \( H_i \) is random. The events \( E_1 \) and \( E_2 \) are observed data. The likelihoods \( P(E_1 | H_i) \) and \( P(E_2 | H_i) \) are fixed.
- What is the smallest useful variable definition? \( H_i \) = hypothesis i is true, \( P(H_i) \) = prior probability

---

## My First Attempt

I used the odds form of Bayes. My thinking was: after \( E_1 \), my odds change by multiplying by \( \frac{P(E_1 | H_i)}{P(E_1 | H_j)} \). After \( E_2 \), my odds change again by multiplying by \( \frac{P(E_2 | H_i)}{P(E_2 | H_j)} \). So sequential updating just multiplies these factors. The book did a longer derivation, but I thought this was simpler.

---

## Solution Strategy
- Step 1: Write Bayes in odds form: \( \frac{P(H_i | E)}{P(H_j | E)} = \frac{P(H_i)}{P(H_j)} \cdot \frac{P(E | H_i)}{P(E | H_j)} \)
- Step 2: Apply twice: first for \( E_1 \), then for \( E_2 \) using \( P(H_i | E_1) \) as the new prior
- Step 3: Multiply to get \( \frac{P(H_i | E_1 E_2)}{P(H_j | E_1 E_2)} = \frac{P(H_i)}{P(H_j)} \cdot \frac{P(E_1 | H_i)}{P(E_1 | H_j)} \cdot \frac{P(E_2 | H_i)}{P(E_2 | H_j)} \)

Why this works: Multiplication is associative and commutative. The one-step method gives \( \frac{P(H_i)}{P(H_j)} \cdot \frac{P(E_1 E_2 | H_i)}{P(E_1 E_2 | H_j)} \). These are equal iff \( P(E_1 E_2 | H_i) = P(E_1 | H_i) P(E_2 | H_i) \) for all \( i \), which is conditional independence.

---

## Full Solution

The answer is that the preceding is legitimate, provided that for each \( j = 1, ..., n \), the events \( E_1 \) and \( E_2 \) are conditionally independent, given \( H_j \). For if this is the case, then

\[
P(E_1 E_2 | H_j) = P(E_2 | H_j) P(E_1 | H_j), \quad j = 1, ..., n
\]

Therefore,

\[
P(H_i | E_1 E_2) = \frac{P(E_2 | H_i) P(E_1 | H_i) P(H_i)}{P(E_1 E_2)}
\]

\[
= \frac{P(E_2 | H_i) P(H_i | E_1) P(E_1)}{P(E_1 E_2)}
\]

\[
= \frac{P(E_2 | H_i) P(H_i | E_1)}{\sum_j P(E_2 | H_j) P(H_j | E_1)}
\]

Thus, updating sequentially works: treat \( P(H_j | E_1) \) as the prior, then use Bayes with \( E_2 \).

---

## Final Answer

\[
P(H_i | E_1 E_2) = \frac{P(E_2 | H_i) P(H_i | E_1)}{\sum_{j=1}^n P(E_2 | H_j) P(H_j | E_1)}
\]

provided \( E_1 \) and \( E_2 \) are conditionally independent given \( H_j \) for all \( j \).

---

## Pattern Recognition
- Pattern type: Sequential Bayesian updating
- Key trick: Odds form multiplies likelihood ratios; conditional independence allows factoring
- Similar problems: Coin flipping with unknown coin, medical testing with two tests, spam filtering

---

## Key Insight (1–2 lines)

Bayes in odds form is just multiplication. Update sequentially by multiplying likelihood ratios one after another.

---

## Mistakes / Lessons
- What I got wrong: I assumed that mutual exclusivity of events implies independence. That is backwards. If two events are mutually exclusive and both have positive probability, they are always dependent.
- What I will remember: Mutual exclusivity does **not** imply independence. For sequential updating, I need **conditional independence** given the hypothesis, not mutual exclusivity.

Tags: Bayes, sequential updating, odds form, conditional independence, mutual exclusivity