import matplotlib.pyplot as plt

# Initialize an empty list to store expenses
expenses = []

# Add an expense
def add_expense():
    date = input("Enter the date (YYYY-MM-DD): ")
    category = input("Enter the category (e.g., Food, Travel): ")

    # Validate the amount input
    while True:
        amount = input("Enter the amount (₹): ")
        if amount.replace('.', '', 1).isdigit():  # Check if it's a valid number
            amount = float(amount)
            break
        else:
            print("Invalid input! Please enter a valid numeric value.")

    # Add the expense to the list 
                                                                                     
    expenses.append({"Date": date, "Category": category, "Amount": amount})
    print("Expense added successfully!")

# View all expenses
def view_expenses():
    if not expenses:
        print("\nNo expenses recorded!")
        return

    print("\nAll Expenses:")
    print("Date\t\tCategory\tAmount")
    print("-" * 30)
    for expense in expenses:
        print(f"{expense['Date']}\t{expense['Category']}\t₹{expense['Amount']:.2f}")

# View summary
def view_summary():
    if not expenses:
        print("\nNo expenses recorded!")
        return
                                                                                      
    total_expenses = 0
    max_expense = expenses[0]["Amount"]
    min_expense = expenses[0]["Amount"]

    for expense in expenses:
        total_expenses += expense["Amount"]
        if expense["Amount"] > max_expense:
            max_expense = expense["Amount"]
        if expense["Amount"] < min_expense:
            min_expense = expense["Amount"]

    average_expense = total_expenses / len(expenses)

    print("\nExpense Summary:")
    print(f"Total Expenses: ₹{total_expenses:.2f}")
    print(f"Average Expense: ₹{average_expense:.2f}")
    print(f"Maximum Expense: ₹{max_expense:.2f}")
    print(f"Minimum Expense: ₹{min_expense:.2f}")

# Generate bar chart using Matplotlib
def generate_bar_chart():                                       
    if not expenses:
        print("\nNo expenses recorded!")
        return

    # Aggregate expenses by date
    expense_by_date = {}
    for expense in expenses:
        date = expense["Date"]
        if date in expense_by_date:
            expense_by_date[date] += expense["Amount"]
        else:
            expense_by_date[date] = expense["Amount"]

    # Prepare data for plotting
    dates = list(expense_by_date.keys())
    amounts = list(expense_by_date.values())

    # Plot the data
    plt.figure(figsize=(8, 5))
    plt.bar(dates, amounts, color="skyblue")
    plt.title("Daily Expenses")
    plt.xlabel("Date")                                                   
    plt.ylabel("Expense Amount (₹)")
    plt.xticks(rotation=45)
    plt.tight_layout()
    plt.show()

# Main menu
while True:
    print("\nExpense Tracker")
    print("1. Add Expense")
    print("2. View Expenses")
    print("3. View Summary")
    print("4. Generate Bar Chart")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_expense()
    elif choice == "2":
        view_expenses()
    elif choice == "3":
        view_summary()
    elif choice == "4":
        generate_bar_chart()                                       
    elif choice == "5":
        print("Exiting... Goodbye!")
        break
    else:
        print("Invalid choice! Please try again.")
