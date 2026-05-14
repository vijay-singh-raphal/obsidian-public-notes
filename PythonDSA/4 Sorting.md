Sorting is one of the most fundamental topics in Data Structures and Algorithms (DSA).  
It is usually taught immediately after topics like:
- Time Complexity
- Arrays
This is because sorting helps build algorithmic thinking and introduces many important problem-solving techniques.
# Why is Sorting Important?
## 1. Sorting Algorithms Teach Important Techniques
There are many sorting algorithms, such as:
- Bubble Sort
- Insertion Sort
- Merge Sort
- Quick Sort
- Counting Sort
Each algorithm teaches an important concept or algorithmic paradigm.
#### Examples
### Merge Sort
Teaches:
- **Divide and Conquer**
## 2. Many Algorithms Require Sorted Input
A large number of algorithms only work when data is sorted.
#### Example: Binary Search
Binary Search works only if:
- The array is already sorted
Without sorting, binary search cannot function correctly.
## 3. Sorting Helps Discover Patterns in Problems
Sometimes while solving problems:
- You may get completely stuck
- No idea comes to mind
- Existing algorithms do not help immediately
# Why Does This Help?
Sorting organizes data in a structured manner.
This helps in:
- Detecting duplicates
- Finding pairs/triplets
- Using two-pointer techniques
- Applying binary search
- Observing mathematical patterns
# What is Sorting?
Sorting means:
Arranging elements of an array in a particular order.
The order can be:
- **Ascending Order** → Smallest to Largest
- **Descending Order** → Largest to Smallest
#### Example of Sorting
### Unsorted Array
[5,1,4,3,2]
### After Sorting in Ascending Order
[1,2,3,4,5]
# Sorting Can Be Applied On
### 1. Numbers
Numbers can be compared directly.
Example:
- Integer arrays
- Floating-point arrays
### 2. Strings
Strings can be sorted:
- `Lexicographically` (dictionary order)
- By length
- By custom rules
### 3. Custom Objects
Custom objects can also be sorted.
Example:
##### Student Objects
Can be sorted based on:
- Marks
- Roll Number
- Name
- Attendance
# Bubble Sort 
Bubble Sort is one of the most basic and beginner-friendly sorting algorithms.
It works by:
### Comparing adjacent (consecutive) elements
and swapping them if they are in the wrong order.
![bubbleSort | 800](https://favtutor.com/resources/images/uploads/mceu_61632030011682402256084.png)
```python
array = [30,20,60,40,10,50]
n = len(array)
print(array,"before bubble sort")
for i in range(n):
	for j in range(n-i-1):
		if array[j] > array[j+1]:
			array[j],array[j+1] = array[j+1],array[j]
print(array,"after bubble sort")
```
# Selection Sort
Selection Sort is one of the:
- Simplest
- Most beginner-friendly  sorting algorithms.
It is even simpler than Bubble Sort in terms of understanding.
Repeatedly select the smallest element from the unsorted part and place it at the beginning.
![selectionSort|500](https://studyalgorithms.com/wp-content/uploads/2014/01/selection-sort.jpg)
```python
array = [30,20,60,40,10,50]
n = len(array)
print(array,"before selection sort")
for i in range(n):
	smallestEle = i
		for j in range(i+1,n):
			if array[j] < array[smallestEle]:
				smallestEle = j
		array[i],array[smallestEle] = array[smallestEle],array[i]
print(array,"after selection sort")
```
# Insertion sort
Insertion Sort divides the array into two parts:
- **Sorted Part**
- **Unsorted Part**
Initially:
- The **first element** is always considered sorted.
- Remaining elements are unsorted.
### Working Principle
Insertion Sort works by:
1. Picking an element from the unsorted part.
2. Placing it into its correct position in the sorted part.
3. Shifting larger elements one position to the right.
![insertionSort|600](https://raw.githubusercontent.com/Codecademy/docs/main/media/insert-sort.png)
```python
array = [30,20,60,40,10,50]
n = len(array)
print(array,"before insertion sort")
for i in range(1,n):
	j = i-1
	key = array[i]
	while (j>=0 and array[j]> key):
		array[j+1] = array[j]
		j = j-1
	array[j+1] = key
print(array,"after insertion sort")
```
# What is Merge Operation?
Merge operation is a technique used to combine **two sorted arrays** into **one sorted array**.
It is the most important concept used in **Merge Sort**.
### Input and Output
We are given:
- Array A → Sorted
- Array B → Sorted
We need to create:
- Array C → Also Sorted
```python
a = [2,5,7,9,11]
b = [3,4,8,10]
c = [2, 3, 4, 5, 7, 8, 9, 10, 11]
```

```python
a = [2,5,7,9,11]
b = [3,4,8,10]
n = len(a) + len(b)
c = [0]*n
i = 0
j = 0
k = 0
while(i<len(a) or j<len(b)):
	if i < len(a) and j < len(b):
		if a[i] <= b[j]:
			c[k] = a[i]
			i = i+1
		else:
			c[k] = b[j]
			j = j+1
	elif i < len(a):
		c[k] = a[i]
		i = i+1
	else:
		c[k] = b[j]
		j = j+1
	k = k + 1
print(c)
```
# What is Merge Sort?
Merge Sort is a:
Divide and Conquer Sorting Algorithm
It divides the array into smaller parts, sorts them, and merges them back.
## Core Idea of Merge Sort
Merge Sort works in 3 major steps:

|Step|Work|
|---|---|
|Divide|Split array into smaller parts|
|Conquer|Sort smaller parts recursively|
|Merge|Combine sorted parts|
![mergeSort|700](https://miro.medium.com/1*7Kox4Bll0Ddvb0td1tiXsg.png)
```python
a = [4,6,3,8,1,9,2,5,7]
def merge(start,mid,end):
	i = start
	j = mid + 1
	k = 0
	c = [0]*(end-start+1)
	while i<=mid or j<=end:
		if i<=mid and j<=end:
			if a[i] <= a[j]:
				c[k] = a[i]
				i = i+1
			else:
				c[k] = a[j]
				j = j+1
		elif (i<=mid):
			c[k] = a[i]
			i = i+1
		else:
			c[k] = a[j]
			j = j+1
		k = k+1
for i in range(len(c)):
	a[start + i] = c[i]

def mergeSort(start,end):
	if start < end:
		mid = (start + end) // 2
		mergeSort(start, mid)
		mergeSort(mid+1,end)
		merge(start,mid,end)

mergeSort(0,len(a)-1)
print(a)
```
# What is Partitioning?
Partitioning means:
Rearranging an array around a selected element called the **key** or **pivot**.
After partitioning:
- Elements **smaller than pivot** go to the left side
- Elements **equal to pivot** stay in the middle
- Elements **greater than pivot** go to the right side
## Partitioning ≠ Sorting
After partitioning:
```python
[2,1,0,3,5,4,6]
```
the array is still **unsorted**.
Notice:
- `2,1,0` are not sorted
- `5,4,6` are not sorted
Partitioning only guarantees:
```python
Left side  < Pivot < Right side
```
It does NOT guarantee full sorting.
## Pivot / Key
The selected element used for partitioning is called:
- **Key**
- **Pivot**
Both mean the same thing.
In this algorithm:
Pivot is assumed to be the LAST element of the array.
## Algorithm
We maintain one variable:
```python
left = -1
No elements smaller than pivot are found yet
```
The algorithm scans array from left → right.
Whenever an element smaller than pivot is found:
1. Increase `left`
2. Swap current element with `arr[left]`
This keeps all smaller elements grouped on the left side.
![[partation.png]]
```python
a = [1,5,2,6,0,4,3]
n = len(a)
key = a[n-1]
left = -1
for i in range(n-1):
	if(a[i] <= key):
		left = left + 1
		a[i],a[left] = a[left],a[i]
left = left + 1
a[n-1],a[left] = a[left],a[n-1]
print(a)
```
# What is `Quicksort`?
`Quicksort` is a **Divide and Conquer Sorting Algorithm** that uses the **Partition Function** to sort the array.
## Main Idea Behind `Quicksort`
The idea is very simple:
1. Choose a Pivot
2. Partition the array around the pivot
3. Pivot reaches its correct position
4. Recursively sort left part
5. Recursively sort right part
```python
a = [1,5,2,6,0,4,7,3]
def partation(start,end):
	left = start - 1
	pivot = a[end]
	for i in range(start,end):
		if a[i] <= pivot:
			left = left + 1
			a[left],a[i] = a[i],a[left]
	left = left + 1
	a[end],a[left] = a[left],a[end]
	return left

def quickSort(left,right):
	if left < right:
		partationPoint = partation(left,right)
		quickSort(left,partationPoint-1)
		quickSort(partationPoint+1,right)

quickSort(0,len(a)-1)
print(a)
```
#### Problem 1
Given an integer array `nums`, move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.
**Note** that you must do this in-place without making a copy of the array.
**Example 1:**
**Input:** `nums` = [0,1,0,3,12]
**Output:** [1,3,12,0,0]
```python
from typing import List
class Solution:
	def moveZeros(self,nums:List[int])->None:
		left = 0
		for i in range(len(nums)):
			if nums[i] != 0:
				nums[left],nums[i]=nums[i],nums[left]
				left = left + 1
s = Solution()
a = [0,1,0,3,12]
s.moveZeros(a)

print(a)
```
#### Problem 2
Given an array `nums` of size `n`, return _the majority element_.
The majority element is the element that appears more than `⌊n / 2⌋` times. You may assume that the majority element always exists in the array.
**Example 1:**
**Input:** nums = [3,2,3]
**Output:** 3

**Example 2:**
**Input:** `nums` = [2,2,1,1,1,2,2]
**Output:** 2
To achieve this we use:
**Moore’s Voting Algorithm**
Also called:
**Boyer–Moore Voting Algorithm**
![[moors.png|800]]
```python
from typing import List
class Solution:
	def majorityElement(self,nums:List[int])->int:
		moc = nums[0]
		co = 1
		for i in range(1,len(nums)):
			if nums[i] == moc:
				co = co + 1
			else:
				co = co - 1
				if co == 0:
					moc = nums[i]
					co = 1
return moc
s = Solution()
a = [1,2,3,2,2,4,2]
x = s.majorityElement(a)
print(x)
```
#### Problem 3
Given an array `nums` with `n` objects colored red, white, or blue, sort them **in-place** so that objects of the same color are adjacent, with the colors in the order red, white, and blue.
We will use the integers `0`, `1`, and `2` to represent the color red, white, and blue, respectively.
You must solve this problem without using the library's sort function.
**Example 1:**
**Input:** `nums` = [2,0,2,1,1,0]
**Output:** [0,0,1,1,2,2]
![[color.png|1000]]
