# Loops
## 1. While loop
a. Please write Python code using a while loop to perform the following steps.
```python
n0 = int(input("Enter a non-negative, non-zero integer: "))
if n0 <= 0:
    print("The number must be a positive integer greater than 0.")
else:
 while n0 != 1:
        print(n0)  # Print current value
        if n0 % 2 == 0:
   n0 = n0 // 2
        else:
            n0 = 3 * n0 + 1
print(n0)
```
b. Write code that uses a while loop and runs indefinitely. Modify the same code to resolve the infinite loop issue.
```python
while True:
    print("This loop will run forever!")
while True:
    user_input = input("Do you want to continue? (yes/no): ").lower()
    
    if user_input == "no":
        print("Exiting the loop. Goodbye!")
        break  # Exit the loop
    
    print("Loop continues...")
```
c. Write a program that takes two integers as input and asks the user to choose an arithmetic operation to perform with those numbers. At the end of the program, prompt the user with the question, "Do you want to continue?" If the user selects "Y" or "y," the program should restart; otherwise, it should exit and display the message, "Have a good day."
```python
while True:
    try:
        num1 = int(input("Enter the first number: "))
        num2 = int(input("Enter the second number: "))
    except ValueError:
        print("\nChoose an operation:")
        print("1. Addition (+)")
        print("2. Subtraction (-)")
        print("3. Multiplication (*)")
        print("4. Division (/)")
        choice = input("Enter your choice (1/2/3/4): ")
        if choice == '1':
            result = num1 + num2
            print("Result:", result)
        elif choice == '2':
            result = num1 - num2
            print("Result:", result)
        elif choice == '3':
            result = num1 * num2
            print("Result:", result)
        elif choice == '4':
            if num2 == 0:
                print("Error: Cannot divide by zero.")
            else:
                result = num1 / num2
                print("Result:", result)
        else:
            print("Invalid choice. Please select 1, 2, 3, or 4.")
            cont = input("\nDo you want to continue? (Y/N): ")
            if cont.lower() != 'y':
                print("Have a good day.")
                break
```
## 2. For loops
a. Write a code that counts the total number of characters in a text and also counts each character individually. For example, consider the sentence "To be, or not to be, that is the question." The code should determine the total number of letters and how many times each letter appears, including specific counts for the letters 't' and 'o', etc. Ignore the upper and lower cases letters, and any punctuations symbols. Use only for loop, while loop, break and continue statements where necessary.
```python
text = "To be, or not to be, that is the question."
text = text.lower()
letter_counts = {}
total_letters = 0
for char in text:
    if char < 'a' or char > 'z':
        continue
    total_letters += 1
    if char in letter_counts:
        letter_counts[char] += 1
    else:
        letter_counts[char] = 1
        print("Total letters:", total_letters)
        print("Letter counts:")
        for letter in sorted(letter_counts):  # sorted for neat output
            print(f"{letter}: {letter_counts[letter]}")
            print("\nSpecific counts:")
            print(f"Count of 't': {letter_counts.get('t', 0)}")
            print(f"Count of 'o': {letter_counts.get('o', 0)}")
```
# Challenges
The main challenge I found was in the first question and actually getting my code to run. 
