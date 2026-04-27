## Source
- Book / Platform:Sheldon Ross
- Chapter / Problem #: 3.33
- Difficulty (1–5): 2

---

## Problem Statement

Ms. Aquina has a possibly cancerous tumor (`α = P(cancer)`).  
She doesn’t want to hear bad news now, but doesn't want “no call” to imply cancer for sure.  

She instructs doctor: Flip a coin.

- **Heads**: Call if good news → don’t call if bad news.  
- **Tails**: Don’t call regardless.

Let `β = P(cancer | no call)`.

**a.** Which is larger, `α` or `β`?  
**b.** Find `β` in terms of `α` and prove part (a).

---

## Key Observations (DO BEFORE SOLVING)
- What type of problem is this?  
  *Bayes’ theorem, conditional probability.*

- What is random vs fixed?  
  - `α` = prior probability of cancer (fixed, unknown).  
  - Coin flip is random (50% each side).  
  - Doctor follows deterministic rule given news and coin.

- What is the smallest useful variable definition?  
  Events:  
  - `B` = cancer  
  - `N` = no call  
  - `C` = call  
  - `H` = heads, `T` = tails

---

## My First Attempt

Let’s compute `P(C)` first:

From problem:
- `P(C | B, H) = 0` (Heads + cancer → no call)
- `P(C | G, H) = 1` (Heads + good news → call)
- `P(C | any, T) = 0`

So  
`P(C|G) = P(H)·1 + P(T)·0 = 0.5`  
`P(C|B) = 0`

Therefore:  
`P(C) = 0.5·P(G) + 0·P(B) = 0.5(1 - α)`  
`P(N) = 1 - P(C) = 0.5 + 0.5α`

Then  
`β = P(B|N) = P(N|B)·P(B) / P(N)`.

`P(N|B) = 1` because doctor never calls when cancer.  
So `β = α / [0.5(1+α)] = 2α / (1+α)`.

Compare α and β:

`α - β = α - 2α/(1+α) = [α(1+α) - 2α] / (1+α) = [α + α² - 2α] / (1+α)`  
`= (α² - α) / (1+α) = α(α - 1)/(1+α)`.

Since `0 < α < 1`, `α-1 < 0`, so `α(α-1)/(1+α) < 0`.  
Thus `α - β < 0` → **α < β**.

---

## Solution Strategy
- Step 1: Find `P(C)` using law of total probability over `B` and `G` given coin.
- Step 2: Find `P(N)`.
- Step 3: Find `β = P(B|N)` = `P(N|B)α / P(N)`.
- Step 4: Compare `α` and `β` using algebra.

Why this works: This gives **β explicitly** and proof that β > α.

---

## Full Solution

Let `α = P(B)`.  
Let `H` = coin heads (P(H)=0.5), `T` = tails.

`P(C|G,H) = 1`, `P(C|B,H) = 0`  
`P(C|⋅,T) = 0`

So:
`P(C|G) = P(H)·1 = 0.5`, `P(C|B) = 0`.

`P(C) = P(C|G)P(G) + P(C|B)P(B)`  
`= 0.5(1 - α) + 0·α = 0.5(1 - α)`.

`P(N) = 1 - P(C) = 0.5 + 0.5α = 0.5(1 + α)`.

`P(N|B) = 1` (always no call if cancer).  

Thus  
`β = P(B|N) = P(N|B)P(B) / P(N) = α / [0.5(1+α)] = 2α / (1+α)`.

Prove β > α:  
`β - α = 2α/(1+α) - α = [2α - α(1+α)]/(1+α) = [2α - α - α²]/(1+α)`  
`= [α - α²]/(1+α) = α(1 - α)/(1+α) > 0` for 0<α<1.

Thus α < β.

---

## Final Answer

- **(a)** β > α  
- **(b)** β = 2α / (1+α)

---

## Pattern Recognition
- Pattern type: Bayes with deterministic call rule and extra randomization
- Key trick: Use `P(C|G)` and `P(C|B)` from coin flips by marginalizing over H/T
- Similar problems: "Repeated testing with imperfect response", "randomized response surveys"

---

## Key Insight (1–2 lines)

Even if doctor never calls for sure in cancer case, no call also possible under good news by Tails → less informative silence, so β > α.

---

## Mistakes / Lessons
- What I got wrong: Initially thought the problem was symmetrical, but not.  
- What I will remember: Randomizing the decision rule changes posterior updating: `P(N)=0.5(1+α)` not 1 – so β > α.

Tags: `#bayes` `#conditional-probability` `#randomized-response`
