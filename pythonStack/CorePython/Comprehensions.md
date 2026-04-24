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
```
# Set Comprehension
### Syntax
```python
{expression for item in iterable}

{x*x for x in range(5)}


```