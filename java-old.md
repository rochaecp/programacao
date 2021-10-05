# Java


## Syntax

~~~java
/* Ex: */
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello World");
  }
}
~~~

## Comments

~~~java
//  comment
/*  comment  */
/** comment - javadoc style    */ 
~~~

## Data Types

### Basic Data Types

- short
- int
- long
- float
- double
- boolean
- byte
- char

### Derived Data Types

## Modifiers

- short
- long
- signed
- unsigned
- ...

## Variables

~~~java

~~~

## Casting

~~~java
varDouble = (double) varInt1 * varInt1;
~~~

## Constants

#### Ex.: constant initialized by the user 

~~~java
/* File  IncrementTest.java*/
public class Increment {
  private int total = 0;
  private final int INCREMENT; // CONSTANTE não inicializada ;)
  
  // Construtor inicializa a constante
  public Increment(int incrementValue) {
    INCREMENT = incrementValue;
 }
  
  public void addIncrementToTotal() {
    total += INCREMENT;
 }
  
  public String toString() {
    return String.format("total = %d", total);
 }
}

/* File  IncrementTest.java*/
public class IncrementTest {
  public static void main(String[] args) {
    Increment value = new Increment(5); // Inicializamos constante
    
    for(int i=0; i < 5; i++) {
      value.addIncrementToTotal();
      System.out.println(value);      
   }
 }
}
~~~

## Operators

- Arithmetic operators: + - * / % ++ -- 
- Assignment operators: = += -= *= /= %= &= |= ^= >>= <<=
- Comparison operators: == != > < >= <=
- Logical operators: && || !
- Bitwise operators: & | ^ << >> ~

## Strings

~~~java
public class Strings {
  public static void main(String [] args) {    
    String name = "Mauricio";
    System.out.println(name.length());       
    System.out.println(name.toUpperCase());
    System.out.println(name.indexOf("ricio"));
  }
}
~~~

## Math 

#### Ex.: File StaticImportTest.java

~~~java
import java.lang.Math.*;

public class StaticImportTest {
  public static void main(String[] args) {
    // Classe Math possui Métodos static, não necessita de import
    /* Math.abs(x) Math.ceil(x)  Math.cos(x)  Math.exp(x)  Math.floor(x) 
    Math.log(x) Math.max(x, y)  Math.min(x, y)  Math.pow(x, y) 
    Math.sin(x)  Math.sqrt(x) Math.tan(x)  */
    
    System.out.printf("%.1f\n", Math.sqrt(900.00));
 }
}
~~~

#### Ex.: File MaximumFinder.java

~~~java
import java.util.Scanner;
public class MaximumFinder {   
  public void determineMaximum()
  {
    Scanner input = new Scanner(System.in);
    
    System.out.println("Digite 3 Double: ");
    double number1 = input.nextDouble();
    double number2 = input.nextDouble();
    double number3 = input.nextDouble();
    
    //max é um método static da classe Math. Math não precisa de import
    double result = Math.max(number1, Math.max(number2, number3));
    
    System.out.println("Maximum is " + result);    
 }
}
~~~

#### Ex.: File MaximumFinderTest.java

~~~java
public class MaximumFinderTest {
  public static void main(String[] args)
  {
    MaximumFinder maximumFinder = new MaximumFinder();
    maximumFinder.determineMaximum();
 }
}
~~~

## Date

~~~java

~~~

## Booleans

~~~java

~~~

## If...Else

~~~java
if (grade >= 6)
  /* commands */
else
  /* commands */
~~~

## Conditional Operator 

~~~java
System.out.println(grade >= 6 ? "Ok" : "not Ok");
~~~

## Switch

~~~java
switch (grades) {
  case 1: /* commands */ break;
  case 2: /* commands */ break;
  default: /* commands */ break; 
}
~~~

## While Loop

~~~java
while (count <= 100) { 
  System.out.printf("%d /n", count); 
  count++; 
}
~~~

## Do...While Loop

~~~cpp
do {  
  /* commands */
} while (counter <= 10); 
~~~

## For Loop

~~~java
// Ex.: 
for (int counter = 1; counter <= 10; counter++)
  /* commands */

// for (type variable : arrayname) {...}
for (String i: cars)
  System.out.println(i);
~~~

## ForEach Loop

~~~java

~~~

## Break

~~~java

~~~

## Continue

~~~java

~~~

## Arrays

- Arrays do not automatically change their size at run time to accommodate additional data. 

~~~java
int [] c = new int [12];                  // init zero 
int c[]  = new int [12];                  
String [] name = {"Mauricio", "Maria"};
int [] n = { 10, 20, 30  };   
tam = n.length;

/* Ex.: */
public class Arrays {
  public static void main(String [] args) {   
    String [] cars = {"Volvo", "BMW", "Ford", "Renault"};  // String cars[] = {"Volvo", "BMW", "Ford", "Renault"};
    int [] myNum = {10, 20, 30, 40, 50};
    
    System.out.println(cars[0]);
    System.out.println(cars.length); // propriedade length - para tamanho do Array
    
    
    for(int i = 0; i < cars.length; i++)
      System.out.println(cars[ i ]);
      
    // for (type variable : arrayname) {...}
    for(String i: cars)
      System.out.println(i);
 }
}

/* Ex.: Multidimensional Arrays */ 
public class Arrays {
  public static void main(String [] args) {   
    int [][] myNumbers = {0, 2, 3}, {4, 5, 6}};
    myNumbers[ 0 ][ 0 ] = 1;
    for (int i = 0; i < myNumbers.length; ++i) 
          for(int j = 0; j < myNumbers[i].length; ++j)
            System.out.println(myNumbers[ i ][ j ]);    
  }
}

/* Ex.: ArraysManipulations.java: */
import java.util.Arrays;

public class ArraysManipulations {
  public static void main(String[] args) {    
    double[] doubleArray = {8.5, 9.5, 10.0, 9.4, 9.9, 8.9, 8.5, 9.4};
    Arrays.sort(doubleArray); //Ordena array em ordem crescente
    int[] intFillArray = new int[8];
    Arrays.fill(intFillArray, 10); // Preenche array com 10    
    int[] arrayInt = {1, 2, 3, 4, 5};
    int[] arrayIntCopy = new int [5];
    System.arraycopy(arrayInt, 0, arrayIntCopy, 0, arrayInt.length); // Copia array    
    boolean verifica = Arrays.equals(arrayInt, arrayIntCopy); // Compara dois arrays    
    int location = Arrays.binarySearch(arrayInt, 11); // Busca o elemento 4 no array arrayInt, se não encontra retorna negativo
  }
}
~~~

## Pointers

~~~java

~~~

## Functions

~~~java

~~~

### Function Parameters

~~~java

~~~

### Function Overloading

~~~java

~~~

## Scope

## Recursion

~~~java

~~~

## Structures 

~~~java

~~~

## Lists

~~~myLang

~~~

## Tuples

~~~myLang

~~~

## Sets

~~~myLang

~~~

## Dictionaries

~~~myLang

~~~

## Trees

~~~myLang

~~~

## Hash Tables

~~~myLang

~~~

## Graphs

~~~myLang

~~~

## OOP

### Classes/Objects

#### Ex.: File: GradeBook.java

~~~java
public class GradeBook {
  // Atributo da classe. É uma declaração para variáveis de instância
  // private: só pode ser modificada pelos métodos da classe GradeBook.
  private String courseName;
  
  // Método para configurar o name do curso
  public void setCourseName(String name) {
    courseName = name;  // ou this.courseName = name  ---> this faz referência ao objeto que courseName pertence
 }
  
  // Método para recuperar o name do curso
  public String getCourseName() {
    return courseName;
 }  
  
  public void displayMessage() {
    System.out.printf("Bem vindo ao curso: %s", getCourseName());
 }
}
~~~

#### Ex.: File: GradeBookTest.java

- Deve estar no mesmo diretório que o arquivo GradeBook.java

~~~java
import java.util.Scanner;

public class GradeBookTest {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    String theName;
    
    // Criando um objeto da classe GradeBook
    // GradeBook() é um Método construtor. Inicializa o objeto. Mesmo name da classe.
    GradeBook grade = new GradeBook();
    
    System.out.printf("name do curso antes de inicializa-lo: %s\n", grade.getCourseName());
    
    System.out.println("Digite o name do curso: ");
    theName = input.nextLine();   //Lê uma linha de texto
    grade.setCourseName(theName);
    grade.displayMessage();
 }
}
~~~

### Class Attributes

~~~java

~~~

### Class Methods

~~~java

~~~

### Class Method Overloading

#### Ex.: File MethodOverload.java
~~~java
public class MethodOverload {
  
  //testando o método square sobrecarregado
  public void testOverloadedMethods() {
    System.out.println("Square of 4 is   " + square(4));
    System.out.println("Square of 4.5 is   " + square(4.5));
 }

  //Método square com argumento int
  public int square(int x) {
    return x*x;
 }
  
  //Método square com argumento double
  public double square(double x) {
    return x*x;
 }
}
~~~

#### Ex.: File MethodOverloadTest.java
~~~java
public class MethodOverloadTest {
  public static void main(String[] args) {
    MethodOverload methodOverload = new MethodOverload();
    methodOverload.testOverloadedMethods();
 }
}
~~~

### Class Method final

~~~java

~~~

### Constructors

#### Ex.: Gradebook - File GradeBook.java

~~~java
public class GradeBook {
  
  private String courseName;
  
  //Método construtor: Inicializa as variáveis, Deve possuir o mesmo name da classe e deve ser public
  public GradeBook(String name) {
    courseName = name;  
 }
  
  public void setCourseName(String name) {
    courseName = name;
 }
  
  public String getCourseName() {
    return courseName;
 }
  
  public void displayMessage() {
    System.out.printf("name do curso: %s\n", getCourseName()); 
 }
}
~~~

#### Ex.: Gradebook - File GradeBookTest.java

~~~java
public class GradeBookTest 
{
  public static void main(String[] args)
  {
    //Criando objeto e utilizando o método construtor
    GradeBook grade1 = new GradeBook("Engenharia de Computacao");
    GradeBook grade2 = new GradeBook("Ciencia da Computacao");
    
    grade1.displayMessage();
    grade2.displayMessage();
 }
}
~~~

#### Ex.: toString - File Time1.java

~~~java
public class Time1 {  
  // Variáveis de instância
  private int hour;
  private int minute;
  private int second;

  // Não declaramos construtor, logo: Utiliza o construtor padrão que inicializa variáveis de instância com valores padrão
  
  public void setTime(int h, int m, int s) {
    hour = ((h >= 0 && h < 24) ? h : 0); // Poderia fazer this.hour = h; 
    minute = ((m >= 0 && m < 60) ? m : 0); // this.minute = m;
    second = ((s >= 0 && s < 60) ? s : 0); // this.second = s;     
 }
  
  public String toString() {
    return String.format("%02d : %02d : %02d", hour, minute, second);    
 }
}
~~~

#### Ex.: toString - File Time1Test.java

~~~java
public class Time1Test {
  public static void main(String[] args)
  {
    Time1 time = new Time1();
    
    System.out.println(time.toString());
    
    time.setTime(12, 9, 88);
    System.out.println(time.toString());    
 }
}
~~~

#### Ex.: Constructors Overloading - File Time1.java

~~~java
public class Time1 {
  
  // Variáveis de instância
  private int hour;
  private int minute;
  private int second;

  // Método construtor sem argumentos
  public Time1() {
    // Poderia fazer apenas this(0, 0, 0) que zerava tudo!
    hour = 0;
    minute = 0;
    second = 0; 
 }
  
  // Método Construtor sobrecarregado com 1 parâmetro
  public Time1(int h){
    this(h, 0, 0); // Usa o construtor já pronto Time(int h, int m, int s)
 }
  
  // Método Construtor sobrecarregado com 2 parâmetros
  public Time1(int h, int m) {
    this(h, m, 0);
 }
  
  // Método Construtor sobrecarregado com 3 parâmetros
  public Time1(int h, int m, int s) {
    setTime(h, m, s);
 }
  
  public void setTime(int h, int m, int s) {
    setHour(h);
    setMinute(m);
    setSecond(s);
 }
  
  public void setHour(int h) {
    hour = ((h >= 0 && h < 24) ? h : 0); // Poderia fazer this.hour = h;     
 }
  
  public void setMinute(int m)
  {
    minute = ((m >= 0 && m < 60) ? m : 0); // this.minute = m;    
 }
  
  public void setSecond(int s)
  {
    second = ((s >= 0 && s < 60) ? s : 0); // this.second = s;       
 }
  
  public int getHour() {
    return hour; 
 }
  
  public int getMinute() {
    return minute;
 }
  
  public int getSecond() {
    return second;
 }
  
  public String toString() {
    return String.format("%02d : %02d : %02d", getHour(), getSecond(), getMinute());
 }
}
~~~

#### Ex.: Constructors Overloading - File Time1Test.java

~~~java
public class Time1Test {
  public static void main(String[] args) {
    Time1 timeA = new Time1(12, 22, 47);
    Time1 timeB = new Time1(12, 64);
    
    System.out.println(timeA.toString());
    System.out.println(timeB.toString());
 }
}
~~~

### Access Specifiers/Modifiers

- public: o método pode ser chamado fora do escopo de declaração de classe. 
- private: a variável só pode ser modificada por métodos da classe que a contém. 
- protected

~~~java

~~~

### Static Methods

#### Ex.: 1 - File Employee.java
~~~java
public class Employee {
  private String name;
  private static int count = 0; // var static quando não inicializada recebe o valor padrão: 0
  
  // Construtor
  public Employee(String n) {
    name = n;
    ++count; // incrementa contagem estática de empregados
    
    System.out.printf("O empregado %s é o empregado de número %d\n\n", name, count);
 }
  
  public String getName() {
    return name;
 }
  
  // Método estático para obter valor de contagem estática
  public static int getCount() {
    return count;
 }
}
~~~

#### Ex.: 2 - File EmployeeTest.java
~~~java
public class EmployeeTest {
  public static void main(String[] args) {
    // Podemos acessar variáveis estáticas sem criar objetos
    System.out.printf("Numero de empregados até agora: %d\n\n", Employee.getCount());
    
    // Criando dois objetos
    Employee e1 = new Employee("Godofredo");
    Employee e2 = new Employee("Joselito");
    
    // Manda para coleta de lixo. Obrigatório ???
    e1 = null;
    e2 = null;
 }
}
~~~

### Static Variables

~~~java

~~~

### Encapsulation

~~~java

~~~

### Association

~~~java

~~~

### Composition

#### Ex.: Composition

~~~java
// Date.java
public class Date {
  private int month;
  private int day;
  private int year;
  
  // Construtor
  public Date(int d, int m, int y)
  {
    month = checkMonth(m);
    day = d;
    year = y;
 }
  
  private int checkMonth(int m)
  {
    if(m > 0 && m <= 12)
      return m; 
    else
      return 0;
 }
  
  public String toString()
  {
    return String.format(" %d / %d / %d ", this.day, month, year); // Aceita o this aqui!
 }
}

// Employee.java
public class Employee {
  private String name;
  private Date birthDate; //Composição: "relacionamento tem um"
  
  // Construtor
  public Employee(String n, Date bD) {
    name = n;
    birthDate = bD;
 }
  
  // Converte classe Employee para formato String
  public String toString() {
    return String.format("Name: %s \nBirth Date: %s", name, birthDate);
 }

}

// EmployeeTest.java
public class EmployeeTest {
  public static void main(String[] args)
  {
    Date birth = new Date(15, 1, 1992);
    Employee employee1 = new Employee("Mauricio Rocha", birth);
    
    System.out.println(employee1);
 }
}
~~~

### Aggregation

~~~cpp

~~~

### Inheritance

#### Ex.: inheritance - File ComissionEmployee.java

~~~java
public class ComissionEmployee { // extends Object é facultativo aqui
  private String firstName;
  private double grossSales; // Vendas brutas
  private double comission;
  
  // Construtor com argumentos: Lembrando, ao criá-lo o compilador não cria um construtor padrão sem argumentos!
  public ComissionEmployee(String fn, double sales, double c) {
    firstName = fn;
    grossSales = sales;
    comission = c;    
 }
  
  public void setName(String name) {
    firstName = name;
 }
  
  public String getName() {
    return firstName;
 }
  
  public void setGrossSales(double sales) {
    grossSales = sales < 0.0 ? 0.0 : sales; 
 }
  
  public double getGrossSales() {
    return grossSales; 
 }
  
  public void setComission(double c) {
    comission = (c > 0.0 && c < 1.0) ? c : 0.0; 
 }
  
  public double getComission() {
    return comission;
 }
  
  // Calcula os lucros
  public double earnings() {
    return getComission() * getGrossSales(); 
 }
  
  // Utilizamos aqui @Override para indicar ao compilador que iremos sobrescrever o método toString()
  // presente na superclasse Object. Como não estamos estendendo (herdando) explicitamente nenhuma classe,
  // implicitamente herdamos a classe Object e estamos sobrescrevendo um método dela
  @Override // Usamos para garantir que não iremos sobrecarregar o método que segue mas sim sobrescrevê-lo 
  public String toString()
  {
    return String.format("name: %s \nVendas brutas: %.2f \nComissao: : %.2f", getName(), getGrossSales(), getComission());
 }
}
~~~

#### Ex.: inheritance - File ComissionEmployee.java

~~~java
// Classe que herda (estende) a classe ComissionEmployee
// Este tipo de funcionário recebe a comissão + um salário base
public class BasePlusComissionEmployee extends ComissionEmployee
{
  private double baseSalary; 
  
  // Método construtor da sublcasse
  public BasePlusComissionEmployee(String fn, double sales, double c, double salary)
  {
    // O construtor da subclasse deve chamar o construtor da superclasse para inicializar suas variáveis de instância
    super(fn, sales, c); // fornecemos isso para o construtor da superclasse ComissionEmployee, super deve ser sempre a primeira instrução
    baseSalary = salary;    
 }
  
  public void setBaseSalary(double salary)
  {
    baseSalary = salary < 0.0 ? 0.0 : salary; 
 }
  
  public double getBaseSalary()
  {
    return baseSalary;
 }
  
  // Calcula os lucros sobrescrevendo o método earnings() da superclasse
  @Override
  public double earnings()
  {
    return getBaseSalary() + super.earnings(); //super.earnings() chama o método da superclasse (antes de ser sobrescrito)
 }
  
  // Sobrescreve o metodo toString()
  @Override
  public String toString()
  {
    return String.format("%s \nSalario base: %.2f\n", super.toString(), getBaseSalary());
 }

}
~~~

#### Ex.: inheritance - File BasePlusComissionEmployeeTest.java

~~~java
public class BasePlusComissionEmployeeTest 
{
  public static void main(String[] args)
  {
    // Instanciando um objeto da classe ComissionEmployee
    ComissionEmployee employee = new ComissionEmployee("Mr Bean", 0.0, 0.5);
    
    // Instanciando um objeto da subclasse de ComissionEmployee
    BasePlusComissionEmployee employeePlus = new BasePlusComissionEmployee ("Mauricio", 4000.0, 0.7, 8000.0);
    
    System.out.printf("Informações do funcionário 1 \n%s\n\n", employee.toString());
    System.out.printf("Informações do funcionário 2 \n%s", employeePlus.toString());
 }
}
~~~

### Polymorphism

#### Ex.: polymorphism - File Employee.java
~~~java
// Classe abstrata: Não podemos instanciar um objeto a partir dela
// Criamos a classe abstrata Employee para representar o conceito geral de um funcionário.
// Exemplo de folha de pagamento em que temos 4 tipos de funcionários que recebem salários 
// de modo diferente. A classe de cada tipo irá estender Employee e sobrescrever seu método abstrato
public abstract class Employee 
{
  private String firstName;
  private String cpf;
  
  // Construtor com dois argumentos
  public Employee(String fn, String c)
  {
    firstName = fn;
    cpf = c;
 }
  
  public void setFirstName(String fn)
  {
    firstName = fn;
 }
  
  public String getFirstName()
  {
    return firstName;
 }
  
  public void setCpf(String c)
  {
    cpf = c;
 }
  
  public String getCpf()
  {
    return cpf;
 }
  
  // Sobrescrevendo o método toString() da classe Object
  @Override // Lembrando, usamos isso para garantir que o método seja sobrescrito e não sobrecarregado
  public String toString()
  {
    return String.format("name: %s \nCpf: %s", getFirstName(), getCpf());
 }
  
  // Método abstrato que será sobrescrito por subclasses de Employee concretas
  // Declaramos esse método como abstrato pois cada subclasse terá uma implementação própria para ele
  public abstract double earnings(); // Não implementamos aqui! 
}
~~~

#### Ex.: polymorphism - File SalariedEmployee.java
~~~java
// Classe concreta que estende a classe abstrata Employee
// Este é um empregado assalariado. 
public class SalariedEmployee extends Employee
{
  private double salary;
  
  public SalariedEmployee(String n, String c, double s)
  {
    super(n, c); // passa para o construtor de Employee
    salary = s; 
 }
  
  public void setSalary(double sal)
  {
    salary = sal < 0.0 ? 0.0 : sal;
 }
  
  public double getSalary()
  {
    return salary;
 }
  
  // Calcula os rendimentos: Sobrescreve o método earnings de Employee
  @Override
  public double earnings()
  {
    return getSalary();
 }
  
  @Override
  public String toString()
  {
    return String.format("Empregado assalariado: \n%s \nSalario: %.2f", super.toString(), getSalary());
 }

}
~~~

#### Ex.: polymorphism - File HourlyEmployee.java
~~~java
// Este é um empregado que ganha por hora
public class HourlyEmployee extends Employee
{
  private double wage; // salário por hora
  private double hour; // horas trabalhadas
  
  // Construtor
  public HourlyEmployee(String n, String c, double w, double h)
  {
    super(n, c); // Passa para o construtor de Employee
    setWage(w);
    setHour(h);    
 }
  
  public void setWage(double w)
  {
    wage = w < 0.0 ? 0.0 : w;
 }
  
  public double getWage()
  {
    return wage;
 }
  
  public void setHour(double h)
  {
    hour = h < 0.0 ? 0.0 : h;
 }
  
  public double getHour()
  {
    return hour;
 }
  
  // Sobrescreve método abstrato earnings de Employee
  @Override
  public double earnings()
  {
    return getWage()*getHour();
 }
  
  @Override
  public String toString()
  {
    return String.format("Empregado ganha por hora: \n%s \nValor hora: %.2f \nNum horas: %.2f", 
                super.toString(), getWage(), getHour());
 }
  

}
~~~

#### Ex.: polymorphism - File ComissionEmployee.java
~~~java
// Este é um empregado que recebe comissão
public class ComissionEmployee extends Employee
{
  private double grossSales; // Vendas brutas
  private double comission; // valor entre 0 e 1
  
  // Construtor
  public ComissionEmployee(String n, String c, double g, double comis)
  {
    super(n, c); // Passa para o construtor de Employee
    setGrossSales(g);
    setComission(comis);
 }
  
  public void setGrossSales(double g)
  {
    grossSales = g < 0.0 ? 0.0 : g;    
 }
  
  public double getGrossSales()
  {
    return grossSales;
 }
  
  public void setComission(double c)
  {
    if(c > 0.0 && c <= 1.0)
      comission = c;
    else
      comission = 0.0;
 }
  
  public double getComission()
  {
    return comission;
 }
  
  @Override
  public double earnings()
  {
    return getComission() * getGrossSales();
 }
  
  @Override
  public String toString()
  {
    return String.format("Comissionado: \n%s \nComissão: %.2f \nVendas Brutas: %.2f ",  
         super.toString(), getComission(), getGrossSales());
 }

}
~~~

#### Ex.: polymorphism - File BasePlusComissionEmployee.java
~~~java
// Classe estende a classe ComissionEmployee (subclasse de Employee)
public class BasePlusComissionEmployee extends ComissionEmployee
{
  private double baseSalary;
  
  public BasePlusComissionEmployee(String name, String cpf, double sales, double comission, double salary)
  {
    super(name, cpf, sales, comission);
    setSalary(salary);
 }
  
  public void setSalary(double s)
  {
    baseSalary = s < 0.0 ? 0.0 : s;
 }
  
  public double getSalary()
  {
    return baseSalary;
 }
  
  @Override
  public double earnings()
  {
    // Calcula os rendimentos conforme superclasse ComisisonEmployee
    // e soma ao salário
    return super.earnings() + getSalary();
 }
  
  @Override
  public String toString()
  {
    return String.format("Empregado com salário e %s \nSalário: %.2f ", 
        super.toString(), getSalary());
 }
}
~~~

#### Ex.: polymorphism - File PayrollSystemTest.java
~~~java
public class PayrollSystemTest 
{
  public static void main(String[] args)
  {
    // Cria objetos de sublcasse
    SalariedEmployee salariedEmployee = new SalariedEmployee("Newnton", "000.000.170-81", 15000.00);
    HourlyEmployee hourlyEmployee = new HourlyEmployee("Ohm", "000.000.200-80", 50.00, 80.00);
    ComissionEmployee comissionEmployee = new ComissionEmployee("Faraday", "021.247.170-80", 500.00, 0.75);
    BasePlusComissionEmployee basePlus = new BasePlusComissionEmployee("Tesla", "0021.247.170-82", 750.00, 0.65, 9000.00);
    
    System.out.println("Empregados processados individualmente: \n");
    
    System.out.printf("%s \nVencimentos: %.2f \n\n", salariedEmployee, salariedEmployee.earnings() );
    System.out.printf("%s \nVencimentos: %.2f \n\n", hourlyEmployee, hourlyEmployee.earnings());
    System.out.printf("%s \nVencimentos: %.2f \n\n", comissionEmployee, comissionEmployee.earnings());
    System.out.printf("%s \nVencimentos: %.2f \n\n", basePlus, basePlus.earnings());
    
    
    // Cria um array de Employee com 4 elementos
    Employee[] employees = new Employee[ 4 ];
    
    employees[0] = salariedEmployee;
    employees[1] = hourlyEmployee;
    employees[2] = comissionEmployee;
    employees[3] = basePlus;
    
    System.out.println("\nEmpregados processados Polimorficamente:");
    
    // Processa genericamente cada elemento de employee
    for(Employee currentEmployee : employees)
    {
      System.out.printf("%s \nVencimentos: %.2f \n\n", currentEmployee, currentEmployee.earnings());
      
      // Vamos, ainda, dar um aumento de 10% ao salário do empregado comissionado 
      // Operador instanceof para determinar se esse Employee é o BasePlusComissionEmployee
      if(currentEmployee instanceof BasePlusComissionEmployee)
      {
        // Downcast da referência de Employee (currentEmployee) para ComissionEmployee (happyEmployee)
        BasePlusComissionEmployee happyEmployee = (BasePlusComissionEmployee) currentEmployee;
        
        happyEmployee.setSalary(happyEmployee.getSalary() * 1.10);
        System.out.printf("****Com créscimo de 10%%: Salário: %.2f\n\n", happyEmployee.getSalary());
     }
   }
        
    // Obtendo o name e o tipo de cada objeto
    for(int i = 0; i < employees.length; i++)
      System.out.printf("Empregado %d é um %s \n", i, employees[ i ].getClass().getName());
      // Método getClass() pertence à classe Object. Retorna um objeto do tipo Class que possui um método getName() 
 }

}
~~~

### Abstract Classes

~~~java

~~~

### Abstract Methods

~~~java

~~~

### Interfaces

#### Ex.: interfaces - File Payable.java
~~~java
// Interface 
public Interface Payable 
{
  // Métodos de Interface são sempre public e abstract 
  // não sendo necessário declará-los assim.
  double getPaymentAmount(); // Não deve ser implementada aqui! 
}
~~~

#### Ex.: interfaces - File Invoice.java
~~~java
// Classe que implementa Payable
public class Invoice implements Payable
{
  private String partNumber;
  private String partDescription;
  private int quantity;
  private double pricePerItem;
  
  // Construtor
  public Invoice(String part, String description, int count, double price)
  {
    partNumber = part;
    partDescription = description;
    quantity = count;
    pricePerItem = price;
 }
  
  public void setPartNumber(String part)
  {
    partNumber = part;
 }
  
  public String getPartNumber()
  {
    return partNumber;
 }
  
  public void setPartDescription(String description)
  {
    partDescription = description;
 }
  
  public String getPartDescription()
  {
    return partDescription;
 }
  
  public void setQuantity(int count)
  {
    quantity = count < 0 ? 0 : count;
 }

  public int getQuantity()
  {
    return quantity;
 }
  
  public void setPricePerItem(double price)
  {
    pricePerItem = price < 0.0 ? 0.0 : price;
 }
  
  public double getPricePerItem()
  {
    return pricePerItem;
 }
  
  // Retorno da representação String do objeto Invoice
  @Override
  public String toString()
  {
    return String.format("%s: \n%s: %s (%s) \n%s: %d \n%s: $%,.2f", 
        "invoice", "part number", getPartNumber(), getPartDescription(), 
        "quantity", getQuantity(), "price per item", getPricePerItem());
 }
  
  // Método requerido para executar o contrato com a Interface Payable
  @Override
  public double getPaymentAmount()
  {
    return getQuantity() * getPricePerItem();
 }
}
~~~

#### Ex.: interfaces - File Employee.java
~~~java
// Superclasse abstrata Employee implementa Payable
public abstract class Employee implements Payable
{
  private String firstName;
  private String lastName;
  private String socialSecurityNumber;
  
  // Construtor com dois argumentos
  public Employee(String first, String last, String ssn)
  {
    firstName = first;
    lastName = last;
    socialSecurityNumber = ssn;
 }
  
  public void setFirstName(String fn)
  {
    firstName = fn;
 }
  
  public String getFirstName()
  {
    return firstName;
 }
  
  public void setLastName(String last)
  {
    lastName = last;
 }
  
  public String getLastName()
  {
    return lastName;
 }
  
  public void setSocialSecurityNumber(String ssn)
  {
    socialSecurityNumber = ssn;
 }
    
  public String getSocialSecurityNumber()
  {
    return socialSecurityNumber;
 }
  
  // Sobrescrevendo o método toString() da classe Object
  @Override // Lembrando, usamos isso para garantir que o método seja sobrescrito e não sobrecarregado
  public String toString()
  {
    return String.format("%s %s \nsocial security number: %s",
        getFirstName(), getLastName(), getSocialSecurityNumber());
 }
  
  // grade: Não implementamos o método Payable getPaymentAmount aqui, mas essa
  // classe deve ser declarada abstrata para evitar erro de compilação. 
}
~~~

#### Ex.: interfaces - File SalariedEmployee.java
~~~java
// Estende a classe Employee que implementa a Interface Payable
public class SalariedEmployee extends Employee
{
  private double weekSalary;
  
  public SalariedEmployee(String first, String last, String ssn, double salary)
  {
    super(first, last, ssn);
    weekSalary = salary;
 }
  
  public void setWeekSalary(double salary)
  {
    weekSalary = salary < 0.0 ? 0.0 : salary;
 }
  
  public double getWeekSalary()
  {
    return weekSalary;
 }
  
  // Calcula vencimentos; Implementa o método Payable da 
  // Interface que era abastrata na superclasse Employee
  @Override
  public double getPaymentAmount()
  {
    return getWeekSalary();
 }
  
  @Override
  public String toString()
  {
    return String.format("Salaried employee: %s\n%s: $%,.2f",
        super.toString(), "weekly salary", getWeekSalary());
 }

}
~~~

#### Ex.: interfaces - File PayableInterfaceTest.java
~~~java
// Testa a Interface Payable
public class PayableInterfaceTest 
{
  public static void main(String[] args)
  {
    // Cria array Payable de quatro elementos
    Payable[] payableObjects = new Payable[ 4 ];
    
    // Preenche array com objetos que implementam Payable
    payableObjects[ 0 ] = new Invoice("01234", "seat", 2, 375.00 );
    payableObjects[ 1 ] = new Invoice("56789", "tire", 4, 79.95 );
    payableObjects[ 2 ] = new SalariedEmployee("John", "Smith", "111-11-1111", 800.00);
    payableObjects[ 3 ] = new SalariedEmployee("Lisa", "Barnes", "888-88-8888", 1200.00);
    
    System.out.println("Invoices and Employees processed polymorphically: \n");
    
    // Processa genericamente cada elemento no array payableObjects
    for(Payable currentPayable : payableObjects)
    {
      System.out.printf("%s \n%s: $%,.2f\n\n", currentPayable.toString(),
          "payment due", currentPayable.getPaymentAmount());
   }
 }
}
~~~

### Collections 

~~~java

~~~

### Enums

#### Ex.: 
~~~java
import java.util.Random;

//Para exemplificar o uso de enum.
//Regras do jogo: Dado = (1) => vence, (2, 3 ou 4 ou 5) => Continua, (6) => perde
public class EnumGame {
  //Cria gerador de números aleatórios para uso no método rollDice
  private static final Random randomNumbers = new Random();
  
  //Enumerações com constantes que representam o status do jogo
  private enum Status {CONTINUE, WON, LOST};
  
  private static final int UNITARIO = 1; //Exemplo de constante
  private static final int SEXTARIO = 6; //Exemplo de constante
  
  //Joga uma partida
  public void play() {
    Status gameStatus; //Variável do tipo Status. Pode conter somente CONTINUE, WIN ou LOST
    
    int dice = rollDice(); //rola o dado
    
    switch(dice) {
      case UNITARIO:
        gameStatus = Status.WON; // 1 ganha
        break;
      case SEXTARIO:
        gameStatus = Status.LOST; // 6 perde
        break;
      default:
        gameStatus = Status.CONTINUE;
        break;
   }
    
    if (gameStatus == Status.CONTINUE)
      System.out.println("Ninguem ganhou.");
    else if (gameStatus == Status.WON)
      System.out.println("Tu ganhou.");
    else
      System.out.println("Tu perdeu");    
 }
  
  public int rollDice()
  {
    int die = 1 + randomNumbers.nextInt(6); //Joga o dado 1 vez
    System.out.println("dice do dado: " + die);
    return die;  
 }
}


//Arquivo EnumTest.java
public class EnumGameTest {
  public static void main(String[] args)
  {
    EnumGame game = new EnumGame();
    game.play();
 }
}
~~~

#### Ex.: 
~~~java
/* File EnumTest.java */
public enum Book {
  //Declara constantes do tipo enum
  PHPOOP("PHP orientado a objetos", "2018-01"),
  JSOOP("JavaScript orientado a objetos", "2018-01"),
  JAVAOOP("Java orientado a objetos", "2018-02");
  
  private final String title;
  private final String year;
  
  // Construtor enum - não recebe public
  Book(String bookTitle, String y) {
    title = bookTitle;
    year = y; 
 }
  
  // Método para acessar titulo
  public String getTitle() {
    return title;
 }
  
  // Método para acessar ano
  public String getYear() {
    return year;
 }
}

/* File EnumTest.java */
public class EnumTest 
{
  public static void main(String[] args)
  {
    for(Book book : Book.values())
      System.out.printf("Livro: %s \nAno: %s\n\n", book.getTitle(), book.getYear());
 }
}
~~~

### ArrayLists

#### Ex.: File TestaTudo.java

~~~java
import java.util.*; 
public class TestaTudo {
  public static void main(String[] args) {
    List <String> l1 = new ArrayList<String>();
    List <Integer> l2 = new LinkedList<Integer>();
    
    for(int i = 0; i < 5; i++) {
      l1.add("sou o elemento " + i);
      l2.add(i, new Integer(i));
   }
    
    // exibindo ArrayList de Strings
    for(int i = 0; i < l1.size(); i++)
      System.out.println(l1.get(i)); // ArrayLists são indexados por números
    
    // exibindo lista ligada de inteiros
    for(Integer obj: l2)
      System.out.println(obj);      
    System.out.println(l2.contains(1));      
 }
}
~~~

#### Ex.: Class Araay - File ArraysManipulations

~~~java
import java.util.ArrayList;
public class ArraysManipulations {
  public static void main(String[] args) {
    
    // Só pode ser usado com tipos não primitivos: String, classes, etc
    // Declara nameAlunos como uma coleção que só pode armazenar Strings: Classe genérica
    ArrayList< String > linguagens = new ArrayList< String >();
    
    linguagens.add("CSS3");
    linguagens.add(0, "HTML5"); //insere no índice zero
    linguagens.add("PHP"); 
    linguagens.add("C++");
    linguagens.add("Phyton");
    
    linguagens.remove(3); // Remove C++
    linguagens.remove("Phyton");
    
    boolean contemPHP = linguagens.contains("Python"); // Retorna FALSE
    
    String elemento = linguagens.get(1); // Retorna elemento de índice = 1
    
    int indiceElemento = linguagens.indexOf("CSS3");
    
    int tamArray = linguagens.size();
    
        // isEmpty() retorna TRUE se o ArrayList for vazio 
    
    // Ver método linguagens.trimToSize() 
    
      // Exibe array com for aprimorada :D
    for(String value : linguagens)
      System.out.println(value);
    
    linguagens.clear(); // Remove todos os elementos do ArrayList    
 }
}
~~~

### LinkedList

~~~java

~~~

### Iterator

~~~java

~~~

### Generic Classes 

~~~cpp

~~~

### Generic Methods 

~~~cpp

~~~

## Exceptions

~~~java

~~~

## Files

### Binary Files

~~~java

~~~

### Text Files

~~~java

~~~

## Objects Serialization 

~~~java

~~~

## Packages

- There must be only one package declaration in a file.

#### Ex.: packages - File Time1.java

~~~java
package PacoteTeste; 

public class Time1 {
  // Variáveis de instância
  private int hour;
  private int minute;
  private int second;

  // Não declaramos construtor, logo: Utiliza o construtor padrão que inicializa variáveis de instância com valores padrão
  
  public void setTime(int h, int m, int s) {
    hour = ((h >= 0 && h < 24) ? h : 0); // Poderia fazer this.hour = h; 
    minute = ((m >= 0 && m < 60) ? m : 0); // this.minute = m;
    second = ((s >= 0 && s < 60) ? s : 0); // this.second = s;     
 }
  
  public String toString() {
    return String.format("%02d : %02d : %02d", hour, minute, second);
 }
}
~~~

#### Ex.: packages - File Time1PackageTest.java

~~~java
import PacoteTeste.Time1;
// Classe está no pacote padrão! 
public class Time1PackageTest {
  public static void main(String[] args) {
    Time1 time = new Time1(); 
    time.setTime(16, 56, 42);
    System.out.println(time.toString());
 }
}
~~~

## Output

- %s 
- %d 
- %f - ex.: %.2f  
  - media = ( 2.0f * a + 3.0f * b  + 5.0f * c ) / 10.0f;

~~~java
System.out.print("Txt");
System.out.println("Txt line break");
System.out.println();                   // line break
System.out.printf("Age: %d", age);      // formatting
~~~

### Special Characters

- \n  \t  \r  \\   

## Input

~~~java
Scanner input = new Scanner (System.in);   
int numero = input.nextInt();
double valor = input.nextDouble();         
String nome = input.nextLine();              // read line until press enter
String nome = input.next();                  // read word until press space

/* Ex.: */
import java.util.Scanner;
class myClass {
  public static void main(String[] args) {

    Scanner input = new Scanner(System.in); // input é um objeto da classe Scanner

    System.out.println("Enter name, age and salary:");

    // String input
    String name = input.nextLine(); // outros: nextBoolean() nextByte() nextDouble() nextFloat() nextInt() nextLine() nextLong() nextShort()

    // Numerical input
    int age = input.nextInt();
    double salary = input.nextDouble();

    // Output input by user
    System.out.println("Name: " + name); 
    System.out.println("Age: " + age); 
    System.out.println("Salary: " + salary); 
  }
}
~~~

## How To

### How To: Random numbers

~~~java
import java.util.Random;
public class RandomIntegers {
  public static void main(String[] args) {
    Random randomNumbers = new Random();
    int dice;     
    dice = 1 + randomNumbers.nextInt(6); 
    System.out.println(dice);
 }
}
~~~

### HowTo 2

~~~java

~~~

## GUI

- [Examples](#)

## Links

- [#](#)
- [#](#)
- [#](#)

## To be continued

- ...

