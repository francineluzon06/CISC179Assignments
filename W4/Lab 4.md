# Lab 4: Child vaccination chart

```python
# Main patient dictionary
patient = {}


def insert():
    """Interactive function to add a patient record."""

    record_number = input("Enter patient record number (e.g., R001): ").strip()
    first_name = input("Enter patient's first name: ").strip()
    last_name = input("Enter patient's last name: ").strip()

    # Create a new record
    patient[record_number] = {
        "first_name": first_name,
        "last_name": last_name,
        "vaccines": {}
    }

    # Ask how many vaccines to enter
    num_vaccines = int(input("How many vaccines to enter? "))

    for _ in range(num_vaccines):
        vaccine_name = input("\nEnter vaccine name (e.g., HepB): ").strip()

        months = input(f"Enter months for {vaccine_name} (comma-separated, e.g., 0,1,6 or Annual): ").strip()

        # Handle months (convert to int list or keep as string if "Annual")
        if months.lower() == "annual":
            patient[record_number]["vaccines"][vaccine_name] = ["Annual"]
        else:
            month_list = [int(m.strip()) for m in months.split(",")]
            patient[record_number]["vaccines"][vaccine_name] = month_list

    print("\n✅ Patient added successfully!\n")


def view_all():
    """View all patient records."""
    if not patient:
        print("\n⚠️ No records found.\n")
    else:
        from pprint import pprint
        print("\n📋 Current Patient Records:")
        pprint(patient)
        print("\n")


def main_menu():
    """Menu system to manage patient records."""
    while True:
        print("------ Patient Records Menu ------")
        print("1. Insert new patient")
        print("2. View all patients")
        print("3. Exit")
        choice = input("Enter your choice: ").strip()

        if choice == "1":
            insert()
        elif choice == "2":
            view_all()
        elif choice == "3":
            print("\n👋 Exiting program. Goodbye!\n")
            break
        else:
            print("\n❌ Invalid choice. Please try again.\n")


# ---- Run Program ----
if __name__ == "__main__":
    main_menu()
```

# Video explanation of your code and its output.
https://youtu.be/NdCd1YTEVME 
