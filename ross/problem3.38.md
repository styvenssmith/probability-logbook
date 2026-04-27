## Source
- Book / Platform:Sheldon Ross
- Chapter / Problem #: 3.38
- Difficulty (1–5): 2

---

## Problem Statement

Stores \( A, B, C \) have 50, 75, and 100 employees respectively, and 50%, 60%, and 70% of them respectively are women. Resignations are equally likely among all employees, regardless of sex. One woman employee resigns. What is the probability that she works in store \( C \)?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Bayes’ theorem with unequal group sizes.

- **What is random vs fixed?**  
  Random: which employee resigns (uniform over all employees), their sex.  
  Fixed: store sizes, % women per store.

- **What is the smallest useful variable definition?**  
  \( A, B, C \): event employee works in store A, B, C.  
  \( W \): event employee is a woman.

---

## My First Attempt

I computed:  
Women in \( A = 0.5 \times 50 = 25 \)  
Women in \( B = 0.6 \times 75 = 45 \)  
Women in \( C = 0.7 \times 100 = 70 \)  
Total women = \( 140 \)  

So \( P(C \mid W) = \frac{70}{140} = 0.5 \).

I got the correct numeric answer, but I didn’t realize the reasoning step:  
The formula \( P(C \mid W) = \frac{\text{women in C}}{\text{total women}} \) actually follows from Bayes:

\[
P(C|W) = \frac{P(W|C)P(C)}{P(W)}
\]
Given uniform resignation, \( P(C) = \frac{\text{# in C}}{\text{total employees}} \),  
\( P(W|C) = \frac{\text{women in C}}{\text{# in C}} \),  
so numerator = \( \frac{\text{women in C}}{\text{total employees}} \)  
Denominator \( P(W) = \frac{\text{total women}}{\text{total employees}} \), so cancellation gives:

\[
P(C|W) = \frac{\text{women in C}}{\text{total women}}
\]

---

## Solution Strategy
- **Step 1:** Identify that selection is uniform among employees → prior on store proportional to store size.
- **Step 2:** Write Bayes but notice cancellation simplifies to proportion of women.
- **Step 3:** Compute number of women in each store and total women.
- **Step 4:** Ratio gives the answer.

Why this works: Because uniform selection over all employees cancels the store size factors.

---

## Full Solution

Women counts:  
\( W_A = 0.5 \times 50 = 25 \)  
\( W_B = 0.6 \times 75 = 45 \)  
\( W_C = 0.7 \times 100 = 70 \)  
Total women = \( 25 + 45 + 70 = 140 \)

\[
P(C \mid W) = \frac{W_C}{W_A + W_B + W_C} = \frac{70}{140} = 0.5
\]

---

## Final Answer

\[
\boxed{0.5}
\]

---

## Pattern Recognition
- **Pattern type:** Bayes with uniform selection from total population → conditioning on subgroup reduces to subgroup count ratio.
- **Key trick:** Write Bayes, cancel employee totals.
- **Similar problems:** “Randomly selected student is female — probability from a certain class?” given class sizes and % female.

---

## Key Insight (1–2 lines)

When sampling uniformly from employees and conditioning on “woman,” the probability she’s from a given store = proportion of **all women** working in that store.

---

## Mistakes / Lessons
- **What I got wrong:** I thought I was getting the answer “by accident” — but actually the shortcut is mathematically justified.
- **What I will remember:** In uniform employee selection, \( P(\text{store} \mid \text{woman}) \) depends only on women counts, not total employee counts.

Tags: `#bayes` `#conditional-probability` `#uniform-sampling`
