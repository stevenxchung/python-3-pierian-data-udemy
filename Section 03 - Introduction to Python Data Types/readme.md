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
