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
d.get("age") # 25  
d.get("salary") # None  
d.get("salary", 0) # 0
```
### Checking Key
```python
"name" in d
```
# Updating Dictionary

### Add / Modify Value
```python
d["age"] = 30
```
### Using `update()`
```python
d.update({"city": "Delhi"})
# Add multiple values
```
# Removing Elements
### pop(key)
```python
d.pop("age")
# Removes key and returns value
```
### popitem()
```python
d.popitem()
# Removes last inserted item
```
### clear()
```python
d.clear()
# Removes everything
```
# Looping Through Dictionary 
### Loop Through Keys
```python
for k in d:
    print(k)
```
### Loop Through Values
```python
for v in d.values():
    print(v)
```
### Loop Through Key-Value Pairs
```python
for k, v in d.items():
    print(k, v)
```
#### Write a program to count the frequency of elements in list.
```python
d = {}

for x in lst:
    d[x] = d.get(x, 0) + 1
```
# Nested Dictionary 
### What is it?
Dictionary inside another dictionary
```python
user = {
    "name": "Rahul",
    "address": {
        "city": "Delhi",
        "pincode": 110001
    }
}
```
### Accessing Nested Values
```python
user["address"]["city"]
```
# Merging Dictionaries ⭐
### Method 1: Using `|` (Python 3.9+)
```python
d3 = d1 | d2
```
### Method 2: Using `update()`
```python
d1.update(d2)
# Modifies original dictionary

d1 = {"a":1}
d2 = {"a":2}

d1.update(d2)
# overwrite the key
```

