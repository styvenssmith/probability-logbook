## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.14
- Difficulty (1–5): 3

---

## Problem Statement

An ordinary deck of 52 cards (containing 4 aces) is randomly divided into 4 hands of 13 cards each.  
We want the probability that each hand has exactly one ace.  

Let \(E_i\) be the event that the \(i\)-th hand has exactly one ace.  
Find \(p = P(E_1 E_2 E_3 E_4)\) using the multiplication rule.

---

## Key Observations (DO BEFORE SOLVING)

- Type: Combinatorial probability, conditional probability (multiplication rule).
- Random: Which cards go into which hand.
- Fixed: Deck composition (4 aces, 48 non-aces).
- Smallest useful variable: \(E_i\) = hand \(i\) has exactly one ace.

---

## My First Attempt

I tried using the multiplication rule directly:  
\(P(E_1) \times P(E_2 \mid E_1) \times P(E_3 \mid E_1 E_2) \times P(E_4 \mid E_1 E_2 E_3)\).  
\(P(E_4 \mid \dots) = 1\) if first three each have one ace, because the last hand gets the remaining ace.

---

## Solution Strategy

- Step 1: Compute \(P(E_1)\) = P(hand 1 has exactly 1 ace).
- Step 2: Compute \(P(E_2 \mid E_1)\) given hand 1 has 1 ace and 12 non-aces.
- Step 3: Compute \(P(E_3 \mid E_1 E_2)\) given hands 1 & 2 each have 1 ace.
- Step 4: Multiply.

Why this works: Multiplication rule for conditional probabilities.

---

## Full Solution

\[
P(E_1) = \frac{\binom{4}{1} \binom{48}{12}}{\binom{52}{13}}
\]

Given \(E_1\): hand 1 has 1 ace, 12 non-aces. Remaining: 51 cards, 3 aces, 36 non-aces.  
\[
P(E_2 \mid E_1) = \frac{\binom{3}{1} \binom{36}{12}}{\binom{51}{13}}
\]

Given \(E_1 E_2\): hands 1 & 2 each have 1 ace. Remaining: 26 cards, 2 aces, 24 non-aces.  
\[
P(E_3 \mid E_1 E_2) = \frac{\binom{2}{1} \binom{24}{12}}{\binom{26}{13}}
\]

\(P(E_4 \mid E_1 E_2 E_3) = 1\).

Thus:
\[
p = \frac{\binom{4}{1} \binom{48}{12}}{\binom{52}{13}} \cdot
\frac{\binom{3}{1} \binom{36}{12}}{\binom{51}{13}} \cdot
\frac{\binom{2}{1} \binom{24}{12}}{\binom{26}{13}}
\]

Simplification (optional):

\[
p = \frac{4 \cdot 3 \cdot 2 \cdot \binom{48}{12} \binom{36}{12} \binom{24}{12}}{\binom{52}{13} \binom{51}{13} \binom{26}{13}}
\]

Using known simplification:
\[
p = \frac{24 \cdot 13^4}{52 \cdot 51 \cdot 50 \cdot 49}
\]

---

## Final Answer

\[
\boxed{\frac{24 \cdot 13^4}{52 \cdot 51 \cdot 50 \cdot 49}}
\]

or equivalently
\[
\frac{39 \cdot 26 \cdot 13}{51 \cdot 50 \cdot 49}
\]

---

## Pattern Recognition

- Pattern type: Multiplication rule for dependent events (sampling without replacement across groups).
- Key trick: Treat each hand sequentially: given previous hands have 1 ace each, the next hand's probability is just choosing 1 ace from the remaining aces over choosing 13 cards from remaining cards.
- Similar problems: "Probability each bridge hand has one ace" (classic), "balls in urns with constraints".

---

## Key Insight (1–2 lines)

Once the first \(k\) hands each get exactly one ace, the remaining aces are equally likely to be anywhere among remaining cards, so easy conditional probabilities.

---

## Mistakes / Lessons

- What I got wrong: Initially thought simpler, but must use binomial coefficients because we choose 13 cards at once, not one card at a time sequentially. But the multiplication rule still works with the conditional probabilities expressed as ratios of binomials.
- What I will remember: In "deal into hands", given previous hands fixed, the remaining cards conditionally uniform simplifies counting.

Tags: probability, conditional-probability, multiplication-rule, bridge-hand, aces, combinatorial-probability