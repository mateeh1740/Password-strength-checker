import string
password = input("Password: ")
checks = [
    len(password) >= 12,
    any(c.islower() for c in password),
    any(c.isupper() for c in password),
    any(c.isdigit() for c in password),
    any(c in string.punctuation for c in password),
]
score = sum(checks)
labels = ["Very weak", "Weak", "Fair", "Strong", "Very strong", "Excellent"]
print(f"Strength: {labels[score]}")
missing = [name for name, ok in zip(
    ["12+ characters", "lowercase", "uppercase", "digit", "special character"], checks
) if not ok]
if missing:
    print("Add: " + ", ".join(missing))# Password-strength-checker
