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

 | Dynamic Typing | Static Typing
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
mystring[:5] # 'Hello'
mystring[::2] # 'HloWrd'
mystring[::-1] # 'dlroW olleH'
```

## String Properties and Methods

Strings are immutable in python:

```python
mystring = "Hello World"
mystring[0] = "J" # Error
```
