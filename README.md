# Experiment 12
## Aim :
To study and implement Constructors and Destructors

## Software :
Vs code

## Theory :
Constructors :
Constructors are unique member functions of a class that are automatically called when an object of the class is created.
The object’s data members are initialized. Resources may also be allocated when required.

There are some key points about costructors which are:

The name of the constructor is same as its class name.
Constructors do not have a return type.
Constructors are mostly declared in the public section of the class.
Multiple constructors can be defined with different parameters, this is known as overloading.

There are mainly 3 types of constructors. They are:
Default Constructor:
A constructor which takes no arguments. It is also called a zero-argument constructor as it has no parameters.

### Parameterized Constructor:
A constructor that takes parameters, allowing the object to be initialized with specific values.

### Copy Constructor:
A constructor that initializes an object using another object of the same class. It is used for deep copying and when passing objects by value.


### Deconstructors -
A destructor is also a special member function like a constructor.

Destructor destroys the class objects created by the constructor.
Destructor has the same name as their class name preceded by a tilde (~) symbol.
It is not possible to define more than one destructor.
The destructor is only one way to destroy the object created by the constructor.
Destructor neither requires any argument nor returns any value.
It is automatically called when an object goes out of scope.
Destructor release memory space occupied by the objects created by the constructor.
### Codes :
~~~
1.
//soham
//23070123084
//entc-B1
//experiment-12
// defining constructor inside the class
#include <iostream>
using namespace std;
class student
{
    int rollno;
    char name[50];
    double fee;
    public:
    student()
    {
        cout<<"Enter the roll number : ";
        cin>>rollno;
        cout<<"Enter the name: ";
        cin>>name;
        cout<<"Enter the fee: ";
        cin>>fee;
    }
    void display()
    {
        cout<<endl<<rollno<<"\t"<<name<<"\t"<<fee<<endl;
    }
};

int main(){
    student s;
    s.display();
    return 0;
}
~~~
2.
~~~
//soham
//23070123084
//entc-B1
//experiment-12A
#include <iostream>
using namespace std;
//defining the constructor outside the class
class student
{
    int rn;
    char name[50];
    float fee;
    public:
    student();
    void display();
};
student::student()
{
    cout<<"Enter the name: ";
    cin>>name;
    cout<<"Enter the roll no.: ";
    cin>>rn;
    cout<<"Enter the fee: ";
    cin>>fee;
}
void student::display()
{
    cout<<endl;
    cout<<"Name: "<<name<<endl;
    cout<<"Roll No: "<<rn<<endl;
    cout<<"Fee: "<<fee<<endl;
}
int main()
{
    student s1;
    s1.display();
}
~~~
3.
~~~
//soham
//23070123084
//entc-B1
//experiment 12B
// Default Constructors
#include<iostream>
#include<string>
using namespace std;

class Data {
    string name;
    int roll_no;
    char dept[50];
    int batch;

public:
    Data() {
        cout << "Name: ";
        cin >> name;
        cout << "Roll Number: ";
        cin >> roll_no;
        cout << "Department: ";
        cin >> dept;
        cout << "Batch: ";
        cin >> batch;
    }

    void display() {
        cout << endl << "DETAILS:" << endl << name << " " << roll_no << " " << dept << " " << batch << endl;
    }
};

int main() {
    Data d1;
    d1.display();
}
~~~
4.
~~~
//soham
//23070123084
//entc-B1
//experiment-12C
//parameterized constructor
#include<iostream>
using namespace std;
// Defining parameterized constructor
class Num {
    // int a=7, b=9;
public:
    Num(int c, int d) {
        if (c > d) {
            cout << c << " is greater"<<endl;
        } else {
            cout << d << " is greater"<<endl;
        }
    }
};

int main() {
    Num n1(4, 3);
}
~~~
5.
~~~
//soham
//23070123084
//entc-B1
//experiment-12D
#include<iostream>
#include<string.h>
using namespace std;

class student {
    int rno;
    char name[50];
    double fee;

public:
    student(int, char[], double);
    student(student &t) // copy constructor
    {
        rno = t.rno;
        strcpy(name, t.name);
        fee = t.fee;
    }
    void display();
};

student::student(int no, char n[], double f) {
    rno = no;
    strcpy(name, n);
    fee = f;
}

void student::display() {
    cout << endl << rno << "\t" << name << "\t" << fee<<endl;
}

int main() {
    student s(084, "soham", 999999);
    s.display();

    student subham(s); // copy constructor called
    subham.display();

    return 0;
}
~~~
6.
~~~
//soham
//23070123084
//entc-B1
//experiment-12E
#include<iostream>
using namespace std;
int count = 0;
class destruct {
public:
    destruct() {
        ::count++;
        cout << "No. of objects created: " << ::count << endl;
    }

    ~destruct() {
        ::count--;
        cout << "No. of objects destroyed: " << ::count << endl;
    }
};

int main() {
    destruct aa, bb, cc;
    {
        destruct dd;
    }
    return 0;
}
~~~
## Outputs :
1.
![image](https://github.com/user-attachments/assets/1489aab1-62e7-4034-a7fc-4f3108f312a1)


2.
![image](https://github.com/user-attachments/assets/07464d9f-70f8-479c-9284-43161fb21788)


3.
![image](https://github.com/user-attachments/assets/3a5d5e1a-0f08-4559-be49-5dc7854896ed)


4.
![image](https://github.com/user-attachments/assets/80f4da14-df48-4bc4-a244-0188cfc68c3d)


5.
Screenshot 2024-09-04 102120

6.
Screenshot 2024-09-04 102133

## Conclusion :
We learnt about constructors and deconstructors in C++.

We learnt the use case of each of them in C++.
