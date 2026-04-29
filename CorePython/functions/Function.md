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
#### Question
```python
def tricky(x):
    x = x + [4]

lst = [1,2,3]
tricky(lst)
print(lst)
```
- `x + [4]` → creates NEW list
- Doesn't modify original
## Parameter vs Argument

|Term|Meaning|
|---|---|
|Parameter|Variable in function definition|
|Argument|Actual value passed|
```python
def add(a, b):   # a, b → parameters
    return a + b

add(2, 3)        # 2, 3 → arguments
```
# Types of Arguments
## Positional Arguments
Order **matters**
```python
def sub(a, b):
    return a - b

sub(5, 2)   # a=5, b=2
```
## Keyword Arguments
Order **does NOT matter**
```python
def sub(a, b):
    return a - b

sub(b=2, a=5)
```
Python matches by **name**, not position
## Default Arguments
Provide default values
```python
def greet(name="Guest"):
    return "Hello " + name

greet()        # Hello Guest
greet("Ram")   # Hello Ram
```
# **Mutable Default Arguments**
## Problem Code
```python
def add_item(item, my_list=[]):
    my_list.append(item)
    return my_list

print(add_item(1))
print(add_item(2))
print(add_item(3))
```
**NOTE** This looks wrong if you expect a fresh list each time.
### REASON
Default arguments are created **ONLY ONCE** when the function is **defined**, not when called.
So:
- `my_list=[]` is created once
- Same list reused every call
## Correct Code
```python
def add_item(item, my_list=None):
    if my_list is None:
        my_list = []
    my_list.append(item)
    return my_list

print(add_item(1))
print(add_item(2))
print(add_item(3))
```
# **Return Statement**
### From your notes:
A function can return:
- One value
- Multiple values (as tuple)
- Nothing (`None` by default)
#### Single Return
```python
def square(x):
    return x * x
```
#### Multiple Return
```python
def coordinates():
    return 10, 20
```
#### No Return
```python
def test():
    pass

# None
```
# **Function Execution Flow**
### When you call a function:
### Steps:
1. **Python looks for function name** (in global scope)
2. **Finds function object in heap**
3. **Creates a new stack frame**
4. Executes function code
5. Returns result
6. **Removes stack frame**
Heap → stores objects (functions, lists, etc.)  
Stack → handles execution (function calls)
```python
def add(a, b):
    c = a + b
    return c

add(2, 3)
```
- `add` → stored in heap
- Call `add(2,3)` → new stack frame created
- `a=2`, `b=3` inside frame
- `c=5`
- return `5`
- frame destroyed
## **Python Memory Model (Global Namespace, Stack, Heap)**
# **Three Core Areas**
Python manages memory in **three main parts**:
### Global Namespace
- Stores:
    - Global variables
    - Function names
- Exists for the **entire program lifecycle**
### Stack (Call Stack)
- Stores:
    - Function calls
    - Local variables
- Works like:
	- Last In → First Out (LIFO)
### Heap
- Stores:
    - Objects (lists, dicts, functions, etc.)
#### Example
```python
def add(a, b):
    c = a + b
    return c

x = 10
y = 20
result = add(x, y)
```
### Step 1: Global Namespace
- `add` → function reference
- `x = 10`, `y = 20`
- `result` (not yet assigned)
### Step 2: Heap
- Objects created:
    - `10`, `20`
    - Function object `add`
### Step 3: Stack (Function Call)
When `add(x, y)` is called:
- New **stack frame** created
- Inside frame:
    - `a = 10`
    - `b = 20`
    - `c = 30`
### Step 4: Return
- `30` returned
- Stack frame **deleted**
- `result = 30` stored in global namespace
