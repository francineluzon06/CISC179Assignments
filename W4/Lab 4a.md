# Tuples in Python

## 1. Exercising tuples
1a) Take five inputs from an user and save it in a tuple called my_tuple
```python
my_tuple = tuple(input(f"Enter value {i+1}: ") for i in range(5))

print("The tuple is:", my_tuple)
```
1b) How do you assign a single element in a tuple?
```python
my_tuple = (10, 20, 30)

# Convert to list
temp_list = list(my_tuple)

# Modify the element
temp_list[1] = 99

# Convert back to tuple
my_tuple = tuple(temp_list)

print(my_tuple)  # Output: (10, 99, 30)
```
1c) my_tuple = (1,2,3,4,3,2,1,2,3,5,4,3,2,1) Count the repeated integers and print the result on the console.
```python
from collections import Counter

my_tuple = (1, 2, 3, 4, 3, 2, 1, 2, 3, 5, 4, 3, 2, 1)

# Count occurrences
counts = Counter(my_tuple)

# Print results
for num, freq in counts.items():
    print(f"{num} appears {freq} times")
```
1d) my_tuple = my_tuple + my_tuple
```python

# Part c
my_tuple_c = (1,2,3,4,3,2,1,2,3,5,4,3,2,1)
print("Part c tuple:", my_tuple_c)
print("ID of my_tuple_c:", id(my_tuple_c))  # memory address

# Part d
my_tuple_d = my_tuple_c + my_tuple_c
print("\nPart d tuple:", my_tuple_d)
print("ID of my_tuple_d:", id(my_tuple_d))  # different memory address

# Proof they are different
print("\nAre they the same object?", my_tuple_c is my_tuple_d)
```
1e) Explain why the following operations aren’t legal for the tuple. Answer without using the Python.

x = (1,2,3,4) This legal! Some may think is illegal due to python using brackets [], however, in tuples is it legal to use parathensis ().
x.append(1) This is illegal because .append() is meant to be a list, not a tuple. Lists are mutable, while tuples are immutable. 
x[1] = "hello" This is illegal due to x[1] being replaced with "hello" violates the whole idea of being immutable.
del x[2] This is illegal because del removes an element at a given index, meaning individual elements cannot be deleted inside.

## 2. Packing and unpacking tuples

2a) What is the data type of each variable?
The data type of each variable is integer (int) type. 

2b) Python has an extended unpacking feature, allowing an element marked with * to absorb any number of elements not matching the other elements.

2c) What will be the result of a, *b, c = x?
```python
x = (1, 2, 3, 4, 5, 6)

a, *b, c = x

print("a =", a)
print("b =", b)
print("c =", c)
```
## 3. Memory management
Discuss how memory addresses are assigned to each index of the list and the tuple. Pay attention to new addresses & re-used addresses.
In Python, lists and tuples don’t hold the values directly. Instead, they store references to objects in memory. If the same value already exists, Python will often reuse the same memory address instead of creating a duplicate. For example, in the numbers 200, 300, and 400 point to the same memory locations in both my_x and my_y. However, 100 (only in the list) and 500 (only in the tuple) each get their own new addresses. This shows how Python optimizes memory by sharing objects when possible. 
