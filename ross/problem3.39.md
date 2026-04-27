## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: 3.39
- Difficulty (1–5): 2

---

## Problem Statement

a. A gambler has a fair coin and a two-headed coin in his pocket. He selects one of the coins at random; when he flips it, it shows heads. What is the probability that it is the fair coin?

b. Suppose that he flips the same coin a second time and, again, it shows heads. Now what is the probability that it is the fair coin?

c. Suppose that he flips the same coin a third time and it shows tails. Now what is the probability that it is the fair coin?

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Bayes’ theorem / odds form of Bayes — sequential updating with independent flips.

- **What is random vs fixed?**  
  Random: which coin is chosen, outcomes of flips.  
  Fixed: coins have fixed probabilities (fair: P(H)=0.5; two-headed: P(H)=1).

- **What is the smallest useful variable definition?**  
  \( F \) = fair coin chosen, \( U \) = two-headed coin chosen.  
  \( H_i \) = heads on flip \( i \), \( T_i \) = tails on flip \( i \).

---

## My First Attempt

I knew the odds form:  
\[
\frac{P(F \mid \text{data})}{P(U \mid \text{data})} = \frac{P(F)}{P(U)} \times \prod \frac{P(\text{data}_i \mid F)}{P(\text{data}_i \mid U)}
\]

Prior odds = 1.  

Part (a): LR = \(0.5/1 = 0.5\) → odds = 0.5 → \(P(F \mid H) = 0.5 / 1.5 = 1/3\). OK.

Part (b): LR for second head = 0.5 again → odds = \(0.5 \times 0.5 = 0.25\) → \(P = 0.25 / 1.25 = 1/5\). OK.

Part (c): Third flip = tails.  
LR = \(0.5 / 0\) → division by zero stumped me.  
I guessed \(P = 1\) because two-headed coin can’t show tails, but I wasn’t confident in the math.

---

## Solution Strategy
- **Step 1:** Recognize flips are independent given the coin type.
- **Step 2:** Use odds form: multiply likelihood ratios sequentially.
- **Step 3:** For zero denominator case (\(P(T \mid U)=0\)), odds become infinite → \(P(F)=1\).

Why this works: Odds form generalizes easily; zero likelihood for \(U\) means \(U\) is impossible given data.

---

## Full Solution

**Prior:**  
\( P(F) = P(U) = 0.5 \) → prior odds = 1.

**Likelihood ratios:**  
\( LR_H = \frac{P(H \mid F)}{P(H \mid U)} = \frac{0.5}{1} = 0.5 \)  
\( LR_T = \frac{P(T \mid F)}{P(T \mid U)} = \frac{0.5}{0} = \infty \)

**a. Data = H**  
Posterior odds = \(1 \times 0.5 = 0.5\)  
\( P(F \mid H) = \frac{0.5}{1.5} = \frac13 \)

**b. Data = HH**  
Posterior odds = \(1 \times 0.5 \times 0.5 = 0.25\)  
\( P(F \mid HH) = \frac{0.25}{1.25} = \frac15 \)

**c. Data = HHT**  
Posterior odds = \(1 \times 0.5 \times 0.5 \times \infty = \infty\)  
\( P(F \mid HHT) = 1 \)

---

## Final Answer

a. \( \frac13 \)  
b. \( \frac15 \)  
c. \( 1 \)

---

## Pattern Recognition
- **Pattern type:** Bayes with binary hypothesis and independent evidence.
- **Key trick:** Odds form — multiply likelihood ratios; zero in denominator → infinite odds → certainty.
- **Similar problems:** Medical testing with perfect specificity; detecting a biased coin.

---

## Key Insight (1–2 lines)

When \(P(\text{data} \mid \text{hypothesis}) = 0\), that hypothesis is ruled out completely → infinite odds for the other hypothesis.

---

## Mistakes / Lessons
- **What I got wrong:** I hesitated when I saw division by zero; should have recognized it means odds → ∞.
- **What I will remember:**  
  LR = \(0.5/0\) is not undefined — it means the numerator \(P(T \mid F) = 0.5\), denominator \(P(T \mid U) = 0\) → likelihood ratio is infinite → posterior odds infinite → posterior probability = 1.

---

Tags: `#bayes` `#odds-form` `#coin-flip` `#ross`
