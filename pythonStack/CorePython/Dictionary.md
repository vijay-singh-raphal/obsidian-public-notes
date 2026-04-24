# What is a Dictionary?
A **dictionary (`dict`)** is a data structure that stores:
**Key → Value pairs**
```python
d = {"name": "Rahul", "age": 25}
```
# Key Features
### 1. Key-Value Structure
- Each key maps to a value
```python
"name" → "Rahul"
```
### 2. Keys Must Be Hashable
Allowed:
```python
{"a": 1}
{1: "hello"}
{(1,2): "point"}
```
Not allowed:
```python
{[1,2]: "value"}   # list not allowed
```
### 3. Mutable
```python
d["age"] = 30
```
### 4. Ordered (Python 3.7+)
Maintains insertion order
# Creating Dictionary
### Method 1
```python
d = {"a": 1, "b": 2}
```
### Method 2
```python
d = dict(a=1, b=2)
```
### Method 3
```python
d = dict([("a",1), ("b",2)])
```
# Accessing Values
### Using Key
```python
d["name"]
# Error if key not present
```
### Using `get()`
```python
d.get("name")
d.get("salary", 0)
# No error (safe access)
```
### Checking Key
```python
"name" in d
```


