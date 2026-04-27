## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 46
- Difficulty (1–5): 3

---

## Problem Statement

Three prisoners are informed by their jailer that one of them has been chosen at random to be executed and the other two are to be freed. Prisoner A asks the jailer to tell him privately which of his fellow prisoners will be set free, claiming that there would be no harm in divulging this information because he already knows that at least one of the two will go free. The jailer refuses to answer the question, pointing out that if A knew which of his fellow prisoners were to be set free, then his own probability of being executed would rise from 1/3 to 1/2 because he would then be one of two prisoners. What do you think of the jailer’s reasoning?

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Conditional probability / Bayes’ theorem / Paradox similar to Monty Hall.
- What is random vs fixed?  
  → Random: which prisoner is executed. Fixed: jailer’s rule for naming a freed prisoner.
- What is the smallest useful variable definition?  
  Let \( A, B, C \) = events that prisoner A, B, or C is executed.  
  Let \( J_B \) = event “jailer says B will be freed” (similarly \( J_C \)).

---

## My First Attempt

Initial thought: If jailer says “B will be freed,” then possible executors are A or C → probability A executed = 1/2. But Bayes says otherwise.

---

## Solution Strategy
- Step 1: Define prior probabilities \( P(A) = P(B) = P(C) = 1/3 \).
- Step 2: Determine jailer’s behavior:
  - If A executed (1/3), jailer picks B or C randomly → \( P(J_B \mid A) = 1/2 \), \( P(J_C \mid A) = 1/2 \).
  - If B executed (1/3), jailer must say C → \( P(J_C \mid B) = 1 \).
  - If C executed (1/3), jailer must say B → \( P(J_B \mid C) = 1 \).
- Step 3: Use Bayes to find \( P(A \mid J_B) \).

Why this works: Jailer’s choice of name gives partial information, but not as much as assuming equal likelihood among remaining prisoners.

---

## Full Solution

**Compute \( P(J_B) \):**  
\[
P(J_B) = P(J_B \mid A)P(A) + P(J_B \mid C)P(C)
\]
\[
P(J_B) = \left(\frac12\right)\left(\frac13\right) + (1)\left(\frac13\right) = \frac16 + \frac13 = \frac12
\]

**Bayes’ theorem:**  
\[
P(A \mid J_B) = \frac{P(J_B \mid A)P(A)}{P(J_B)} = \frac{\frac12 \cdot \frac13}{\frac12} = \frac13
\]

Similarly \( P(A \mid J_C) = 1/3 \).

Thus, hearing a name does **not** change A’s probability of execution — it remains \( 1/3 \).

---

## Final Answer

\[
\boxed{\text{The jailer’s reasoning is incorrect.}}
\]

Prisoner A’s probability of being executed stays \( 1/3 \) after hearing a name.

---

## Pattern Recognition
- Pattern type: Conditional probability with non-uniform response probabilities.
- Key trick: Map out jailer’s behavior completely — don’t assume all responses equally likely.
- Similar problems: Monty Hall problem, two-child paradox.

---

## Key Insight (1–2 lines)

The jailer’s choice of which name to give is **not random** in the same way across all cases — when A is the one executed, the jailer has a choice; when C is executed, jailer is forced to say B. This asymmetry keeps A’s probability at 1/3.

---

## Mistakes / Lessons
- What I got wrong: Initially trusted the jailer’s claim instead of the math.
- What I will remember: The problem narrative may state a character’s *belief*, but that belief can be wrong. Always verify with Bayes.

Tags: Bayes' theorem, conditional probability, paradox, Monty Hall, three prisoners
