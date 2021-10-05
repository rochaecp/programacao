# Php

## Run 

~~~shell
php -S localhost:8888
  
# on browser:
localhost:8888/index.php
~~~

## Syntax

~~~php

~~~

## Comments

~~~php
// comment 
/* comment */ 
# comment 
~~~

## Data Types

### Basic Data Types

### Derived Data Types

## Modifiers

- short
- long
- signed
- unsigned
- static

## Variables

~~~php
$name = "Maurício";  
$my_bool = TRUE;  
$b = &$a;        
$my_bool = TRUE;   
$num = 1234;      
$num = 0123;      
$num = 0x1A;      
$num = 4e23;  

$var = 'name';
$$var = 'maria';
echo $name; 
~~~

## Casting

~~~php

~~~

## Constants

~~~php
define("PI", 3.1413); 
echo "PI = " .  PI ; 
~~~

## Operators

- Arithmetic operators: + - * / % ++ -- 
- Assignment operators: = += -= *= /= %= &= |= ^= >>= <<=
- Comparison operators: == === != <> > < >= <=
- Logical operators: && || ! and or xor
- Bitwise operators: & | ^ << >> ~

## Strings

~~~php
$var1 = "my string 1";  
$var2 = 'my string 2';   
print "$var<br/>"; 
print '$var<br/>'; 
print "Hi: " . $var;


$text = <<<MYKEY
  line 1 <br>
  line 2 <br>
  line 3 <br>
MYKEY;

print strlen($my_str);     
print strtoupper($my_str); 
print strtolower($my_str); 
print substr($my_str, 0, 5); 
print strpos($my_str, "aaa"); 
print stripos($my_str, "aaa"); 
print str_replace("aaa", "bbb", $my_str); 
print str_ireplace("aaa", "bbb", $my_str); 
$vector = str_word_count ($my_str, 1) ;
$vector = explode(" ", $my_str);    
$vector = str_split($my_str);      
print implode(" ", $vector);        
print ucfirst($my_str);          
print ucwords($my_str);        
print substr_count($my_str, "aaa");  
print str_word_count($my_str, 0);     
print str_repeat($my_str, 5);             
print str_pad($my_str, $tam, "#", STR_PAD_LEFT);  
print wordwrap($my_str, 10, "<br/>\n", false);  
print chr(61); 
print ord('a'); 
print strrev($my_str);
~~~

## Math 

~~~php

~~~

## Date 

~~~php
gedgdate_default_timezone_set('America/Sao_Paulo'); 
$date = date("l - d / m / Y");  
$hour = date("H : i : s ");
echo "Data: $date <br/>";
echo "Hora: $hour"; 
~~~

## Booleans

~~~php

~~~

## If...Else

~~~php
if ($my_bool)
  echo "True";
else
  echo "False";
~~~

## Conditional Operator 

~~~php
$answ = ($grade >= 6 )  ? 'Ok' : 'not Ok';
~~~

## Switch

~~~php
switch ($my_op) {
  case "a": 
    echo "a"; 
    break;
  case "b": 
    echo "b"; 
    break;
  default: 
    echo "c"; 
    break;  
}   
~~~

## While Loop

~~~php
$num = 0;
while ($num <= 10) {
  echo "$num <br/>";
  $num = $num + 1;
}
~~~

## Do...While Loop

~~~php php

~~~

## For Loop

~~~php
for ($num = 0; $num <= 10; $num++)
  echo "$num ";
~~~

## ForEach Loop

~~~php
$fruits = array ("orange", "banana", "apple");
foreach ($fruits as $var)
  echo "$var <br>";
~~~

## Break

~~~php

~~~

## Continue

~~~php

~~~

## Arrays

~~~php
$names = array("Mauricio", "Maria", "Jose");
echo $names[1];

$vector = array('Mauricio', 'Maria', 'Joana');           
$vector = array(0 => 'Mauricio', 1 => 'Maria', 2 => 'Joana'); 

$vector[] = 'maria'; 
$vector[] = 'jose';
$vector[] = 'antonia';
print_r($vector);

$vector = array('name' => 'Mauricio', 'age' => 28, 'weight' => 81.2);

$vector['name'] = 'Mauricio';
$vector['age'] = 28;
$vector['weight'] = 81.2;

$Persons = array(
          'Person1' => array('name' => 'mauricio', 'age' => 28),
          'Person2' => array('name' => 'maria', 'age' => 61),
          'Person3' => array('name' => 'joana', 'age' => 84) 
       );
print $Persons['Person1']['name'];  

$Persons['Person1']['name']  = 'mauricio';
$Persons['Person1']['age'] = 28;
$Persons['Person2']['name'] = 'maria';
$Persons['Person2']['age'] = 61;

foreach($Persons as $p => $attributes  {
  print "Person: $p <br>";
  foreach($attributes as $a => $var)
    print "$a: $var <br>";
}

var_dump($vector); 
print_r ($vector); 
var_export($vector);

print count($vector);       
array_push($vector, 10);        
array_pop($vector);        
array_shift($vector);       
array_unshift($vector, 10);     
$vector = array_pad($vector, 10, 1); 
$vector = array_reverse($vector);   
$vector = array_merge($vet1, $vet2); 
$indices = array_keys($vector);   
$ind = array_keys($vector, 'aaa');  
$vares = array_values($vector); 
$vector = array_slice($vector, 2, 3); 
print in_array(10, $vector);     
sort($vector);             
rsort($vector);           
asort($vector);          
arsort($vector);             
ksort($vector);          
krsort($vector);             
$vector = explode('/', $my_str); 
$my_str = implode('*', $vector); 
$vector = range(0, 1, 0.1);      
unset($vector[2]); 
~~~

## Pointers

~~~php

~~~

## Functions

~~~php
function my_func ($a, $b) {
  return $a + $b;
}
~~~

#### Ex.: functions with global var

~~~php
$var = 1;
function my_func ($i) {
  global $var;
  $var += $i;
}
my_func (1);
echo $var;
~~~

#### Ex.: functions with static var

~~~php
function my_func () {
  static $var;
  $var += 1;
  echo $var."<br>";    
}
my_func();
my_func();
~~~

### Function Parameters

- Formal parameters.
- Actual function parameters.

#### Ex.: functions with default value for argument 

~~~php
function my_func ($var = 10) {
  echo $var; 
}
my_func();   
my_func (50);
~~~

#### Ex.: functions with variable amount of arguments 

~~~php
function my_func() {
  $args = func_get_args();
  $amount = func_num_args();
  
  foreach ($args as $var)
    echo "Hi $var <br/>";
}
my_func ("Mauricio", "Maria", "Jose");
~~~

#### Ex.: Parameters passed by reference

~~~php
function my_func (&$var, $i) {
    $var += $i;
}
$a = 0;
my_func ($a, 10);
echo $a; 
~~~

### Function Overloading

~~~php

~~~

## Scope

~~~php

~~~

## Recursion

#### Ex.: factorial

~~~php
function factorial ($num) {
  if ($num == 1)
    return $num;
  else
    return $num * factorial ($num - 1);
} 
~~~

## Structures 

~~~php

~~~

## Lists

~~~php

~~~

## Tuples

~~~php

~~~

## Sets

~~~php

~~~

## Dictionaries

~~~php

~~~

## Trees

~~~php

~~~

## Hash Tables

~~~php

~~~

## Graphs

~~~php

~~~

## OOP

#### Functions to manipulate objects 

~~~php
$vector = get_class_methods('Person');  
$vector = get_class_vars('Person');    
$vector = get_object_vars($object);   
$my_str = get_class($object);   
$my_str = get_parent?_class($obj); 
$bool = is_subclass_of($obj,'my_class');
$bool = method_exists($obj,'my_method'); 
call_user_func(array($obj, 'my_method')); 
~~~

### Classes/Objects

~~~php
class Person {
  public $name;
  function myFunc() {
    echo "Hello {$this->name}";
  }
}
$object = new Person;
$object->name = "Mauricio";
$object->myFunc();
~~~

### Class Attributes

~~~php

~~~

### Class Methods

~~~php

~~~

### Class Method Overloading

~~~php

~~~

### Class Method final

~~~php

~~~

### Constructors

~~~php

~~~

### Access Specifiers/Modifiers

~~~php

~~~

### Static Methods

~~~php

~~~

### Static Variables

~~~php

~~~

### Encapsulation

~~~php

~~~

### Association

~~~php

~~~

### Composition

~~~php

~~~

### Aggregation

~~~php

~~~

### Inheritance

~~~php

~~~

### Polymorphism

~~~php

~~~

### Abstract Classes

~~~php

~~~

### Abstract Methods

~~~php

~~~

### Interfaces

~~~php

~~~

### Collections 

~~~php

~~~

### Enums

~~~php

~~~

### ArrayLists

~~~php

~~~

### LinkedList

~~~php

~~~

### Iterator

~~~php

~~~

### Generic Classes 

~~~cpp

~~~

### Generic Methods 

~~~cpp

~~~

## Exceptions

~~~php

~~~

## Files

~~~php
echo getcwd();          
is_file($my_file);  
mkdir($nameDir, 0777);     
chdir("dir/img");     
rmdir("dir");       
opendir($dir);     
closedir($dir);    
readdir(opendir('/')); 
~~~

### Binary Files

~~~php

~~~

### Text Files

#### Ex.: Files - read - fgets

~~~php
$my_file = fopen("my_fileuivo.txt", "r");
while(!feof($my_file)) {
  $buffer = fgets ($my_file, 4096); 
  echo $buffer."<br/>";
}
fclose($my_file); 
~~~

#### Ex.: Files - read - file_get_contents

~~~php
echo file_get_contents ("text.txt");
~~~

#### Ex.: Files - read - file 

~~~php
$my_file = file ("text.txt");
foreach ($my_file as $var)
  echo $var."<br/>"; 
~~~

#### Ex.: Files - write - fwrite

~~~php
$my_file = fopen ("text.txt", "a");
fwrite ($my_file, "\r\nHello"); 
fclose ($fp); 
~~~

#### Ex.: Files - write - file_put_contents

~~~php
file_put_contents("text.txt", "text \ntext \ntext"); 
~~~

#### Ex.: Files - copy

~~~php
$my_file = "text.txt";
$my_file2= "copy_text.txt";
copy ($my_file, $my_file2);
~~~

#### Ex.: Files - rename

~~~php
$file1 = "text.txt";
$file2 = "teste.txt";
rename ($file1, $file2);
~~~

#### Ex.: Files - delete

~~~php
$my_file = "my_file.txt";
unlink($my_file);
~~~

#### Ex.: Files - exists

~~~php
$my_file = "text.txt";
if (file_exists ($my_file)
  echo "$my_file exists!";
~~~

## Directories 

#### Ex.: 

~~~php
$dir = getcwd();
if (is_dir($dir)) {
  $ident = opendir($dir);
  while ($my_file = readdir ($ident) {
    echo $my_file."<br/>";
  }
  closedir($ident);
}
~~~


## Objects Serialization 

~~~php

~~~

## Packages/Modules

~~~php

~~~

## Output

~~~php
echo  "Name = " . $Name . "<br>"; 
echo  "Name =  $Name <br>";     
print("Name = " . $Name . "<br>");  
printf("Numero = %.3f", $num);    
echo number_format ($var, 2);  
print_r($vector);          
var_dump($vector);         
~~~

### Special Characters

~~~php

~~~

## Input

~~~php

~~~

## How To

### How To: Random numbers

~~~php

~~~

### How To mysqli - Query

~~~php
$conn = mysqli_connect('localhost', 'root', '', 'my_training');

if(!$conn)
  echo "error";  
  
$sql = "select * from myusers ORDER BY name";
$res = mysqli_query($conn, $sql) or die("Erro"); 

$var = mysqli_num_rows($res);
echo "total = $var <br><br>";

while($data = mysqli_fetch_assoc($res)) {  
  echo "id: "   . $data['id']      . '<br>';
  echo "name: "   . $data['name']   . '<br>';
  echo "email: "   . $data['email']   . '<br><br>';     
}

mysqli_close($conn);
~~~

### How To mysqli - insert

~~~php
$conn = mysqli_connect('localhost', 'root', '', 'treinophp');

$sql = "INSERT INTO myusers (name, email) VALUES ('Marieta', 'marieta@hotmail.com')";
mysqli_query($conn, $sql); 

mysqli_close($conn);
~~~

### How To PDO - query

~~~php
try { 
  $conn = new PDO('mysql:host=localhost;port=80;dbname=treinophp', 'root', '');
  $my_query = $conn->query("SELECT * FROM myusers");
  if($my_query) {   
    while($row = $my_query->fetch(PDO::FETCH_OBJ)) {
      echo "name = " . $row->name  . "<br>\n";          
      echo "name = " . $row->email . "<br><br>\n";          
    }    
  }     
  $conn = null;
}
catch(PDOException $e) { 
  print("Erro! \n");
  die();
}
~~~

### How To PDO - query

~~~php
try { 
  $conn = new PDO('mysql:host=localhost;port=80;dbname=treinophp', 'root', ''); 
  $my_query = $conn->query("SELECT * FROM myusers ORDER BY name");
  if($my_query) {   
    foreach($my_query as $row) {    
      echo "name = " . $row['name']  . "<br>\n";          
      echo "name = " . $row['email'] . "<br><br>\n";          
    }    
  }  
  $conn = null;
}
catch(PDOException $e) { 
  print("Error! \n");
  die();
}
~~~

### How To ...

~~~php

~~~

## GUI

- [Examples](#)

## Links

- [W3schools](https://www.w3schools.com/php/default.asp)    
- [Doc](http://php.net/manual/pt_BR/)          
- [Rightway](http://br.phptherightway.com/) 


## To be continued

- [Forms and DBs](https://www.youtube.com/watch?v=4tBeeMcw2sM)
- PHP PDO!!    
- Design Pattern
- Query Object

