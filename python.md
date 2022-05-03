# Python

- [Built in Functions Reference](https://www.w3schools.com/python/python_ref_functions.asp)

## The Python Command Line

~~~shell
python3 nameFile.py

python3 -V ou python3 --version

python3 # run on terminal
>>> commands here
>>> exit() # Ctrl + d
~~~

## Syntax

- Python uses indentation to indicate a block of code.

~~~python
 if 5 > 2:
  print("Five is greater than two!")
~~~

## Comments

~~~python
# comment

"""
comments - multiline string
"""

'''
comments - multiline string
'''
~~~

## Variables

- In Python, variables are created when you assign a value to it.
- Python has no command for declaring a variable.
- Multi Words Variable Names:
  - Camel Case
  - Pascal Case
  - Snake Case

~~~python
x = 2     # int
x = 2.1   # float, ex.: 35e3 ou 12E4
x = 1j    # complex
x = True  # bool: True ou False

# One Value to Multiple Variables
x = y = z = "Orange"

# Many Values to Multiple Variables
x, y, z = "Orange", "Banana", "Cherry"

# Unpack a Collection
x, y, z = fruits # fruits = ["apple", "banana", "cherry"]
~~~

## Data Types

### Built-in Data Types 

- Text Type: 	    str
- Numeric Types: 	int, float, complex (ex.: 1j)
- Sequence Types: list, tuple, range
- Mapping Type: 	dict
- Set Types: 	    set, frozenset
- Boolean Type: 	bool
- Binary Types: 	bytes, bytearray, memoryview

> to store collections of data: list, tuple, set and dictionary

~~~python
myType = type(var)
~~~

## Numbers

- There are three numeric types in Python:
 - int
 - float
 - complex

~~~python
x = 1    # int
y = 2.8  # float
z = 1j   # complex
~~~

## Casting

- If you want to specify the data type of a variable, this can be done with casting.

~~~python
myVar = int(var)
myVar = float(var)
myVar = str(var)
myVar = bool(var)
myVar = complex(var)
~~~

## Strings

- Strings are Arrays of bytes representing unicode characters.
- The String 'hello' is the some that "hello".
- Python does not have a character data type, a single character is simply a string with a length of 1.
- [String Methods Reference](https://www.w3schools.com/python/python_ref_string.asp)

~~~python
myString = "abcdefg"
myString = 'abcdefg'
myString = "abcdefg" + "hijk" # concatenation

firstCharacter = myString[0]
size = len(string)
myUnicode = ord("A") # integer - Unicode of character
myString = chr(35)  # string - character whose Unicode code point is the integer
myBool = "a" in myString # checking string
myBool = "a" not in myString # Check if NOT
myBool = "aaa" < "bbb"   # True
myBool = "aaa" == "bbb"  # False

# multiline string
a = """Mauricio
Rocha
"""

# Looping Through a String
for x in myString:
  print(x)

# Slicing Strings
mySlicing = myString[-1] # the last
mySlicing = myString[2:5] # from position 2 to position 5 - not included
mySlicing = myString[:5] # from the start
mySlicing = myString[2:] # to the end
mySlicing = myString[-3:] # last 3

# Modify Strings - All string methods returns new values. They do not change the original string.
myString = myString.upper()
myString = myString.lower()
myString = myString.replace("a", "x")
my_list = umaString.split(" ")
myString = myString.strip() # removes any whitespace from the beginning or the end
~~~

## Booleans

- Booleans represent one of two values: True or False.
- Any string is True, except empty strings.
- Any number is True, except 0.
- Any list, tuple, set, and dictionary are True, except empty ones.
- Values to False: (), [], {}, "", the number 0, the value None, False.

~~~python
# The following will return True:
myBool = bool(True) # or True
myBool = bool("Hello")
myBool = bool(15)

# The following will return False:
myBool = bool(False) # or False
myBool = bool(None)
myBool = bool(0)
myBool = bool("")
myBool = bool(())
myBool = bool([])
myBool = bool({}) 
~~~

## Operators

- Arithmetic operators: + - * ** / // % ++ --
- Assignment operators: = += -= *= /= %= &= |= ^= >>= <<=
- Comparison operators: == != > < >= <=
- Logical operators: and or not
- Identity Operators: is, is not
- Membership Operators: in, not in
- Bitwise operators: & | ^ << >> ~

## Lists

- Lists are used to store multiple items in a single variable.
- List items are ordered, changeable, and allow duplicate values.
- A list can contain different data types.
- From Python's perspective, lists are defined as objects with the data type 'list'.
- You cannot copy a list simply by typing list2 = list1, because: list2 will only be a reference to list1, and changes made in list1 will automatically also be made in list2. There are ways to make a copy, one way is to use the built-in List method copy().
- There are four collection data types in the Python programming language:
  - List
  - Tuple
  - Set
  - Dictionary
- [List Methods Reference](https://www.w3schools.com/python/python_ref_list.asp)

~~~python
my_list = []
my_list = [1, 2, 3, 4]
my_list = ["apple", "banana", "cherry"]

# The list() Constructor
my_list = list("my_string")
my_list = list(my_tuple)
my_list = list(my_set)

# Access Items - Negative indexing means start from the end
item = my_list[0] # first
item = my_list[-1] # last
item = my_list[-2]

# Range of Indexes
my_list = my_list[2:5] # 2 (included) and end at index 5 (not included)
my_list = my_list[:3] # start at the first item, 3 (not included)
my_list = my_list[0:3]
my_list = my_list[2:] # 2 (included) to the end 
my_list = my_list[-2:]
my_list = my_list[-4:-1]

# Check if Item Exists
if "apple" in my_list:
  print("Yes, 'apple' is in my_list")

# Change Item Value
my_list[0] = "apple"
my_list[1:3] = ["apple", "cherry"] # change a range of item values

# Insert and Add List Items and Extend List
my_list.insert(1, "apple") # inserts an item at the specified index
my_list.append("apple") # add to the end
my_list.extend(my_list2) # add elementsof my_list2 to the end of my_list
my_list.extend(my_tuple) # add any iterable objects (tuple, set, dictionarie, etc)

# Remove List Items
my_list.remove("apple")
my_list.pop(1) # removes the specified index
my_list.pop(-1) # removes the last item
my_list.pop() # removes the last item
del my_list[0] # removes the specified index
del my_list # delete the list completely
my_list.clear()

# Loop Through a List
my_list = ["apple", "banana", "cherry"]
for x in my_list:
  print(x) 

# Loop Through the Index Numbers
my_list = ["apple", "banana", "cherry"]
for i in range(len(my_list)):
  print(my_list[i]) 

# Loop Using a While Loop
my_list = ["apple", "banana", "cherry"]
i = 0
while i < len(my_list):
  print(my_list[i])
  i = i + 1

# Looping Using List Comprehension
my_list = ["apple", "banana", "cherry"]
[print(x) for x in my_list] 

# List Comprehension - a shorter syntax when you want to create a new list based on the values of an existing list.
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
my_list = [x for x in fruits] # copy the list fruits
my_list = [x for x in fruits if "a" in x] # fruits with the letter "a" in the name
my_list = [x for x in fruits if x[0] == "a"]
my_list = [x.upper() for x in fruits] 
my_list = [x * 2 for x in range(10)]
my_list = [x for x in range(10) if x % 2 == 0]
my_list = [x if x != "banana" else "orange" for x in fruits] # returns orange instead of banana

# Sort Lists
my_list.sort() # all capital letters being sorted before lower case letters == case sensitive
my_list.sort(reverse = True)
my_list.reverse()

# Customize Sort Function

## Sort the list based on how close the number is to 50
def myFunction(n):
  return abs(n - 50)
my_list = [100, 50, 65, 82, 23]
my_list.sort(key = myFunction)

## Case Insensitive Sort
my_list = ["banana", "Orange", "Kiwi", "cherry"]
my_list.sort(key = str.lower)

# Copy Lists
my_list_cpy = my_list.copy()

# Copy Lists - another way
my_list_cpy = list(my_list)

# Join Lists
list3 = list1 + list2
list1.extend(list2)

# Join Lists
for x in list2:
  list1.append(x)

# Other methods
counter = my_list.count("apple")
index = my_list.index("apple")
my_len = len(my_list)
my_sum = sum(my_list)
my_max = max(my_list)
my_min = min(my_list)

# Eliminating duplicate items and order
my_list = [5, 1, 1, 2, 2, 3, 4, 4]
my_set = set(my_list)
my_list = list(my_set)
~~~

## Tuples

- Tuple is a collection which is ordered and unchangeable. Allows duplicate members.
- A tuple is a collection of objects which ordered and immutable.
- You can convert the tuple into a list, change the list, and convert the list back into a tuple.
- From Python's perspective, tuples are defined as objects with the data type 'tuple'.
- [Tuple Methods Reference](https://www.w3schools.com/python/python_ref_tuple.asp)

~~~python
my_tuple = ("apple", "banana", "cherry")

# The tuple() Constructor
my_tuple = tuple(("apple", "banana", "cherry")) # note the double round-brackets
myTuple = tuple((1, 2, 3, 4))
my_tuple = tuple(my_list)

# Access Items
item = my_tuple[0] # first
item = my_tuple[-1] # last 

# Range of Indexes
my_tuple = my_tuple[0:3]

# Check if Item Exists 
my_bool = "apple" in my_tuple

# Change Tuple Values
my_tuple = ("apple", "banana", "cherry")
my_list = list(my_tuple) # convert into lista
my_list[1] = "kiwi"
my_tuple = tuple(my_list)

# Add tuple to a tuple
my_tuple = ("apple", "banana", "cherry")
my_tuple2 = ("orange",)
my_tuple += my_tuple2

# Join Two Tuples
my_tuple3 = my_tuple1 + my_tuple2

# Unpacking a Tuple
fruits = ("apple", "banana", "cherry")
(green, yellow, red) = fruits # "unpacking" == extract the values back into variables

# Unpacking a Tuple
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")
(green, yellow, *red) = fruits # red == list

# Loop Through a Tuple
my_tuple = ("apple", "banana", "cherry")
for x in my_tuple:
  print(x)

# Loop Through the Index Numbers
my_tuple = ("apple", "banana", "cherry")
for i in range(len(my_tuple)):
  print(my_tuple[i])

# Using a While Loop
my_tuple = ("apple", "banana", "cherry")
i = 0
while i < len(my_tuple):
  print(my_tuple[i])
  i = i + 1 

# Multiply Tuples
fruits = ("apple", "banana", "cherry")
mytuple = fruits * 2

# Others
my_len = len(my_tuple)
my_max = max(my_tuple)
my_min = min(my_tuple)
my_type = type(my_tuple)

# Python has two built-in methods that you can use on tuples
my_count = my_tuple.count("myValue") # Returns the number of times a specified value occurs in a tuple
my_index = my_tuple.index("myValue") # finds the first occurrence of the specified value
~~~

## Sets

- Set is a collection which is unordered and unindexed. No duplicate members.
- Sets are unordered, so you cannot be sure in which order the items will appear.
- Set items are unordered, unchangeable, and do not allow duplicate values.
- Set items can be of any data type.
- [Set Methods Reference](https://www.w3schools.com/python/python_ref_set.asp)

~~~python
# Creating a set
my_set = {"apple", "banana", "cherry"}

# The set() Constructor
my_set = set(("apple", "banana", "cherry")) # note the double round-brackets

# Duplicates Not Allowed
my_set = {"apple", "banana", "cherry", "apple"}
my_set = {1, 2, 3, 3, 3}

# Get the Length of a Set
my_len = len(my_set)

# Access Items
## You cannot access items in a set by referring to an index or a key.
for x in my_set:
  print(x) 

# Check if "banana" is present in the set
my_bool = "banana" in my_set

# Change Items
## Once a set is created, you cannot change its items, but you can add new items.

# Add Items
my_set.add("orange")

# Add Sets or any iterable object (tuples, lists, dictionaries etc.)
my_set.update(my_set2) # add items from my_set2 set into my_set
my_set.update(my_list) # add items from the list into my_set

# Remove Item
my_set.remove("banana") # raise an error if dont exist
my_set.discard("banana") # dont raise an error if dont exist
last_item = my_set.pop() # remember: the sets are unordered
my_set.clear() # empties the set
del my_set # delete the set completely

# Loop Items
for item in my_set:
  print(item) 

# Join Two Sets - elimine duplicates
my_set3 = my_set1.union(my_set2)
my_set1.update(my_set2) # insert the items in my_set2 into my_set1

# Join Two Sets - Keep ONLY the Duplicates
my_set1.intersection_update(my_set2)
my_set3 = my_set1.intersection(my_set2) # Return a set that contains the items that exist in both set

# Join Two Sets - Keep All, But NOT the Duplicates
my_set3 = my_set1.symmetric_difference(my_set2) # return a new set, that contains only the elements that are NOT present in both sets.

# Other methods
my_set = my_set.difference(my_set2)
answ = my_set.issubset(my_set2)
answ = my_set.issuperset(my_set2)
my_set = set(my_list)
~~~

## Dictionaries

- Dictionary is a collection which is ordered* and changeable. No duplicate members.
  - *As of Python version 3.7, dictionaries are ordered. In Python 3.6 and earlier, dictionaries are unordered.
- Dictionaries are used to store data values in key:value pairs.
- Dictionary items are ordered, changeable, and does not allow duplicates.
- The values in dictionary items can be of any data type.
- You cannot copy a dictionary simply by typing dict2 = dict1, because: dict2 will only be a reference to dict1, and changes made in dict1 will automatically also be made in dict2.
- [Dictionary Methods Reference](https://www.w3schools.com/python/python_ref_dictionary.asp)

~~~python
# Create a dictionary
my_dict =	{
  "model": "Mustang",
  "electric": False,
  "year": 1964,
  "colors": ["red", "white", "blue"]
}

# Access Items
my_item = my_dic["model"]
my_item = my_dic.get("model")

# Get Keys
keys = my_dict.keys() # list - reference

# Get Values
values = my_dict.values() # list - reference

# Get Items
items = my_dict.items() # return each item in a dictionary, as tuples in a list

# Check if Key Exists
if "model" in my_dict:
  print("Yes") 

# Change values
my_dict['age'] = 30
my_dict.update({"age": 31}) 

# Add Items
car["brand"] = "Ford"
my_dict.update({"brand": "Ford"})

# Remove Items
my_dict.pop("age")
my_dict..popitem() # 3.7 - random item
del my_dict['age']
del my_dict
my_dict.clear()

# Loop Through a Dictionary
for x in my_dict:
  print(x) # keys

for x in my_dict:
  print(my_dict[x]) # values

for x in my_dict.values():
  print(x) # values

for x in my_dict.keys():
  print(x) 

for x, y in my_dict.items():
  print(x, y) # keys, values

# Copy a Dictionary
my_dict_cpy = my_dict.copy()
my_dict_cpy = dict(my_dict)

# Nested Dictionaries - A dictionary that contain dictionaries
myfamily = {
  "child1" : {
    "name" : "Emil",
    "year" : 2004
  },
  "child2" : {
    "name" : "Tobias",
    "year" : 2007
  },
  "child3" : {
    "name" : "Linus",
    "year" : 2011
  }
}
print(myfamily["child1"]) # {'name': 'Emil', 'year': 2004}
print(myfamily["child1"]["name"]) # Emil


# Nested Dictionaries - ex2
child1 = {
  "name" : "Emil",
  "year" : 2004
}
child2 = {
  "name" : "Tobias",
  "year" : 2007
}
child3 = {
  "name" : "Linus",
  "year" : 2011
}

myfamily = {
  "child1" : child1,
  "child2" : child2,
  "child3" : child3
}

my_len = len(my_dict)
my_type = type(my_dict)
~~~

## If...Else

~~~python
if grade >= 6:
  print "Ok"
elif grade >= 5:
  print "not Ok"
else:
  print "oh no"

# The pass statement
if b > a:
  pass # if statements cannot be empty, but if you for some reason have an if statement with no content, put in the pass statement to avoid getting an error.
~~~

## Conditional Operator

- This technique is known as Ternary Operators, or Conditional Expressions.

~~~python
min = a if a < b else b
if a > b: print("a is greater than b") 
print("A") if a > b else print("B")
print("A") if a > b else print("=") if a == b else print("B")
~~~

> There is no switch statement in python 

## While Loop

~~~python
# Ex.: while loop
i = 1
while i <= 10:
  print(i)
  i += 1

# Ex.: while loop with else
i = 1
while i <= 10:
  print(i)
  i += 1
else:
  print("The End")
~~~

> Do...While doesn't exist in python.

~~~python python
while True:
  x = input("Enter 0 to exit: ")
  if x == "0":
    break
~~~

## For Loop

~~~python
# For Loop
for i in range(1, 11):
  print(i)

# For With Lists
names = ["aa", "bb", "cc"]
for i in names:
  print("x = ", i)

# Else in For Loop
for x in range(6):
  print(x)
else:
  print("Finally finished!") 

# Nested Loops
for x in adj:
  for y in fruits:
    print(x, y) 
~~~

## Functions

- If the number of arguments is unknown, add a * before the parameter name.
  - This way the function will receive a tuple of arguments, and can access the items accordingly.
  - Arbitrary Arguments are often shortened to *args in Python documentations.
- The phrase Keyword Arguments are often shortened to kwargs in Python documentations.
- If you do not know how many keyword arguments that will be passed into your function, add two asterisk: ** before the parameter name in the function definition.
  - This way the function will receive a dictionary of arguments, and can access the items accordingly.
  - Arbitrary Kword Arguments are often shortened to **kwargs in Python documentations.

~~~python
def myFunc():
  print("Hello from a function") 
myFunc() # call

# Arguments
def myFunc(fname, lname): # parameter
  print("Hi " + name + " " + lname)
myFunc("Mauricio", "Rocha") # call, arguments

# Arbitrary Arguments, *args
def myFunc(*kids):
  print("The youngest child is " + kids[2])
myFunc("Emil", "Tobias", "Linus") 

# Keyword Arguments
def myFunc(child3, child2, child1):
  print("The youngest child is " + child3)
myFunc(child1 = "Emil", child2 = "Tobias", child3 = "Linus") 

# Arbitrary Keyword Arguments, **kwargs
def myFunc(**kid):
  print("His last name is " + kid["lname"])
myFunc(fname = "Tobias", lname = "Refsnes") 

# Default Parameter Value
def myFunc(country = "Norway"):
  print("I am from " + country)
myFunc()
myFunc("Brazil") 

# Passing a List as an Argument
def myFunc(food):
  for x in food:
    print(x)
fruits = ["apple", "banana", "cherry"]
myFunc(fruits)

# Return Two Values
def myFunc(a = 1, b = 2): # valuees default
  return a + b, a * b
s, p = myFunc() # return 3 and 2

# global var
def myFunc():
  global x # access global var
  x = "fantastic"
~~~

## Recursion

- Python also accepts function recursion, which means a defined function can call itself.
- The developer should be very careful with recursion as it can be quite easy to slip into writing a function which never terminates, or one that uses excess amounts of memory or processor power.

~~~python
def tri_recursion(k):
  if(k > 0):
    result = k + tri_recursion(k - 1)
    print(result)
  else:
    result = 0
  return result

print("\n\nRecursion Example Results")
tri_recursion(6)
~~~

## Lambda

- A lambda function is a small anonymous function.
- A lambda function can take any number of arguments, but can only have one expression.
- Syntax: 
  - lambda arguments : expression 

~~~python
# sum
my_sum = lambda a, b: a + b 
x = my_sum(5, 10)

# square
square = lambda a: a ** 2
x = square(9)

# min value
min = lambda a, b: a if a < b else b
x = min(10, 20)

# doubles the number you send
def myfunc(n):
  return lambda a : a * n
mydoubler = myfunc(2)
print(mydoubler(11))

# letter counter in a list
letter_counter = lambda my_list: [len(x) for x in my_list] # output == list
my_list_animais = ["dog", "cat", "horse"]
print(letter_counter(my_list_animais))

# calculator with dicts
my_dict = {
  'my_sum': lambda a, b: a + b,
  'subtraction': lambda a, b: a - b,
  'multiplication': lambda a, b: a * b,
  'division': lambda a, b: a / b,
}
my_sum = my_dict['my_sum']
my_mult = my_dict['multiplication']
print(type(my_dict))
print(my_sum(10, 5))
print(my_mult(10, 5))

# sort - dictionaries 
my_list = {1: 2, 3: 4, 4: 3, 2: 1, 0: 0}
my_ordered_list = {k: v for k, v in sorted(my_list.items(), key=lambda item: item[1])}
print(my_ordered_list)
~~~

## Arrays

- Python does not have built-in support for Arrays, but Python Lists can be used instead.
- To work with arrays in Python you will have to import a library, like the NumPy library.

## Classes/Objects

- Everything in Python is an object, with its properties and methods.
- All classes have a built-in function called __init__(), which is always executed when the class is being initiated.
- Use the __init__() function to assign values to object properties, or other operations that are necessary to do when the object is being created
- The __init__() function is called automatically every time the class is being used to create a new object.
- The self parameter is a reference to the current instance of the class, and is used to access variables that belong to the class.
  - It does not have to be named self , you can call it whatever you like, but it has to be the first parameter of any function in the class.

~~~python
# Create a Class - The __init__() Function
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age
  def myfunc(self):
    print("Hello my name is " + self.name)

# Create Object
p1 = Person("John", 36)
p1.myfunc()

# Modify Object Properties
p1.age = 30

# Delete Object Properties
del p1.age 

# Delete Objects
del p1

# Another example
class Television:
  def __init__(self):
    self.ligada = False
    self.canal = 5
  def power(self):
    if self.ligada == True:
      self.ligada = False
    else:
      self.ligada = True
  def increase_channel(self):
    if self.ligada:
      self.canal += 1
Television = Television()
print(Television.ligada)
Television.power()
print(Television.ligada)
print(Television.canal)
Television.increase_channel()
print(Television.canal)
~~~

## Inheritance

~~~python

~~~

## Iterators

~~~python

~~~

## Scope

~~~python

~~~

## Modules

- Each .py file is a module.
- We can have several classes within a single module.
- Classes contained in a module do not need to have the same name as the module.
- We import modules omitting the .py extension.

#### Ex.: modules - open at the terminal

~~~python
## File Television.py
class Television:
  def __init__(self):
    self.tv_is_on = False
    self.canal = 5
  def power(self):
    if self.tv_is_on == True:
      self.tv_is_on = False
    else:
      self.tv_is_on = True
  def increase_channel(self):
    if self.tv_is_on:
      self.canal += 1

## on Terminal
python3
import Television
t = Television.Television()
t.tv_is_on
t.power()

## on Terminal - another way
python3
from Television import Television
t = Television()
t.tv_is_on
~~~

#### Ex.: modules

~~~python
## File Television.py
class Television:
  def __init__(self):
    self.tv_is_on = False
    self.canal = 5
  def power(self):
    if self.tv_is_on == True:
      self.tv_is_on = False
    else:
      self.tv_is_on = True
  def increase_channel(self):
    if self.tv_is_on:
      self.canal += 1

print(__name__)

if __name__ == '__main__':
  Television = Television()
  print(Television.tv_is_on)
  Television.power()
  print(Television.tv_is_on)
  print(Television.canal)
  Television.increase_channel()
  print(Television.canal)

## ## on Terminal - test 1
python3 Television.py

## ## on Terminal - test 2
python3
import Television
~~~

#### Ex.: modules - import classes - File myTest.py

~~~python
from Television import Television
t = Television()
print(t.tv_is_on)
t.power()
print(t.tv_is_on)
~~~

#### Ex.: modules - import classes - File myTest.py

~~~python
from nameModule import nameFunction1, nameFunction2
x = nameFunction1()
y = nameFunction2()
~~~

## Library

- Library is a collection of packages.
- Some libraries:
  - Web: Django, Flask, Pyramid, Tornado, ...
  - Desktop: Tkinter, PyQT, Kivy
  - DC: SciPy, Pandas, IPython, ...
  - IA: Scikit Learn, ...

## Date

~~~python
# from datetime import date
current_date = date.today()
current_date = date.today().strftime('%d/%m/%Y') 
current_date = datetime.now()
current_date = datetime.now().strftime('%d/%m/%Y - %H:%M:%S')

# from datetime import datetime
current_date = datetime.now()
my_year = current_date.year
my_month = current_date.month
my_weekday = current_date.weekday()
my_day = current_date.day
my_hour = current_date.hour
my_minute = current_date.minute
my_second = current_date.second

my_tuple = ("Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday")
my_day = my_tuple[current_date.weekday()]

my_personal_date = datetime(2021, 3, 24, 15, 40, 20)

date_string = "01/01/2019"
date_formated = datetime.strptime(date_string, "%d/%m/%Y")

# from datetime import time
my_time = time(hour=17, minute=11, second=30)
my_time = time(hour=17, minute=11, second=30).strftime('%H:%M:%S')

# from datetime import datetime, timedelta
my_date = datetime(2021, 3, 30)
new_date = my_date - timedelta(days=365, hours=2, minutes=15)
~~~

## Math

~~~python
x = round(num)
x = floor(num)    # from math import floor
x = ceil(num)     # from math import ceil

x = sum(my_list)
x = max(my_list)
x = min(my_list)
x = len(my_list)

myVar = eval(expression)

x = bin(6)[2:] # binary - returns '110'
~~~

## JSON

~~~python

~~~

## RegEx

~~~python

~~~

## Python PIP

### Packages - Installing packages in python

- Package is a collection of modules.
- Pip is a package manager for Python.

~~~shell
pip --version
pip --help
pip freeze
pip list
pip install requests
~~~

## Exceptions

- [Built-in Exceptions Reference](https://www.w3schools.com/python/python_ref_exceptions.asp)

#### Ex.: exceptions - basic
~~~python
my_list = [1, 10]


try:
  #division = 10 / 0
  #x = my_list[2]
  x = a #
except ZeroDivisionError:
  print("Impossible to divide by zero.")
except IndexError:
  print("Invalid index.")
except BaseException as ex: 
  print("Unknown error. Error: {}".format(ex))
else:
  print("Code executed when there is no exception.")
finally:
  print("Excerpt that is always performed. Good to insert the .close () file here ")
~~~

#### Ex.: exceptions - custom exceptions

~~~python
class Error(Exception):
  pass

class InputError(Error):
  def __init__(self, message):
    self.message = message

while True:
  try:
    x = int(input("Enter a value from 0 to 10 "))
    if x > 10:
      raise InputError("Value cannot be greater than 10. ")
    elif x < 0:
      raise InputError("Value cannot be less than 0. ")
    break
  except ValueError:
    print("Invalid value. Enter numbers only. ")
  except InputError as ex:
    print(ex)
~~~

## User Input

~~~python
x = input("name:  ")        # python 3 - string
x = raw_input("name:  ")    # python 2 - string
a = int(input())
~~~

## User Output

- Formats: %f, %i

~~~python
print("Hi " + nome)
print("s = ", s, "p = ", p)
print("value = " + str(x))
print("value = %i" %x)
print("value = %0.4f" %x)
print("mauricio" * 3)
print(my_list)
print(my_list[0])

print("x = {} e y = {}".format(x, y))
print("MEDIA = {:.1f}".format(media))
print("x = {a} e y = {b}".format(a=x, b=y))
~~~

## String Formatting

~~~python

~~~


## File Handling

- [File Methods Reference](https://www.w3schools.com/python/python_ref_file.asp)

#### Ex.: Text Files - write and update

~~~python
def write_file(name_file, txt):
  my_file = open(name_file, "w")
  my_file.write(txt)
  my_file.close()

def change_file(name_file, txt):
  my_file = open(name_file, "a")
  my_file.write(txt)
  my_file.close()

if __name__ == "__main__":
  change_file("my txt\n")
~~~

#### Ex.: Text Files - read

~~~python
def le_my_file(name_file):
  my_file = open(name_file, "r")
  txt = my_file.read()
  linhas = txt.split("\n")
  print(linhas[0])
  print(linhas[-1])

if __name__ == "__main__":
  le_my_file("notes.txt")
~~~

#### Ex.: Files - copy a file

~~~python
import shutil  # biblioteca
def copy_my_file(name_file):
  shutil.copy(name_file, "./example") # copy o my_file para o diretorio example, renameando: ./example/novoname

if __name__ == "__main__":
  copy_my_file("notes.txt")
~~~

#### Ex.: Files - move a file

~~~python
import shutil  # biblioteca
def move_my_file(name_file):
  shutil.move(name_file, "./example")

if __name__ == "__main__":
  move_my_file("notes.txt")
~~~

- - - 

## How To Random numbers

~~~python
import random

print(random.randrange(1, 10))
~~~

## How To use webservice viacep

~~~python
import requests

response = requests.get("http://viacep.com.br/ws/91786599/json/")

print(response.status_code)   # 200 == sucess, 400 == not found
print(response.text)          
data_cep = response.json()   
print(data_cep["logradouro"])
~~~

### How To use API pokemons

~~~python
import requests

def retorna_data_pokemon(pokemon):
  response = requests.get("https://pokeapi.co/api/v2/pokemon/{}/".format(pokemon))
  data_pokemon = response.json()
  return data_pokemon

data_pokemon = retorna_data_pokemon("pikachu")
print(data_pokemon)
print(data_pokemon['sprites']['front_shiny']) # img
~~~

### How To get source code for any page

~~~python
import requests

def retorna_response(url):
  response = requests.get(url)
  return response.text

response = retorna_response('https://www.inf.ufrgs.br/site')
print(response)
~~~

### How read in URI

~~~python
# many values on the same line 
my_line = input().split()
my_list = list(map(int, my_line)) # map function transforms values to integers 

# many values in many lines - lists
my_list = []
for i in range(0, 6): # to read 6 float values
  my_list.append(float(input()))
~~~

### How To EOF in URI

~~~python
while True:
  try:
    # code here
  except EOFError:
    break
~~~

### .venv

~~~python
# criar uma venv
python3 -m venv .venv 

# ativar uma venv
. .venv/bin/activate
pip install --upgrade pip
make install-dependencies

jupyter notebook

# desativar uma venv
deactivate
~~~


## Links

- [Built in Functions Reference](https://www.w3schools.com/python/python_ref_functions.asp)
- [Google Colab](#)
- [Jupyter Notebook](https://jupyter.org/)
- [Kaggle](https://www.kaggle.com/)
- [Kaggle - Análise de dados do IBGE (Manaus-AM)](https://www.kaggle.com/maurciorocha/an-lise-de-dados-do-ibge-manaus-am/edit)
- [doc](https://docs.python.org/pt-br/3/library/)
- [oficial tutorial](https://docs.python.org/pt-br/3/tutorial/index.html)
- [w3schools](https://www.w3schools.com/python/)
- [Viacep](http://viacep.com.br/ws/91786599/json/) - webservice CEPs
- [pokeapi](https://pokeapi.co/api/v2/pokemon) - api

 To be continued

- [Youtube - Trybe](https://www.youtube.com/playlist?list=PLP6Z8YhN_d5QsIWuVqVFXqjHBssxqvp89)
- [ler PDFs - link Ricardo](https://colab.research.google.com/drive/1VLpWnbukrw9OgIvuBFtmDSOTZO4Mmkl_?usp=sharing)
- [GUI programming](https://www.tutorialspoint.com/python/python_gui_programming.htm)
- faster code in python 
- Data Structures in Python

https://www.w3schools.com/python/python_inheritance.asp
