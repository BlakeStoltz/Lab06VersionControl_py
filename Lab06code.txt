# runs encoder
def encoder(message):
    result = ''
    for digit in message:
        new_digit = str((int(digit) + 3) % 10)
        result += new_digit
    return result


# Takes a numeric string with each digit shifted up by 3 and returns a message with the given and decoded string.
def decode(encoded_password):
    original_string = ""
    for char in encoded_password:
        # If conditions accounts for numbers that were larger in the original string.
        if (char == '0'):
            original_string += '7'
        elif (char == '1'):
            original_string += '8'
        elif (char == '2'):
            original_string += '9'
        else:
            original_string += str(int(char) - 3)
    return "The encoded password is " + (encoded_password) + ", and the original password is " + (original_string) + "."


# runs the menu and options
def main():
    # prints menu
    while True:
        print("Menu")
        print("-------------")
        print("1. Encode")
        print("2. Decode")
        print("3. Quit")
        choice = input("Please enter an option: ")

        # calls the encoder and encodes a password
        if choice == "1":
            value = input("Please enter your password to encode: ")
            print("Your password has been encoded and stored!")

        # calls the decoder and decodes a password
        elif choice == "2":
            print(decode(value))
            print()

        # terminates/exits code
        elif choice == "3":
            break

        # displays message if invalid choice is inputed
        else:
            print("Invalid choice")
        print()


main()
