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
![selectionSort|500](https://studyalgorithms.com/wp-content/uploads/2014/01/selection-sort.jpg)
```python
array = [30,20,60,40,10,50]
n = len(array)
print(array,"before bubble sort")
	for i in range(n):
		smallestEle = i
		for j in range(i+1,n):
			if array[j] < array[smallestEle]:
				smallestEle = j
		array[i],array[smallestEle] = array[smallestEle],array[i]
print(array,"after bubble sort")
```
