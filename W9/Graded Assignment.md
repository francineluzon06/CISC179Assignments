### Write a GUI program that calculates a car’s gas mileage. The program’s window should have Entry widgets that let the user enter the number of gallons of gas the car holds, and the number of miles it can be driven on a full tank. When a Calculate MPG button is clicked, the program should display the number of miles that the car may be driven per gallon of gas. Use the following formula to calculate miles-per-gallon:
#### MPG = miles / gallons

```python
import tkinter as tk

def calculate_mpg():
    gallons = float(entry_gallons.get())
    miles = float(entry_miles.get())
    mpg = miles / gallons
    label_result.config(text=f"MPG: {mpg:.2f}")

root = tk.Tk()
root.title("Gas Mileage Calculator")

tk.Label(root, text="Gallons of gas:").pack()
entry_gallons = tk.Entry(root)
entry_gallons.pack()

tk.Label(root, text="Miles on full tank:").pack()
entry_miles = tk.Entry(root)
entry_miles.pack()

tk.Button(root, text="Calculate MPG", command=calculate_mpg).pack()

label_result = tk.Label(root, text="MPG: ")
label_result.pack()

root.mainloop()
```
