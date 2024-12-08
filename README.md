# **Emerald Bank**

Emerald Bank is a simple, console-based banking application written in C++. It allows users to register, log in, check their balance, deposit, withdraw, and transfer money between accounts. This project is an excellent demonstration of file-based user data management and authentication in C++.

---

## **Features**
1. **User Authentication**:
   - Register new users with a username and password.
   - Log in using a two-step authentication system (username and password).
2. **Banking Features**:
   - View account balance.
   - Deposit money into your account.
   - Withdraw money from your account.
   - Transfer money between accounts.
3. **File-Based Data Management**:
   - User data is stored securely in individual `.dat` files under the `data/` directory.
4. **User-Friendly Console Interface**:
   - Simple menu-driven UI for easy navigation.

---

## **Project Structure**

### **Files and Directories**
- `EmeraldBank.cpp`: The main source file containing the core implementation.
- `data/`: A folder that stores `.dat` files for each registered user.
  - Example: `data/username.dat` contains the user's credentials and balance.
- `header.txt`: A decorative file displayed at the top of the application.

---

## **How It Works**

### **1. Registration**
- Users register with a unique username and password.
- The system creates a new file named `data/<username>.dat`.
- The file contains:
  - Line 1: Username
  - Line 2: Password
  - Line 3: Initial balance (₹0).

#### **Example**
For a user `John` registering with the password `password123`, the file `data/John.dat` will contain:


---

### **2. Login**
- The system checks if the file `data/<username>.dat` exists.
- The entered password is verified against the stored password in the file.

---

### **3. Banking Operations**
After logging in, users can:
- **View Balance**: Reads the balance from the user's `.dat` file.
- **Deposit Money**:
  - Reads the current balance.
  - Adds the deposit amount.
  - Updates the balance in the file.
- **Withdraw Money**:
  - Checks if the withdrawal amount is less than or equal to the balance.
  - Deducts the amount and updates the file.
- **Transfer Money**:
  - Verifies the recipient's username.
  - Withdraws the amount from the sender and deposits it into the recipient's account.

---

## **Code Explanation**

### **Authentication**
1. **Username Verification**:
   - Checks if the user file exists (`data/<username>.dat`).
2. **Password Verification**:
   - Reads the stored password from the file and compares it with the entered password.

#### **Code Snippet**
```cpp
bool Bank::authenticateUser(const string usernameAttempt) {
    string fileName = "data\\" + usernameAttempt + ".dat";
    return ifstream(fileName); // True if file exists
}

bool Bank::authenticatePassword(const string usernameAttempt, const string passwordAttempt) {
    string fileName = "data\\" + usernameAttempt + ".dat";
    string storedPassword = readLine(fileName, 1); // Read password (Line 2)
    return storedPassword == passwordAttempt;
}
