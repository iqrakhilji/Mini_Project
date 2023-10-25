""" Mini Project (12 Hours Drill)
Bank Account Manager - 
Create a class called Account which will be an abstract class for three other classes called CheckingAccount, SavingsAccount and BusinessAccount. 
Manage credits and debits from these accounts through an ATM style program.
"""
from abc import ABC, abstractmethod

class Account(ABC):
    def __init__(self, account_number, balance=0):
        self.account_number = account_number
        self.balance = balance

    @abstractmethod
    def deposit(self, amount):
        pass

    @abstractmethod
    def withdraw(self, amount):
        pass

    def get_balance(self):
        return self.balance

class CheckingAccount(Account):
    def __init__(self, account_number):
        super().__init__(account_number)

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
        else:
            print("Invalid amount for deposit")

    def withdraw(self, amount):
        if amount > 0:
            if self.balance >= amount:
                self.balance -= amount
                print("Withdrawal of ${:.2f} successful.".format(amount))
            else:
                print("Insufficient funds")
        else:
            print("Invalid amount for withdrawal")

class SavingsAccount(Account):
    def __init__(self, account_number):
        super().__init__(account_number)

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print("Deposit of ${:.2f} successful.".format(amount))
        else:
            print("Invalid amount for deposit")

    def withdraw(self, amount):
        if amount > 0:
            if self.balance >= amount:
                self.balance -= amount
                print("Withdrawal of ${:.2f} successful.".format(amount))
            else:
                print("Insufficient funds")
        else:
            print("Invalid amount for withdrawal")

class BusinessAccount(Account):
    def __init__(self, account_number):
        super().__init__(account_number)

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print("Deposit of ${:.2f} successful.".format(amount))
        else:
            print("Invalid amount for deposit")

    def withdraw(self, amount):
        if amount > 0:
            if self.balance >= amount:
                self.balance -= amount
                print("Withdrawal of ${:.2f} successful.".format(amount))
            else:
                print("Insufficient funds")
        else:
            print("Invalid amount for withdrawal")

def main():
    accounts = {}
    while True:
        ch = int(input('1: create account\n2: view account\n3: deposit\n4: withdraw\n5: delete account\n6: exit\n'))
        if ch == 1:
            accnum = input('Enter account number: ')
            account_type = input('Enter account type \n1:Checking \n2:Savings \n3:Business \n ')

            if account_type.lower() == '1':
                account = CheckingAccount(accnum)
            elif account_type.lower() == '2':
                account = SavingsAccount(accnum)
            elif account_type.lower() == '3':
                account = BusinessAccount(accnum)
            else:
                print("Invalid account type")
                continue

            accounts[accnum] = account
            print("Account created successfully!")

        elif ch == 2:
            accnum = input('Enter account number: ')
            account = accounts.get(accnum)
            if account:
                print(f"Account Number: {account.account_number}")
                print(f"Current Balance: ${account.get_balance()}")
            else:
                print("Account not found")

        elif ch == 3:
            accnum = input('Enter account number: ')
            account = accounts.get(accnum)
            if account:
                amount = float(input('Enter the deposit amount: $'))
                account.deposit(amount)
            else:
                print("Account not found")

        elif ch == 4:
            accnum = input('Enter account number: ')
            account = accounts.get(accnum)
            if account:
                amount = float(input('Enter the withdrawal amount: $'))
                account.withdraw(amount)
            else:
                print("Account not found")

        elif ch == 5:
            accnum = input('Enter account number: ')
            if accnum in accounts:
                del accounts[accnum]
                print(f"Account {accnum} deleted")
            else:
                print("Account not found")

        elif ch == 6:
            exit(0)

main()
"""
--------Expected output -------------
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
1
Enter account number: 1234
Enter account type
1:Checking
2:Savings
3:Business : 2
Account created successfully!
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
2
Enter account number: 1234
Account Number: 1234
Current Balance: $0
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
3
Enter account number: 1234
Enter the deposit amount: $12345
Deposit of $12345.00 successful.
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
2
Enter account number: 1234
Account Number: 1234
Current Balance: $12345.0
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
4 
Enter account number: 1234
Enter the withdrawal amount: $123 
Withdrawal of $123.00 successful.
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
2
Enter account number: 1234
Account Number: 1234
Current Balance: $12222.0
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
5
Enter account number: 1234
Account 1234 deleted
1: create account
2: view account
3: deposit
4: withdraw
5: delete account
6: exit
6
----------------------------------
"""