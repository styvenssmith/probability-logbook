## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.3
- Difficulty (1–5): 3

---

## Problem Statement

Use Equation (2.1) to compute in a hand of bridge the conditional probability that East has 3 spades given that North and South have a combined total of 8 spades.

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Conditional probability with a fixed deck of cards, dealing 13 cards each to 4 players.

- **What is random vs fixed?**  
  Random: distribution of cards to N, S, E, W.  
  Fixed: N+S together have 8 spades (this is the conditioning event).

- **What is the smallest useful variable definition?**  
  \( A \) = “East has 3 spades”  
  \( B \) = “North and South together have 8 spades”

We want \( P(A \mid B) \).

---

## My First Attempt

I reasoned:

If N+S together have 8 spades, then of the original 13 spades, \( 13 - 8 = 5 \) remain for E+W.

N+S together have 26 cards (13+13), so \( 52 - 26 = 26 \) cards remain for E+W.  
Those 26 cards consist of: 5 spades, 21 non-spades.

East gets 13 cards from these 26, all possible hands equally likely.

So:

\[
P(A \mid B) = \frac{\binom{5}{3}\binom{21}{10}}{\binom{26}{13}}.
\]

This matches the combinatorial interpretation of conditional probability:  
Given B, East’s hand is uniformly random from the remaining 26 cards.

---

## Solution Strategy

### Step 1:
Use the definition \( P(A \mid B) = P(A \cap B)/P(B) \) but recognize that \( P(A \cap B)/P(B) = |A \cap B|/|B| \) (in terms of equally likely deals) counts the same as fixing B and counting completions.

### Step 2:
Given B (N+S have 8 spades), remaining deck for E+W:  
- 26 cards total  
- 5 spades, 21 non-spades.

### Step 3:
East’s hand size = 13.  
Number of ways to get 3 spades and 10 non-spades from available cards: \( \binom{5}{3}\binom{21}{10} \).  
Total possible East hands from the 26 remaining cards: \( \binom{26}{13} \).

---

Why this works:  
Once we condition on N+S’s cards (with fixed spade count), the remaining distribution to East is uniform over all subsets of size 13 from the 26 remaining cards. The count ratio directly gives the conditional probability.

---

## Full Solution

We are told: N+S together have exactly 8 spades.

Spades left for E+W: \( 13 - 8 = 5 \).  
Non-spades left for E+W: \( 39 - (\text{N+S non-spades})\). But easier:  
Cards left for E+W = \( 52 - 26 = 26 \) total cards:  
\[
\#\text{spades left} = 5, \quad \#\text{non-spades left} = 26 - 5 = 21.
\]

Given this, East draws 13 cards from these 26, with all subsets equally likely.

- To have exactly 3 spades, East chooses 3 spades from the 5 available: \( \binom{5}{3} \) ways.  
- And \( 13 - 3 = 10 \) non-spades from the 21 available: \( \binom{21}{10} \) ways.

Thus:

\[
P(A \mid B) = \frac{\binom{5}{3} \binom{21}{10}}{\binom{26}{13}}.
\]

---

## Final Answer

\[
\boxed{\frac{\binom{5}{3}\binom{21}{10}}{\binom{26}{13}}}
\]

Numerically (optional):  
\[
\binom{5}{3} = 10,\quad \binom{21}{10} = 352716,\quad \binom{26}{13} = 10400600
\]
\[
P = \frac{10 \times 352716}{10400600} \approx 0.339
\]

---

## Pattern Recognition
- **Pattern type:** Conditional probability in card dealing with hypergeometric distribution.
- **Key trick:** Once you condition on N+S’s combined hand, the remaining deck is of known composition; East’s hand is hypergeometric from that reduced deck.
- **Similar problems:**  
  “P(East has exactly k aces given N+S have m aces)”  
  “P(West has at least 4 hearts given N has 5 hearts)”  
  Hypergeometric probability problems in sampling without replacement.

---

## Key Insight (1–2 lines)

Conditioning on another player’s cards reduces the sample space to a smaller "remaining deck" with known makeup. Hypergeometric counting from that reduced deck directly gives the conditional probability.

---

## Mistakes / Lessons
- **What I got wrong:** Initially forgot that after conditioning, the possible East hands are not all \( \binom{52}{13} \) but only those consistent with N+S’s fixed cards.  
  But my final approach avoided this by directly counting from remaining 26 cards.

- **What I will remember:** In card problems with multiple players, conditioning on some players’ hands tells us exactly what cards remain, making the probability just a hypergeometric problem.

Tags: conditional probability, bridge, cards, hypergeometric distribution, fixed sum of cards
