## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3 / Problem 54
- Difficulty (1–5): 2

---

## Problem Statement

Players \( A, B, C, D \) are randomly lined up. The first two players in line then play a game; the winner of that game then plays a game with the person who is third in line; the winner of that game then plays a game with the person who is fourth in line. The winner of that last game is considered the winner of the tournament. If \( A \) wins each game it plays with probability \( p \), determine the probability that \( A \) is the winner of the tournament.

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  → Sequential probability, conditioning on position in line.

- What is random vs fixed?  
  → Random: lineup order (uniform over 4! permutations). Fixed: \( A \) wins any game with prob \( p \).

- What is the smallest useful variable definition?  
  Let \( f(k) = P(A \text{ wins tournament} \mid A \text{ starts in position } k) \).

---

## My First Attempt

Condition on \( A \)’s position (1 to 4 equally likely). Compute \( f(k) \) for each \( k \), then average.

---

## Solution Strategy
- Step 1: Compute \( f(1) \) and \( f(2) \) — \( A \) must win 3 games in a row.
- Step 2: Compute \( f(3) \) — \( A \) must win 2 games (after entering in match 2).
- Step 3: Compute \( f(4) \) — \( A \) must win 1 game (final match only).
- Step 4: Average over \( k = 1,2,3,4 \).

Why this works: The tournament structure is fixed given \( A \)’s starting position.

---

## Full Solution

**Case \( k = 1 \) (A first in line):**  
Match 1: A vs P2 → win (prob \( p \))  
Match 2: A vs P3 → win (prob \( p \))  
Match 3: A vs P4 → win (prob \( p \))  
\[
f(1) = p \cdot p \cdot p = p^3
\]

**Case \( k = 2 \) (A second in line):**  
Match 1: P1 vs A → win (prob \( p \))  
Then same path as \( k=1 \): must win next two matches.  
\[
f(2) = p \cdot p \cdot p = p^3
\]

**Case \( k = 3 \) (A third in line):**  
Match 1: P1 vs P2 → some winner W1  
Match 2: W1 vs A → win (prob \( p \))  
Match 3: A vs P4 → win (prob \( p \))  
\[
f(3) = p \cdot p = p^2
\]

**Case \( k = 4 \) (A fourth in line):**  
Match 1: P1 vs P2 → W1  
Match 2: W1 vs P3 → W2  
Match 3: W2 vs A → win (prob \( p \))  
\[
f(4) = p
\]

**Unconditional probability:**  
Positions equally likely: \( P(\text{pos } k) = \frac14 \)

\[
P(A \text{ wins}) = \frac14 \left[ f(1) + f(2) + f(3) + f(4) \right]
\]
\[
= \frac14 \left[ p^3 + p^3 + p^2 + p \right]
\]
\[
= \frac14 \left( p + p^2 + 2p^3 \right)
\]

---

## Final Answer

\[
\boxed{\frac{p + p^2 + 2p^3}{4}}
\]

---

## Pattern Recognition
- Pattern type: Sequential tournament, conditioning on random start position.
- Key trick: Break into cases by \( A \)’s position; path length = number of matches \( A \) must win.
- Similar problems: Any “random seeding in a knockout bracket” problem.

---

## Key Insight (1–2 lines)

\( A \)’s chance to win = average over starting positions of \( p^{\text{(number of matches A must play)}} \).  
Positions 1 and 2 require 3 wins, position 3 requires 2 wins, position 4 requires 1 win.

---

## Mistakes / Lessons
- What I got wrong: Nothing — correct on first try.
- What I will remember: In random-lineup tournaments, condition on the position of the player of interest.

Tags: sequential probability, tournament, random permutation, conditioning
