# Password-generator-tool
import random
import string

def generate_password(length=12):
    # Define available characters for the password
    characters = string.ascii_letters + string.digits + string.punctuation
    
    # Generate the password
    password = ''.join(random.choice(characters) for _ in range(length))
    
    return password

def main():
    print("Welcome to the Password Generator Tool!")
    print("--------------------------------------")
    
    while True:
        try:
            length = int(input("Enter the length of the password (at least 6 characters): "))
            if length < 6:
                print("Password length should be at least 6 characters.")
                continue
            
            password = generate_password(length)
            print(f"Generated Password: {password}")
            
            # Ask user if they want to generate another password
            while True:
                another = input("Generate another password? (yes/no): ").lower()
                if another == 'yes':
                    break
                elif another == 'no':
                    print("Thank you for using the Password Generator Tool. Stay secure!")
                    return
                else:
                    print("Invalid input. Please enter 'yes' or 'no'.")
        
        except ValueError:
            print("Invalid input. Please enter a valid number for password length.")

if __name__ == "__main__":
    main()
