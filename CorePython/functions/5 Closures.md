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