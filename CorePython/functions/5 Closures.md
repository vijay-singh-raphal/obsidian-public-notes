# **What is a Closure?**
A closure is a function that **remembers variables from its enclosing scope**, even after that outer function has finished execution.
```python
def outer():
    x = 10
    def inner():
        print(x)
    return inner
f = outer()
f()
```
`outer()` has already finished  
But `inner()` still remembers `x`
# Internal Working
When `outer()` runs:
- `x = 10` is created
- `inner()` is defined
- `inner` captures `x`
When `outer()` returns:
- Normally variables should be destroyed  
    But NOT here
Because `inner` is still using `x`
#### Example
```python
def counter():
    count = 0

    def increment():
        nonlocal count
        count += 1
        return count

    return increment

c = counter()
print(c())  # 1
print(c())  # 2
```
- `count` persists across calls
- State is maintained
## Use Case
```python
def multiplier(n):
    def multiply(x):
        return x * n
    return multiply

double = multiplier(2)
triple = multiplier(3)

print(double(5))  # 10
print(triple(5))  # 15

print(f.__closure__)
```
