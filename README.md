def add(num1, num2):
    """Adds two numbers and returns the result."""
    return num1 + num2
def subtract(num1, num2):
    """Subtracts the second number from the first and returns the result."""
    return num1 - num2
def multiply(num1, num2):
    """Multiplies two numbers and returns the result."""
    return num1 * num2
def divide(num1, num2):
    """
    Divides the first number by the second.
    Handles the case of division by zero.
    """
    if num2 == 0:
        return "Error! Cannot divide by zero."
    else:
        return num1 / num2
def calculator():
    """Main function to run the calculator program."""
    print("Welcome to the Simple Python Calculator!")
    print("Available operations: +, -, *, /")
    while True:
        try:
            # Get the first number from the user
            num1_str = input("Enter the first number (or 'exit' to quit): ")
            if num1_str.lower() == 'exit':
                print("Goodbye!")
                break
            num1 = float(num1_str)
            operator = input("Enter an operator (+, -, *, /): ")
            num2_str = input("Enter the second number: ")
            num2 = float(num2_str)
            if operator == '+':
                result = add(num1, num2)
            elif operator == '-':
                result = subtract(num1, num2)
            elif operator == '*':
                result = multiply(num1, num2)
            elif operator == '/':
                result = divide(num1, num2)
            else:
                print("Invalid operator. Please try again.")
                continue
            print(f"The result is: {result}\n")
        except ValueError:
            print("Invalid input. Please enter a valid number.\n")
        except Exception as e:
            print(f"An error occurred: {e}\n")
if __name__ == "__main__":
    calculator()
