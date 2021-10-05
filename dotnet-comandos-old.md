# C#

## Syntax

- Unlike Java, the name of the C# file does not have to match the class name, but they often do (for better organization).

~~~csharp
using System; //classes from the System namespace

namespace HelloWorld { // is a used to organize your code, and it is a container for classes and other namespaces.
  class Program { // class is a container for data and methods, which brings functionality to your program. Every line of code that runs in C# must be inside a class.
    static void Main(string[] args){
      Console.WriteLine("Hello World!"); // Console is a class of the System namespace, If you omit the using System line, you would have to write System.Console.WriteLine()
    }
  }
}
~~~

## Comments

~~~csharp
// Comment
/* Multi-line Comment */
~~~

## Variables and Data Types

- Value types:
  - Integer types:
    - *byte* : 1 byte unsigned 0 to 255
    - *sbyte* : 8 byte signed -127 to 128
    - *ushort* : 2 bytes unsigned 0 to 65535
    - *short* : 2 bytes signed -32768 to 32767
    - *uint* : 4 bytes unsigned 0 to 4294967295
    - *int* : 4 bytes signed -2147483648 to 147483647
    - *ulong* : 8 bytes unsigned      
    - *long* : 8 bytes signed
  - Floating point types:
    - *float* : 4 bytes 7 digits
    - *double* : 8 bytes 15 digits
    - *decimal*
  - *bool* : 1 bit
  - *char* : 2 bytes - unicode
  - *enum*
  - *struct*
  - *nullable*

- Reference types:
  - *String* 
  - *Class*
  - *Object*
  - *Array*
  - *Interface*
  - *Delegate*

~~~csharp
int myNum = 5; // Integer (whole number)
long myNum = 15000000000L;   

float myNum = 5.75F;
float f1 = 35e3F;
double myDoubleNum = 5.99D; // Floating point number
double d1 = 12E4D;

char myLetter = 'D'; // Character
bool myBool = true; // Boolean
string myText = "Hello"; // String
~~~

## Constants

~~~csharp
const int myNum = 15;
myNum = 20; // error
~~~

## Type Casting

- Implicit Casting (automatically):
  - converting a smaller type to a larger type size: char -> int -> long -> float -> double
- Explicit Casting (manually):
  - converting a larger type to a smaller size type: double -> float -> long -> int -> char

~~~csharp
// Implicit Casting
int myInt = 9;
double myDouble = myInt; // Automatic casting: int to double

// Explicit Casting
double myDouble = 9.78;
int myInt = (int) myDouble;    // Manual casting: double to int

// Type Conversion Methods
string myString = Convert.ToString(myInt); 
string myString = Convert.ToString(myBool); 
double myDouble = Convert.ToDouble(myInt); 
int myInt = Convert.ToInt32(myDouble);  
long myLong = Convert.ToInt64(myDouble);
bool myBool = Convert.ToBoolean(myInt);

// TryParse -> bool
if (decimal.TryParse(Console.ReadLine(), out decimal grade))
  student.Grade = grade;
else
  throw new ArgumentException("O valor da nota deve ser decimal.");
~~~

## Operators

- Arithmetic Operators:  +  -  *  /  %  ++  --
- Assignment Operators: =  +=  -=  *=  /=  %=  &=  |=  ^=  >>=  <<=
- Comparison Operators: ==  !=  >  <  >=  <=
- Logical Operators: &&  ||  !

## Math

~~~csharp
int myNum = Math.Max(2, 5);
int myNum = Math.Min(2, 5);
int myNum = Math.Sqrt(64);
int myNum = Math.Abs(-10);
int myNum = Math.Round(9.99); // 10
~~~

## Strings

- Escape characters: \' \" \n \t \b \\ 

~~~csharp
string myString = "Hello";

// Array of Strings
string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

// String Concatenation
string name = firstName + lastName;
string name = string.Concat(firstName, lastName);

// String Interpolation - in C# version 6
string name = $"My full name is: {firstName} {lastName}";

// Access Strings
string myString = "Mauricio";
char firstLetter = myString[0]; // M

// Methods
int myLength = myString.Length;
int myIndex = myString.IndexOf("M"); // -1 == did not find
string txt = myString.Substring(2); // extracts the characters from a string, starting from the position 2 
string txt = myString.ToUpper();
string txt = myString.ToLower();
bool myBool = string.IsNullOrEmpty(myString);
bool myBool = myString.Equals("myText");
~~~

## Booleans

~~~csharp
bool isCSharpFun = true;
bool isFishTasty = false;
~~~

## If..Else

~~~csharp
int time = 22;
if (time < 10) {
  Console.WriteLine("Good morning.");
} else if (time < 20) {
  Console.WriteLine("Good day.");
} else {
  Console.WriteLine("Good evening.");
}
~~~

## Ternary Operator

~~~csharp
int time = 20;
string result = (time < 18) ? "Good day." : "Good evening.";
~~~

## Switch

~~~csharp
int day = 4;
switch (day) {
  case 6:
    Console.WriteLine("Today is Saturday.");
    break;
  case 7:
    Console.WriteLine("Today is Sunday.");
    break;
  default:
    Console.WriteLine("Looking forward to the Weekend.");
    break;
}
~~~

## While and do/while Loop

~~~csharp
// While Loop
int i = 0;
while (i < 5) {
  Console.WriteLine(i);
  i++;
}

// Do/While Loop
int i = 0;
do {
  Console.WriteLine(i);
  i++;
} while (i < 5);
~~~

## For Loop

- When you know exactly how many times you want to loop through a block of code, use the for loop instead of a while loop.

~~~csharp
// For Loop
for (int i = 0; i < 5; i++) {
  Console.WriteLine(i);
}

// Foreach Loop
string[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
foreach (string i in cars) {
  Console.WriteLine(i);
}
~~~

## Break / Continue

- The break statement can also be used to jump out of a loop.
- The continue statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop.

~~~csharp
// Break
for (int i = 0; i < 10; i++) {
  if (i == 4)   {
    break;
  }
  Console.WriteLine(i);
}

// Continue
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    continue;
  }
  Console.WriteLine(i);
}

// Continue
int i = 0;
while (i < 10) {
  if (i == 4) {
    i++;
    continue;
  }
  Console.WriteLine(i);
  i++;
}
~~~

## Arrays

~~~csharp
// Create an one-dimensional array
int[] myArray = new int[3];
int[] myArray = new int[3] {10, 20, 30};
int[] myArray = new int[] {10, 20, 30};
int[] myArray = {10, 20, 30}; // easier to read
string[] myArrayCars = {"Volvo", "BMW", "Ford"};

// Different Example 
string[] cars;
cars = new string[] {"Volvo", "BMW", "Ford"};

// Access the Elements of an one-dimensional Array
int myItem = myArrayCars[0];

// Change an Array Element
myArrayCars[0] = "Opel";

// Array Properties 
int myLength = myArrayCars.Length;

// Array Methods
Array.Sort(myArrayCars); // sort a string
Array.Sort(myArrayInt); // sort a int

// System.Linq Namespace
// using System.Linq;
int myMax = myNumbers.Max();
int myMin = myNumbers.Min();
int mySum = myNumbers.Sum();

// Loop Through an Array
string[] cars = {"Volvo", "BMW", "Ford"};
for (int i = 0; i < cars.Length; i++) {
  Console.WriteLine(cars[i]);
}

// The foreach Loop
string[] cars = {"Volvo", "BMW", "Ford"};
foreach (string i in cars) {
  Console.WriteLine(i);
}

// Create an multidimensional array - 2d
int[,] myArray = new int[10, 5];

// Create an multidimensional array - 3d
int[,,] myArray = new int[10, 5, 2];
~~~

## Methods

- A method is a block of code which only runs when it is called.

~~~csharp
using System;
namespace Treinos {
  class Program {  
    static string sayHello(string name) { // name is a parameter, static means that the method belongs to the Program class and not an object of the Program class. 
      return $"Hello {name}";
    }
    static void Main(string[] args) {
      Console.WriteLine(sayHello("Mauricio")); // "Mauricio" is an argument
    }
  }
}

// Another Examples 

// Default Parameter Value
static void MyMethod(string country = "Norway") { // country is an optional parameter
  Console.WriteLine(country);
}

// Multiple Parameters
static void MyMethod(string fname, int age) {
  Console.WriteLine(fname + " is " + age);
}

// Named Arguments
static void MyMethod(string child1, string child2, string child3) {
  Console.WriteLine("The youngest child is: " + child3);
}
static void Main(string[] args) {
  MyMethod(child3: "John", child1: "Liam", child2: "Liam"); // call
}

// Named Arguments and Default Parameter Value
static void MyMethod(string child1 = "Liam", string child2 = "Jenny", string child3 = "John") {
  Console.WriteLine(child3); //
}
static void Main(string[] args) {
  MyMethod(); // John
  MyMethod("Joao", "Jose", "Maria"); // Maria
}

// Method Overloading
// With method overloading, multiple methods can have the same name with different parameters.
static int PlusMethod(int x, int y) {
  return x + y;
}
static double PlusMethod(double x, double y) {
  return x + y;
}

// String or Array by argument
static void printArgs(string[] myArgs) {
  if (myArgs.Length == 0)
    Console.WriteLine("no argument");
  else
    Console.WriteLine($"{myArgs.Length} arguments");
}
static void Main(string[] args) {
  string[] names = new string[3] { "Mauricio", "Maria", "Jose" };
  printArgs(names);
}

// ref paramethers
static void swapInt(ref int x, ref int y) { // by reference
  int temp = x;
  x = y;
  y = temp;
}
static void Main(string[] args) {
  int x = 10, y = 20;
  swapInt(ref x, ref y); // call
  Console.WriteLine($"x = {x}, y = {y}");
}

// out paramethers
static void divide(int x, int y, out int result, out int rest) {
  result = x / y;
  rest = x % y;
}

static void Main(string[] args) {
  int result, rest;
  divide(10, 3, out result, out rest);
  Console.WriteLine($"result = {result}, rest = {rest}");
}
~~~

## Classes

- OOP helps to keep the C# code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
- The "Don't Repeat Yourself" (DRY) principle is about reducing the repetition of code.
- Class: Fruit, Objects: Apple, Banana, Mango
- So, a class is a template for objects, and an object is an instance of a class.
- A Class is like an object constructor, or a "blueprint" for creating objects.
- When a variable is declared directly in a class, it is often referred to as a field (or attribute).

> It is not required, but it is a good practice to start with an uppercase first letter when naming classes.
> Also, it is common that the name of the C# file and the class matches, as it makes our code organized. 
> However it is not required (like in Java).

- **Class Members**
  - Fields and methods inside classes are often referred to as "Class Members".
  - Methods normally belongs to a class, and they define how an object of a class behaves.

- **Constructors**
  - A constructor is a special method that is used to initialize objects. 
  - The advantage of a constructor, is that it is called when an object of a class is created. 
  - It can be used to set initial values for fields.
  - Note that the constructor name must match the class name, and it cannot have a return type (like void or int). 
  - Also note that the constructor is called when the object is created.
  - All classes have constructors by default: if you do not create a class constructor yourself, C# creates one for you.
  - Just like other methods, constructors can be overloaded by using different numbers of parameters.

~~~csharp
// file Car.cs, dir: MyApplication
using System;
namespace MyApplication {
  class Car {
    public string color; // field (or attribute)
    public Car(string color) { // constructor
      this.color = color;
    }
    public Car() { // overloaded constructor 
      this.color = "blue";
    }
    public void printColor() { // method
      Console.WriteLine($"Color: {color}");
    }
  }
}

// file Program.cs, dir: MyApplication
using System;
namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      Car myObj = new Car("red");
      myObj.printColor();
    }
  }
}
~~~

## Access Modifiers

- **public**: The code is accessible for all classes.
- **private**: The code is only accessible within the same class.
- **protected**: The code is accessible within the same class, or in a class that is inherited from that class. 
- **internal**: The code is only accessible within its own assembly, but not from another assembly. 
- **protected internal**: The code is only accessible within the same class or in a class that is inherited from that class or in its own assembly.

> There's also two combinations: protected internal and private protected.
> By default, all members of a class are private if you don't specify an access modifier

## Properties and Encapsulation

- The meaning of Encapsulation, is to make sure that "sensitive" data is hidden from users. To achieve this, you must:
  - declare fields/variables as private
  - provide public get and set methods, through properties, to access and update the value of a private field
- A property is like a combination of a variable and a method, and it has two methods: a get and a set method.
- The Name property is associated with the name field. It is a good practice to use the same name for both the property and the private field, but with an uppercase first letter.
- C# also provides a way to use short-hand / automatic properties, where you do not have to define the field for the property, and you only have to write get; and set; inside the property.
- Fields can be made read-only (if you only use the get method), or write-only (if you only use the set method)

~~~csharp
// file Person.cs, dir: MyApplication
using System;
namespace MyApplication {
  class Person {
    private string name;  // field
    public string Name {    // property
      get { return name; }
      set { name = value; }
      // or short hand: get; set; 
    }
  }
}

// file Program.cs, dir: MyApplication
using System;
namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      Person myObj = new Person();
      myObj.Name = "Mauricio";
      Console.WriteLine(myObj.Name);
    }
  }
}
~~~

## Inheritance

- Inheritance lets us inherit fields and methods from another class. 
- We group the "inheritance concept" into two categories:
  - Derived Class (child) - the class that inherits from another class
  - Base Class (parent) - the class being inherited from
- To inherit from a class, use the : symbol.
- It is useful for code reusability: reuse fields and methods of an existing class when you create a new class.
- If you don't want other classes to inherit from a class, use the **sealed** keyword.

~~~csharp
// file Vehicle.cs, dir MyApplication
using System;
namespace MyApplication {
  class Vehicle { // Base class
    public string brand = "Ford";  // Vehicle field
    public void honk() {            // Vehicle method 
      Console.WriteLine("Tuut, tuut!");
    }
  }
}

// file Car.cs, dir MyApplication
using System;
namespace MyApplication {
  class Car : Vehicle {  // Derived class
    public string modelName = "Mustang";  // Car field
  }
}

// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      // Create a myCar object
      Car myCar = new Car();

      // Call the honk() method (From the Vehicle class) on the myCar object
      myCar.honk();

      // Display the value of the brand field (from the Vehicle class) and the value of the modelName from the Car class
      Console.WriteLine(myCar.brand + " " + myCar.modelName);
    }
  }
}

// Another Examples

// If you don't want other classes to inherit from a class, use the sealed keyword.
sealed class Vehicle {
  ...
}
~~~

## Polymorphism

- Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.
- Polymorphism uses those methods to perform different tasks. This allows us to perform a single action in different ways.
- C# provides an option to override the base class method, by adding the **virtual keyword** to the method inside the base class, and by using the override keyword for each derived class methods.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  class Animal { // Base class (parent) 
    public virtual void animalSound() { // note virtual keyword
      Console.WriteLine("The animal makes a sound");
    }
  }

  class Pig : Animal { // Derived class (child) 
    public override void animalSound() {
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Dog : Animal { // Derived class (child) 
    public override void animalSound() {
      Console.WriteLine("The dog says: bow wow");
    }
  }

  class Program {
    static void Main(string[] args) {
      Animal myAnimal = new Animal(); // Create a Animal object
      Animal myPig = new Pig();  // Create a Pig object
      Animal myDog = new Dog();  // Create a Dog object

      myAnimal.animalSound();
      myPig.animalSound();
      myDog.animalSound();
    }
  }
}
~~~

## Abstraction

- Data abstraction is the process of hiding certain details and showing only essential information to the user.
- **Abstract class**: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
- **Abstract method**: can only be used in an abstract class, and it does not have a body. The body is provided by the derived class (inherited from).
- An abstract class can have both abstract and regular methods.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  // Abstract class
  abstract class Animal {
    // Abstract method (does not have a body)
    public abstract void animalSound();
    // Regular method
    public void sleep() {
      Console.WriteLine("Zzz");
    }
  }

  // Derived class (inherit from Animal)
  class Pig : Animal {
    public override void animalSound() {
      // The body of animalSound() is provided here
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Program {
    static void Main(string[] args) {
      Pig myPig = new Pig();  // Create a Pig object
      myPig.animalSound();
      myPig.sleep();
    }
  }
}
~~~

## Interfaces

- Another way to achieve abstraction in C#, is with interfaces.
- An interface is a completely "abstract class", which can only contain abstract methods and properties (with empty bodies).
- It is considered good practice to start with the letter "I" at the beginning of an interface, as it makes it easier for yourself and others to remember that it is an interface and not a class.
- By default, members of an interface are abstract and public.
- Interfaces can contain properties and methods, but not fields.
- To access the interface methods, the interface must be "implemented" (kinda like inherited) by another class. 
- The body of the interface method is provided by the "implement" class. Note that you do not have to use the override keyword when implementing an interface.
- Like abstract classes, interfaces cannot be used to create objects.
- Interface methods do not have a body - the body is provided by the "implement" class.
- Interface members are by default **abstract** and **public**.
- An interface cannot contain a constructor (as it cannot be used to create objects).
- C# does not support "multiple inheritance" (a class can only inherit from one base class).
- However, it can be achieved with interfaces, because the class can implement multiple interfaces.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  // Interface
  interface IAnimal {
    void animalSound(); // interface method (does not have a body)
  }

  // Pig "implements" the IAnimal interface
  class Pig : IAnimal {
    public void animalSound() {
      // The body of animalSound() is provided here
      Console.WriteLine("The pig says: wee wee");
    }
  }

  class Program {
    static void Main(string[] args) {
      Pig myPig = new Pig();  // Create a Pig object
      myPig.animalSound();
    }
  }
}
~~~

### Multiple Interfaces 

~~~csharp
// file Program.cs, dir MyApplication
using System;

namespace MyApplication {
  interface IFirstInterface {
    void myMethod(); // interface method
  }

  interface ISecondInterface {
    void myOtherMethod(); // interface method
  }

  // Implement multiple interfaces
  class DemoClass : IFirstInterface, ISecondInterface {
    public void myMethod() {
      Console.WriteLine("Some text..");
    }
    public void myOtherMethod() {
      Console.WriteLine("Some other text...");
    }
  }

  class Program {
    static void Main(string[] args) {
      DemoClass myObj = new DemoClass();
      myObj.myMethod();
      myObj.myOtherMethod();
    }
  }
}
~~~

## Enums

- An enum is a special "class" that represents a group of constants (unchangeable/read-only variables).
- By default, the first item of an enum has the value 0. The second has the value 1, and so on.
- To get the integer value from an item, you must explicitly convert the item to an int.
- Use enums when you have values that you know aren't going to change, like month days, days, colors, deck of cards, etc.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  enum Level {
    Low, // 0
    Medium, // 1
    High // 2
  }
  class Program {
    static void Main(string[] args) {
      Level myVar = Level.Medium;
      Console.WriteLine(myVar);
    }
  }
}

// Another example

// file Program.cs, dir MyApplication - Enum inside a class
using System;
namespace MyApplication {
  class Program {
    enum Level {
      Low, // 0
      Medium, // 1
      High // 2
    }
    static void Main(string[] args) {
      Level myVar = Level.Medium;
      Console.WriteLine(myVar);
    }
  }
}

// Another example

// file Program.cs, dir MyApplication - Enum in a Switch Statement
using System;
namespace MyApplication {
  class Program {
    enum Level {
      Low,
      Medium,
      High
    }
    static void Main(string[] args) {
      Level myVar = Level.Medium;
      switch (myVar) {
        case Level.Low:
          Console.WriteLine("Low level");
          break;
        case Level.Medium:
          Console.WriteLine("Medium level");
          break;
        case Level.High:
          Console.WriteLine("High level");
          break;
      }
    }
  }
}

// Another example

// You can also assign your own enum values, and the next items will update the number accordingly:
enum Level: sbyte { // type == sbyte
  Low=10,
  Medium=20, 
  High=30 
}
~~~

## Files

- The File class from the **System.IO namespace**, allows us to work with files.
- The File class has many useful methods for creating and getting information about files. For example:
  - AppendText() - Appends text at the end of an existing file
  - Copy() - Copies a file
  - Create() - Creates or overwrites a file
  - Delete() - Deletes a file
  - Exists() - Tests whether the file exists
  - ReadAllText() - Reads the contents of a file
  - Replace() - Replaces the contents of a file with the contents of another file
  - WriteAllText() - Creates a new file and writes the contents to it. If the file already exists, it will be - overwritten.

~~~csharp
// file Program.cs, dir MyApplication
using System;
using System.IO;  // include the System.IO namespace

namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      string writeText = "Hello World!";  // Create a text string
      File.WriteAllText("filename.txt", writeText);  // Create a file and write the contents of writeText to it

      string readText = File.ReadAllText("filename.txt"); // Read the contents of the file
      Console.WriteLine(readText); // Output the content
    }
  }
}

// Another examples

// using
using (System.IO.TextWriter w = System.IO.File.CreateText("test.txt")) {
  w.WriteLine("Line 1");
  w.WriteLine("Line 2");
  w.WriteLine("Line 3");
}
~~~

## Exceptions

- When executing C# code, different errors can occur: coding errors made by the programmer, errors due to wrong input, or other unforeseeable things.
- When an error occurs, C# will normally stop and generate an error message. The technical term for this is: C# will throw an exception (throw an error).
- The **try** statement allows you to define a block of code to be tested for errors while it is being executed.
- The **catch** statement allows you to define a block of code to be executed, if an error occurs in the try block.
- The **finally** statement lets you execute code, after try...catch
- The **throw** statement allows you to create a custom error.
- The throw statement is used together with an exception class. There are many exception classes available in C#: ArithmeticException, FileNotFoundException, IndexOutOfRangeException, TimeOutException, etc.

~~~csharp
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  class Program {
    static void Main(string[] args) {
      try {
        int[] myNumbers = { 1, 2, 3 };
        Console.WriteLine(myNumbers[10]);
      } catch (Exception e) {
        Console.WriteLine(e.Message);
      }
    }
  }
}

// Another examples

// You can also output your own error message
try {
  int[] myNumbers = { 1, 2, 3 };
  Console.WriteLine(myNumbers[10]);
} catch (Exception e) {
  Console.WriteLine("Something went wrong.");
}

// The finally statement lets you execute code, after try...catch
try {
  int[] myNumbers = { 1, 2, 3 };
  Console.WriteLine(myNumbers[10]);
} catch (Exception e) {
  Console.WriteLine("Something went wrong.");
} finally {
  Console.WriteLine("The 'try catch' is finished.");
}

// The throw statement allows you to create a custom error.
// file Program.cs, dir MyApplication
using System;
namespace MyApplication {
  class Program {
    static void checkAge(int age) {
      if (age < 18) {
        throw new ArithmeticException("Access denied - You must be at least 18 years old.");
      } else {
        Console.WriteLine("Access granted - You are old enough!");
      }
    }
    static void Main(string[] args) {
      checkAge(20);
    }
  }
}

// Another example

// Custom error
int players = 2, score = 0;
try {
  if (players != 2)
    throw new InvalidOperationException("error: must have 2 players ");
  players = 1 / score;
} catch (InvalidOperationException e) {
  Console.WriteLine(e.Message);
} catch (Exception e) {
  Console.WriteLine($"Generic error: {e.Message}");
}


// TryParse
if (decimal.TryParse(Console.ReadLine(), out decimal grade))
  student.Grade = grade;
else
  throw new ArgumentException("O valor da nota deve ser decimal.");


// Another exceptions

throw new ArgumentOutOfRangeException();
~~~

## Structs

- Structs are allocated on the stack.
- Structures do not allow inheritance.

~~~csharp
// file Program.cs, dir: MyApplication
public struct Point {
  public int x, y;
  public Point(int x, int y) {
    this.x = x;
    this.y = y;
  }
}
~~~

## User Input

~~~csharp
text = Console.ReadLine(); // return string
int age = Convert.ToInt32(Console.ReadLine()); 
~~~

## User Output

~~~csharp
Console.WriteLine("on a new line.");
Console.Write("on the same line.");  

Console.WriteLine($"Hello {userName}");
Console.WriteLine("Hello: " + userName);
Console.WriteLine("Your age is: " + age); // int
~~~




