A function is:
- A **block of reusable code**
- Takes **input (arguments)**
- Performs **computation**
- Returns **output**
### **Why Functions are Important**
- **Code reuse** → write once, use many times
- **Modularity** → break big systems into small parts
- **Abstraction** → hide complexity
- **Maintainability** → easier to update code
- **Testing** → easier to test small units
#### Example
```python
def greet(name):
    return "Hello " + name
```
### What happens internally:
- `def greet(name)` → creates a **function object**
- Stored in **memory (heap)**
- Name `greet` → **reference to that object**
### **Functions are first-class objects in Python**
This means:
- Stored in variables
- Passed as arguments
- Returned from other functions
#### Example
```python
def greet():
    return "Hi"

x = greet   # storing function
print(x())  # calling via variable
```
### **Types of Functions (from your notes)**
#### Built-in Functions
- Already provided by Python
```python
print()
len()
type()
```
#### User-defined Functions
- Created using `def`
```python
def add(a, b):
    return a + b
```
#### Anonymous Functions (Lambda)
```python
square = lambda x: x * x
```
**NOTE** When you write a function, Python does NOT run it immediately.
Instead:
1. It creates a **function object**
2. Stores it in memory
3. Runs it only when called
# Parameter Passing Model
Python uses:
**Call by Object Reference** (also called _call by sharing_)
## What does that actually mean?
- When you pass a variable to a function:
    - Python passes the **reference (address)** of the object
    - NOT a copy (like C pass-by-value)
    - NOT full control (like pass-by-reference in C++)
#### Key Rule
- You **can modify mutable objects**  
- You **cannot rebind immutable objects**
## Immutable (int)
```python
def change(x):
    x = x + 10

a = 5
change(a)
print(a)   # ?
```
- `a` → points to `5`
- `x` → gets same reference initially
- `x = x + 10` → creates NEW object `15`
- `x` now points to new object
- `a` still points to `5`
## Mutable (list)
```python
def change(lst):
    lst.append(4)

nums = [1, 2, 3]
change(nums)
print(nums)
```
- `nums` and `lst` → both point to SAME list
- `.append()` modifies object **in-place**
“You cannot rebind caller variable, but you can mutate mutable objects.”
