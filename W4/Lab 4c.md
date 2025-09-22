# Functions in Python

## 1a. Research and find out the conversion factor between the units.
1 kilometer per liter (kpl) = 2.35215 miles per gallon (mpg)
1 mile per gallon (mpg) = 0.42514 kilometers per liter (kpl)

So the formulas are: mpg = kpl * 2.35215 and kpl = mpg * 0.42514

## 1b. How would you write a function that could take any number of unnamed arguments and print their values out in reverse order?
```python
def print_reverse(*args):
    for value in reversed(args):
        print(value)

# Example usage
print_reverse(10, "hello", 3.14, True, "Python")
```
## 1c. What would be the result of changing a list or dictionary that was passed into a function as a parameter value? Which operations would be likely to create changes that would be visible outside the function? What steps might you take to minimize that risk?
When a list or dictionary is passed to a function, in-place changes (like appending, updating, or deleting) affect the original object outside the function, so using a copy helps avoid unintended side effects.

## 1d. Assuming that x = 5, what will be the value of x after funct_1() below executes? After funct_2() executes?
After funct_1() > x = 5 and After funct_2() > x = 2

## 2. Troubleshooting 

## 2a. Correct the following code. There might be more than one correct answers. Explain your reasoning.
This worksbecause **c only collects keyword arugments, while **c collects extra positional arugments.
```python
def my_func(a, b, *c):
    print(c)

my_func(1, 2, 3, 4, 5, 6)
# Output: (3, 4, 5, 6)
```

## 2b. Using the following code, x should print 100 but it prints 10, why?
This is because x = 100 inside my_func_global() creates a local variable instead of modifying the global x, so the global x remains 10.
