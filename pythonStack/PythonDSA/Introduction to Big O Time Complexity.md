# What Is Complexity Analysis?
Complexity analysis measures **how efficient an algorithm is**.
It helps answer:
- How much **time** an algorithm takes
- How much **memory** an algorithm uses
#### Example problem
```python
input = N
output = (N-1) + (N-2) + ... + 1

N = 5
Approach 1
4 + 3 + 2 + 1 (iterate from (n-1) to 1 and keep adding) => 10

Approach 2
Sum Formula
1 + 2 + 3 + ⋯ + (N−1) = (N−1)N​/2
```
# Which Approach Is Better?
## Why care about identifying which is better?
Huge amount of data gives significant performance difference between solution.
## What does better means?
- Fast => Time Complexity
- Less memory => Space Complexity
# Complexity Analysis, Big O
#### Important Concept: Time Is NOT Measured in Seconds
We do **not** measure algorithm efficiency by stopwatch time.
Because:
- Different computers have different speeds
- Different languages run differently
- System load affects timing
## How We Measure Time Complexity
We measure by:
**Number of simple operations performed
Examples of operations:
- Addition
- Comparison
- Assignment
- Array access