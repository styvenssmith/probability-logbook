## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: 3.25
- Difficulty (1–5): 1

---

## Problem Statement

Twenty percent of B’s phone calls are with her daughter.  
Sixty-five percent of the time that B speaks with her daughter she hangs up with a smile on her face.  
Given that B has just hung up with a smile, find the conditional probability the call was with her daughter, or state if not enough info.

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  Conditional probability, Bayes’ theorem — but missing data case.
- What is random vs fixed?  
  Random: whether call is with daughter, whether she smiles.  
  Fixed: given percentages except P(smile | not daughter).
- What is the smallest useful variable definition?  
  \( D \) = call with daughter, \( S \) = hangs up smiling.

---

## My First Attempt

I wrote:

\[
P(D \mid S) = \frac{0.20 \times 0.65}{0.20 \times 0.65 + 0.80 \times 0.35}
\]

That assumes \( P(S \mid D^c) = 0.35 \).  
But \( 0.35 = 1 - P(S \mid D) \), which is \( P(S^c \mid D) \), **not** \( P(S \mid D^c) \).  
There’s no justification for \( P(S \mid D^c) \) = \( P(S^c \mid D) \).

So my attempt was invalid — I made an unwarranted assumption.

---

## Solution Strategy
- Step 1: Identify known quantities: \( P(D) \), \( P(S \mid D) \).
- Step 2: Bayes’ theorem shows need \( P(S \mid D^c) \).
- Step 3: Conclude insufficient info.

Why this works:  
Because \( P(S) = P(D)P(S \mid D) + P(D^c)P(S \mid D^c) \) — without \( P(S \mid D^c) \), unknown.

---

## Full Solution

Let:
- \( D \) = call with daughter, \( P(D) = 0.20 \)
- \( S \) = smile on hangup, \( P(S \mid D) = 0.65 \)
- \( D^c \) = call not with daughter

Bayes’ theorem:

\[
P(D \mid S) = \frac{P(D)P(S \mid D)}{P(D)P(S \mid D) + P(D^c)P(S \mid D^c)}
\]

Numerator known: \( 0.20 \times 0.65 = 0.13 \).  
Denominator requires \( P(S \mid D^c) \), which is **not given**.

Thus: **Not enough information**.

---

## Final Answer

\[
\boxed{\text{No — need } P(S \mid D^c)}
\]

---

## Pattern Recognition
- Pattern type: Bayes’ theorem with missing conditional.
- Key trick: Recognizing when Bayes’ can’t be completed due to missing \( P(\text{evidence} \mid \text{complement}) \).
- Similar problems: Medical testing without false positive rate; screening with unknown specificity.

---

## Key Insight (1–2 lines)

Without \( P(\text{smile} \mid \text{not daughter}) \), the denominator of Bayes’ is incomplete — no single number for \( P(D \mid S) \) can be determined.

---

## Mistakes / Lessons
- What I got wrong:  
  Mistakenly assumed \( P(S \mid D^c) = 1 - P(S \mid D) \), i.e., same smile rate for non-daughter calls as non-smile rate for daughter calls.
- What I will remember:  
  \( P(S \mid D^c) \) is independent of \( P(S \mid D) \) in general. Don’t swap complements across conditions.

Tags: `bayes-theorem`, `conditional-probability`, `missing-data`, `complement-mistake`
