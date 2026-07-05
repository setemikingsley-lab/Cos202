import os
import math

def clear_screen():
    # Clear terminal screen
    os.system('cls' if os.name == 'nt' else 'clear')

def show_menu():
    print("="*40)
    print("  MATHEMATICAL CALCULATOR - MC")
    print("  Your Pocket Calculator")
    print("="*40)
    print("  Available Operations:")
    print("  +  : Addition")
    print("  -  : Subtraction") 
    print("  *  : Multiplication")
    print("  /  : Division")
    print("  // : Floor Division")
    print("  %  : Modulus - Remainder")
    print("  ** : Power - Exponent")
    print("  C  : Clear Screen")
    print("  OFF: Exit Calculator")
    print("="*40)

def calculate(num1, operator, num2):
    # Selection control statements for operations
    if operator == '+':
        return num1 + num2
    elif operator == '-':
        return num1 - num2
    elif operator == '*':
        return num1 * num2
    elif operator == '/':
        if num2 == 0:
            return "Error: Division by Zero!"
        return num1 / num2
    elif operator == '//':
        if num2 == 0:
            return "Error: Division by Zero!"
        return num1 // num2
    elif operator == '%':
        if num2 == 0:
            return "Error: Division by Zero!"
        return num1 % num2
    elif operator == '**':
        return num1 ** num2
    else:
        return "Invalid Operator"

def main():
    while True:
        show_menu()
        operator = input("\nEnter operator [ + - * / // % ** C OFF ]: ").strip()

        # Selection for special commands
        if operator.upper() == 'OFF':
            print("\nThank you for using MC. Goodbye! ")
            break
        elif operator.upper() == 'C':
            clear_screen()
            continue
        
        # Get numbers
        try:
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))
        except ValueError:
            print("Error: Please enter valid numbers!")
            input("Press Enter to continue...")
            clear_screen()
            continue

        # Perform calculation
        result = calculate(num1, operator, num2)
        
        print("-"*40)
        print(f"  Result: {num1} {operator} {num2} = {result}")
        print("-"*40)
        
        input("\nPress Enter to continue...")
        clear_screen()

# Run the calculator
main()<img width="1080" height="2340" alt="Screenshot_2026-07-05-20-30-53-824_ru iiec pydroid3" src="https://github.com/user-attachments/assets/6b5420e6-d2a0-4415-8a6e-beb5b1c247b2" />
