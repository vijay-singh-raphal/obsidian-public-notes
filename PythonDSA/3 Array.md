# What are Arrays?
An **array** is a **fundamental data structure** present in almost every programming language.  
Arrays store elements in a **continuous block of memory**.
### Key Idea
- Arrays are stored in **contiguous (continuous) memory locations**
- Elements are stored one after another
- Arrays are usually **homogeneous**
# Continuous Memory Allocation
Suppose we write in Java:
```java
int[] arr = new int[10];
```
If:
- `int = 4 bytes`
- array size = `10`
Then total memory required:
$$10×4=40 bytes$$
These 40 bytes are allocated **continuously in RAM**.
# Arrays are Homogeneous
All elements inside an array must be of the **same data type**.
Example:
```java
int[] arr = new int[5];
// allowed 1, 2, 3, 4
// not allowed 1, "hello", 5.6
```
# Why Arrays are Fast?
Arrays are fast because memory is continuous.
This allows direct calculation of any element’s address.
$$Address=Base Address+(Index×Size of Data Type)$$
# Drawbacks of Arrays
Arrays are very fast because they use **continuous memory allocation**.  
But this same property also creates several limitations.
## 1. Static Size (Fixed Size)
Traditional arrays have a **fixed size**.
Once the array is created:
- size cannot be changed easily
- memory is already reserved
```java
int[] arr = new int[10];
```
- array size = 10
- fixed at creation time
Suppose:
- you created array of size 10
- later you need 100 elements
Problem:
- array cannot grow automatically
- new larger array must be created
### Solution
Modern languages solve this using:
- Dynamic Arrays
- ArrayList
- Vector
- Python List
These structures internally resize themselves automatically.
## 2. Insertion in Beginning or Middle is Inefficient
This is one of the biggest drawbacks.
Suppose array contains:
```java
10 20 30 40 50 60 70 80
```
Now insert `35` between `30` and `40`.
### What Happens Internally?
To create space:
- 40 shifts right
- 50 shifts right
- 60 shifts right
- 70 shifts right
Then 35 is inserted.
New array:
```java
10 20 30 35 40 50 60 70 80
```
### Why is This Slow?
Because many elements must move.
If insertion happens at beginning:
- almost all elements shift
This requires iteration through array.
$$O(n)$$
## 3. Deletion is Also Inefficient
Suppose we delete `20`.
Before deletion:
```java
10 20 30 40 50 60 70 80
```
After deleting `20`:
- all elements shift left
- ```java
  10 30 40 50 60 70 80
  ```
### Why Deletion is Slow?
Because:
- elements must move to fill gap
- requires traversal and shifting
$$O(n)$$
### Why Do These Problems Exist?
Because arrays are:
- Continuous in memory
- Fixed in structure
This continuity gives:
- fast access
But causes:
- difficult insertion/deletion
# Abstract Data Type of array
- Access -> S, T = O(1)
- Set -> S, T = O(1)
- Traverse / Search -> T = O(n) , S = (1)
- Copy -> S,T = O(n)
- Insert
	- First -> T = O(n),  S = O(1)
	- End -> T = O(1),  S = O(1)
	- Between -> T = O(n),  S = O(1)
- Remove
	- First -> T = O(n),  S = O(1)
	- End -> T = O(n),  S = O(1)
	- Between -> T = O(n),  S = O(1)
# Resizable Arrays (Dynamic Arrays / ArrayList / Vector) 
Traditional arrays have a major drawback:
- their size is fixed (static)
To solve this problem, modern languages provide:
- Dynamic Arrays
- ArrayList
- Vector
- Python List
These are called **Resizable Arrays**.
```java
ArrayList<Integer> arr = new ArrayList<>();
```
Internally:
- a small array is created
Suppose initial capacity = 2

|Index|Value|
|---|---|
|0|empty|
|1|empty|
```java
size = 0
capacity = 2
```
## Amortized Time Complexity
Since resizing does NOT happen every time:
Average complexity becomes:
$$O(1)$$
This is called: Amortized O(1)
## What is Amortized Complexity?
Amortized complexity means:
- some operations are expensive
- most operations are cheap
Average cost over many operations becomes small.
## Drawbacks of Resizable Arrays
### 1. Resizing Cost
Copying elements can be expensive.
### 2. Extra Memory Usage
Unused capacity may exist.
# Creating a List in Python
```python
brands = ["Tesla", "Skoda", "Toyota", "Suzuki"]
```

|Operation|Time Complexity|
|---|---|
|Access|O(1)|
|Append|O(1) amortized|
|Pop End|O(1)|
|Insert Middle|O(n)|
|Remove Middle|O(n)|
|Sort|O(n log n)|
|Reverse|O(n)|
# Array problems
#### Problem 1
Given a binary array `nums`, return _the maximum number of consecutive_ `1`_'s in the array_.
**Input:** `nums` = [1,1,0,1,1,1]
**Output:** 3
**Explanation:** The first two digits or the last three digits are consecutive `1s`. The maximum number of consecutive `1s` is 3.
```python
from typing import List
class Solution:
	def findMaxConsutiveOnes(self,nums:List[int])->int:
		ans = 0
		count = 0
		n = len(nums)
		for i in range(n):
			if nums[i] == 1:
				count = count+1
			if ans < count:
				ans = count
			if nums[i] == 0:
				count = 0
		return ans

s = Solution()
x = s.findMaxConsutiveOnes([1,1,0,1,1,1,0,0,1,1,1,1,0,0,1])
print(x)
```
#### Problem 1
Given an integer array `nums` sorted in **non-decreasing order**, return a new array containing the **squares of each element**, also sorted in **non-decreasing (ascending) order**.
##### **Constraints**
- $0≤len(nums)≤10^5$
- $−10^4≤nums[i]≤10^4$
##### **Notes**
- The input array may contain **negative numbers, zeros, and positive numbers**.
- The input array is **not guaranteed to be sorted**.
- The output must always be **sorted after squaring**.
- If the input array is empty, return an empty array.
##### **Examples**
Input: nums = [1, 3, 5]
Output: [1, 9, 25]
Input: nums = [6, 0, 5]
Output: [0, 25, 36]
Input: nums = [-4, -2, 0, 1, 3]
Output: [0, 1, 4, 9, 16]
Input: nums = [3, 2, 3]
Output: [4, 9, 9]
Input: nums = []
Output: []
**Can you solve this problem in O(n) time instead of O(nlog⁡n)?**
###### Method 1 Brute force
```python
def sorted_square(array):
	n = len(array)
	res = []*n
	for i in range(n):
		res[i] = array[i]**2
	res.sort()
	return res
```
###### Method 2 Two-Pointer Approach
- The input array is **sorted in non-decreasing order**.
- When we take squares:
    - Negative numbers become positive.
    - The **largest square values come from elements with largest absolute values** (either leftmost negative or rightmost positive).
- Therefore, the largest square will be at **either end of the array**.
<-----------------------------------------------------0-----------------------------------------------------> 
- value of square while we reach to left or right most end.
- [-3,1,2,7] -> sorted array
- [0,0,0,0] -> initialize an empty output array.
- -3 = 9 , 7 = 49 compare both values put the largest value and decrement and continue.
```python
def sorted_square(array):
	n = len(array)
	i,j = 0, n-1
	res = [0]*n
	for k in reversed(range(n)):
		if array[i]**2 > array[j]**2:
			res[k] = array[i]**2
			i += 1
		else:
			res[k] = array[j]**2
			j -= 1
	return res	
```
#### Problem 2
## **Check if an Array is Monotonic**
An array is said to be **monotonic** if it is either:
- **Monotone Increasing**: All elements from left to right are **non-decreasing**  
    (i.e., `arr[i] ≤ arr[i+1]` for all valid `i`)
**OR**
- **Monotone Decreasing**: All elements from left to right are **non-increasing**  
    (i.e., `arr[i] ≥ arr[i+1]` for all valid `i`)
##### **Task**
Given an integer array, return:
- `true` if the array is **monotonic**
- `false` otherwise
##### **Notes**
- An empty array is considered **monotonic**
- An array with only one element is also **monotonic**
- Elements in the array may be **equal (duplicates allowed)**
##### Monotonic
[1, 2, 3] → true
[1, 2, 3, 3] → true
[1, 2, 2] → true
[3, 2, 1] → true
[3, 2, 1, 1] → true
[3, 3, 3] → true
##### Non Monotonic
[2, 2, 3, 1] → false
##### Edge Cases
[7] → true
[] → true
##### **Constraints Insight**
- Time Complexity: `O(n)`
- Space Complexity: `O(1)`
```python
def monotonic_array(arr):
    n = len(arr)
    if n <= 1:
        return True  
    increasing = True
    decreasing = True
    for i in range(n - 1):
        if arr[i] > arr[i + 1]:
            increasing = False
        if arr[i] < arr[i + 1]:
            decreasing = False
    return increasing or decreasing
```
