# C++

## Compiling 

~~~cpp
g++ main.cpp -o main // compile
./main               // run
~~~

## Syntax

~~~cpp
/* Ex.: 1 */
#include <iostream>   // header file library - lets us work with input and output objects, ex: cout.
using namespace std;  // use names for objects and variables from the standard library.

int main() {
  cout << "Ola\n";    // cout is an object. << is the insert operator.
  return 0;
} 

/* Ex.: 2 */
#include <iostream>

int main() {
  std::cout << "Ola"; // The using namespace std line can be omitted and replaced with the std keyword, followed by the :: operator for some objects
  return 0;
}

/* Ex.: 3 */
/* The using namespace std line can be omitted and replaced with the std keyword, 
followed by the :: operator for string (and cout) objects */
#include <iostream>
#include <string>

int main() {
  std::string greeting = "Hello";
  std::cout << greeting;
  return 0;
} 
~~~

## Comments

~~~cpp
// This is a comment
/* This is a multi-line comment */
~~~

## Data Types

### Basic Data Types

- int - 4 bytes - stores integers (whole numbers), without decimals.
- float - 4 bytes - Stores fractional numbers, containing one or more decimals. Sufficient for storing 7 decimal digits.
- double - 8 bytes - Stores fractional numbers, containing one or more decimals. Sufficient for storing 15 decimal digits.
- char - 1 byte - Stores a single character/letter/number, or ASCII values.
- bool - 1 byte - Stores true (1) or false (0) values.
- string - stores text, such as "Hello World". String values are surrounded by double quotes
- ...

### Derived Data Types

- Array
- Structure
- Union
- Enum
- Pointer
- ...

## Modifiers

- short
- long
- signed
- unsigned
- ...

## Variables

~~~cpp
int myInt = 10;
double myFloat = 9.99;
char myLetter = 'a';         
string myText = "Hello";     
bool myBoolean = true;   
float f1 = 35e3;  // Scientific Numbers - power of 10
double d1 = 12E4;
int x = 5, y = 6, z = 50;  // declare many variables
~~~

## Casting

~~~cpp

~~~

## Constants

~~~cpp
const int myNum = 15; // myNum will always be 15
myNum = 10;           // error: assignment of read-only variable 'myNum'
~~~

## Operators

- Arithmetic operators: + - * / % ++ -- 
  - C++ uses the + operator for both addition and concatenation.
- Assignment operators: = += -= *= /= %= &= |= ^= >>= <<=
- Comparison operators: == != > < >= <=
  - The return value of a comparison is either true (1) or false (0).
- Logical operators: && || !
- Bitwise operators: & | ^ << >> ~

- << insertion operator 
- \>\> extraction operator
- :: scope resolution operator

## Strings

- To use strings, you must include an additional header file in the source code, the <string> library.
- A string in C++ is actually an object, which contain functions that can perform certain operations on strings.
- If you try to add a number to a string, an error occurs.

~~~c++
string greeting = "Hello";
greeting = "Hello " + name;                   // concatenate
string fullName = firstName.append(lastName); // append function - concatenate - its faster than '+'
int size = txt.length();                      // lib string
int size = txt.size();                        // size is an alias of length
char c = txt[0];                              // first character of the string
txt[0] = 'B';                                 // change string characters
~~~

## Math 

~~~c++
maxValue = max(var1, var2); // find the highest value - int, float, double
minValue = min(var1, var2); // find the lowest value - int, float, double

// library - #include <cmath>
var = abs(x)          // Returns the absolute value of x
var = acos(x)         // Returns the arccosine of x
var = asin(x)         // Returns the arcsine of x
var = atan(x)         // Returns the arctangent of x
var = cbrt(x)         // Returns the cube root of x
var = ceil(x)         // Returns the value of x rounded up to its nearest integer
var = cos(x)          // Returns the cosine of x
var = cosh(x)         // Returns the hyperbolic cosine of x
var = exp(x)          // Returns the value of Ex
var = expm1(x)        // Returns ex -1
var = fabs(x)         // Returns the absolute value of a floating x
var = fdim(x, y)      // Returns the positive difference between x and y
var = floor(x)        // Returns the value of x rounded down to its nearest integer
var = hypot(x, y)     // Returns sqrt(x2 +y2) without intermediate overflow or underflow
var = fma(x, y, z)    // Returns x*y+z without losing precision
var = fmax(x, y)      // Returns the highest value of a floating x and y
var = fmin(x, y)      // Returns the lowest value of a floating x and y
var = fmod(x, y)      // Returns the floating point remainder of x/y
var = log(1);         // returns 0
var = pow(x, y)       // Returns the value of x to the power of y
var = round(2.6);     // returns 3
var = sin(x)          // Returns the sine of x (x is in radians)
var = sinh(x)         // Returns the hyperbolic sine of a double value
var = sqrt(64);       // returns 8
var = tan(x)          // Returns the tangent of an angle
var = tanh(x)         // Returns the hyperbolic tangent of a double value
~~~

## Date

~~~cpp

~~~

## Booleans

~~~cpp
  bool isCodingFun = true;
  bool itsRaining = false;
  cout << isCodingFun << endl; 
  cout << itsRaining << endl;  
~~~

## If...Else

~~~cpp
int time = 20;
if (time < 18) {
  cout << "Good day.";
} else {
  cout << "Good evening.";
}
~~~

## Conditional Operator 

~~~cpp
string result = (time < 18) ? "Good day." : "Good evening.";
~~~

## Switch

~~~cpp
int day = 4;
switch (day) {
  case 1:
    cout << "Monday";
    break;
  case 2:
    cout << "Tuesday";
    break;
  case 3:
    cout << "Wednesday";
    break;
  case 4:
    cout << "Thursday";
    break;
  case 5:
    cout << "Friday";
    break;
  case 6:
    cout << "Saturday";
    break;
  case 7:
    cout << "Sunday";
    break;
}
~~~

## While Loop

~~~cpp
int i = 0;
while (i < 5) {
  cout << i << "\n";
  i++;
}
~~~

## Do...While Loop

~~~cpp
int i = 0;
do {
  cout << i << "\n";
  i++;
}
while (i < 5);
~~~

## For Loop

~~~cpp
for (int i = 0; i < 5; i++) {
  cout << i << "\n";
}
~~~

## Break

- When C++ reaches a break keyword, it breaks out of the block.
- The break statement can also be used to jump out of a loop.

~~~cpp
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    break;
  }
  cout << i << "\n";
}
~~~

## Continue

- The continue statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.

~~~cpp
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    continue;
  }
  cout << i << "\n";
} 
~~~

## Arrays

~~~cpp
int myNum[3] = {10, 20, 30};

cout << myNum << endl; 
cout << myNum[0] << endl;
myNum[2] = 40;
~~~

#### Ex.: arrays - loop in array

~~~cpp
string cars[4] = {"Volvo", "BMW", "Ford", "Mazda"};
for(int i = 0; i < 4; i++) {
  cout << i << ": " << cars[i] << "\n";
~~~

## Pointers

- A pointer is a variable that stores the memory address as its value. 
- The type of the pointer has to match the type of the variable you're working with.
- & reference operator: get the memory address of a variable.
- * dereference operator: get the value of the variable.

#### Ex.: pointers

~~~cpp
cout << ptr << endl;  // mem address
cout << *ptr << endl; // 10
*ptr = 20; //change the value of the pointer
cout << *ptr << endl; // 20
~~~

## Functions

- A function is a block of code which only runs when it is called.
- To call a function, write the function's name followed by two parentheses () and a semicolon ;
- A C++ function consist of two parts:
  - Declaration: the function's name, return type, and parameters (if any)
  - Definition: the body of the function (code to be executed)
- It is possible to separate the declaration and the definition of the function - for code optimization - Ex2.
- The void keyword indicates that the function should not return a value.
- The return keyword indicates that the function should return a value. Use a data type instead of void.

#### Ex.: functions - void function

~~~cpp
#include <iostream>

using namespace std;

void myFunction() { // declaration
  cout << "I just got executed!"; // definition
}

int main() {
  myFunction(); // call the function
  return 0;
}
~~~

#### Ex.: functions - int function

~~~cpp
#include <iostream>

using namespace std;

int mySum(int x, int y) {
  return x + y;
}

int main() {
  cout << mySum(2, 3) << endl;
  return 0;
}
~~~

#### Ex.: functions - separate the declaration and the definition of the function 

~~~cpp
#include <iostream>

using namespace std;

void myFunction();

int main() {
  myFunction();  // call the function
  return 0;
}

void myFunction() {
  cout << "I just got executed!";
}
~~~

### Function Parameters

- Parameters act as variables inside the function.
- When a parameter is passed to the function, it is called an argument.


#### Ex: function parameters

- fname is a parameter, while Liam and Jenny are arguments.

~~~cpp
#include <iostream>

using namespace std;

void myFunction(string fname) {
  cout << "Hi " << fname << "\n";
}

int main() {
  myFunction("Liam");
  myFunction("Jenny");
  return 0;
}
~~~

#### Ex.: parameters - default parameter value

- A parameter with a default value, is often known as an "optional parameter". 

~~~c++
#include <iostream>

using namespace std;

void myFunction(string country = "empty") {
  cout << country << "\n";
}

int main() {
  myFunction();
  myFunction("Brasil");
  return 0;
}
~~~

#### Ex.: pass by reference

~~~cpp
#include <iostream>

using namespace std;

void swapNums(int &x, int &y) {
  int z = x;
  x = y;
  y = z;
}

int main() {
  int x = 2, y = 3;
  swapNums(x, y);
  cout << "x, y = " << x << ", " << y << endl;
  return 0;
}
~~~

### Function Overloading

- Instead of defining two functions that should do the same thing, it is better to overload one. 
- Multiple functions can have the same name as long as the number and/or type of parameters are different.

~~~cpp
#include <iostream>
using namespace std;

int plusFunc(int x, int y) {
  return x + y;
}

double plusFunc(double x, double y) {
  return x + y;
}

int main() {
  int numI = plusFunc(2, 3);
  double numF = plusFunc(2.1, 3.4); 
  
  cout << numI << endl;
  cout << numF << endl;
  
  return 0;
}
~~~

## Scope

## Recursion

~~~cpp

~~~

## Structures 

~~~cpp

~~~

## Lists

~~~cpp

~~~

## Tuples

~~~cpp

~~~

## Sets

~~~cpp

~~~

## Dictionaries

~~~cpp

~~~

## Trees

~~~cpp

~~~

## Hash Tables

~~~cpp

~~~

## Graphs

~~~cpp

~~~

## OOP - Object-Oriented Programming

- Object-oriented programming is about creating objects that contain both data and functions.
- OOP makes it possible to create full reusable applications with less code and shorter development time.
- So, a class is a template for objects, and an object is an instance of a class.
- When the individual objects are created, they inherit all the variables and functions from the class.

> The "Don't Repeat Yourself" (DRY) principle is about reducing the repetition of code. You should extract out the codes that are common for the application, and place them at a single place and reuse them instead of repeating it.

### Classes/Objects

- Classes and objects are the two main aspects of object-oriented programming.
- Class: Fruit -> Objects: Apple, Banana, Orange
- Class: Car -> Objects: Volvo, Audi, Toyota

### Class Attributes

- Attributes and methods are basically variables and functions that belongs to the class.
- These are often referred to as "class members".
- A class is a user-defined data type that we can use in our program, and it works as an object constructor, or a "blueprint" for creating objects.

#### Ex.: create a class and a object with atributes

~~~cpp
#include <iostream>
#include <string>
using namespace std;

class MyClass {       // The class
  public:             // Access specifier
    int myNum;        // Attribute (int variable)
    string myString;  // Attribute (string variable)
};

int main() {
  MyClass myObj;  // Create an object of MyClass

  // Access attributes and set values
  myObj.myNum = 15;
  myObj.myString = "Some text";

  // Print values
  cout << myObj.myNum << "\n"; 
  cout << myObj.myString << "\n"; 
  return 0;
}
~~~

### Class Methods

- Methods are functions that belongs to the class.
- There are two ways to define functions that belongs to a class:
  - Inside class definition
  - Outside class definition

#### Ex.: class methods - inside class definition

~~~cpp
#include <iostream>
using namespace std;

class MyClass {         // The class
  public:               // Access specifier
    void myMethod() {   // Method/function
      cout << "Hello World!\n";
    }
};

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}
~~~

#### Ex.: class methods - outside class definition

~~~cpp
#include <iostream>
using namespace std;

class MyClass {         // The class
  public:               // Access specifier
    void myMethod();    // Method/function declaration
};

// Method/function definition outside the class
void MyClass::myMethod() {
  cout << "Hello World!\n";
}

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}
~~~

#### Ex.: class methods - outside class definition - parameters

~~~cpp
#include <iostream>
using namespace std;

class Car {
  public:
    int speed(int maxSpeed);
};

int Car::speed(int maxSpeed) {
  return maxSpeed;
}

int main() {
  Car myObj;
  cout << myObj.speed(200) << endl;
  return 0;
}
~~~

### Constructors

- A constructor in C++ is a special method that is automatically called when an object of a class is created.
- The constructor has the same name as the class, it is always public, and it does not have any return value.
- Constructors can also take parameters (just like regular functions), which can be useful for setting initial values for attributes.

#### Ex.: constructors

~~~cpp
#include <iostream>
using namespace std;

class Car {        // The class
  public:          // Access specifier
    string brand;  // Attribute
    string model;  // Attribute
    int year;      // Attribute
    Car(string x, string y, int z) {  // Constructor with parameters
      brand = x;
      model = y;
      year = z;
    }
};

int main() {
  // Create Car objects and call the constructor with different values
  Car carObj1("BMW", "X5", 1999);
  Car carObj2("Ford", "Mustang", 1969);

  // Print values
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";
  return 0;
}
~~~

#### Ex.: constructors - defined outside the class

~~~cpp
#include <iostream>
using namespace std;

class Car {        // The class
  public:          // Access specifier
    string brand;  // Attribute
    string model;  // Attribute
    int year;      // Attribute
    Car(string x, string y, int z); // Constructor declaration
};

// Constructor definition outside the class
Car::Car(string x, string y, int z) {
  brand = x;
  model = y;
  year = z;
}

int main() {
  // Create Car objects and call the constructor with different values
  Car carObj1("BMW", "X5", 1999);
  Car carObj2("Ford", "Mustang", 1969);

  // Print values
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";
  return 0;
}
~~~

### Access Specifiers/Modifiers

- Access specifiers define how the members (attributes and methods) of a class can be accessed.
- In C++, there are three access specifiers:
  - public - members are accessible from outside the class
  - private - members cannot be accessed (or viewed) from outside the class
  - protected - members cannot be accessed from outside the class, however, they can be accessed in inherited classes.
- It is considered good practice to declare your class attributes as private (as often as you can). This will reduce the possibility of yourself (or others) to mess up the code. This is also the main ingredient of the Encapsulation concept.

> Note: By default, all members of a class are private if you don't specify an access specifier.

~~~cpp
#include <iostream>
using namespace std;

class MyClass {
  public:    // Public access specifier
    int x;   // Public attribute
  private:   // Private access specifier
    int y;   // Private attribute
};

int main() {
  MyClass myObj;
  myObj.x = 25;  // Allowed (public)
  myObj.y = 50;  // Not allowed (private)
  return 0;
}
~~~

### Encapsulation

- The meaning of Encapsulation, is to make sure that "sensitive" data is hidden from users.
- To achieve this, you must declare class variables/attributes as private (cannot be accessed from outside the class).
- If you want others to read or modify the value of a private member, you can provide public get and set methods.

~~~cpp
#include <iostream>
using namespace std;

class Employee {
  private:
    int salary;

  public:
    void setSalary(int s) {
      salary = s;
    }
    int getSalary() {
      return salary;
    }
};

int main() {
  Employee myObj;
  myObj.setSalary(50000);
  cout << myObj.getSalary() << endl;
  return 0;
}

~~~

### Inheritance

- We group the "inheritance concept" into two categories:
  - derived class (child) - the class that inherits from another class
  - base class (parent) - the class being inherited from
- To inherit from a class, use the : symbol.
- It is useful for code reusability: reuse attributes and methods of an existing class when you create a new class.

~~~cpp
#include <iostream>
#include <string>
using namespace std;

// Base class
class Vehicle {
  public: 
    string brand = "Ford";
    void honk() {
      cout << "Tuut, tuut! \n" ;
    }
};

// Derived class
class Car: public Vehicle {
  public: 
    string model = "Mustang";
};

int main() {
  Car myCar;
  myCar.honk();
  cout << myCar.brand + " " + myCar.model << endl;
  return 0;
}
~~~

#### Ex.: C++ Multilevel Inheritance

- A class can also be derived from one class, which is already derived from another class.

~~~cpp
#include <iostream>
using namespace std;

// Parent class
class MyClass {
  public: 
    void myFunction() {
      cout << "Some content in parent class.\n" ;
    }
};

// Child class
class MyChild: public MyClass {
};

// Grandchild class 
class MyGrandChild: public MyChild {
};

int main() {
  MyGrandChild myObj;
  myObj.myFunction();
  return 0;
}
~~~

#### Ex.: C++ Multiple Inheritance

- A class can also be derived from more than one base class, using a comma-separated list.

~~~cpp
#include <iostream>
using namespace std;

// Base class
class MyClass {
  public:
    void myFunction() {
      cout << "Some content in parent class.\n" ;
    }
};

// Another base class
class MyOtherClass {
  public:
    void myOtherFunction() {
      cout << "Some content in another class.\n" ;
    }
};

// Derived class
class MyChildClass: public MyClass, public MyOtherClass {
};

int main() {
  MyChildClass myObj;
  myObj.myFunction();
  myObj.myOtherFunction();
  return 0;
}
~~~

#### Ex.: C++ Inheritance Access

-  The third specifier, protected, is similar to private, but it can also be accessed in the inherited class.

~~~cpp
#include <iostream>
using namespace std;

// Base class
class Employee  {
  protected:  // Protected access specifier
    int salary;
};

// Derived class
class Programmer: public Employee {
  public:
    int bonus;
    void setSalary(int s) {
      salary = s;
    }
    int getSalary() {
      return salary;
    }
};

int main() {
  Programmer myObj;
  myObj.setSalary(50000);
  myObj.bonus = 15000;
  cout << "Salary: " << myObj.getSalary() << "\n";
  cout << "Bonus: " << myObj.bonus << "\n";
  return 0;
}
~~~

### Polymorphism

- Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.

~~~cpp
#include <iostream>
#include <string>
using namespace std;

// Base class
class Animal {
  public:
    void animalSound() {
      cout << "The animal makes a sound \n" ;
    }
};

// Derived class
class Pig : public Animal {
  public:
    void animalSound() {
      cout << "The pig says: wee wee \n" ;
    }
};

// Derived class
class Dog : public Animal {
  public:
    void animalSound() {
      cout << "The dog says: bow wow \n" ;
    }
};

int main() {
  Animal myAnimal;
  Pig myPig;
  Dog myDog;

  myAnimal.animalSound();
  myPig.animalSound();
  myDog.animalSound();
  return 0;
}
~~~

### Class Method Overloading

~~~cpp

~~~

### Class Method final

~~~cpp

~~~

### Static Methods

~~~cpp

~~~

### Static Variables

~~~cpp

~~~

### Association

~~~cpp

~~~

### Composition

~~~cpp

~~~

### Aggregation

~~~cpp

~~~

### Abstract Classes

~~~cpp

~~~

### Abstract Methods

~~~cpp

~~~

### Interfaces

~~~cpp

~~~

### Collections 

~~~cpp

~~~

### Enums

~~~cpp

~~~

### ArrayLists

~~~cpp

~~~

### LinkedList

~~~cpp

~~~

### Iterator

~~~cpp

~~~

### Generic Classes 

~~~cpp

~~~

### Generic Methods 

~~~cpp

~~~

## Exceptions

- Exception handling in C++ consist of three keywords: try, throw and catch:
  - The try statement allows you to define a block of code to be tested for errors while it is being executed.
  - The throw keyword throws an exception when a problem is detected, which lets us create a custom error. 
  - The catch statement allows you to define a block of code to be executed, if an error occurs in the try block. 

~~~cpp
#include <iostream>
using namespace std;

int main() {
  try {
    int age = 15;
    if (age >= 18) {
      cout << "Access granted - you are old enough.";
    } else {
      throw 505;
    }
  }
  catch (...) {
    cout << "Access denied - You must be at least 18 years old.\n";
  }
  return 0;
}
~~~

## Files

- The fstream library allows us to work with files.
- To use the fstream library, include both the standard <iostream> AND the <fstream> header file.
- There are three classes included in the fstream library, which are used to create, write or read files:
  - ofstream 	Creates and writes to files
  - ifstream 	Reads from files
  - fstream 	A combination of ofstream and ifstream: creates, reads, and writes to files

> Why do we close the file? It is considered good practice, and it can clean up unnecessary memory space.

#### Ex.: read a file

~~~cpp
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main () {
  // Create a text file
  ofstream MyWriteFile("filename.txt");

  // Write to the file
  MyWriteFile << "Files can be tricky, but it is fun enough!";
 
  // Close the file
  MyWriteFile.close();

  // Create a text string, which is used to output the text file
  string myText;

  // Read from the text file
  ifstream MyReadFile("filename.txt");

  // Use a while loop together with the getline() function to read the file line by line
  while (getline (MyReadFile, myText)) {
    // Output the text from the file
    cout << myText;
  }

  // Close the file
  MyReadFile.close();
}

~~~

## Objects Serialization 

~~~cpp

~~~

## Output

~~~cpp
cout << "Hello \n";                  // new line - preferred way
cout << "Hello" << endl;             // new line
cout << "Hello " << myName << endl;  // print var string
cout << "Hello " << myName << "\n";  // print var string
cout << myInt << "\n";               // print var int
~~~

#### Ex.: input - formatting double

~~~cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
  const double pi = 3.14159;
  double r;
  double area;

  cin >> r;
  area = pi * r * r;
  cout << fixed << setprecision(4); // #include <iomanip>
  cout << "A = " << area << endl;

  return 0;
}
~~~

### Special Characters

~~~cpp

~~~

## Input

~~~cpp
cin >> myName;   // Get user input from the keyboard - only 1 word
~~~

## How To

### How To: Random numbers

~~~cpp

~~~

### How To: ...

~~~cpp

~~~

## GUI

- [Examples](#)

## Links

- [W3schools](https://www.w3schools.com/cpp/default.asp)
- [Tutorialspoint - OOP](https://www.tutorialspoint.com/cplusplus/cpp_object_oriented.htm)
- [Ntu - OOP](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/cp3_OOP.html)
- [Cplusplus](http://www.cplusplus.com/doc/tutorial/)
- [Tutorial STL - 1bit](http://www.1bit.com.br/content.1bit/weblog/stl_tutorial_0)
- [Geeksforgeeks - OOP](https://www.geeksforgeeks.org/object-oriented-programming-in-cpp/)

## To be continued

- OOP
- Data structs - create dir in git
- OpenGl UFRGS
- CPP and DBs
- framework Qt Creator

https://www.youtube.com/watch?v=iVLQeWbgbXs&list=PL43pGnjiVwgTJg7uz8KUGdXRdGKE0W_jN
https://youtu.be/wN0x9eZLix4?t=11m
https://www.w3schools.com/cpp/cpp_files.asp