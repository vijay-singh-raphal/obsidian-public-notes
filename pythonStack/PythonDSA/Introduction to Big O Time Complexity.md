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
#### Example to solve
$$f(n) = n^2 + 3n$$
$$f(n) = 2n^2 + 5n$$

$$f(n)=2n^2 + 5n$$
$$f(n)=3n + 10$$
$$f(n)=7n^3 + 2n^2 + n$$
$$f(n)=5\log n + 20$$
$$f(n)=n^2 + 100n + 500$$
$$f(n)=4$$
$$f(n)=n\log n + n$$
$$f(n)=10n^2 + 3n^3$$
$$f(n)=2^n + n^2$$
$$f(n)=n! + n^3$$
$$f(n)=\sqrt{n} + n$$
$$f(n)=n^2\log n + n^2$$
$$f(n)=3\log n + \sqrt{n}$$
$$f(n)=n^4 + n^3 + n$$
$$f(n)=\log n + \log(n^2)$$
$$f(n)=n + n\log n$$
$$f(n)=2^n + 3^n$$
$$f(n)=n^{1.5} + n$$
$$f(n)=1000n + 5000$$
$$f(n)=n^2 + n\log n$$
```python
# 1
for i in range(n):
    print(i)

# 2
for i in range(n):
    for j in range(n):
        print(i, j)

# 3
i = 1
while i < n:
    i = i * 2

# 4
i = n
while i > 0:
    i = i // 2

# 5
for i in range(n):
    for j in range(i):
        print(i, j)

# 6
for i in range(n):
    for j in range(n):
        for k in range(n):
            print(i, j, k)

# 7
for i in range(n):
    print(i)
for j in range(n):
    print(j)

# 8
for i in range(n):
    for j in range(1, n, 2):
        print(i, j)

# 9
for i in range(n):
    j = 1
    while j < n:
        j *= 2

# 10
for i in range(n):
    j = n
    while j > 0:
        j //= 2

# 11
for i in range(n):
    for j in range(i, n):
        print(i, j)

# 12
for i in range(n):
    for j in range(n):
        break

# 13
for i in range(n):
    if i % 2 == 0:
        print(i)

# 14
i = 1
while i < n:
    j = 1
    while j < n:
        j *= 2
    i *= 2

# 15
for i in range(n):
    for j in range(n):
        if j == n-1:
            print(i)

# 16
for i in range(n):
    j = i
    while j > 0:
        j -= 1

# 17
for i in range(n):
    for j in range(n):
        if j % 2 == 0:
            print(j)

# 18
i = n
while i > 1:
    i = i ** 0.5

# 19
for i in range(n):
    for j in range(i*i):
        print(j)

# 20
for i in range(n):
    for j in range(n):
        for k in range(j):
            print(i, j, k)
```

|#|Time Complexity|
|---|---|
|1|O(n)|
|2|O(n²)|
|3|O(log n)|
|4|O(log n)|
|5|O(n²)|
|6|O(n³)|
|7|O(n)|
|8|O(n²)|
|9|O(n log n)|
|10|O(n log n)|
|11|O(n²)|
|12|O(n)|
|13|O(n)|
|14|O((log n)²)|
|15|O(n²)|
|16|O(n²)|
|17|O(n²)|
|18|O(log log n)|
|19|O(n³)|
|20|O(n³)|
