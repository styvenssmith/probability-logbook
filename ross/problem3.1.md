# Problem: Conditional probability with dice

## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.1
- Difficulty (1–5): 2

---

## Problem Statement

Two fair dice are rolled. What is the conditional probability that at least one lands on a 6, given that the dice land on different numbers?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Conditional probability with equally likely outcomes and finite sample space.

- **What is random vs fixed?**  
  Random: outcomes of two dice rolls.  
  Fixed: dice fair, rolls independent.

- **What is smallest useful variable definition?**  
  Let \( A = \) “at least one die shows 6”  
  Let \( B = \) “dice show different numbers”  
  We want \( P(A \mid B) \).

---

## My First Attempt

I wrote:

\[
P(A \cap B) = \frac{10}{36},\quad P(B) = \frac{30}{36},\quad P(A \mid B) = \frac{1}{3}.
\]

This matches the book answer.

---

## Solution Strategy

### Step 1:
Define the events as above.

### Step 2:
Find \( |A \cap B| \):

- Case 1: first die = 6, second ≠ 6 → 5 outcomes.
- Case 2: second die = 6, first ≠ 6 → 5 outcomes.
- Total \( |A \cap B| = 10 \).

So \( P(A \cap B) = \frac{10}{36} \).

### Step 3:
Find \( |B| \):

Number of outcomes with different numbers:  
36 − 6 (for same numbers) = 30.

So \( P(B) = \frac{30}{36} \).

Conditional probability:

\[
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{\frac{10}{36}}{\frac{30}{36}} = \frac{10}{30} = \frac{1}{3}.
\]

Why this works:  
Because all outcomes equally likely, the formula is valid.

---

## Full Solution

Two dice are rolled: \( 6 \times 6 = 36 \) equally likely outcomes.  
Event \( B \) (different numbers) has \( 30 \) outcomes.  
Event \( A \cap B \) (at least one 6 and different) has \( 10 \) outcomes.  

\[
P(A \mid B) = \frac{|A \cap B|}{|B|} = \frac{10}{30} = \frac{1}{3}.
\]

---

## Final Answer

\[
\boxed{\frac{1}{3}}
\]

---

## Pattern Recognition
- **Pattern type:** Standard conditional probability with symmetric dice.
- **Key trick:** Count directly from definition: \( P(A|B) = |A \cap B| / |B| \) due to equally likely outcomes.
- **Similar problems:**  
  Any "given different values" problems, "given sum is odd" problems, "given one die shows a certain number" problems.

---

## Key Insight (1–2 lines)

Many conditional probability problems with dice and "at least one condition" can be solved by counting the favorable outcomes in the reduced sample space (\( B \)) directly, rather than using formulas like inclusion–exclusion blindly.

---

## Mistakes / Lessons
- **What I got wrong:** Initially thought maybe "both dice showing 6" is part of \( A \cap B \) — no, because they are not different numbers.
- **What I will remember:** When \( P(A \cap B) \) and \( P(B) \) are both easily countable from the sample space in equally likely settings, the "fraction of outcomes" method is fastest and safest.

Tags: conditional probability, dice, equally likely outcomes, Sheldon Ross
