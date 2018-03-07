#include <iostream>
#include "checking.h"

using namespace std;


class Checking
{
public:
    int num;
    float balance;

    Checking();
    Checking(int account_num, float initial_balance);

    void open(int account_num, float initial_balance);
    void writeCheck(float amount);
    void deposit(float amount);
    void display();


    void clientCode3()
    {
        Checking a,b;
        a.open(2345, 1500);
        a.writeCheck(835);
        a.writeCheck(284);
        a.deposit(1450);
        a.display();

        b.open(9876, 4200);
        b.deposit(720);
        b.writeCheck(2279);
        b.display();
    }

    void clientCode5()
    {
        Checking accounts[5];

        Checking &a=accounts[0], &b=accounts[1];

        a.open(2345, 1500);
        a.writeCheck(835);
        a.writeCheck(284);
        a.deposit(1450);
        a.display();

        b.open(9876, 4200);
        b.deposit(720);
        b.writeCheck(2279);
        b.display();
    }

    int main(int argc, char *argv[])
    {
        clientCode5();


        Checking::Checking():num(1111),balance(0)
        {
        }

        Checking::Checking(int account_num, float initial_balance):num(account_num),balance(initial_balance)
        {
        }

        void Checking::open(int account_num, float initial_balance)
        {
            num = account_num;
            balance = initial_balance;
        }

        void Checking::writeCheck(float amount)
        {
            if (balance<amount){
                cout<<"Insufficient balance"<<endl;
                return;
            }
            else{
                cout<<"Check: "<<num <<"|" <<amount<<endl;
            }
        }

        void Checking::deposit(float amount)
        {
            balance += amount;
        }

        void Checking::display()
        {
            cout<<"Account Number:"<<num<<" Current Balance"<<balance<<endl;
        }

        system("PAUSE");
        return EXIT_SUCCESS;
    }

};
