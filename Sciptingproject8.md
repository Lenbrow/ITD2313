# ITD2313
def newton(number, estimate=0.5):
    if number == 0:
        return 0

    # Newton's method iteration
    new_estimate = (estimate + number / estimate) / 2
    if abs(new_estimate - estimate) < 1e-7:
        return new_estimate

    return newton(number, new_estimate)


def main():
    while True:
        input_number = input("Enter a number to compute its square root (press Enter to quit): ")
        if input_number == "":
            break
        try:
            number = float(input_number)
            result = newton(number)
            print(f"Square root of {number}: {result:.6f}")
        except ValueError:
            print("Invalid input. Please enter a valid number.")


if __name__ == "__main__":
    main()
