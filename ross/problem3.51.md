## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 51
- Difficulty (1–5): 2

---

## Problem Statement

Prostate cancer is the most common type of cancer found in males. As an indicator of whether a male has prostate cancer, doctors often perform a test that measures the level of the prostate-specific antigen (PSA) that is produced only by the prostate gland. Although PSA levels are indicative of cancer, the test is notoriously unreliable. Indeed, the probability that a noncancerous man will have an elevated PSA level is approximately 0.135, increasing to approximately 0.268 if the man does have cancer. If, on the basis of other factors, a physician is 70 percent certain that a male has prostate cancer, what is the conditional probability that he has the cancer given that

a. the test indicated an elevated PSA level?  
b. the test did not indicate an elevated PSA level?

Repeat the preceding calculation, this time assuming that the physician initially believes that there is a 30 percent chance that the man has prostate cancer.

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Conditional probability / Bayes’ theorem with a binary test.

- What is random vs fixed?  
  → Random: cancer status, then test result. Fixed: test sensitivity and specificity (given as probabilities).

- What is the smallest useful variable definition?  
  Let \( C \) = has prostate cancer, \( T^+ \) = elevated PSA, \( T^- \) = not elevated.  
  Given: \( P(T^+ \mid C^c) = 0.135 \), \( P(T^+ \mid C) = 0.268 \), so \( P(T^- \mid C) = 0.732 \), \( P(T^- \mid C^c) = 0.865 \).

---

## My First Attempt

Straightforward Bayes. Compute \( P(T^+) \) by total probability, then \( P(C \mid T^+) \) and \( P(C \mid T^-) \) for each prior \( P(C) \).

---

## Solution Strategy
- Step 1: Write Bayes’ formula for \( P(C \mid T^+) \) and \( P(C \mid T^-) \).
- Step 2: Compute \( P(T^+) \) and \( P(T^-) \) using law of total probability.
- Step 3: Substitute for each prior (0.70 and 0.30).

Why this works: The test results give evidence that updates the prior probability of cancer.

---

## Full Solution

**Given:**  
\( P(T^+ \mid C) = 0.268 \), \( P(T^+ \mid C^c) = 0.135 \)  
\( P(T^- \mid C) = 0.732 \), \( P(T^- \mid C^c) = 0.865 \)

---

### Case 1: \( P(C) = 0.70 \), \( P(C^c) = 0.30 \)

**a. \( P(C \mid T^+) \)**  

\[
P(T^+) = (0.268)(0.70) + (0.135)(0.30) = 0.1876 + 0.0405 = 0.2281
\]
\[
P(C \mid T^+) = \frac{0.268 \times 0.70}{0.2281} = \frac{0.1876}{0.2281} \approx 0.8224
\]

**b. \( P(C \mid T^-) \)**  

\[
P(T^-) = (0.732)(0.70) + (0.865)(0.30) = 0.5124 + 0.2595 = 0.7719
\]
\[
P(C \mid T^-) = \frac{0.732 \times 0.70}{0.7719} = \frac{0.5124}{0.7719} \approx 0.6638
\]

---

### Case 2: \( P(C) = 0.30 \), \( P(C^c) = 0.70 \)

**a. \( P(C \mid T^+) \)**  

\[
P(T^+) = (0.268)(0.30) + (0.135)(0.70) = 0.0804 + 0.0945 = 0.1749
\]
\[
P(C \mid T^+) = \frac{0.0804}{0.1749} \approx 0.4597
\]

**b. \( P(C \mid T^-) \)**  

\[
P(T^-) = (0.732)(0.30) + (0.865)(0.70) = 0.2196 + 0.6055 = 0.8251
\]
\[
P(C \mid T^-) = \frac{0.2196}{0.8251} \approx 0.2661
\]

---

## Final Answer

**Prior \( P(C) = 0.70 \):**  
a. \( \boxed{0.8224} \)  
b. \( \boxed{0.6638} \)

**Prior \( P(C) = 0.30 \):**  
a. \( \boxed{0.4597} \)  
b. \( \boxed{0.2661} \)

---

## Pattern Recognition
- Pattern type: Medical test / Bayes with binary outcomes.
- Key trick: Always compute \( P(T^+) \) and \( P(T^-) \) first using total probability.
- Similar problems: Drug testing, spam filtering, signal detection.

---

## Key Insight (1–2 lines)

Even a weak test (sensitivity 0.268, specificity 0.865) updates beliefs meaningfully. Negative result doesn’t rule out cancer because false negative rate is high (0.732).

---

## Mistakes / Lessons
- What I got wrong: Nothing — straightforward.
- What I will remember: Bayes for test problems: posterior = (sensitivity × prior) / (sensitivity×prior + false positive×(1−prior)).

Tags: Bayes' theorem, conditional probability, medical test, PSA
