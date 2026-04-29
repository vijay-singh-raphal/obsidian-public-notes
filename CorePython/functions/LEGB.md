# **What is LEGB Rule?**
It defines **variable lookup order**:
L → E → G → B

|Level|Meaning|
|---|---|
|L|Local|
|E|Enclosing|
|G|Global|
|B|Built-in|
When you use a variable:
```python
print(x)
```
Python searches in this order:
1. **Local** (inside current function)
2. **Enclosing** (outer function)
3. **Global** (file level)
4. **Built-in** (Python predefined)
## **Local Scope**
```python
def greet():
    message = "Hello"
    print(message)

greet()
```
`message` is **local to greet()**
## Enclosing Scope
```python
def outer():
    msg = "Hi"

    def inner():
        print(msg)
    inner()
outer()
```
`msg` is not in `inner()`  
Python checks **enclosing (outer)** → finds it
## Global Scope
```python
name = "Python"

def show():
    print(name)
show()
```
`name` found in global
## Built-in Scope
```python
print("Hello")
```
`print` is from built-in scope
#### Example
```python
x = 10

def func():
    x = 5
    print(x)

func()
print(x)
```
# Global Keyword
```python
count = 0

def increase():
    global count
    count += 1
```
Without `global` → error  
Because Python assumes it's local
```python
def show():
    print(name)

name = "Python"
show()
```
