## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: 3.40
- Difficulty (1–5): 1

---

## Problem Statement

Urn A has 5 white and 7 black balls. Urn B has 3 white and 12 black balls.  
We flip a fair coin. If heads, pick a ball from urn A; if tails, pick from urn B.  
Suppose a white ball is selected. What is the probability that the coin landed tails?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Bayes’ theorem — prior over coin flip, likelihood from urn composition.

- **What is random vs fixed?**  
  Random: coin flip, which ball is drawn.  
  Fixed: urn compositions.

- **What is the smallest useful variable definition?**  
  \( H \) = heads (choose urn A), \( T \) = tails (choose urn B), \( W \) = white ball drawn.

---

## My First Attempt

Given:  
\( P(H) = P(T) = 0.5 \)  
\( P(W \mid H) = \frac{5}{12} \)  
\( P(W \mid T) = \frac{3}{15} = \frac{1}{5} \)

By Bayes:

\[
P(T \mid W) = \frac{P(W \mid T)P(T)}{P(W \mid T)P(T) + P(W \mid H)P(H)}
\]
\[
= \frac{\frac{1}{5} \cdot 0.5}{\frac{1}{5} \cdot 0.5 + \frac{5}{12} \cdot 0.5}
= \frac{\frac{1}{5}}{\frac{1}{5} + \frac{5}{12}}
\]

Common denominator 60:  
\( \frac{1}{5} = \frac{12}{60}, \quad \frac{5}{12} = \frac{25}{60} \)  
Sum = \( \frac{37}{60} \)

So:
\[
P(T \mid W) = \frac{12/60}{37/60} = \frac{12}{37}
\]

---

## Solution Strategy
- **Step 1:** Write down priors and likelihoods.
- **Step 2:** Apply Bayes’ theorem.
- **Step 3:** Simplify fraction.

Why this works: Direct substitution into Bayes’ formula — no tricky steps.

---

## Full Solution

\[
P(T \mid W) = \frac{\frac{1}{5} \cdot \frac12}{\frac{1}{5} \cdot \frac12 + \frac{5}{12} \cdot \frac12}
= \frac{\frac{1}{5}}{\frac{1}{5} + \frac{5}{12}}
= \frac{\frac{12}{60}}{\frac{12}{60} + \frac{25}{60}}
= \frac{12}{37}
\]

---

## Final Answer

\[
\boxed{\frac{12}{37}}
\]

---

## Pattern Recognition
- **Pattern type:** Bayes with two urns / two hypotheses.
- **Key trick:** Cancel the common factor \(0.5\) early.
- **Similar problems:** Any “choose an urn, then draw a ball” problem.

---

## Key Insight (1–2 lines)

Uniform prior over coin flip × different urn compositions → update belief about which urn was chosen given ball color.

---

## Mistakes / Lessons
- **What I got wrong:** Nothing — straightforward.
- **What I will remember:** Cancel common factors to simplify arithmetic.

Tags: `#bayes` `#urn-problem` `#conditional-probability`
