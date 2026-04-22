# What is Recursion?
Recursion is a programming technique where a **function calls itself** repeatedly until a **base condition (terminating condition)** is met.
**OR**
A function solving a problem by breaking it into **smaller sub-problems of the same type**.
# Basic Structure of Recursion
Every recursive function has **two main parts**:
1. **Base Case (Stopping Condition)**
    - Prevents infinite recursion
    - Terminates the function
2. **Recursive Case**
    - Function calls itself with a smaller/simpler input
#### Example: Print Numbers 1 to 5
```python
def func(n):
    if n > 5:
        return
    print(n)
    func(n + 1)
func(1)
```
## Stack Behavior
- Each recursive call is stored in the **call stack**
- If no base condition is provided → **Stack Overflow Error**
## When to Use Recursion?
Use recursion when:
- The problem can be broken into **smaller sub-problems**
- Each sub-problem is **similar to the original problem**
- Solving sub-problems helps solve the main problem
## Divide and Solve
Recursion works best when:
- Problem → divided into smaller pieces
- Smaller pieces → solved recursively
- Final answer → built from those solutions
#### Example: Factorial
Find factorial of a number `n`
$$ n! = n × (n-1) × (n-2) × ... × 1 $$
$$ 5! = 5 × 4 × 3 × 2 × 1 $$
**Recursive case :**$$ n! = n × (n-1)! $$
**Base case :**
$$ 1! = 1 , 0! = 1 $$
```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))
```
## What is “Recursive Leap of Faith”?
It is a mindset used while solving recursion problems:
**Assume that the recursive function will correctly solve the smaller sub-problem**, and focus only on how to use that result to solve the bigger problem.
#### Example print the sequence 321123
### Identify the Sub-problem
- Break the problem into a smaller version of the same problem.
Original: 3 2 1 1 2 3  
Sub-problem: 2 1 1 2
- Same pattern, just smaller input.
### Trust / Faith
- You must **trust recursion**:
    - Assume the recursive call works correctly for smaller inputs
- Do NOT try to simulate every recursive step mentally
- Assume:
	- If the function works for smaller input, it will work for larger input
### Base Condition
- Defines when recursion should stop
- If n == 0 → return
```python
def seq(n):
    if n == 0:
        return 
    print(n)
    seq(n - 1)
    print(n)
seq(3)
```
# Visualizing Recursion
#### Recursion Tree
                seq(3)
               /      \
        print(3)     print(3)
             |
            seq(2)
           /      \
    print(2)     print(2)
         |
        seq(1)
       /      \
print(1)     print(1)
     |
    seq(0)
     |
   return
#### Recursion Call Stack
![[recursionStack.png]]
