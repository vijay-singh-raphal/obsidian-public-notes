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
$$ (N - 1) * N /2 $$
Number of operation performed  = 3 OP so complexity will be O(3) → Constant Work
**Loop Example** if N = 5
$$ 4 + 3 + 2 + 1 $$
n - 1 operation for each digits
n - 2 operation for each operator
so the total operations are 
$$ 2n -3 $$
If N = 5 so number of operations are 7.
If N= 1000 so number of operations are 
$$ 2 * 1000 - 3 = 1997 $$
If we use n*(n-1)/2 there are 3 OP only
$$ 1000 * (1000 - 1) / 2 $$
As input size increases, how does the number of operations grow?
This is the core idea of **Time Complexity**.
#### Time Complexity
Time complexity measures how the runtime of an algorithm grows as input size (N) increases.
To identify time complexity we do asymptotic analysis.
And asymptotic expression is expressed using Big O notation.
#### Asymptotic Analysis
For I/P size N -> number of operation has to done by the computer is f(N).
$$ f(x) = x^2 + 1 $$
We can test the growth by give the value of x.
When we do complexity analysis we are not interested in the precision we are interested in the trend.
