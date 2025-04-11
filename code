#include <iostream>
#include<fstream>
#include <string>
static int count=0;
using namespace std;
class Account 
{
    private:
    string accountHolder;
    int accountNumber;
    float balance;


    public:
    Account(){};
    Account(string name, int number, float initialBalance = 0.0)
    {
         accountHolder = name;
         accountNumber = number;
         balance = initialBalance; 
    }

    int getaccountnumber()
    {
        return accountNumber;
    }

    void deposit(float amount) 
    {
        balance += amount;
    }

    bool withdraw(float amount) 
    {
        if (amount > balance) 
        {
            cout << "Insufficient amount" << endl;
            return false;
        }
        balance -= amount;
        return true;
    }

    float getBalance() 
    {
        return balance;
    }

    void displayInfo()  
    {
        cout << "Account Holder: " << accountHolder << endl;
        cout << "Account Number: " << accountNumber << endl;
        cout << "Balance: " << balance <<"rupees"<< endl;
    }

};

class Bankk 
{
    private:
    Account accounts[100];
    public:
    void createAccount(string name, int number, float initialBalance) 
    {
        count++;
        Account a(name,number,initialBalance);
        Account *p;
        p=findAccount(number);
        if (!p)
        {
            accounts[count]=a;
            cout << "account created successfully!" << endl;
        }
        else
        {
            cout<<"your account can't created"<<endl;
        }
    }

    Account* findAccount(int number) 
    {
        for (int i=0;i<count;i++) 
        {
            if (accounts[i].getaccountnumber() == number) 
            {
                return &accounts[i];
            }
        }
        return nullptr;
    }

    void listAccounts()  
    {
        for (int i=0;i<count;i++) 
        {
            Account *j;
            j=&accounts[i];
            j->displayInfo();
            cout << endl;
        }
    }
};

int main() 
{

    Bankk xyz;

    int choice;
    do {
        cout << "1. Create Account" << endl;
        cout << "2. Deposit" << endl;
        cout << "3. Withdraw" << endl;
        cout << "4. Check Balance" << endl;
        cout << "5. List All Accounts" << endl;
        cout << "6. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;

        if (choice == 1) 
        {
            string name;
            int number;
            float initialBalance;
            cout << "Enter account holder name: ";
            cin >> name;
            cout << "Enter account number: ";
            cin >> number;
            cout << "Enter initial balance: ";
            cin >> initialBalance;

            xyz.createAccount(name, number, initialBalance);
            
        } 
        else if (choice == 2) 
        {
            int number;
            float amount;
            cout << "Enter account number: ";
            cin >> number;
            cout << "Enter amount to deposit: ";
            cin >> amount;

            Account* account = xyz.findAccount(number);
            if (account) 
            {
                account->deposit(amount);
                cout << "Deposit successful!" << endl;
            } else 
            {
                cout << "Account not found." << endl;
            }
        } 
        else if (choice == 3) 
        {
            int number;
            float amount;
            cout << "Enter account number: ";
            cin >> number;
            cout << "Enter amount to withdraw: ";
            cin >> amount;

            Account* account = xyz.findAccount(number);
            if (account->withdraw(amount)) 
            {
                cout << "Withdrawal successful!" << endl;
            } else 
            {
                cout << "Withdrawal failed." << endl;
            }
        } 
        else if (choice == 4) 
        {
            int number;
            cout << "Enter account number: ";
            cin >> number;

            Account* account = xyz.findAccount(number);
            if (account) 
            {
                cout << "Account Balance: " << account->getBalance() << endl;
            } 
            else 
            {
                cout << "Account not found." << endl;
            }
        } 
        else if (choice == 5) 
        {
            xyz.listAccounts();
        }

    } while (choice<6&&choice>=1);

    cout << "Have a nice day" << endl;
    return 0;
}

