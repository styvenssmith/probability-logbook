# Problem: Conditional probability that first die is 6 given sum i

## Source
- Book / Platform: Sheldon Ross
- Chapter / Problem #: Chapter 3, Problem 3.2
- Difficulty (1–5): 2

---

## Problem Statement

If two fair dice are rolled, what is the conditional probability that the first one lands on 6 given that the sum of the dice is \(i\)? Compute for all values of \(i\) between 2 and 12.

---

## Key Observations (DO BEFORE SOLVING)
- **What type of problem is this?**  
  Conditional probability, with conditioning on sum of two dice.

- **What is random vs fixed?**  
  Random: outcomes of two dice rolls.  
  Fixed: dice fair, rolls independent.

- **What is the smallest useful variable definition?**  
  \(A\) = “first die shows 6”  
  \(B_i\) = “sum of two dice = \(i\)”  
  Want \(P(A \mid B_i)\) for \(i = 2, 3, \dots, 12\)

---

## My First Attempt

I reasoned:

- For sums less than 7, first die cannot be 6 because smallest possible sum with first die = 6 is 6+1=7.  
  So \(P(A \mid B_i) = 0\) for \(i = 2, 3, 4, 5, 6\).

- For sums ≥ 7:  
  If first die = 6 and sum = i ⇒ second die = i − 6, which must be between 1 and 6 (true for i=7..12).  
  This is exactly 1 outcome out of total outcomes with sum i.

  Counting: number of outcomes with sum i, call it k(i).  
  Then \(P(A \mid B_i) = \frac{1/36}{k(i)/36} = \frac{1}{k(i)}\).

So the answer comes from \(k(i) = \#\{(a,b): a+b = i\}\).

---

## Solution Strategy

### Step 1:
For sums 2–6, \(P(A \mid B_i) = 0\) (impossible for first die to be 6).

### Step 2:
For sums 7–12:

We know \(A \cap B_i\) = “first = 6 and second = i−6” → exactly 1 ordered pair.

Number of outcomes with sum \(i\):  
\(k(i) = \min(i-1, 13-i)\) because in ordered pairs (a,b) with a,b in 1..6, the count is 1,2,3,4,5,6,5,4,3,2,1 for i=2..12.

### Step 3:
Conditional probability formula:  
\[
P(A \mid B_i) = \frac{|A \cap B_i|}{|B_i|} = \frac{1}{k(i)}.
\]

So list:

i=7: k=6 → 1/6  
i=8: k=5 → 1/5  
i=9: k=4 → 1/4  
i=10: k=3 → 1/3  
i=11: k=2 → 1/2  
i=12: k=1 → 1  

---

Why this works:  
Because all outcomes equally likely, probability = count in intersection divided by count in conditioning event.

---

## Full Solution

Given two dice rolls,  
Let \(A\) = {first die = 6}, \(B_i\) = {sum = i}, \(i=2,\dots,12\).

We compute \(P(A \mid B_i) = \frac{|A \cap B_i|}{|B_i|}\).

**Case 1:** \(i < 7\):  
If first die = 6, minimum sum = 7 ⇒ impossible. So \(|A \cap B_i| = 0 ⇒ P=0\).

**Case 2:** \(i \ge 7\):  
\(A \cap B_i\) = {(6, i−6)}. There is exactly 1 outcome.  
\(|B_i|\) = number of ordered pairs (a,b) with a+b = i, a,b ∈ {1,…,6}:

- i=7: (1,6),(2,5),(3,4),(4,3),(5,2),(6,1) → 6 ways → P = 1/6  
- i=8: 5 ways → 1/5  
- i=9: 4 ways → 1/4  
- i=10: 3 ways → 1/3  
- i=11: 2 ways → 1/2  
- i=12: 1 way → 1/1 = 1

---

## Final Answer

\[
\boxed{
P(A|B_2)=0,\; P(A|B_3)=0,\; P(A|B_4)=0,\; P(A|B_5)=0,\; P(A|B_6)=0,
}
\]
\[
\boxed{
P(A|B_7)=\frac{1}{6},\; P(A|B_8)=\frac{1}{5},\; P(A|B_9)=\frac{1}{4},\;
P(A|B_{10})=\frac{1}{3},\; P(A|B_{11})=\frac{1}{2},\; P(A|B_{12})=1
}
\]

---

## Pattern Recognition
- **Pattern type:** Conditional probability with sum of dice.
- **Key trick:** For i≥7, \(P = 1 / (\text{#outcomes with sum }i)\) because exactly one of those outcomes has first die=6.
- **Similar problems:**  
  “First die is 1 given sum is 7” → 1/6;  
  “Second die is 4 given sum is 9” → 1/4; any fixed first die value given sum.

---

## Key Insight (1–2 lines)

Given the sum of two dice, the probability that the first die equals a specific value is either 0 (if impossible) or 1 divided by the number of pairs with that sum. That’s because only one of the equally likely pairs achieving the sum has that specific first die value.

---

## Mistakes / Lessons
- **What I got wrong:** Initially thought the conditional probability might be constant for all i≥7, but it varies: 1/6 for i=7, …, 1 for i=12.
- **What I will remember:** Always check if the event you’re conditioning on (sum here) is larger than the intersection when using “fraction of outcomes” in equally likely space — and in count form, \(P(A|B) = |A∩B|/|B|\). When |A∩B|=1, it’s just \(1/|B|\).

Tags: conditional probability, dice, sum of dice, equally likely outcomes, first die fixed
