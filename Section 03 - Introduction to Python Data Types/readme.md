# Section 3 Notes

This section covers the basics on python objects and data structures

## Data Types

Below is a table on the main data types seen in python:

Name | Type | Description
--- | --- | ---
Integers | int | Whole numbers: 3, 300, 200
Floating Point | float | Numbers with a decimal point: 2.3, 4.6, 100.0
Strings | str | Ordered sequence of characters: "hello", "2000"
Lists | list | Ordered sequence of objects: [10, "hello", 200.3]
Dictionaries | dict | Unordered key-value pairs: {"key": "value"}
Tuples | tup | Ordered immutable sequence of objects: (10, "hello", 200.3)
Sets | set | Unordered collection of unique objects: {"a", "b"}
Booleans | bool | Logical value indicating True or False

## Variable Assignments

* We generally want to keep variable names in lowercase
* Python uses Dynamic Typing which reassigns variables to different datatypes

 Case | Dynamic Typing | Static Typing
--- | --- | ---
Before | my_dog = 1 | int my_dog = 1
After | my_dog = "hello" | my_dog = "hello" // Error!

Pros of Dynamic Typing:
* Very easy to work with
* Faster development time

Cons of Dynamic Typing:
* May result in bugs for unexpected data types
* You need to be aware of type()

## Strings

Strings are sequences of characters, using the syntax of either single quotes or double quotes:
* 'hello'
* "Hello"

Because strings are **ordered sequences** it means that we can use **indexing** and **slicing** to grab sub-sections of the string

* Indexing: grab a single character from the string
* Slicing: grab a subsection of multiple characters: [start:stop:step]
  * **start**: is a numerical index for the slice start
  * **stop**: is the index you will go up to (but not include)
  * **step**: is the size of the "jump" you take

## String Indexing and Slicing

```python
# Indexing example
mystring = "Hello World"
mystring[0] # 'H'
mystring[-11] # 'H'

# Slicing example
mystring[:5] # "Hello"
mystring[::2] # "HloWrd"
mystring[::-1] # "dlroW olleH"
```

## String Properties and Methods

Strings are immutable in python:

```python
mystring = "Hello World"
mystring[0] = "J" # Error
```

String concatenation allows you to "add" strings together

```python
a = "Hello"
b = "World"
a + b # "Hello World"
```
## Print Formatting with Strings

Often, we will want to "inject" a variable into your string for printing:

```python
mystring = "What a what a wonderful world!"
print("Hello World! " + mystring) # Hello World! What a what a wonderful world!
```

A good way to format objects into your strings for print statements is with the string .format() method:

```python
print("The {2} {1} {0}".format("fox", "brown", "quick")) # The quick brown fox

print("The {q} {b} {f}".format(f="fox", b="brown", q="quick")) # The quick brown fox
```

We can also format float values by using {value:width.precision f}:

```python
import math
result = math.pi
print("Pi is approximately {r:1.3f}".format(r=result)); # 3.142

# Alternatively
print(f"Pi is approximately {result:1.3f}"); # 3.142
```

## Lists in Python

We can use indexing and slicing on lists as they are ordered:

```python
mylist = ["one", "two", "three"]
mylist[0] # "one"
```

We can also concatenate lists:

```python
mylist1 = ["one", "two", "three"]
mylist2 = ["four", "five"]
newlist = mylist1 + mylist2 # ["one", "two", "three", "four", "five"]
```

* Unlike strings, we can change elements inside lists to be of a different value
* The append() method allows us to app new elements to the end of a list
* The pop() method allows us to take an element out of the list

```python
newlist = ["one", "two", "three", "four", "five"]
newlist.append("six") # ["one", "two", "three", "four", "five", "six"]
newlist.pop("one") # ["two", "three", "four", "five", "six"]
```

* The sort() method allows us to sort elements numerically or alphabetically, the changes are in place meaning that it reassigns the list to be sorted
* The reverse() method allows us to reverse a list, the changes are in place meaning that it reassigns the list to be reversed

```python
newlist = [1, 4, 3, 2]
newlist.sort() # [1, 2, 3, 4]
newlist.reverse() # [4, 3, 2, 1]
```

## Dictionaries in Python

Dictionaries are unordered mappings for storing objects. Previously we saw how lists store objects in an ordered sequence, dictionaries use a key-value pairing instead.

When to choose a list and when to choose a dictionary?
* Use a dictionary when you want to retrieve data fast and are not concerned about location (cannot perform sort, index, or slice)
* Use a list when you want to sort, index, or slice data

```python
prices = {"apple" : 1.99, "oranges" : 2.99, "milk", 3.99}
prices["apple"] # 1.99
prices["oranges"] # 2.99
prices["milk"] # 3.99
```

## Tuples with Python

Tuples are similar to lists. However, unlike lists, Tuples are **immutable** - the values stored inside of a tuple cannot be changed

Why would you want to use a tuple if they function as a list with less features?
* Because in some cases you may want to keep certain variables the same, in this case you would want to use a tuple

There are only two methods with tuples:

```python
t = (1, 2, 3)
t.count(1) # 1
t.index(1) # 0
```

## Sets in Python

Sets are unordered collections of unique elements:

```python
newset = set()
newset.add(1)
newset # {1}
newset.add(2)
newset # {1, 2}
newlist = [1, 1, 1, 2, 2, 2, 3, 3, 3]
set(newlist) # {1, 2, 3}
```

## Booleans in Python

Booleans are operators that allow you to convey **True** or **False** statements

```python
(1 + 1) == 2 # True
(1 + 1) == 1 # False
```

## I/O with Basic Files in Python

This subsection covers input and output on Jupyter Notebooks:

```python
%%writefile myfile.txt
Hello this is a text file
This is the second line
This is the third line

myfile = open("myfile.txt") # Opens file

myfile.read() # Reads file and returns everything from that file into one string
myfile.read() # Returns nothing because file has already been read
myfile.seek(0) # Returns reader head to the beginning of the file
myfile.read() # Now it prints your text file as a string like before
myfile.seek(0)
myfile.readlines() # Prints text file with each line stored in a list

# Below is a cleaner way to open and read files
with open("myfile.txt") as my_new_file:
  contents = my_new_file.read()

# Additionally, we can add the permissions when opening a file by changing the mode
with open("myfile.txt", mode='r') as my_new_file: # Read only mode
  contents = my_new_file.read()
```

There are many different modes you can open a file with:
* mode='r' is read only
* mode='w' is write only (will overwrite files or create new)
* mode='a' is append only (will only add on to files)
* mode='r+' is reading and writing
* mode='w+' is writing and reading (overwrites existing files or creates a new file)
