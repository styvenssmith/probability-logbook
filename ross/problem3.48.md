## Source
- Book / Platform: Sheldon Rosss
- Chapter / Problem #: Chapter 3 / Problem 48
- Difficulty (1–5): 3

---

## Problem Statement

In any given year, a male automobile policyholder will make a claim with probability \( p_m \) and a female policyholder with probability \( p_f \), where \( p_f \neq p_m \). The fraction of policyholders that are male is \( \alpha \), \( 0 < \alpha < 1 \). A policyholder is randomly chosen. If \( A_i \) denotes the event that this policyholder will make a claim in year \( i \), show that

\[
P(A_2 \mid A_1) > P(A_1)
\]

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Conditional probability, law of total probability, inequality proof.

- What is random vs fixed?  
  → Random: gender of the chosen policyholder, and whether they make a claim each year. Fixed: \( p_m, p_f, \alpha \).

- What is the smallest useful variable definition?  
  Let \( M \) = policyholder is male, \( F \) = policyholder is female.  
  \( P(M) = \alpha \), \( P(F) = 1 - \alpha \).  
  \( P(A_i \mid M) = p_m \), \( P(A_i \mid F) = p_f \) (same for any year \( i \)).  
  Claims in different years are independent given gender.

---

## My First Attempt

Initially wanted to use Bayes, but that was unnecessary — direct conditioning works.  
Bayes would give \( P(A_2 \mid A_1) = \frac{P(A_1 \mid A_2) P(A_2)}{P(A_1)} \), which is symmetric and doesn’t help.

---

## Solution Strategy
- Step 1: Compute \( P(A_1) \) using law of total probability conditioning on gender.
- Step 2: Compute \( P(A_1 \cap A_2) \) similarly.
- Step 3: Use \( P(A_2 \mid A_1) = \frac{P(A_1 \cap A_2)}{P(A_1)} \).
- Step 4: Show inequality \( P(A_2 \mid A_1) > P(A_1) \) by algebra / variance identity.

Why this works:  
Given gender, claims are independent across years, so joint probability = square of marginal given gender.

---

## Full Solution

**Step 1 – Unconditional claim probability**

\[
P(A_1) = P(A_1 \mid M)P(M) + P(A_1 \mid F)P(F)
\]
\[
P(A_1) = \alpha p_m + (1 - \alpha) p_f
\]

**Step 2 – Joint probability of claims in both years**

\[
P(A_1 \cap A_2 \mid M) = p_m^2, \quad P(A_1 \cap A_2 \mid F) = p_f^2
\]
\[
P(A_1 \cap A_2) = \alpha p_m^2 + (1 - \alpha) p_f^2
\]

**Step 3 – Conditional probability**

\[
P(A_2 \mid A_1) = \frac{P(A_1 \cap A_2)}{P(A_1)} = \frac{\alpha p_m^2 + (1 - \alpha) p_f^2}{\alpha p_m + (1 - \alpha) p_f}
\]

**Step 4 – Show \( P(A_2 \mid A_1) > P(A_1) \)**

Need to show:
\[
\frac{\alpha p_m^2 + (1 - \alpha) p_f^2}{\alpha p_m + (1 - \alpha) p_f} > \alpha p_m + (1 - \alpha) p_f
\]

Multiply both sides by denominator (positive):
\[
\alpha p_m^2 + (1 - \alpha) p_f^2 > [\alpha p_m + (1 - \alpha) p_f]^2
\]

Expand RHS:
\[
[\alpha p_m + (1 - \alpha) p_f]^2 = \alpha^2 p_m^2 + (1 - \alpha)^2 p_f^2 + 2\alpha(1 - \alpha) p_m p_f
\]

Bring all terms to one side:
\[
\alpha p_m^2 + (1 - \alpha) p_f^2 - \alpha^2 p_m^2 - (1 - \alpha)^2 p_f^2 - 2\alpha(1 - \alpha) p_m p_f > 0
\]

Simplify coefficients for \( p_m^2 \):
\[
\alpha - \alpha^2 = \alpha(1 - \alpha)
\]

For \( p_f^2 \):
\[
(1 - \alpha) - (1 - \alpha)^2 = (1 - \alpha)[1 - (1 - \alpha)] = (1 - \alpha)\alpha = \alpha(1 - \alpha)
\]

So LHS becomes:
\[
\alpha(1 - \alpha) p_m^2 + \alpha(1 - \alpha) p_f^2 - 2\alpha(1 - \alpha) p_m p_f
\]
\[
= \alpha(1 - \alpha) [p_m^2 + p_f^2 - 2 p_m p_f]
\]
\[
= \alpha(1 - \alpha) (p_m - p_f)^2
\]

Since \( 0 < \alpha < 1 \) and \( p_m \neq p_f \), we have:
\[
\alpha(1 - \alpha) (p_m - p_f)^2 > 0
\]

Thus the inequality holds strictly.

---

## Final Answer

\[
\boxed{P(A_2 \mid A_1) > P(A_1)}
\]

Interpretation: Observing a claim in year 1 makes a claim in year 2 more likely because it shifts belief toward the higher-risk gender.

---

## Pattern Recognition
- Pattern type: Conditional probability with hidden variable (gender).
- Key trick: Use the fact that \( E[X^2] > (E[X])^2 \) for non-degenerate \( X \) (variance positive) — this is essentially Jensen’s inequality / convexity of \( x^2 \).
- Similar problems: Two-period insurance claims, medical test-retest, any setting with persistent unobserved heterogeneity.

---

## Key Insight (1–2 lines)

The inequality follows from \( x^2 \) being convex: \( E[p^2] > (E[p])^2 \) if \( p \) varies across groups. Here \( p \) = claim probability, random because gender is random.

---

## Mistakes / Lessons
- What I got wrong: Initially wanted to use Bayes reflexively — unnecessary here.
- What I will remember: Use direct conditioning \( P(A|B) = P(A \cap B)/P(B) \) when you can compute joint and marginal directly (e.g., by conditioning on a hidden variable). Bayes is only when you know \( P(B|A) \) but can’t easily get \( P(A \cap B) \) otherwise.

Tags: conditional probability, law of total probability, Jensen's inequality, variance, unobserved heterogeneity
