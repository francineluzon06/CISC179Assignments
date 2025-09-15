# Decision statements
## 1. Comparison operators 
```python
import string
printable_chars = string.printable
print(f"Character: {repr(char):>4}  ASCII: {ord(char)}")
```
## 5. Problem Solving 
a. Find the largest three integers just using if statements. Take user inputs and display the result.
```python
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))
num3 = int(input("Enter third number: "))
if num1 >= num2 and num1 >= num3:
    largest = num1
if num2 >= num1 and num2 >= num3:
    largest = num2
if num3 >= num1 and num3 >= num2:
    largest = num3
print("The largest number is:", largest)
``` 
b. Identify multiple methods to determine if a number is even or odd. The user will input an integer, and the output will indicate whether it's "odd" or "even." The code should be organized into sections, with comments separating each part. For example
```python
number = int(input("Enter an integer to check if it is even or odd: "))
if number % 2 == 0:
    print("Approach 1: Even")
else:
    print("Approach 1: Odd")
if (number // 2) * 2 == number:
    print("Approach 2: Even")
else:
    print("Approach 2: Odd")
last_digit = number % 10
if last_digit in [0, 2, 4, 6, 8]:
    print("Approach 3: Even")
else:
    print("Approach 3: Odd")
```
d. Write a code which takes and, or, not as an user input. Create a truth table by writing your expressions. Display the truth table using print() function. Research how the truth tables for logical operators are structured.
```python
operator = input("Enter logical operator (and, or, not): ").lower()
values = [True, False]
print("\nTruth Table for", operator)
print("-" * 30)
if operator == "and":
    print("A\tB\tA and B")
    for A in values:
        for B in values:
            print(f"{A}\t{B}\t{A and B}")
elif operator == "or":
    print("A\tB\tA or B")
    for A in values:
        for B in values:
            result = A or B
            print(f"{A}\t{B}\t{result}")
elif operator == "not":
    print("A\tnot A")
    for A in values:
        result = not A
           print(f"{A}\t{result}")
print("Invalid input. Please enter 'and', 'or', or 'not'.")
```
e. To determine whether an integer is even or odd using only a bitwise AND operator. the user will input an integer. Your code should utilize the bitwise AND operator to differentiate between even and odd numbers. Finally, use the print() function to display the result. Avoid using any modulus or remainder operators.
```python
number = int(input("Enter an integer: "))
if number & 1 == 0:
    print("The number is Even (using bitwise AND)")
else:
    print("The number is Odd (using bitwise AND)")
```
## 6. Code revision
Revise the code using nested if, elif, and else statements, and add comments to clarify the logic.
```python
name = input("What's your name? ")
time = int(input("What time is it? (Enter time in 24-hour format, e.g., 930, 1530): "))
if time < 1200:
 print("Hi " + name + ", good morning!")
elif time < 1800:
  print("Hi " + name + ", good afternoon!")
else:
 print("Hi " + name + ", good evening!")
print("Good Bye")
```
## 7. Output verification
What will be the output of the code provided below without using Python?
The output would be "one" and "two" 
# Challenge(s)
The main challenge I faced was where to begin with my code especially in question 5 part d.

