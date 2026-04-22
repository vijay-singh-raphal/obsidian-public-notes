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
# Array problems
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
def monotonic_array(array):
	n = len(array)
	if n == 0 :
		return
	first = array[0]
	last = array[n-1]
	
	if first > last:
		for k in range(n-1):
			if array[k] < array[k+1]:
				return false
```