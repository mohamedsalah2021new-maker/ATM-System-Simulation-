# ATM-System-Simulation-
A simple ATM System Simulation using c++
#include <iostream>
#include <chrono>
#include <thread>
using namespace std;
int main ()
{

//************var*************//
    double balance =1000;
    int withdrawn=0;
    int deposit =0;
    int  choice ;
    int password=1234;
    int number_trys =0;

//"*********************//

    // المفترض إن العميل ادخل ال " card balance"
    cout << "your main menu " << endl;
    cout << "    1: withdraw" << endl;
    cout << "    2: deposit" << endl;
    cout << "    3: balance " << endl;
    cout << "\a " << endl;

    cout<<".    enter your password 🔑 "<<endl;
    cin >>password;
    while(password!= 1234 && number_trys<2) {
        cout << "\a " << endl;
        cout << "your password is wrong. "<<endl;
        cout <<" please enter your correct password 🔑 \n  "<<endl;

        cin >>password;
        ++number_trys;
    }
    if (password !=1234) {
        cout <<" your bank card balance has been withdrawn"<<endl;
        return 0;
    }

    if(password==1234) {

        cout<<"your balance is"<< balance <<"$"<<" what do you want to do ?" <<endl;

road:
        cout << "enter your choice (1,2,3) from the main menu" << endl;
        cin >>choice;
        cout <<" \n";
        if (choice !=1 && choice!=2 && choice!=3) {
            cout << "\a " << endl;
            cout<<" your choice is not exist"<<endl;
            goto road;
        }
        // االحمدلله تم البرنامج بنجاح
        switch(choice)
        {
        case 1 :
            cout <<"what you want withdrawn 😜 😁 "<<endl;
choice :
            cin >>withdrawn;
            if ( withdrawn> balance)
            {
                cout << "\a " << endl;
                cout <<"your balance not enough your balance is:"<<"$"<<balance<< endl;
                break;
            }

            cout <<" your balance now is "<<balance - withdrawn<< endl;
            break;
        case 2 :
            cout<<"what you want deposit"<<endl;
            cin >>deposit;

            cout<< " your balance now is "<< balance+deposit<<endl;
            break;
        case 3 :
            cout<<" your balance now is "<< balance<<endl;
        }
    }


    if (choice==1) {

        if ( withdrawn > balance)
        {
            cout << "\a " << endl;
            cout <<" please again your obration \n  " << endl ;

            goto choice;



        }
        else
        {
            cout << ".\n \n  👏 The withdraw process successfully" << endl;

            cout << "\a " << endl;
            cout << "\a " << endl;
        }
    }
    else if (choice==2) {

        cout<<". \n \n   🎉 The deposit process successfully. "<<endl;
        cout << "\a " << endl;
    }
    else if (choice==3) {
        cout << " \n \n 🎉 The balance process successfully" << endl;
    }


    string stand;
    cout << "Do you want a receipt 🧾 yes or no ??" << endl;
    cin >> stand ;
    if ( stand =="yes") {



        cout << " \nwait 5 seconds " << flush;

        // Wait for 5 seconds
        this_thread::sleep_for(chrono::seconds(5));

        // Clear the line (move cursor to beginning and clear line)
        cout << "\r\033[K"; // \r = return to start of line, \033[K = clear line


        if ( choice==1) {
            cout<<" \n  The reminder of your balance : " <<balance - withdrawn<< endl;
            cout << "\a " << endl;
            return 0;
        }
        else if (choice== 2 ) {
            cout << " \n  A valuable in your balance : " << deposit+ balance << endl;
            cout << "\a " << endl;
            return 0;
        }
        else ( choice == 3) ;
        {
            cout << " \n  your balance now is "<< balance << endl;
            cout << "\a " << endl;
            return 0;
        }

    }
    else (stand == "no");
    {
        cout << " \n complete operation 💯✅ " << endl;
    }
    cout << "\a " << endl;

    cout<< " *********************** ";
