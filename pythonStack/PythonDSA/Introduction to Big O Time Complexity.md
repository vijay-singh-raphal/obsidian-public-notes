## <span style="color:#ED6AFF;">What Is Complexity Analysis?</span>
Complexity analysis measures **how efficient an algorithm is**.
It helps answer:
- How much **time** an algorithm takes
- How much **memory** an algorithm uses
<span style="color:orange;">Example problem</span>
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
## <span style="color:#ED6AFF;">Which Approach Is Better?</span>
## <span style="color:#ED6AFF;">Why care about identifying which is better?</span>
Huge amount of data gives significant performance difference between solution.
## <span style="color:#ED6AFF;">What does better means?</span>
- Fast => Time Complexity
- Less memory => Space Complexity
## <span style="color:#ED6AFF;">Complexity Analysis, Big O</span>
#### Important Concept: Time Is NOT Measured in Seconds
We do **not** measure algorithm efficiency by stopwatch time.
Because:
- Different computers have different speeds
- Different languages run differently
- System load affects timing
