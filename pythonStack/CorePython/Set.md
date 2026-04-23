# What is a Set?
A **set** is a data structure that:
- Stores **unique elements only**
- Is **unordered**
- Is **mutable**
- Uses **hashing internally**
```python
s = {1, 2, 3}

s = {1,1,2,2,3}
# {1,2,3}
```
## Key Properties
### Unordered
```python
s = {1,2,3}
# Output order is not guaranteed
```
### Mutable
```python
s.add(4)
```
### Only Hashable Elements
Allowed:
```python
{1, "hello", (1,2)}
```
Not allowed:
```python
{[1,2]}   # list is not hashable
```
## Creating Sets
```python
s = {1,2,3}
s = set([1,2,3])
```
## Empty Set
```python
s = {}
s = set()
```
### Why sets are fast
Sets use hash tables internally.
So -> add, remove, search => O(1)
## Set Operations & Methods
## `add(x)`
Adds single element
```python
s.add(5)
```
## `update(iterable)`
Adds multiple elements
```python
s.update([6,7])
```
## `remove(x)`
Removes element (error if not found)
```python
s.remove(2)
```
## `discard(x)`
Removes element (NO error)
```python
s.discard(2)
```
## `pop()`
Removes random element
```python
s.pop()
```
## Mathematical Set Operations
```python
A = {1,2,3}
B = {3,4,5}
```
### Union (Combine)
```python
A | B
```
### Intersection (Common)
```python
A & B
```
### Difference
```python
A - B
```
### Symmetric Difference
```python
A ^ B
```
# ## What is `frozenset`?
Immutable version of set
```python
fs = frozenset([1,2,3])
```
### Why Needed?
- Can be used as:
    - dictionary key
    - set element
- `set` → mutable
- `frozenset` → immutable + hashable
# What is Hashing?
**Hashing** is a technique used to:
- Convert a value → into a **fixed integer (hash value)**
- Store and retrieve data **very fast**
```python
hash("hello")
```
Output → some integer (depends on system)
# Why Hashing is Important
Because it enables:
- **Fast lookup → O(1)** average
- Used in:
    - `set`
    - `dict`
## Hashable vs Non-Hashable
### Hashable Objects
Must be:
- **Immutable**
- Value does not change
Examples:
```python
1
"hello"
(1,2)
```
### Non-Hashable Objects
Mutable → cannot be hashed
Examples:
```python
[1,2]   # list
{1,2}   # set
{a:1}   # dict
```
# Why Mutable Objects are Not Hashable
Because:
- Their value can change
- Hash value would become invalid
### Hashing in Set
```python
s = {1,2,3}
```
Internally:
- Each element stored using **hash value**
- That’s why lookup is fast
### Hashing in Dictionary
```python
d = {"a": 1}
```
Key `"a"` is hashed → used to store value
### Performance Comparison
| Operation | List | Set/Dict |
| --------- | ---- | -------- |
| Search    | O(n) | O(1)     |
| Insert    | O(1) | O(1)     |
| Delete    | O(n) | O(1)     |