Inheritance

Aim:To understand and implement various types of inheritance in C++ .

Theory:
Inheritance is a key feature of object-oriented programming (OOP) that allows a new class (derived class) to inherit properties and behaviors (methods) from an existing class (base class). This promotes code reusability and establishes a natural hierarchy between classes.

Key Concepts
1.Base Class: The class whose properties and methods are inherited.
2.Derived Class: The class that inherits from the base class.
3.Access Specifiers: Control the access level of the base class members in the derived class. These include:
4.public: Members are accessible from outside the class.
5.protected: Members are accessible within the class and by derived classes.
6.private: Members are accessible only within the class.
Types of Inheritance
1.Single Inheritance: A derived class inherits from a single base class.
#include<iostream>
#include<string>
using namespace std;

class Uni {
    public:
    string university="Symbiosis International University: ";
    void discipline()
    {
        cout<<"Engineering"<<endl;
    }
};
class Department: public 
    Uni 
    {
    public:
    string dept="Electronics & Communication";
    };

int main(){
    Department a1;
    a1.discipline();
    cout<<a1.university+" "+a1.dept;
}
2.Multiple Inheritance: A derived class inherits from more than one base class.
#include<iostream>
#include<string>
using namespace std;

//Parent Class-1
class Vehicle 
{
    public:
    string company="Ford";
    void type()
    {
        cout<<"Mustang"<<endl;
    }
};
//Parent Class-2
class Specs 
{
    public:
    string mileage="8 kmpl";
    void colour()
    {
        cout<<"Grey and Black"<<endl;
    }
};
//Child Class-1 (derived from parent-1&2)
class Car: public Vehicle, public Specs 
{
    public:
    string seater="4 seater";
};

int main()
{
    //Multiple Inheritance
    Car f1;
    f1.colour();
    cout<<f1.company<<" ";
    f1.type();
    cout<<"("<<f1.seater<<")"<<endl<<"MILEAGE: "<<f1.mileage<<endl;
}
3.Multilevel Inheritance: A class is derived from another derived class.
#include<iostream>
#include<string>
using namespace std;

//Parent Class-1
class Food 
{
    public:
    string cuisine="Indian";
    void type()
    {
        cout<<"Asian"<<endl;
    }
};
//Child Class-1 (derived from parent-1)
class Dish: public Food 
{
    public:
    string dish="Biryani";
};
//Child Class-2 (derived from child-1)
class Restaurant: public Dish 
{
    public:
    string name="Spice Kitchen";
};

int main()
{
    //Multilevel Inheritance
    Restaurant f3;
    f3.type();
    cout<<f3.cuisine<<": "<<f3.dish<<endl;
    cout<<"Restaurant: "<<f3.name;
}
4.Hierarchical Inheritance: Multiple classes are derived from a single base class.
#include<iostream>
#include<string>
using namespace std;

//Parent Class-1
class Jeans 
{
    public:
    string type[3]= {"Bootcut", "Wide Leg", "Skinny"};
    void brand()
    {
        cout<<"H&M - &Denim"<<endl;
    }
};
//Child Class-1
class Bootcut: public Jeans 
{
    public:
    string color="Dark Blue";
};
//Child Class-2
class WL: public Jeans 
{
    public:
    string color="Black";
};
//Child Class-3
class Skinny: public Jeans 
{
    public:
    string color="Grey";
};

//Hierarchical Inheritance
int main()
{
    Bootcut j1;
    cout<<endl;
    j1.brand();
    cout<<j1.type[0]<<": "<<j1.color<<endl;

    WL j2;
    cout<<endl;
    j2.brand();
    cout<<j2.type[1]<<": "<<j2.color<<endl;

    Skinny j3;
    cout<<endl;
    j3.brand();
    cout<<j3.type[2]<<": "<<j3.color<<endl;
}
5.Hybrid Inheritance: A combination of two or more types of inheritance.

Algorithm:
1.Single Inheritance
.Class Definition: Uni
Define a class Uni with a public string variable university, initialized to "Symbiosis International University: ".
Define a public method discipline() that prints "Engineering".
.Class Definition: Department
Define a class Department that inherits publicly from the Uni class.
In this class, define a public string variable dept, initialized to "Electronics & Communication".
.Main Function:
Create an object a1 of the class Department.
Call the method discipline() using the object a1, which will print "Engineering".
Access the university string variable from the Uni class using the a1 object and concatenate it with the dept variable from the Department class.
Print the concatenated result, which will output: "Symbiosis International University: Electronics & Communication".
2.Multiple Inheritance
.Class Definition: Vehicle
Define a class Vehicle with:
A public string variable company, initialized to "Ford".
A public method type() that prints "Mustang".
.Class Definition: Specs
Define a class Specs with:
A public string variable mileage, initialized to "8 kmpl".
A public method colour() that prints "Grey and Black".
.Class Definition: Car (Child Class)
Define a class Car that inherits publicly from both Vehicle and Specs (demonstrating multiple inheritance).
In this class, define a public string variable seater, initialized to "4 seater".
.Main Function:
Create an object f1 of the class Car.
Call the colour() method using the object f1, which prints "Grey and Black".
Access and print the company string variable from the Vehicle class using the f1 object, which will output "Ford".
Call the type() method from the Vehicle class, which prints "Mustang".
Access and print the seater string variable from the Car class, concatenating it in the form "(4 seater)".
Access and print the mileage string variable from the Specs class, which outputs "MILEAGE: 8 kmpl".
About
No description, website, or topics provided.
Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 1 watching
Forks
 0 forks
Report repository
Releases
No releases published
Packages
No packages published
Languages
C++
100.0%
Footer
