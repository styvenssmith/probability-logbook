## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.10
- Difficulty (1–5): 2

---

## Problem Statement

Three cards are randomly selected, without replacement, from an ordinary deck of 52 playing cards. Compute the conditional probability that the first card selected is a spade given that the second and third cards are spades.

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability with sampling without replacement.

- What is random vs fixed?  
  Random: which cards are drawn. Fixed: deck composition (13 spades, 39 non-spades).

- What is the smallest useful variable definition?  
  \(S_1\): first card spade, \(S_2\): second card spade, \(S_3\): third card spade.

---

## My First Attempt

We want \(P(S_1 \mid S_2 \cap S_3)\).  

Using Bayes:
\[
P(S_1 \mid S_2 S_3) = \frac{P(S_2 S_3 \mid S_1) P(S_1)}{P(S_2 S_3)}
\]
Then compute \(P(S_2 S_3)\) via law of total probability conditioning on \(S_1\) and \(S_1^c\).

---

## Solution Strategy

- Step 1: Recognize symmetry — given \(S_2\) and \(S_3\) occurred, we've removed 2 spades from the deck before considering \(S_1\).
- Step 2: Compute directly: After observing \(S_2\) and \(S_3\), 50 cards remain, 11 of which are spades. First card is just one of these 50 equally likely cards.
- Step 3: Thus probability = \(\frac{11}{50}\).

Why this works: Conditional on future events in symmetric without-replacement sampling, the set of possible remaining cards is equally likely.

---

## Full Solution

Let \(S_1, S_2, S_3\) be events that 1st, 2nd, 3rd cards are spades.

We want \(P(S_1 \mid S_2 \cap S_3)\).

By definition:
\[
P(S_1 \mid S_2 S_3) = \frac{P(S_1 \cap S_2 \cap S_3)}{P(S_2 \cap S_3)}
\]

**Method 1: Direct counting after conditioning**

Given \(S_2\) and \(S_3\) have occurred, we know:
- Two spades have been removed from the deck.
- 50 cards remain (since 3 drawn total, but positions: card 1 is among the remaining if we think of draws in order? Wait — careful: \(S_2\) and \(S_3\) fixed as spades means we condition on the *actual* 2nd and 3rd draws being spades. That leaves 50 cards possibly for position 1: the 50 cards not drawn as 2nd or 3rd.)

But the 50 possible cards for position 1 are: all cards except the 2 specific spades drawn as 2nd and 3rd. These 50 contain 11 spades (since original 13 spades minus the 2 we *know* are at positions 2 and 3).

Given the symmetry of random draws without replacement, each of these 50 cards is equally likely to be in position 1. So:
\[
P(S_1 \mid S_2 S_3) = \frac{11}{50}
\]

**Method 2: Bayes (verification)**

\(P(S_1) = \frac{13}{52} = \frac14\)  
\(P(S_2 S_3 \mid S_1) = \frac{12}{51} \cdot \frac{11}{50}\)

\(P(S_2 S_3) = P(S_1)P(S_2 S_3 \mid S_1) + P(S_1^c)P(S_2 S_3 \mid S_1^c)\)  
= \(\frac14 \cdot \frac{12}{51} \cdot \frac{11}{50} + \frac34 \cdot \frac{13}{51} \cdot \frac{12}{50}\)  
= \(\frac{33}{51\cdot 50} + \frac{117}{51\cdot 50} = \frac{150}{51\cdot 50} = \frac{1}{17}\)

Thus:
\[
P(S_1 \mid S_2 S_3) = \frac{ \frac{12}{51} \cdot \frac{11}{50} \cdot \frac14 }{ \frac{1}{17} }
\]
But \( \frac{12}{51} = \frac{4}{17} \), so numerator = \(\frac{4}{17} \cdot \frac{11}{50} \cdot \frac14 = \frac{11}{17 \cdot 50}\).  

Divide by \( \frac{1}{17} \) gives \( \frac{11}{50} \).

---

## Final Answer

\[
\boxed{\frac{11}{50}}
\]

---

## Pattern Recognition

- Pattern type: Conditional probability in without-replacement sampling, symmetry argument.
- Key trick: Given future draws are fixed, condition on them first — reduces sample space.
- Similar problems: "Probability first card ace given 2nd and 3rd are aces", "probability 1st ball red given 2nd and 3rd are red" (urn without replacement).

---

## Key Insight (1–2 lines)

When conditioning on future draws in a random sequence without replacement, the set of remaining cards for earlier positions is uniformly distributed among cards not used in the conditioned events.

---

## Mistakes / Lessons

- What I got wrong: Nothing here — straightforward.
- What I will remember: Don't overcomplicate — use reduced sample space after conditioning on future events.

Tags: probability, conditional-probability, without-replacement, symmetry, deck-of-cards
