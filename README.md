![WhatsApp Image 2026-01-09 at 2 39 18 PM](https://github.com/user-attachments/assets/4e2af277-5b7d-40b8-bcba-8bc3171b2922)
# password-strength-checker
Password checker documentation and files
def check_password_strength(password):
    strength = 0

    if len(password) >= 8:
        strength += 1
    if any(char.isupper() for char in password):
        strength += 1
    if any(char.islower() for char in password):
        strength += 1
    if any(char.isdigit() for char in password):
        strength += 1
    if any(char in "!@#$%^&*()_+" for char in password):
        strength += 1

    if strength <= 2:
        return "Weak Password"
    elif strength == 3 or strength == 4:
        return "Medium Password"
    else:
        return "Strong Password"


password = input("Enter your password: ")
result = check_password_strength(password)
print("Password Strength:", result)
