# Dictionary in Python

## 1. Creating and accessing dictionary
1a) Create dictionary of your choice of keys and values. Create dictionary size of 10 elements.
```python
student_info = {
    "id": 123,
    "first_name": "John",
    "last_name": "Doe",
    "age": 20,
    "major": "Computer Science",
    "gpa": 3.8,
    "email": "john.doe@example.com",
    "graduated": False,
    "credits_completed": 56,
    "university": "Miramar College"
}

print("Student Dictionary with 10 elements:")
print(student_info)
```
1b. Take inputs from a user and add them in a dictionary called my_user_dict
```python
my_user_dict = {
    "SSN": "111-222-3333",
    "Name": "Steve Hawkins"
}
# Empty dictionary
my_user_dict = {}

while True:
    ssn = input("Enter SSN: ")
    name = input("Enter Name: ")

    # Add entry to dictionary
    my_user_dict[ssn] = name

    # Ask if user wants to continue
    choice = input("Do you want to continue (Y/N)? ").strip().lower()
    if choice == "n":
        break

print("\nFinal Dictionary:")
print(my_user_dict)
```

1c. Based on the given tuple, create a code which checks for valid key & value pairs, and check for key duplication.
```python
# Input list of tuples
a = [
    ('Name', 'Sarah Connor'),
    ('Date of birth', '1 Jan 1980'),
    ('Address', '1000 Black Mountain Drive', 92126),
    ('Name', 'Jim Hawkins')
]

# Empty dictionary
my_dict = {}

for pair in a:
    # ✅ Step 1: Check if it's a valid pair (length = 2)
    if len(pair) != 2:
        print("Invalid pair:", pair)
        print("Please correct this pair (must be in form: (key, value))")
        continue

    key, value = pair  # unpack

    # ✅ Step 2: Check for duplicate key
    while key in my_dict:
        print(f"Duplicate key found: '{key}' with value '{value}'")
        key = input("Please enter a new key: ")

    # ✅ Step 3: Add to dictionary
    my_dict[key] = value

print("\nFinal dictionary:")
print(my_dict)
```
1d. Convert the following list into a dictionary. Automate the process by using the loop.
```python
a = [
    ("Name", "Sarah Connor"),
    ("Date of birth", "1 Jan 1980"),
    ("Address", "1000 Black Mountain Drive"),
    ("SSN", "111-222-3333"),
    ("Phone", "123-456-7890")
]

# Empty dictionary
my_dict = {}

# Loop through the list of tuples
for key, value in a:
    my_dict[key] = value

print("Converted dictionary:")
print(my_dict)
```
1e. Use the following text and count the number of words using dictionary. Remember The or the counts as 2.
```python
text = """The tiger (Panthera tigris) is a large cat and a member of the genus Panthera native to Asia. 
It has a powerful, muscular body with a large head and paws, a long tail and orange fur with black, 
mostly vertical stripes. It is traditionally classified into nine recent subspecies, though some recognise 
only two subspecies, mainland Asian tigers and the island tigers of the Sunda Islands."""

# Split text into words
words = text.split()

# Empty dictionary
word_count = {}

# Loop to count words
for word in words:
    if word not in word_count:
        word_count[word] = 1
    else:
        word_count[word] += 1

# Print results
print("Word count dictionary:\n")
print(word_count)
```

## 2. Troubleshooting
2a. Change the content of d_copy and make sure the content does not affect the d_orig dictionary. Verify using the code.
```python
d_orig = {123: "Coconut"}

# Make a true copy
d_copy = d_orig.copy()

# Change d_copy
d_copy[123] = "Mango"

print("Original dictionary:", d_orig)
print("Copied dictionary:", d_copy)
```
2b. If it changes the content of the original dictionary, then propose how can you solve this problem.
```python
d_orig = {123: "Coconut"}

# Wrong way (shared reference):
d_copy = d_orig
d_copy[123] = "Mango"

print("Shared reference:")
print("d_orig:", d_orig)   # changes too ❌
print("d_copy:", d_copy)

# Correct way (independent copy):
d_copy = d_orig.copy()     # or dict(d_orig)
d_copy[123] = "Banana"

print("\nIndependent copy:")
print("d_orig:", d_orig)   # unchanged ✅
print("d_copy:", d_copy)
```
2c. Write a code that generates the following error and explain why there is such an error. 
The error occurs because lists are mutable and therefore unhashable, so they cannot be used as dictionary keys.
```python
# Trying to use a list as a dictionary key
my_dict = {
    [1, 2, 3]: "numbers"
}
```

## Challenges 
The main challange I had was with 2c and really understanding it,
