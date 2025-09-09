# User input using input() function
## 1. User input
**a. Write a program that prompts the user to enter the weight of a person in kilograms and outputs the equivalent weight in pounds. (Note that 1 kilogram = 2.2 pounds).**

```python
kilograms = float(input("Enter weight in kilograms: "))
```
**b.**
```python
net_balance = float(input("Enter net balance (in $): "))
payment = float(input("Enter payment made (in $): "))
d1 = int(input("Enter number of days in billing cycle: "))
d2 = int(input("Enter number of days payment is made before billing cycle ends: "))
monthly_interest_rate = float(input("Enter monthly interest rate (e.g., 0.0152 for 1.52%): "))
```
**c. Write a program that prompts the user to enter the average speed of both the cars and the elapsed time (in hours and minutes) and outputs the (shortest) distance between the cars.**
```python
x = float(input("Enter the average speed of Car A (in mph): "))
y = float(input("Enter the average speed of Car B (in mph): "))
hours = int(input("Enter elapsed time - Hours: "))
minutes = int(input("Enter elapsed time - Minutes: "))
print(f"\nThe shortest distance between the two cars is: {distance:.2f} miles")
```

## 2. Troubleshooting

a. hello = "hello" - Is ok due to assigning string to the variable hello.
b. _var = 100 - Is ok because variables can start with an underscore.
c. !var_1 = 200 - Is false because variable cannot start with !, or special characters.
d. print = "print me" - Seems ok, but print() is better.
e. False = 0 - Is false due to syntax error.

# Challenges
My only main challenge was troubleshooting the problems in 2. 

