# **Emerald Bank - A Beginner's Banking System in C++**

---

## **Overview**

Emerald Bank is a console-based banking system developed in C++ as a beginner project to learn and explore various programming concepts. This system provides functionality to register, login, and manage basic banking tasks like checking balance, depositing money, withdrawing money, and transferring funds between accounts. All monetary values are displayed in **₹ (Indian Rupees)**.

---

## **Features**

1. **User Registration**:
   - Users can create an account with a unique username and a secure password.

2. **User Authentication**:
   - Secure login system to ensure authorized access.

3. **Banking Features**:
   - **View Balance**: Check account balance.
   - **Deposit Money**: Add funds to the account.
   - **Withdraw Money**: Remove funds from the account (with balance checks).
   - **Transfer Money**: Transfer funds to other users.

4. **Data Storage**:
   - User data (username, password, balance) is stored in text files within a `data` directory for simplicity.

5. **Error Handling**:
   - Handles incorrect login attempts, invalid inputs, and ensures smooth user experience.

6. **Extensibility**:
   - Simple architecture makes it easy to add new features.

---

## **Folder Structure**

```plaintext
Emerald_Bank/
│
├── data/                 # Folder to store user account data files
├── header.txt            # ASCII art or welcome message displayed at startup
├── EmeraldBank.cpp       # Main source code file
└── README.md             # Project documentation
