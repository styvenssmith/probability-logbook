## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 49
- Difficulty (1–5): 2

---

## Problem Statement

An urn contains 5 white and 10 black balls. A fair die is rolled and that number of balls is randomly chosen from the urn.  

a. What is the probability that all of the balls selected are white?  
b. What is the conditional probability that the die landed on 3 if all the balls selected are white?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Law of total probability + Bayes’ theorem.

- What is random vs fixed?  
  → Random: die roll (1–6), then which balls are drawn. Fixed: urn composition.

- What is the smallest useful variable definition?  
  Let \( D_k \) = die shows \( k \) (k = 1,…,6), \( P(D_k) = 1/6 \).  
  Let \( A \) = all selected balls are white.

---

## My First Attempt

Very straightforward:  
- For each k, P(A|D_k) = C(5,k)/C(15,k) if k ≤ 5, else 0.  
- Part (a): P(A) = (1/6) * sum_{k=1 to 5} C(5,k)/C(15,k).  
- Part (b): Bayes: P(D_3|A) = [P(A|D_3)*(1/6)] / P(A).

No issues.

---

## Solution Strategy
- Step 1: Compute P(A|D_k) for k = 1..5.
- Step 2: Use law of total probability to find P(A).
- Step 3: Use Bayes’ theorem to find P(D_3|A).

Why this works: The die roll determines how many balls are drawn, and drawing is uniform without replacement.

---

## Full Solution

**Given:**  
Urn: 5 white, 10 black. Total = 15.  
\( D_k \): die shows k, \( P(D_k) = 1/6 \).

**Step 1 – P(A | D_k)**  

If \( k \le 5 \):  
\[
P(A \mid D_k) = \frac{\binom{5}{k}}{\binom{15}{k}}
\]  
If \( k \ge 6 \): \( P(A \mid D_k) = 0 \) (not enough white balls).

Compute values:  
- \( k=1 \): \( \binom{5}{1}/\binom{15}{1} = 5/15 = 1/3 \)  
- \( k=2 \): \( 10/105 = 2/21 \)  
- \( k=3 \): \( 10/455 = 2/91 \)  
- \( k=4 \): \( 5/1365 = 1/273 \)  
- \( k=5 \): \( 1/3003 \)

**Step 2 – P(A) via total probability**

\[
P(A) = \frac16 \left( \frac13 + \frac{2}{21} + \frac{2}{91} + \frac{1}{273} + \frac{1}{3003} \right)
\]

Common denominator 3003:  
\( 1/3 = 1001/3003 \)  
\( 2/21 = 286/3003 \)  
\( 2/91 = 66/3003 \)  
\( 1/273 = 11/3003 \)  
\( 1/3003 = 1/3003 \)  

Sum numerators: \( 1001+286=1287,\; +66=1353,\; +11=1364,\; +1=1365 \)  
So sum = \( 1365/3003 = 455/1001 = 5/11 \) (since \( 455=5×7×13,\; 1001=7×11×13 \) → cancel 91).

Thus:  
\[
P(A) = \frac16 \times \frac{5}{11} = \frac{5}{66}
\]

**Step 3 – P(D_3 | A) via Bayes**

\[
P(D_3 \mid A) = \frac{P(A \mid D_3) P(D_3)}{P(A)}
\]
\[
= \frac{\frac{2}{91} \cdot \frac16}{\frac{5}{66}}
= \frac{\frac{2}{546}}{\frac{5}{66}}
= \frac{2}{546} \times \frac{66}{5}
\]
\( 2/546 = 1/273 \).  
\[
= \frac{1}{273} \times \frac{66}{5} = \frac{66}{1365}
\]
Divide numerator and denominator by 3: \( 22/455 \).  
No further simplification (gcd(22,455)=1).

---

## Final Answer

a. \( \displaystyle \frac{5}{66} \)  
b. \( \displaystyle \frac{22}{455} \)

---

## Pattern Recognition
- Pattern type: Two-stage experiment (die → draw balls).
- Key trick: Recognize that for k > #white balls, P(A|D_k)=0.
- Similar problems: Any “roll a die then draw from an urn” or “choose a random sample size” problem.

---

## Key Insight (1–2 lines)

All white means k ≤ 5 automatically. P(A) = (1/6) × sum of hypergeometric probabilities. Bayes gives the conditional probability of the die roll given all white.

---

## Mistakes / Lessons
- What I got wrong: Nothing — problem was straightforward.
- What I will remember: For “all white” with limited white balls, only k up to #white matter.

Tags: law of total probability, Bayes' theorem, hypergeometric, die roll, urn model
