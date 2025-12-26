# CodeAlpha_cyberSecurity_task-3
Task_3
# Secure login system using hashing and validation

import hashlib
import time

# Simulated database with hashed passwords
users_db = {
    "admin": hashlib.sha256("Admin@123".encode()).hexdigest(),
    "user": hashlib.sha256("User@123".encode()).hexdigest()
}

MAX_ATTEMPTS = 3
attempts = 0

def hash_password(password):
    return hashlib.sha256(password.encode()).hexdigest()

while attempts < MAX_ATTEMPTS:
    username = input("Enter username: ").strip()
    password = input("Enter password: ").strip()

    # Input validation
    if not username or not password:
        print("Input cannot be empty.")
        continue

    hashed_input_password = hash_password(password)

    if username in users_db and users_db[username] == hashed_input_password:
        print("Login successful!")
        break
    else:
        attempts += 1
        print("Invalid credentials.")

    if attempts == MAX_ATTEMPTS:
        print("Account locked. Too many failed attempts.")
        time.sleep(2)


**OUTPUT:-**
<img width="715" height="291" alt="image" src="https://github.com/user-attachments/assets/3463283b-7b24-496c-b529-e54ab10bd253" />
