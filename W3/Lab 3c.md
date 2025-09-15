# Lists in Python
a. Using a range function, generate a list of 100 integers and assign the list to my_list. Verify that the variable my_list data type is list. Use your favorite four methods and apply on the list. You can find the methods on Python Docs
```python
my_list = list(range(100))
print(type(my_list))
my_list.append(100)
count_50 = my_list.count(50)
index_25 = my_list.index(25)
last_item = my_list.pop()

print("Count of 50:", count_50)
print("Index of 25:", index_25)
print("Last item popped:", last_item)
print("Length of my_list after pop:", len(my_list))
```
b. Suppose that you have a list of 10 items long. How might you move the last three items from the end of the list to the beginning, keeping them in the same order?
```python
my_list_10 = list(range(10))
my_list_10 = my_list_10[-3:] + my_list_10[:-3]
print(my_list_10)
```
c. What would be the result of len([[1,2]] * 3)? Try to do it without coding and then verify using Python.
Output for be 3.

d. Create a list my-list-ten of 10 items that includes some duplicate entries. Then, generate a second list my-list-ten-mem that contains the memory addresses of the items from the list my-list-ten. Use Python to research and identify the unique and duplicate memory addresses.
```python 
my_list_ten = [1, 2, 3, 2, 1, 4, 5, 4, 6, 1]
my_list_ten_mem = [id(item) for item in my_list_ten]

print("Memory addresses:", my_list_ten_mem)
unique_addrs = set()
duplicates = set()
for addr in my_list_ten_mem:
    if addr in unique_addrs:
        duplicates.add(addr)
    else:
        unique_addrs.add(addr)

print("Unique addresses:", unique_addrs)
print("Duplicate addresses:", duplicates)
```
e. Delete the list my-list-ten created in the above step.
```python
del my_list_ten
```
f. Create a new list my-new-list of the same 10 items used in my-list-ten. Generate memory addresses of the items in my-new-list and compare them with the memory addresses in my-list-ten-mem. Discuss what do you observe.
```python
my_new_list = [1, 2, 3, 2, 1, 4, 5, 4, 6, 1]
my_new_list_mem = [id(item) for item in my_new_list]

print("Old addresses:", my_list_ten_mem)
print("New addresses:", my_new_list_mem)
```
g. Suppose that you have the following list: x = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]. What code could you use to get a copy y of that list in which you could change the elements without the side effect of changing the contents of x?
```python
import copy

x = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
y = copy.deepcopy(x)
```
h. Is it possible to use multiple expressions within a list comprehension?
Yes, 
```python
[(x, y) for x in range(3) for y in range(2)]
```
i. Using a list comprehension, count how many spaces are in the following statement. "To be, or not to be, this is the question"
```python
statement = "To be, or not to be, this is the question"
space_count = sum([1 for char in statement if char == ' '])
print("Number of spaces:", space_count)
``` 
**Number of spaces: 9** 
j. Choose any 5 lists operations of your choice from the link https://docs.python.org/3/tutorial/datastructures.html
```python
lst = [1, 2, 3]
lst.append(4)
lst.extend([5, 6])
lst.insert(0, 0)
lst.remove(3)
lst.reverse()
print(lst)
```







