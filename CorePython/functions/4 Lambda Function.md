A lambda function is a **small anonymous function** (no name, defined in one line).
```python
lambda arguments: expression
```
#### Example
```python
square = lambda x: x * x
print(square(5))
```
## Rules
- Only **one expression** allowed
- No statements (`if`, `for`, etc. in normal form)
- Automatically returns value
## Multiple Arguments
```python
add = lambda a, b: a + b
print(add(2, 3))
```
# **Where Lambda is Used 
Lambda is mostly used with:
- `map()`
- `filter()`
- `sorted()`
#### Example: `map()`
```python
nums = [1, 2, 3]
result = list(map(lambda x: x * 2, nums))
```
#### Example: `filter()`
```python
nums = [1, 2, 3, 4]
result = list(filter(lambda x: x % 2 == 0, nums))
```
#### Example: `sorted()`
```python
nums = [5, 2, 9, 1]
result = sorted(nums, key=lambda x: x)
print(result)
```
**Sort by absolute value**
```python
nums = [-10, 5, -2, 3]
result = sorted(nums, key=lambda x: abs(x))
print(result)
```
**Sort list of tuples**
```python
data = [(1, 3), (2, 1), (4, 2)]
result = sorted(data, key=lambda x: x[1])
print(result)
```
**Sort dictionaries**
```python
students = [
    {"name": "A", "marks": 85},
    {"name": "B", "marks": 92},
    {"name": "C", "marks": 78}
]
result = sorted(students, key=lambda x: x["marks"])
print(result)
```
**Reverse sorting**
```python
nums = [1, 4, 2, 8]
result = sorted(nums, key=lambda x: x, reverse=True)
print(result)
```
# When NOT to use Lambda
Don’t use lambda when:
- Logic is complex
- Multiple steps required
