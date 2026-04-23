# What is a List?
A **list in Python** is a **built-in data structure** that:
- Stores **multiple elements**
- Is **ordered** (keeps position)
- Is **mutable** (can be changed after creation)
```python
a = [1, 2, 3]
b = ["apple", 5, 2.5, True]
```
Lists can store **mixed data types** (unlike arrays in some languages)
## Properties of List
### 1. Ordered
- Elements have a **fixed position (index)**
```python
a = [10, 20, 30]
# 10 → index 0
```
### 2. Mutable 
You can modify list after creation
```python
a = [1,2,3]
a[0] = 100   # changed
```
### 3. Allows Duplicates
```python
a = [1,1,2,2]
```
### 4. Dynamic Size
- You can add/remove elements anytime
### 5. Mixed Data Types
```python
a = [1, "hello", 3.5, True]
```
## Creating Lists
### Method 1: Direct
```python
lst = [1, 2, 3]
```
### Method 2: Using list()
```python
lst = list((1,2,3))
```
### Method 3: From String
```python
lst = list("hello")
# ['h', 'e', 'l', 'l', 'o']
```
## Accessing Elements
### 1. Indexing
Access single element
```python
lst = [10, 20, 30]

lst[0]   # 10
lst[1]   # 20
```
### 2. Negative Indexing
```python
lst[-1]  # last
lst[-2]  # second last
```
### 3. Slicing
Extract multiple elements
```python
lst = [1,2,3,4,5]

lst[1:4]    # [2,3,4]
lst[:3]     # [1,2,3]
lst[::2]    # [1,3,5]
lst[::-1]   # reverse list
```
- **Indexing → O(1)** (fast)
- **Slicing → O(n)** (creates new list)
- Lists are internally **dynamic arrays**
## Python List Methods

| Function             | What it does          | Example                |
| -------------------- | --------------------- | ---------------------- |
| `append(x)`          | Add one element       | `l.append(3)`          |
| `extend(iterable)`   | Add multiple elements | `l.extend([3,4])`      |
| `insert(i, x)`       | Insert at index       | `l.insert(1,2)`        |
| `remove(x)`          | Remove value          | `l.remove(2)`          |
| `pop()`              | Remove last           | `l.pop()`              |
| `pop(i)`             | Remove index          | `l.pop(1)`             |
| `clear()`            | Remove all            | `l.clear()`            |
| `index(x)`           | Find index            | `l.index(2)`           |
| `count(x)`           | Count occurrence      | `l.count(1)`           |
| `sort()`             | Sort ascending        | `l.sort()`             |
| `sort(reverse=True)` | Sort descending       | `l.sort(reverse=True)` |
| `reverse()`          | Reverse list          | `l.reverse()`          |
| `copy()`             | Copy list             | `l.copy()`             |
# Important Differences
### append vs extend
```python
l=[1,2]

l.append([3,4])
# [1,2,[3,4]]

l.extend([3,4])
# [1,2,3,4]
```
### remove vs pop
- `remove(x)` → value based
- `pop()` → index based
### sort vs sorted
```python
l=[3,1,2]

l.sort()      # modifies original
sorted(l)     # returns new list
```
## # **List Iteration**
### Using Index
```python
for i in range(len(lst)):
    print(lst[i])
```
### Using `enumerate()` 
Gives **index + value**
```python
for i, v in enumerate(lst):
    print(i, v)
```
### Reverse Iteration
```python
for x in reversed(lst):
    print(x)
```
# **Nested Lists (2D Lists / Matrix)**
### What is Nested List?
A list inside another list
```python
matrix = [[1,2], [3,4]]
```
### Accessing Elements
```python
matrix[0]      # [1,2]
matrix[0][1]   # 2
```
## Iterating Nested List
### Method 1: Nested Loop
```python
for row in matrix:
    for val in row:
        print(val)
```
### Method 2: Using Index
```python
for i in range(len(matrix)):
    for j in range(len(matrix[i])):
        print(matrix[i][j])
```
