## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: 3.42
- Difficulty (1–5): 2

---

## Problem Statement

Start with an urn containing 5 white and 7 red balls.  
At each stage: draw a ball, note its color, then return it to the urn **along with an additional ball of the same color**.  
A sample of size 3 is drawn this way. Find the probability that the sample contains exactly:

a. 0 white balls  
b. 1 white ball  
c. 3 white balls  
d. 2 white balls

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Polya’s urn — draws are not independent; probability of next draw depends on previous draws’ colors.

- **What is random vs fixed?**  
  Random: sequence of colors drawn.  
  Fixed: initial composition (5W, 7R), addition rule.

- **What is the smallest useful variable definition?**  
  \( W_i \) = white on draw \( i \), \( R_i \) = red on draw \( i \).

---

## My First Attempt

I directly computed probabilities for each sequence (WWW, WWR, WRW, RWW, etc.) using the Polya rule, then summed to get each case's total probability. Straightforward conditioning.

---

## Solution Strategy
- **Step 1:** Recognize that after \( k \) draws, total balls = \( 12 + k \), white balls = \( 5 + (\text{# white drawn so far}) \)  
- **Step 2:** Compute probability for each specific sequence by multiplying conditional probabilities.
- **Step 3:** Group sequences by number of white balls and sum.

Why this works: Polya’s urn is a Markov process — probability of next draw depends only on current state.

---

## Full Solution

**Initial:** 5W, 7R, total = 12.

### a. 0 white balls (RRR)

\[
P(R_1) = \frac{7}{12}
\]
After 1st R: W=5, R=8, total=13  
\[
P(R_2 \mid R_1) = \frac{8}{13}
\]
After 2nd R: W=5, R=9, total=14  
\[
P(R_3 \mid R_1R_2) = \frac{9}{14}
\]

Multiply:
\[
\frac{7}{12} \cdot \frac{8}{13} \cdot \frac{9}{14} = \frac{504}{2184}
\]
Simplify: divide numerator and denominator by 168 → \( \frac{3}{13} \).

\[
\boxed{\frac{3}{13}}
\]

---

### b. 1 white ball

Possible sequences: WRR, RWR, RRW.

**WRR**:  
\[
\frac{5}{12} \cdot \frac{7}{13} \cdot \frac{8}{14} = \frac{5 \cdot 7 \cdot 8}{12 \cdot 13 \cdot 14}
\]
Simplify \( \frac{7}{14} = \frac12 \): \( \frac{5}{12} \cdot \frac12 \cdot \frac{8}{13} = \frac{5 \cdot 8}{24 \cdot 13} = \frac{40}{312} = \frac{5}{39} \)

**RWR**:  
\[
\frac{7}{12} \cdot \frac{5}{13} \cdot \frac{8}{14} = \frac{5 \cdot 8}{24 \cdot 13} \times \frac{7}{12}/\dots
\]
Better: \( \frac{7}{12} \cdot \frac{5}{13} = \frac{35}{156} \)  
Multiply by \( \frac{8}{14} = \frac{4}{7} \): \( \frac{35}{156} \cdot \frac{4}{7} = \frac{140}{1092} = \frac{35}{273} = \frac{5}{39} \) after cancel by 7.

**RRW**:  
\[
\frac{7}{12} \cdot \frac{8}{13} \cdot \frac{5}{14} = \frac{280}{2184} = \frac{35}{273} = \frac{5}{39}
\]

Each sequence probability \( = \frac{5}{39} \), 3 sequences → \( \frac{15}{39} = \frac{5}{13} \).

\[
\boxed{\frac{5}{13}}
\]

---

### c. 3 white balls (WWW)

\[
\frac{5}{12} \cdot \frac{6}{13} \cdot \frac{7}{14}
\]
\[
= \frac{5 \cdot 6 \cdot 7}{12 \cdot 13 \cdot 14} = \frac{210}{2184} = \frac{5}{52}
\]

\[
\boxed{\frac{5}{52}}
\]

---

### d. 2 white balls

By complement:
\[
1 - \left( \frac{3}{13} + \frac{5}{13} + \frac{5}{52} \right)
\]
\[
\frac{3}{13} + \frac{5}{13} = \frac{8}{13} = \frac{32}{52}
\]
\[
\frac{32}{52} + \frac{5}{52} = \frac{37}{52}
\]
\[
1 - \frac{37}{52} = \frac{15}{52}
\]

\[
\boxed{\frac{15}{52}}
\]

---

## Final Answer

a. \( \frac{3}{13} \)  
b. \( \frac{5}{13} \)  
c. \( \frac{5}{52} \)  
d. \( \frac{15}{52} \)

---

## Pattern Recognition
- **Pattern type:** Polya’s urn — draws without replacement but with reinforcement.
- **Key trick:** Probability of a sequence depends only on the counts of W and R, not on order (exchangeable).
- **Similar problems:** Any “balls added back plus extra” process; Dirichlet-multinomial distribution.

---

## Key Insight (1–2 lines)

In Polya’s urn, the probability of a sequence with \( k \) whites in \( n \) draws depends only on \( k \), not the order — due to exchangeability.

---

## Mistakes / Lessons
- **What I got wrong:** Nothing — straightforward.
- **What I will remember:** Always adjust probabilities after each draw because the composition changes deterministically given the outcome.

Tags: `#polya-urn` `#conditional-probability` `#exchangeability` `#ross`
