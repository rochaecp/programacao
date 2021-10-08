# Dotnet

## Dotnet CLI (command-line interface )

~~~bash
# geral
dotnet --version
dotnet --help 
dotnet --info

# help
dotnet new --help 
dotnet new console --help 

# criando apps
dotnet new console -n meuPrimeiroProjeto # cria uma aplicação do tipo console 

dotnet restore 
dotnet build 

# rodando
dotnet run 
~~~

## Dotnet C#

### Coomandos básicos

~~~csharp
// tipos valor - outros:  enum, struct, nullable 
byte myByte = 10; 
sbyte mySbyte = 10; 
short myShort = 10;
ushort myUshort;
int myInt = 10;
uint myUint = 10;
long myLong = 10L;
ulong myUlong;
float myFloat = 10F;
double myDouble = 10D;
decimal myDecimal;
char myChar = 'a';
bool myBoolean = true;

// tipos referência - outros: Class, Object, Array, Interface, Delegate
string myString = "abc";

// constantes
const int myConst = 10;

// casting implícita: char -> int -> long -> float -> double
double myDouble = myInt;

// casting explícita
int myInt = (int)myDouble;

// métodos de conversão
myString = Convert.ToString(myInt);
myDouble = Convert.ToDouble(myInt);
myInt = Convert.ToInt32(myDouble);
myLong = Convert.ToInt64(myDouble);
myBool = Convert.ToBoolean(myInt);

// math
myNum = Math.Max(2, 5);
myNum = Math.Min(2, 5);
myNum = Math.Sqrt(64);
myNum = Math.Abs(-10);
myNum = Math.Round(9.99); // 10

// comando if..else
if (myInt == 1)
    Console.WriteLine("Um");
else if (myInt == 2)
    Console.WriteLine("Dois");
else
    Console.WriteLine("Nenhum");

// operador ternário
myString = (myInt == 10) ? "dez" : "zero";

// switch
switch (myInt)
{
    case 1:
        Console.WriteLine("Um");
        break;
    case 2:
        Console.WriteLine("Dois");
        break;
    default:
        Console.WriteLine("Nenhum");
        break;
}

// while
int i = 0;
while (i < 5) {
    Console.WriteLine(i);
    i++;
}

// do .. while
int i = 0;
do {
    Console.WriteLine(i);
    i++;
} while (i < 5);

// for
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}

// foreach
string[] cars = { "Volvo", "BMW", "Ford", "Mazda" };
foreach (string i in cars)
{
    Console.WriteLine(i);
}

// break
for (int i = 0; i < 10; i++)
{
    if (i == 4)
    {
        break;
    }
    Console.WriteLine(i);
}

// continue
for (int i = 0; i < 10; i++)
{
    if (i == 4)
    {
        continue;
    }
    Console.WriteLine(i);
}

// Continue
int i = 0;
while (i < 10)
{
    if (i == 4)
    {
        i++;
        continue;
    }
    Console.WriteLine(i);
    i++;
}

// saída no console
Console.WriteLine($"Var = {myInt}" );
Console.WriteLine($"Const = {myConst}" );
~~~

### Strings

~~~csharp
// strings
string myString = "aaa " + "bbb";
myChar = myString[0];
myString = $"Hello {Name}"; // interpolacao

// métodos para strings
myString = string.Concat(myString1, myString2);
myLength = myString.Length;
myIndex = myString.IndexOf("M"); 
mySubStr = myString.Substring(2); 
mySubStr = myString.ToUpper();
mySubStr = myString.ToLower();
myBool = string.IsNullOrEmpty(myString);
myBool = myString.Equals("myText");
~~~

### Arrays

~~~csharp
// criando arrays
int[] myArray = {10, 20, 30};
string[] myArrayStrings = {"aaa", "bbb", "ccc"};

// criando arrays - outra forma
int[] myArray2 = new int[3];
int[] myArray3 = new int[3] {10, 20, 30};
int[] myArray4 = new int[] {10, 20, 30};

// criando arrays - outra forma
string[] cars;
cars = new string[] {"Volvo", "BMW", "Ford"};

// criando array multidimensional
int[,] myArray = new int[10, 5];
int[,,] myArray = new int[10, 5, 2];

int myItem = myArrayCars[0];
myArray[0] = "myText";
int myLength = myArrayCars.Length;

// métodos para arrays
Array.Sort(myArrayString); // sort a string
Array.Sort(myArrayInt); // sort a int

// System.Linq Namespace
// using System.Linq;
int myMax = myNumbers.Max();
int myMin = myNumbers.Min();
int mySum = myNumbers.Sum();

// acessando elementos array
string[] cars = {"Volvo", "BMW", "Ford"};
for (int i = 0; i < cars.Length; i++) {
  Console.WriteLine(cars[i]);
}

// acessando elementos array
string[] cars = {"Volvo", "BMW", "Ford"};
foreach (string i in cars) {
  Console.WriteLine(i);
}
~~~


