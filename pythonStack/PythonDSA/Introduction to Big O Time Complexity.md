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
![complexity|600](https://cdn.botpenguin.com/assets/website/0_ou_Bk_T_Mg_A_yg_Etfz_cd048b679d.webp)
For identifying the trend we use asymptotic analysis.
$$ f(n) = n + 3$$
if n = 1 => no. of operation are 4
if n = 1000 => no. of operation are 1003
But suppose if N is very large and equation is (N + 3).
"This 3 becomes insignificant so we can ignore it because we are not checking the precision we want a trend so it become".
$$ f(n) = n $$
So we can say that the time complexity of the order on N or O(N).
O(N) => This tells as I/P size increases, time take increases linearly.

So asymptotic analysis says that we are interested in the properties of a function f(N) as N become very large.
#### Example solve
$$f(n) = n^2 + 3n$$
$$f(n) = 2n^2 + 5n$$
