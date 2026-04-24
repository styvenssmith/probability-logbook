
## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.7
- Difficulty (1–5): 2

---

## Problem Statement

The king comes from a family of 2 children. What is the probability that the other child is his sister?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Conditional probability with equally likely gender outcomes, “boy or girl paradox” variant.

- **What is random vs fixed?**  
  Random: genders of the two children (ordered by birth).  
  Fixed: the king is male (so the family contains at least one boy).

- **What is the smallest useful variable definition?**  
  Let \( A \) = “other child is a girl”  
  Let \( B \) = “family has at least one boy” (since king exists)  
  We want \( P(A \mid B) \).

---

## My First Attempt

I initially only considered the unordered case \( BG \) and forgot \( GB \).  
So I got \( P = \frac{1/4}{3/4} = 1/3 \) — wrong.  
The mistake was treating \( BG \) as the only “one boy, one girl” case without accounting for birth order, which matters when computing probabilities from ordered equally likely outcomes.

---

## Solution Strategy

### Step 1:
List equally likely ordered outcomes for two children (older, younger):  
\( BB, BG, GB, GG \) — each probability \( 1/4 \).

### Step 2:
Given king exists ⇒ family has at least one boy ⇒ eliminate \( GG \).  
Remaining equally likely: \( BB, BG, GB \), each probability \( 1/3 \) given \( B \).

### Step 3:
“Other child is a girl” happens in \( BG \) and \( GB \) — 2 out of 3 cases.  
So \( P = 2/3 \).

---

Why this works:  
Conditioning on “at least one boy” in ordered equally likely outcomes leaves \( BB, BG, GB \) equally likely. Count favorable.

---

## Full Solution

Possible ordered outcomes: \( BB, BG, GB, GG \) each with prob \( 1/4 \).

Let \( B \) = “at least one boy” ⇒ \( P(B) = 3/4 \).  
Let \( A \) = “other child is a girl” ⇒ \( A \cap B = \{BG, GB\} \), \( P(A \cap B) = 2/4 = 1/2 \).

\[
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{1/2}{3/4} = \frac{2}{3}.
\]

So the king’s sibling is his sister with probability \( 2/3 \).

---

## Final Answer

\[
\boxed{\frac{2}{3}}
\]

---

## Pattern Recognition
- **Pattern type:** Conditional probability with equally likely ordered outcomes, “at least one” conditioning.
- **Key trick:** Don’t collapse unordered cases too early — the equally likely space is ordered pairs for births.
- **Similar problems:**  
  “Given a family has two children and one is a boy, prob both are boys?” (Answer: 1/3)  
  “Given at least one is a boy born on Tuesday, prob both boys?” (Famous Tuesday boy problem)

---

## Key Insight (1–2 lines)

Order matters for equally likely outcomes when birth order isn’t specified but can be assumed for uniform probability. The unordered collection \(\{BG\}\) actually corresponds to two ordered outcomes: \(BG\) and \(GB\).

---

## Mistakes / Lessons
- **What I got wrong:** Forgot \( GB \) case, thought only one arrangement of “one boy, one girl” existed in probability calculation after conditioning.
- **What I will remember:** Always consider ordered outcomes if probability space is originally defined with order (e.g., older/younger child). Once you condition, each remaining ordered outcome has equal conditional probability.

Tags: conditional probability, boy-girl paradox, equally likely outcomes, ordered pairs, at least one
