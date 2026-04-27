## Source
- Book / Platform:Sheldon Ross
- Chapter / Problem #: 3.36 (based on Example 3f)
- Difficulty (1–5): 2

---

## Problem Statement

In Example 3f, the inspector is initially 60% convinced of guilt, and new evidence shows the criminal has a certain characteristic (e.g., left-handedness, baldness, brown hair).  
20% of the population has this characteristic.

Suppose now the new evidence is subject to different possible interpretations and in fact shows **only that it is 90% likely that the criminal possesses the characteristic** (rather than certainty).  

How likely would it be that the suspect is guilty (assuming, as before, that the suspect has the characteristic)?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Bayes' theorem — prior over guilt updated by evidence about the characteristic.

- **What is random vs fixed?**  
  Random: guilt of suspect, whether suspect has characteristic given guilt status.  
  Fixed: prior probability of guilt (0.6), base rate of characteristic (0.2), and new reliability (0.9).

- **What is the smallest useful variable definition?**  
  \( G \): suspect guilty  
  \( C \): suspect has characteristic  
  \( C_\text{criminal} \): criminal has characteristic (evidence says \( P(C_\text{criminal} \mid G) = 0.9 \) now, not 1)

---

## My First Attempt

In Example 3f:  
\( P(G) = 0.6 \), \( P(C \mid G) = 1 \), \( P(C \mid G^c) = 0.2 \)

Now evidence is less reliable: “90% likely that the criminal possesses the characteristic” ⇒ \( P(C \mid G) = 0.9 \)  
Also: suspect has characteristic \( C \) given.

So:  
\( P(C \mid G) = 0.9 \)  
\( P(C \mid G^c) = 0.2 \) (unchanged base rate)  
\( P(G) = 0.6 \)

Use Bayes:

\[
P(G \mid C) = \frac{0.9 \times 0.6}{0.9 \times 0.6 + 0.2 \times 0.4} = \frac{0.54}{0.54 + 0.08} = \frac{0.54}{0.62} = \frac{54}{62} = \frac{27}{31}
\]

---

## Solution Strategy
- **Step 1:** Identify modified \( P(C \mid G) \) = 0.9 (instead of 1).
- **Step 2:** Keep \( P(C \mid G^c) = 0.2 \) (base rate of characteristic).
- **Step 3:** Apply Bayes' theorem with prior \( P(G) = 0.6 \).

Why this works: The only change from Example 3f is the reduced certainty that the criminal has the characteristic given guilt.

---

## Full Solution

Let \( G \) = suspect guilty, \( C \) = suspect has the characteristic.

Prior:  
\[
P(G) = 0.6,\quad P(G^c) = 0.4
\]

Likelihoods:  
\[
P(C \mid G) = 0.9 \quad\text{(new evidence only 90% certain)}
\]  
\[
P(C \mid G^c) = 0.2 \quad\text{(base rate in population)}
\]

Bayes:  
\[
P(G \mid C) = \frac{P(C \mid G)P(G)}{P(C \mid G)P(G) + P(C \mid G^c)P(G^c)}
\]  
\[
= \frac{0.9 \times 0.6}{0.9 \times 0.6 + 0.2 \times 0.4}
\]  
\[
= \frac{0.54}{0.54 + 0.08} = \frac{0.54}{0.62} = \frac{54}{62} = \frac{27}{31}
\]  
\[
\approx 0.87097
\]

---

## Final Answer

\[
\boxed{\frac{27}{31}}
\]

---

## Pattern Recognition
- **Pattern type:** Bayes' theorem with imperfect evidence
- **Key trick:** Changing \(P(C \mid G)\) from 1 to 0.9 reduces posterior probability of guilt slightly
- **Similar problems:** Medical test with sensitivity < 1; eyewitness testimony with reliability < 1

---

## Key Insight (1–2 lines)

When evidence is less than perfectly reliable, the posterior probability of guilt decreases, even if suspect has the characteristic.

---

## Mistakes / Lessons
- **What I got wrong:** Nothing — straightforward application.
- **What I will remember:** Always separate \( P(\text{evidence observed} \mid \text{guilt}) \) from \( P(\text{criminal has trait} \mid \text{guilt}) \) when reinterpreted.

Tags: `#bayes` `#imperfect-evidence` `#conditional-probability`
