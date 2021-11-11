//Creates File Search Engine which can Find,Replace or delete any word(Substring)from the entire String of characters. 

#include<iostream>
#include<fstream>
#include<stdlib.h>
#include<cctype>
#include<string>
#include<algorithm> 
#include <functional>
using namespace std;
using std::search; 
using std::count; 
using std::string;
class SearchFile                          
{
    public:
    string name;
    int n,choice2;
    char choice3,c,l,cont,store;
    
   string input();
   void SearchWord();
   void MainMenu();
   void findAndReplace(string search, string replaceStr);
   void eraseString(string & mainStr, const string & toErase);
   void Update();
};

int main()                   //Main Function
{
    SearchFile s1;
    char ans;
    char ch,R,k;
    string x;
    int i,choice1;
        do{
        cout << endl << endl<< endl;
        cout << "             WELCOME TO SEARCH FILE ENGINE" << endl;              //Main menu screen for the user to choose either to create a new file or write in an existing file
        cout << "      -----------------------------------------" << endl;

        cout << "             1: Create a New File and Write" << endl;
        cout << "             2: Write in the existing File" << endl;
        cout << "             3: Exit                      " << endl;
        cout << endl<<endl;
        cout << "What would you like to do?" << endl;
        cin >> choice1;
    if (choice1 == 1)
    {
        ofstream ofs("Search.txt",ios::trunc);
        x = s1.input();
        ofs<<x;
        s1.MainMenu();
        break;
    }

   else if (choice1 == 2)
    {
        ofstream ofs("Search.txt",ios::app);
        x = s1.input();
        ofs<<x;
        s1.MainMenu();
        break;
    }
     
     else if(choice1 == 3)
     {
         break;
     }
     else
     {
          cout<<"Enter the correct choice!Press R to return or any key to exit.";
            cin>>R;
            k=R;
     }
}while(k=='R');
     return 0;
}

string SearchFile::input()
    {
        cout<<"Enter your data in the file:";
        cin.ignore();
        getline(cin, name);
        return name;
    }
void SearchFile::SearchWord()
    {
        string str;
        cout<<"Enter to find the string";
        cin.ignore();
        getline(cin,str);
        string::const_iterator it;
        it = search(name.begin(), name.end(), 
                str.begin(), str.end());

       if (it != name.end())
       cout<<"found";

       else
       cout<<"not found";
    }
void SearchFile::MainMenu()
    {
        do{
        cout << endl << endl<< endl;
        cout << "             WELCOME TO SEARCH FILE ENGINE" << endl;
        cout << "      -----------------------------------------" << endl;
        cout << "             1: Update a File:" << endl;
        cout << "             2: Search any word within a File" << endl;
        cout << "             3: Delete a File" << endl;
        cout << "             4: Display the file" << endl;
        cout << "             5: Return to main menu" << endl;
        cin>>choice2;
         if (choice2 == 1)
         {
            Update();
         }
         else if (choice2 == 2)
         {
             char ans2,m,l;
            SearchWord();
            do
            {
            cout<<"\n  Do you want to update the searched word?y/n?";    
            cin>>ans2;
            m = toupper(ans2);
            if(m == 'Y')
            {
                Update();
            }
            else if(m == 'N')
            {
                break;
            }
            else
            {
                cout<<"Wrong choice!Enter y/n if you want to try again!";
                cin>>l;
            }
            }while(tolower(l) == 'y');
         }
         else if (choice2 == 3)
         {
             int status;
                char file[20];
                cout << "Enter the Name of File: ";
                cin >> file;
                status = remove(file);
                if (status == 0)
                        cout << "\nFile Deleted Successfully!";
                else
                        cout << "\nError Occurred!";
                cout << endl;
         }
         else if (choice2 == 4)
         {
            ifstream infile;
            infile.open("Search.txt",ios::in);
            infile>>name;
            cout<<name;
            if(!infile)
             {
             cout<<"\nFile cannot be opened\n";
             }
            if(infile.eof())
             {
             cout<<"End of file is reached!";
             infile.close();
             }
             break;
         }
         else if (choice2 == 5)
         {
             MainMenu();
         }
         else
         {
             cout<<"Enter the correct choice!Do you want to continue?Y/N?\n";
             cin>>cont;
         }
        }while(toupper(cont) == 'Y');
    }
void SearchFile::findAndReplace(string search, string replaceStr)
    {
       while(name.find(search) != string::npos) {
        name.replace(name.find(search), search.size(), replaceStr);
       }
    }
    
void SearchFile::eraseString(string & mainStr, const string & toErase)
{
    size_t pos = string::npos;
    while ((pos  = mainStr.find(toErase) )!= string::npos)
    {
        mainStr.erase(pos, toErase.length());
    }
}

void SearchFile::Update()
     {
              do
             {
             cout<<"\nA.Replace any words \nB.Delete any word\n\n";
             cin>>choice3;
             c = toupper(choice3);
             if(c == 'A')
             {
                 string str1,str2;
                 cout<<"Enter the string you want to Replace:\n";
                 cin>>str1;
                 cout<<"Enter the new string: \n";
                 cin>>str2;
                 findAndReplace(str1, str2);
                 cout<<"Updated data:\n" << name << endl;
             }
             else if(c == 'B')
             {
                 string str3;
                 cout<<"Enter the string you want to delete \n";
                 cin>>str3;
                 eraseString(name, str3);
                 cout << name << endl;
             }
             else
             {
                 cout<<"Enter the correct choice.Press R to return or any key to exit.";
                 char r,store;
                 cin>>r;
                 store = r;
             }
            }while(toupper(store) == 'R');
     }
