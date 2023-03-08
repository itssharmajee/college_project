#include<iostream>
#include<fstream>
#include<conio.h>
#include<string.h>
using namespace std;
class course
{
    string name,clas,email;
    int mob;
public:
    void menu();
    void programming();
    void english();
    void anal_skills();
    void viewcourse();
    void trending();
    void service();
    void registration();
    void display();

    course()
    {
        cout<<"\t\t\t------------------------------------------------------------------"<<endl;

        cout<<"\t\t\t||............WELCOME LOVELY PROFESIONAL UNIVERSITY.............||"<<endl;

        cout<<"\t\t\t------------------------------------------------------------------\n\n"<<endl;
        cout<<"\t\t\t-----------------------------------------------------------------"<<endl;
        cout<<"\t\t\t||..............SEARCH ENGINE FOR SKILLED PROGRAM .............||"<<endl;
        cout<<"\t\t\t-----------------------------------------------------------------\n\n"<<endl;
        cout<<"\t\t\t____________________________________________________\n"<<endl;
        cout<<"\t\t\t...................WELCOME TO YOU .................."<<endl;
        cout<<"\t\t\t____________________________________________________\n\n"<<endl;
        cout<<"\t\t\t.Enter your choice \n"<<endl;
    }

};
void course::menu()
{

    cout<<"\t\t\t 1> View courses."<<endl;
    cout<<"\t\t\t 2> Trending course ."<<endl;
    cout<<"\t\t\t 3> services for query related program."<<endl;
    cout<<"\t\t\t 4> To get Enroll yourself."<<endl;
    cout<<"\t\t\t 5> Exit."<<endl;


    int n;
    cout<<"Enter the choice"<<endl;
    cin>>n;

    switch(n)
    {

    case 1:
    {
        system("cls");
        viewcourse();
        break;
    }
    case 2:
    {
        system("cls");
        trending();
        break;


    }
    case 3 :
    {
        system("cls");
        service();
        break;
    }
    case 4:
    {
         system("cls");
        registration();
    }
    break;
    case 5 :
        {
            system("cls");
            cout<<"\n\n\n\t\tEnter Any key to exit from program"<<endl;
        }
    break;
    default:
    {
        system("cls");

        cout<<"You have entered wrong input "<<endl;
        cout<<"Please try again "<<endl;
        menu();
    }
    }
}
void course::viewcourse()
{
    cout<<"\t \t||...........COURSES AVAILABLE..........||"<<endl;
    cout<<"\t \t.1.Programing Language"<<endl;
    cout<<"\t \t.2.English "<<endl;
    cout<<"\t \t.3.Analytical Skills"<<endl;
    cout<<"\t \t.4.To go back previous menu "<<endl;
    cout<<" \n \t \t  Enter the choice "<<endl;
    int c;
    cin>>c;
    if (c==1)
    {
        programming();

    }
    else if (c==2)
    {

        english();

    }
    else if ( c==3)
    {

        anal_skills();

    }


    if (c==4)
    {
        menu();

    }

}
void course::programming()
{
    cout<<"\t\t a) C++ "<<endl;
    cout<<"\t\t b) Python"<<endl;
    cout<<"\t\t c) Java script"<<endl;
    cout<<"\t\t d) C language"<<endl;
    cout<<"\t\t e) PHP "<<endl;
    cout<<"\t\t f) Programing Language"<<endl;
    cout<<"\t\t g) SQL"<<endl;
    int d;
    cout<<"Enter 0 for previous phase "<<endl;
    cin>>d;
    if (d==0)
    {
        system("cls");
        viewcourse();
    }

}
void course::english()
{
    cout<<"\t\tSpoken English"<<endl;
    cout<<"\t\tLiterature"<<endl;
    cout<<"\t\tEnglish Academic for 10th class"<<endl;
    cout<<"\t\tEnglish Academic for 11th class"<<endl;
    cout<<"\t\tEnglish Academic for 12th class"<<endl;
    int i;
    cout<<"Enter 5 to go back"<<endl;
    cin>>i;
    if (i==5)
    {
        viewcourse();
    }
    else
    {
        cout<<"you entered wrong input "<<endl;
        cout<<"Sorry Next time ";
    }
}
void course::anal_skills()
{
    cout<<"\t\t\t|............Analytical skills...........| "<<endl;
    cout<<"\t\tQuantitative Aptitude "<<endl;
    cout<<"\t\tReasoning "<<endl;
    cout<<"\t\t"<<endl;
    cout<<"Enter 5 to go back"<<endl;
    int i;
    cin>>i;
    if (i==5)
    {
        viewcourse();
    }
}
void course::trending()
{
    cout<<"\t\t C++ "<<endl;
    cout<<"\t\tPython"<<endl;
    cout<<"\t\tSpoken English "<<endl;
}
void course::service()
{
    cout<<"\t\t............. Welcome to 24 by 7 Helping Services .................\n\n"<<endl;
    cout<<"\t\t           CALL 8299690199 to immediate service\n"<<endl;
    cout<<"\t\t           WHATSAPP me your query 8789565237\n"<<endl;
    cout<<"\t\t           EMAIL me sgautamkumar71@gmail.com\n"<<endl;
    cout<<"\t\tEnter 5 to go back"<<endl;
    int n;
    cin>>n;
    if (n==5)
    {
    system("cls");
    viewcourse();
    }
    else{

    }

}
void course::registration()
{
    cout<<"\t\tEnter your name"<<endl;
    cin>>name;
    cout<<"\t\tEnter your last qualification"<<endl;
    cin>>clas;
    cout<<"\t\tEnter your Email ID"<<endl;
    cin>>email;
    cout<<"\t\tEnter your Mobile number "<<endl;
    cin>>mob;
    int i;
    cout<<"To go back enter anynumber[1-10]     "<<endl;
    cin>>i;
    if(i==0)
    {
        menu();
    }
    else
    {
        menu();
    }

}
void course::display()
{
    cout<<"\t\t  Name   :   "<<name<<endl;
    cout<<"\t\t  Class  :   "<<clas<<endl;
    cout<<"\t\t  Email ID : "<<email<<endl;
    cout<<"\t\t  Contact No. : "<<mob<<endl;
}
int main()
{
    course obj;
    ofstream fout;
    fout.open("PROJECT.txt",ios::out | ios::app);
    fout.write((char*)&obj,sizeof(obj));
    obj.menu();
    obj.registration();
    fout.close();
    ifstream fin;
    fin.open("PROJECT.txt",ios::in);
    fin.read((char*)&obj,sizeof(obj));
    obj.display();
    fin.close();
    

    return 0;

}
