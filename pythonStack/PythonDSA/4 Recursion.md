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
