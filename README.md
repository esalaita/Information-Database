# Personal-Information-Database

Developed a C++ program that demonstrates the usage of a personType class, managing and displaying personal information
Utilized the standard input and output libraries (iostream) and included the personType class definition from an external header file
Implemented the main function,  creating an instance of the personType class, initialized with first, middle, and last names
Displayed the full name of the student using the print method
Defined set methods, setting the first name, middle name, and last name individually
Defined get methods, retrieving the first name, middle name, and last name


#include <iostream>
#include "personType.h"
using namespace std;

int main()
{ 
    personType student("Mary", "Beth", "Regan");

    student.print();
    cout<<endl;

    if (student.isLastName("Robin"))
        cout<<"Student\'s last name is Regan"<<endl;
    else
        cout<<"Student\'s last name is not Regan"<<endl;
  
     if (student.isFirstName("Mary"))
        cout<<"Student\'s first name is Mary"<<endl;
    else
        cout<<"Student\'s first name is not Mary"<<endl;

    return 0;
}



 
#include <string> 
using namespace std;

class personType
{
public:
    void print() const;
    void setName(string first, string middle, string last);
	void setLastName(string last);
	void setFirstName(string first);
	void setMiddleName(string middle);

	bool isLastName(string last) const;
	bool isFirstName(string first) const;

    string getFirstName() const;
	string getMiddleName() const;
	string getLastName() const;

    personType(string first = "", string middle = "", string last = "");

private:
    string firstName; 
    string middleName; 
    string lastName;  
};
 


#include <iostream> 
#include <string>
#include "personType.h"

using namespace std;

void personType::print() const
{
    cout << firstName << " " << middleName << " " << lastName;
}

void personType::setName(string first, string middle, string last)
{
    firstName = first;
    middleName = middle;
    lastName = last;
}

void personType::setLastName(string last)
{
    lastName = last;
}

void personType::setFirstName(string first)
{
    firstName = first;
}

void personType::setMiddleName(string middle)
{
    middleName = middle;
}

bool personType::isLastName(string last) const
{
    return (lastName == last);
}

bool personType::isFirstName(string first) const
{
    return (firstName == first);
}

string personType::getFirstName() const
{
    return firstName;
}

string personType::getMiddleName() const
{
    return middleName;
}

string personType::getLastName() const
{
    return lastName;
}


//constructor 
personType::personType(string first, string middle, string last) 

{ 
    firstName = first;
    middleName = middle;
    lastName = last;
}
