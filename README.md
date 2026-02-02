Banking System in C
Project Overview

A console-based banking management system written in C that allows users to create accounts, perform transactions, and manage banking operations with basic security features.
Features
Core Functionalities:

    Account Creation: Create new bank accounts with unique phone numbers as account numbers

    Balance Management: Deposit and withdraw money with PIN verification

    Account Search: Look up account details with PIN authentication

    Account Display: View all accounts (requires authorized access key)

    Data Persistence: Automatically saves account data to files

Security Features:

    5-digit PIN system for account access

    PIN verification for sensitive operations

    Admin key protection for account display

    Protection against duplicate account numbers

File Structure

banking_system.c  - Main source code file
Accounts.txt      - Primary database file (auto-generated)
Output.txt        - Temporary output file during operations

Data Structure

typedef struct {
    int accountNumber;    // Phone number (without leading 0)
    char name[50];        // Account holder name (use '_' for spaces)
    float balance;        // Account balance
    int pin;              // 5-digit security PIN
} Account;

How to Compile and Run
Compilation:
bash

gcc banking_system.c -o banking_system

Execution:
bash

./banking_system

Usage Instructions
Main Menu Options:

    1. Create a New Account

        Enter phone number (without leading 0)

        Enter name (use '_' instead of spaces)

        Set initial deposit amount

        Create a 5-digit PIN

    2. Display Accounts (Authorized Use Only)

        Requires admin key: 17122845

        Shows all account details except PINs

    3. Deposit Money

        Enter account number

        Verify PIN

        Enter deposit amount

    4. Withdraw Money

        Enter account number

        Verify PIN

        Enter withdrawal amount (checks balance)

    5. Search Account

        Enter account number

        Verify PIN

        View account details

    6. Save & Exit

        Saves all changes to files

        Exits the program

Important Notes
Naming Convention:

    Use underscores (_) instead of spaces in names

    Example: "John_Doe" instead of "John Doe"

Account Numbers:

    Use phone numbers without the leading 0

    Example: 1234567890 (not 01234567890)

PIN Security:

    PIN must be exactly 5 digits

    PIN is required for transactions and account access

    PINs are stored in plain text (for educational purposes)

File Handling:

    Initial data loads from Accounts.txt

    Changes are saved to Output.txt during operations

    On exit, data is copied from Output.txt to Accounts.txt

Limitations and Considerations
Security:

    PINs are stored in plain text (not encrypted)

    Admin key is hardcoded in the source

    File data is not encrypted

Technical Limitations:

    Maximum of 100 accounts

    No transaction history tracking

    No interest calculation

    No account deletion feature

Input Restrictions:

    Names must not contain spaces (use underscores)

    Account numbers must be integers

    Balance is stored as float (potential precision issues)

Future Enhancements

Potential Improvements:

    Security

        Encrypt PINs and sensitive data

        Implement password hashing

        Add login system for administrators

    Features

        Transaction history

        Interest calculation

        Account deactivation

        Fund transfers between accounts

    User Experience

        GUI implementation

        Better error messages

        Data export/import features

    Technical

        Database integration

        Network capabilities

        Multi-user support

Error Handling

The system includes basic error handling for:

    Duplicate account numbers

    Insufficient funds during withdrawal

    Invalid PIN entries

    File I/O errors

    Invalid menu choices

Dependencies

    Standard C libraries only

    No external dependencies required

    Compatible with any C compiler

Author

This is an educational banking system project demonstrating:

    C programming fundamentals

    File handling operations

    Basic data structures

    Simple security implementation

    Console-based menu systems

License

Educational use only. Modify and distribute as needed for learning purposes.
Disclaimer

This is a simplified educational project. DO NOT USE FOR REAL BANKING OPERATIONS. The system lacks essential security features required for real financial applications.

