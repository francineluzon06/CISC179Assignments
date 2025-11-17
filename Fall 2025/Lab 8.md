# Lab 8

## Part 1: GUI Application
```python
import tkinter as tk
from tkinter import messagebox

def calculate_charge():
    try:
        minutes = float(minutes_entry.get())
        rate = rate_var.get()

root = tk.Tk()
root.title("Long Distance Call Calculator")

rate_var = tk.StringVar(value="day")

tk.Label(root, text="Select Rate Category:").pack()

tk.Radiobutton(root, text="Daytime (0.07/min)", variable=rate_var, value="day").pack()
tk.Radiobutton(root, text="Evening (0.12/min)", variable=rate_var, value="evening").pack()
tk.Radiobutton(root, text="Off-Peak (0.05/min)", variable=rate_var, value="off").pack()

tk.Label(root, text="Enter number of minutes:").pack()
minutes_entry = tk.Entry(root)
minutes_entry.pack()

tk.Button(root, text="Calculate Charge", command=calculate_charge).pack(pady=10)

root.mainloop()
```
## Part 2: GUI Program
```python
import tkinter as tk
from tkinter import messagebox

def calculate_tax():
    try:
        actual_value = float(value_entry.get())

        assessment = actual_value * 0.60
        tax = (assessment / 100) * 0.75

        messagebox.showinfo(
            "Property Tax Info",
            f"Assessment value: ${assessment:.2f}\nProperty tax: ${tax:.2f}"
        )

    except ValueError:
        messagebox.showerror("Error", "Please enter a valid number.")

root = tk.Tk()
root.title("Property Tax Calculator")

tk.Label(root, text="Enter actual property value:").pack()

value_entry = tk.Entry(root)
value_entry.pack()

tk.Button(root, text="Calculate Tax", command=calculate_tax).pack(pady=10)

root.mainloop()
```
