# **`*args` (Variable Positional Arguments)**
Allows function to accept **any number of positional arguments**
```python
def add_numbers(*args):
    print(args)

add_numbers(1, 2, 3)
```
`args` becomes a **tuple**
# Why `*args` exists?
Because:
- You don’t always know number of inputs
- Makes functions flexible
# **`**kwargs` (Variable Keyword Arguments)**
Allows a function to accept **any number of keyword arguments**
```python
def show_info(**kwargs):
    print(kwargs)

show_info(name="Java", age=30)
```
`kwargs` becomes a **dictionary**
# **Full Parameter Order
```python
def func(positional, default=10, *args, **kwargs):
    pass
```
This order is mandatory**
# Packing & Unpacking
## Packing
Collect values into one variable
```python
def func(*args):
    print(args)

func(1, 2, 3)
```
## Unpacking
### List / Tuple
```python
def add(a, b, c):
    return a + b + c

nums = [1, 2, 3]
print(add(*nums))
```
### Dictionary
```python
def show(name, age):
    print(name, age)

info = {"name": "Java", "age": 30}
show(**info)
```
