# Drawbacks of Arrays & Introduction to Linked Lists – Detailed Notes
## 1. Introduction to Arrays
An array is a linear data structure that stores elements in **contiguous memory locations**.
This means:
- All elements are stored one after another in memory.
- Every element has a fixed index.
- Accessing elements is very fast.
Example:

| Index | Value |
| ----- | ----- |
| 0     | 10    |
| 1     | 20    |
| 2     | 30    |
| 3     | 40    |
| 4     | 50    |
| 5     | 60    |
# Contiguous Memory Allocation
Arrays occupy continuous memory locations.
Suppose:
- Array size = 6
- Starting address = 100
- Integer size = 4 bytes
Then memory allocation becomes:

|Index|Value|Memory Address|
|---|---|---|
|0|10|100|
|1|20|104|
|2|30|108|
|3|40|112|
|4|50|116|
|5|60|120|
Since each integer takes 4 bytes:
$$Address of element=Base Address+(Index×Size)$$
Example:
$$100 + (3 \times 4) = 112$$
So index 3 is stored at address 112.
# Advantage of Contiguous Nature
Because memory is continuous:
- CPU can directly calculate addresses.
- Random access becomes very fast.
Time Complexity:

| Operation       | Complexity |
| --------------- | ---------- |
| Access by index | O(1)       |
Example:
- Accessing array[4] is direct.
- No traversal required.
This is the biggest advantage of arrays.
# Major Drawback of Arrays
Although arrays provide fast access, they have a major limitation:
## Arrays have fixed size and contiguous storage.
Because of this:
- Insertion in middle is difficult.
- Deletion in middle is difficult.
- Elements need shifting.
# Why Arrays Become Inefficient
The main reason:
## Contiguous memory allocation
Since memory must remain continuous:
- Existing elements cannot move automatically.
- Manual shifting is required.
This causes:
- Extra time
- Extra operations
- Lower efficiency
# When Arrays Are Preferred
Arrays are best when:
- Fast access is needed.
- Mostly read operations occur.
- Insertions/deletions are rare.
- Data size is fixed.
Examples:
- Mathematical computations
- Static datasets
- Lookup tables
# When Arrays Are NOT Preferred
Arrays are not preferred when:
- Frequent insertions occur.
- Frequent deletions occur.
- Dynamic memory is needed.
Especially:
- Insertions at beginning
- Insertions in middle
- Deletions at beginning
- Deletions in middle
# Solution to Array Drawbacks
To solve these problems, we use:
### Linked List
- Does not require contiguous memory.
- Allows easy insertion and deletion.
- No shifting required.
Instead of shifting:
- We simply change links/pointers.

| Feature          | Array      | Linked List              |
| ---------------- | ---------- | ------------------------ |
| Memory           | Contiguous | Non-contiguous           |
| Access           | Fast O(1)  | Slow O(n)                |
| Insert in middle | O(n)       | O(1) after reaching node |
| Delete in middle | O(n)       | O(1) after reaching node |
| Size             | Fixed      | Dynamic                  |
# Basic implementation of LinkedList
```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None

a = Node("AAA")
b = Node("BBB")
c = Node("CCC")
d = Node("DDD")
e = Node("EEE")

head = a
a.next = b
b.next = c
c.next = d
d.next = e

curr = head
while(curr is not None):
	print(curr.data)
	curr = curr.next
```
# Insert Node at first
```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None

head = None
def insertAtFirst(data):
	global head
	newNode = Node(data)
	if head is None:
		head = newNode
	else:
		newNode.next = head
		head = newNode

def traverse():
	curr = head
	while(curr is not None):
		print(curr.data)
		curr = curr.next

insertAtFirst("AAAA")
insertAtFirst("BBBB")
insertAtFirst("CCCC")
insertAtFirst("DDDD")
insertAtFirst("EEEE") 

traverse()
```
# Insert Node at end
```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None

head = None
tail = None
def insertAtEnd(data):
	global head
	global tail
	newNode = Node(data)
	if head is None:
		head = newNode
		tail = newNode
	else:
		tail.next = newNode
		tail = newNode
  
def traverse():
	curr = head
	while(curr is not None):
		print(curr.data)
		curr = curr.next

insertAtEnd("AAAA")
insertAtEnd("BBBB")
insertAtEnd("CCCC")
insertAtEnd("DDDD")
insertAtEnd("EEEE")

traverse()
```
# Insert Node at middle
```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None

head = None
tail = None
length = 0

def insertAtEnd(data):
	global head
	global tail
	global length
	newNode = Node(data)
		if head is None:
			head = newNode
			tail = newNode
			length += 1
		else:
			tail.next = newNode
			tail = newNode
			length +=1

def insertAtMiddle(pos,data):
	if pos < 1 or pos > length:
		return
	global length
	newNode = Node(data)
	i = 1
	curr = head
	while(i < pos-1):
		curr = curr.next
		i += 1
		newNode.next = curr.next
		curr.next = newNode
		length += 1

def traverse():
	curr = head
	while(curr is not None):
		print(curr.data)
		curr = curr.next

insertAtEnd("AAAA")
insertAtEnd("BBBB")
insertAtEnd("CCCC")
insertAtEnd("DDDD")
insertAtEnd("EEEE")

insertAtMiddle(2,200)
insertAtMiddle(4,400)

traverse()
```
# Delete from first
```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None

head = None
tail = None
length = 0

def insertAtEnd(data):
	global head
	global tail
	global length
	newNode = Node(data)
	if head is None:
		head = newNode
		tail = newNode
		length += 1
	else:
		tail.next = newNode
		tail = newNode
		length +=1

def deleteFromFirst():
	global head
	global tail
	global length
	if head is None:
		print("No item found")
		return

	head = head.next
	
	if head is None:
		tail = None
	
	length -= 1
	print(f"first item is deleted successfully")

def traverse():
	curr = head
	while(curr is not None):
		print(curr.data)
		curr = curr.next
  
insertAtEnd("AAAA")
insertAtEnd("BBBB")
insertAtEnd("CCCC")
insertAtEnd("DDDD")
insertAtEnd("EEEE")

traverse()

deleteFromFirst()
deleteFromFirst()

traverse()
```
# Delete from last
```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None

head = None
tail = None
length = 0

def insertAtEnd(data):
	global head
	global tail
	global length

	newNode = Node(data)

	if head is None:
		head = newNode
		tail = newNode
		length += 1
	else:
		tail.next = newNode
		tail = newNode
		length +=1

def deleteFromLast():
	global head
	global tail
	global length

	if head is None:
		print("No item available")
		return

	if head == tail:
		head = None
		tail = None
		length -= 1
		print("Last item deleted successfully")
		return

	curr = head
	while (curr.next != tail):
		curr = curr.next
		curr.next = None
		tail = curr

	length -= 1
	print("Last item is deleted successfully")

def traverse():
	curr = head
	while(curr is not None):
		print(curr.data)
		curr = curr.next

insertAtEnd("AAAA")
insertAtEnd("BBBB")
insertAtEnd("CCCC")
insertAtEnd("DDDD")
insertAtEnd("EEEE")

traverse()

deleteFromLast()
deleteFromLast()

traverse()
```
# Delete from middle
```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None
  
head = None
tail = None
length = 0

def insertAtEnd(data):
	global head
	global tail
	global length

	newNode = Node(data)

	if head is None:
		head = newNode
		tail = newNode
		length += 1
	else:
		tail.next = newNode
		tail = newNode
		length +=1

def deleteFromMiddle(pos):
	global head
	global tail
	global length
  
	if head is None:
		print("No item available")
		return
	
	if pos <= 1 or pos >= length:
		print("invalid position")
		return
	
	curr = head
	temp = None
	i = 1

	while (i < pos):
		temp = curr
		curr = curr.next
		i += 1
	temp.next = curr.next
	curr = None

	length -= 1
	print("middle element deleted successfully")

def traverse():
	curr = head
	while(curr is not None):
		print(curr.data)
		curr = curr.next

insertAtEnd("AAAA")
insertAtEnd("BBBB")
insertAtEnd("CCCC")
insertAtEnd("DDDD")
insertAtEnd("EEEE")
  
traverse() 

deleteFromMiddle(2)
deleteFromMiddle(3)

traverse()
```
#### Problem 1
Given the heads of two singly linked-lists `headA` and `headB`, return _the node at which the two lists intersect_. If the two linked lists have no intersection at all, return `null`.
For example, the following two linked lists begin to intersect at node `c1`:
![list](https://assets.leetcode.com/uploads/2021/03/05/160_statement.png)
```python
class Solution:

	def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> Optional[ListNode]:
		n = self.length(headA)
		m = self.length(headB)
		first = headA
		second = headB

		if m <= n:
			for i in range(n-m):
				first = first.next
		else:
			for i in range(m-n):
				second = second.next

		while first is not None:
			if(first == second):
				return first
			first = first.next
			second = second.next
		return None
  
	def length(self,head):
		x = 0
		curr = head
		while(curr is not None):
			curr = curr.next
				x += 1
		return x
```
#### Problem 2
Given the `head` of a singly linked list, reverse the list, and return _the reversed list_.
**Example 1:**
![reverse](https://assets.leetcode.com/uploads/2021/02/19/rev1ex1.jpg)
```python
class Solution:
def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
	pre = None
	curr = head
	while(curr is not None):
		nextNode = curr.next
		curr.next = pre
		pre = curr
		curr = nextNode
	return pre
```
#### Problem 3
You are given the heads of two sorted linked lists `list1` and `list2`.
Merge the two lists into one **sorted** list. The list should be made by splicing together the nodes of the first two lists.
Return _the head of the merged linked list_.
![merge](https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg)
```python
class Solution:
	def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
		p1 = list1
		p2 = list2
		head = None
		tail = None

		while(p1 is not None or p2 is not None):
			data = None
			if (p1 is not None and p2 is not None):
				if(p1.val <= p2.val):
					data = p1.val
					p1 = p1.next
				else:
					data = p2.val
					p2 = p2.next
			elif(p1 is not None):
				data = p1.val
				p1 = p1.next
			else:
				data = p2.val
				p2 = p2.next

			if tail is None:
				head = self.insertAtLast(tail, data)
				tail = head
			else:
				tail = self.insertAtLast(tail, data)
		return head

def insertAtLast(self,tail,data):
newNode = ListNode(data)
if tail is not None:
tail.next = newNode
return newNode
```
#### Problem 4
Given `head`, the head of a linked list, determine if the linked list has a cycle in it.
There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the `next` pointer. Internally, `pos` is used to denote the index of the node that tail's `next` pointer is connected to. **Note that `pos` is not passed as a parameter**.
Return `true` _if there is a cycle in the linked list_. Otherwise, return `false`.
![cycle](https://assets.leetcode.com/uploads/2018/12/07/circularlinkedlist.png)
```python
class Solution:
	def hasCycle(self, head: Optional[ListNode]) -> bool:
		if head is None or head.next is None:
			return False
		first = head
		second = head.next.next

		while first is not None and second is not None and second.next is not None:
			if first == second:
				return True
			first = first.next
			second = second.next.next
		return False
```
