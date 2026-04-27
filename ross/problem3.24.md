## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: 3.24
- Difficulty (1–5): 2

---

## Problem Statement

Urn I: 2 white (W), 4 red (R)  
Urn II: 1 white, 1 red  

Step 1: Pick a ball randomly from Urn I → put into Urn II.  
Step 2: Pick a ball randomly from Urn II.

a. Find \(P(\text{ball from Urn II is white})\)
b. Find \(P(\text{transferred ball was white} \mid \text{Urn II pick is white})\)

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  Conditional probability with two-stage experiment (transfer then draw).
- What is random vs fixed?  
  Transfer outcome random; second urn composition depends on transfer.
- What is the smallest useful variable definition?  
  Let \(W_T\) = transferred ball is white.  
  Let \(W_S\) = selected ball from Urn II (after transfer) is white.

---

## My First Attempt

We can use law of total probability for part a.

Case 1: Transferred ball is white (\(W_T\)):  
Probability of \(W_T = \frac{2}{6} = \frac{1}{3}\).  
After transfer, Urn II: from (1W,1R) → (2W,1R) if white transferred.  
P(white from Urn II | \(W_T\)) = \(\frac{2}{3}\).

Case 2: Transferred ball is red (\(R_T\)):  
Probability \(R_T = \frac{4}{6} = \frac{2}{3}\).  
After transfer, Urn II: (1W,2R).  
P(white from Urn II | \(R_T\)) = \(\frac{1}{3}\).

Part a:  
\[
P(W_S) = \frac{1}{3} \cdot \frac{2}{3} + \frac{2}{3} \cdot \frac{1}{3} = \frac{2}{9} + \frac{2}{9} = \frac{4}{9}.
\]

Part b:  
\[
P(W_T \mid W_S) = \frac{P(W_T \cap W_S)}{P(W_S)} = \frac{\frac{1}{3} \cdot \frac{2}{3}}{\frac{4}{9}} 
= \frac{\frac{2}{9}}{\frac{4}{9}} = \frac{1}{2}.
\]

---

## Solution Strategy
- Step 1: Define events clearly.
- Step 2: Apply law of total probability for \(P(W_S)\) by conditioning on transfer.
- Step 3: Use Bayes’ theorem to find \(P(W_T \mid W_S)\).

Why this works: Because the composition of Urn II after transfer completely determines the probability of drawing white.

---

## Full Solution

Let:
- \(W_T\) = transferred ball is white, \(P(W_T) = \frac{2}{6} = \frac{1}{3}\).
- \(R_T\) = transferred ball is red, \(P(R_T) = \frac{4}{6} = \frac{2}{3}\).
- \(W_S\) = second pick from Urn II is white.

**After \(W_T\)**: Urn II has 2W, 1R ⇒ \(P(W_S \mid W_T) = \frac{2}{3}\).
**After \(R_T\)**: Urn II has 1W, 2R ⇒ \(P(W_S \mid R_T) = \frac{1}{3}\).

(a) By total probability:
\[
P(W_S) = P(W_T)P(W_S\mid W_T) + P(R_T)P(W_S\mid R_T)
\]
\[
P(W_S) = \frac{1}{3} \cdot \frac{2}{3} + \frac{2}{3} \cdot \frac{1}{3} 
= \frac{2}{9} + \frac{2}{9} = \frac{4}{9}.
\]

(b) By Bayes’ theorem:
\[
P(W_T \mid W_S) = \frac{P(W_T \cap W_S)}{P(W_S)}
= \frac{P(W_T)P(W_S \mid W_T)}{P(W_S)}
= \frac{\frac{1}{3} \cdot \frac{2}{3}}{\frac{4}{9}}
= \frac{\frac{2}{9}}{\frac{4}{9}} = \frac{1}{2}.
\]

---

## Final Answer

\[
\boxed{\frac{4}{9},\ \frac{1}{2}}
\]

---

## Pattern Recognition
- Pattern type: Classic "transfer then draw" problem.
- Key trick: Use law of total probability for unconditional, Bayes for reverse conditional.
- Similar problems: Randomly moving items between urns; medical test with false positives; Monty Hall type problems.

---

## Key Insight (1–2 lines)

The probability of drawing white from the second urn depends only on the final composition, so condition on the **intermediate outcome** (transfer) → use total probability and Bayes.

---

## Mistakes / Lessons
- What I got wrong: None conceptually here, but common mistake is forgetting to update Urn II composition correctly.
- What I will remember: When stage 1 changes stage 2’s distribution, condition on stage 1 outcome, then apply total probability / Bayes.

Tags: `probability`, `bayes-theorem`, `law-of-total-probability`, `urn-problem`
