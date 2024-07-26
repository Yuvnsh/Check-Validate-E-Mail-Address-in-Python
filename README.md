# Check-Validate-E-Mail-Address-in-Python
Email Validation Script This Python script validates an email address based on several conditions. The conditions ensure that the email address follows a standard format and includes necessary components like alphabetic characters, the "@" symbol, and a username name.


How It Works
The script follows these validation steps:

Length Check: The email must be at least 6 characters long.
First Character Check: The first character of the email must be an alphabet letter.
"@" Check: The email must contain exactly one "@" symbol.
Domain Check: The email must have a "." either three or four characters from the end.
Character Validation: The script checks each character in the email to ensure:
There are no spaces.
There are no uppercase letters.
Only valid characters are used (letters, digits, underscores, periods, and the "@" symbol).


email = input("Enter Your Email: ")  # e.g., g@g.in , yuvnishkumar01@gmail.com

# Check if the length of the email is at least 6 characters
if len(email) >= 6:  # Condition 1
    print("Condition 1 passed")
    # Check if the first character is an alphabet letter
    if email[0].isalpha():  # Condition 2
        print("Condition 2 passed")
        # Check if there is exactly one "@" in the email
        if ("@" in email) and (email.count("@") == 1):  # Condition 3
            print("Condition 3 passed")
            # Check if there is a "." either three or four characters from the end
            if (email[-4] == ".") ^ (email[-3] == "."):  # Condition 4 (XOR operator)
                print("Condition 4 passed")
                k, j, d = 0, 0, 0
                for i in email:
                    if i.isspace():  # Check for spaces
                        k = 1
                    elif i.isalpha():
                        if i.isupper():  # Check for uppercase letters
                            j = 1
                    elif i.isdigit():
                        continue
                    elif i in ("_", ".", "@"):
                        continue
                    else:
                        d = 1

                if k == 0 and j == 0 and d == 0:
                    print("Right Email")
                else:
                    print("Wrong Email")
            else:
                print("Wrong Email (Condition 4 failed)")
        else:
            print("Wrong Email (Condition 3 failed)")
    else:
        print("Wrong Email (Condition 2 failed)")
else:
    print("Wrong Email (Condition 1 failed)")

