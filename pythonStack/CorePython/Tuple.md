# What is a Tuple?
A **tuple** is a Python data structure that is:
- **Ordered**
- **Immutable (cannot change after creation)** 
- Allows **duplicate values**
- Can store **mixed data type**
```python
t = (1, 2, 3)
t = (1, "hello", 3.5, True)
```
### List vs Tuple

| Feature     | List         | Tuple      |
| ----------- | ------------ | ---------- |
| Mutability  | Mutable      | Immutable  |
| Syntax      | `[]`         | `()`       |
| Performance | Slower       | Faster     |
| Use case    | Dynamic data | Fixed data |
## Why Tuples are Important
You don’t use tuples just for storage — you use them for:
### 1. Fixed Data
```python
point = (x, y)
```
### 2. Returning Multiple Values
```python
def func():
    return 1, 2
```
### 3. Dictionary Keys
```python
d = {(1,2): "point"}
```
## Creating Tuples
```python
t = (1,2,3)
t = 1,2,3
t = tuple([1,2,3])
```
### Single Element Tuple
```python
t = (1)
t = (1,)
```
## Accessing Elements
### Indexing
```python
t[0]
t[-1]
```
### Slicing
```python
t[1:3]
```
Returns **new tuple**
## Tuple Operations & Immutability
### Immutability
#### What does Immutable mean?
You **cannot change** tuple elements
```python
t = (1,2,3)
t[0] = 10
```
*If tuple contains **mutable objects**, they can change*
```python
t = (1, [2,3])
t[1].append(4)
```
- Tuple is immutable → **reference cannot change**
- But list inside → **mutable object**
### Packing & Unpacking
### packing
```python
t = 1,2,3
# Automatically creates tuple
```
### Unpacking
```python
a, b, c = (1,2,3)
```
### Extended Unpacking
```python
a, *b = (1,2,3,4)
```
## Tuple Methods
```python
t.count(1)
t.index(2)
```
## Iterating Tuple
```python
for x in t:
    print(x)
    
t = (10, 20, 30)
for i, v in enumerate(t):
    print(i, v)
```
## Nested Tuple
```python
t = ((1,2), (3,4))

for i, row in enumerate(t):
    for j, val in enumerate(row):
        print(i, j, val)
```
## Functions Returning Tuples
Python functions can return **multiple values**, but internally they return a **tuple**
```python
def func():
    return 1, 2
a, b = func()
```
## Named Tuple
### Problem with Normal Tuple
```python
p = (2,3)
```
What is `2`? x or y?  (not clear)
### Solution
```python
from collections import namedtuple

Point = namedtuple("Point", ["x", "y"])
p = Point(2,3)
print(p.x)
print(p.y)
```

