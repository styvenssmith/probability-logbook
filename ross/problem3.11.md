## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.11
- Difficulty (1–5): 2

---

## Problem Statement

Two cards are randomly chosen without replacement from an ordinary deck of 52 cards. Let \( B \) be the event that both cards are aces, let \( A_s \) be the event that the ace of spades is chosen, and let \( A \) be the event that at least one ace is chosen. Find  

a. \( P(B \mid A_s) \)  
b. \( P(B \mid A) \)

---

## Key Observations (DO BEFORE SOLVING)

- What type of problem is this?  
  Conditional probability with cards (without replacement).

- What is random vs fixed?  
  Random: which two cards are drawn. Fixed: deck composition (4 aces, 1 ace of spades).

- What is the smallest useful variable definition?  
  \(B\): both aces, \(A_s\): ace of spades in hand, \(A\): at least one ace.

---

## My First Attempt

For part (a), I tried using Bayes' theorem unnecessarily.  
For part (b), I forgot that \(B \subset A\), so \(P(B \cap A) = P(B)\) directly.

---

## Solution Strategy

- Step 1 (a): Given \(A_s\) (ace of spades chosen), the second card must be an ace (3 remaining aces out of 51 remaining cards). So \(P(B \mid A_s) = 3/51\).
- Step 2 (b): \(B \subset A\), so \(P(B \mid A) = P(B) / P(A)\).
- Step 3: Compute \(P(B) = \binom{4}{2} / \binom{52}{2}\) and \(P(A) = 1 - P(\text{no aces})\).

Why this works:  
(a) Conditioning on \(A_s\) reduces the sample space to equally likely remaining cards.  
(b) Set inclusion simplifies numerator.

---

## Full Solution

**Part (a):**  

Given ace of spades is chosen, 51 cards remain, of which 3 are aces (the other 3 aces). For both cards to be aces, the second card must be one of these 3.

\[
P(B \mid A_s) = \frac{3}{51} = \frac{1}{17}
\]

**Part (b):**  

\(B \subset A \Rightarrow P(B \cap A) = P(B)\)

\[
P(B) = \frac{\binom{4}{2}}{\binom{52}{2}} = \frac{6}{1326} = \frac{1}{221}
\]

\[
P(A) = 1 - P(\text{no aces}) = 1 - \frac{\binom{48}{2}}{\binom{52}{2}} = 1 - \frac{48 \cdot 47}{52 \cdot 51}
\]

\[
\frac{48 \cdot 47}{52 \cdot 51} = \frac{2256}{2652} = \frac{188}{221}
\]
\[
P(A) = 1 - \frac{188}{221} = \frac{33}{221}
\]

Thus:
\[
P(B \mid A) = \frac{P(B)}{P(A)} = \frac{1/221}{33/221} = \frac{1}{33}
\]

---

## Final Answer

\[
\text{(a) } \boxed{\frac{1}{17}}, \quad \text{(b) } \boxed{\frac{1}{33}}
\]

---

## Pattern Recognition

- Pattern type: Conditional probability with cards, set inclusion simplification.
- Key trick: For (a), fix the known card and count remaining favorable. For (b), recognize \(B \subset A\).
- Similar problems: Any "both are X given at least one is X" or "both given specific one".

---

## Key Insight (1–2 lines)

When conditioning on \(A_s\), we don't need Bayes — just reduced sample space.  
When conditioning on \(A\) (at least one ace), \(B \subset A\) simplifies numerator to \(P(B)\).

---

## Mistakes / Lessons

- What I got wrong:  
  (a) Overcomplicated with Bayes — direct counting is faster.  
  (b) Forgot \(B \subset A\), so \(P(B \cap A) = P(B)\).

- What I will remember:  
  Always check if one event is a subset of the other before applying Bayes.  
  When conditioning on a specific card being drawn, just count remaining cards.

Tags: probability, conditional-probability, cards, without-replacement, aces, bayes-alternative
