# What is Comprehension?
A **short and efficient way** to create collections (list, set, dict)
# List Comprehension 
### Syntax
```python
[expression for item in iterable]

[x for x in range(5)]

[x*x for x in range(5)]

[x for x in range(10) if x % 2 == 0]

names = ["a", "b", "c"]
upper = [x.upper() for x in names]

[x for x in range(5) if x]
```
# Set Comprehension
### Syntax
```python
{expression for item in iterable}

{x*x for x in range(5)}
```
# Dictionary Comprehension
### Syntax
```python
{key_expression: value_expression for item in iterable}

{x: x*x for x in range(5)}

{x: x*x for x in range(5) if x % 2 == 0}
```

# Nested Comprehension ⭐
### What is it?
A comprehension **inside another loop**
