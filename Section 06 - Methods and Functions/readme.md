# Section 6 Notes

This section covers python methods and functions.

## Methods and the Python Documentation

To see available methods on a particular object on Jupyter Notebook, press the '.' after an object and a list of methods will pop up.

Another way (in Jupyter Notebook) to explore a new method is by hitting s"shift + tab" on the keyboard after a method is selected.

A built in help() function will also provide instructions on how to use a particular method.

In addition, the python documentation will be a useful resource if more in-depth information is desired.

## Functions in Python

Creating clean, repeatable code is a key of becoming an effective programmer. Functions allow us to create blocks of code that can be easily executed many times, without needing to constantly rewrite the entire block of code.

```python
def say_hello():
  '''
  DOCSTRING: Information about the function
  INPUT: No input
  OUTPUT: Hello
  '''
  print("Hello")

say_hello() # Prints "Hello"
```

To return values and assign it to a variable:

```python
def say_hello(name="name"):
  return "Hello " + name

result = say_hello("Jose") # "Hello Jose"
```

Here are more examples of functions:

```python
# Find out if the word "dog" (case does not matter) is in a string
def dog_check(mystring):
  return "dog" in mystring.lower()

dog_check("Dog ran away") # True
```

Let's do an example:

```python
# Pig Latin
# If word starts with a vowel, add "ay" to end
# If word does not start with a vowel, put first letter at the end, then add "ay"
# word -> ordway
# apple -> appleay

def pig_latin(word):
  first_letter = word[0]

  # Check if vowel
  if first_letter in "aeiou":
    pig_word = word + "ay"
  else:
    pig_word = word[1:] + first letter + "ay"

  return pig_word

pig_latin("word") # "ordway"
pig_latin("apple") # "appleay"
```

## *args and *kwargs in Python

* *agrs - arguments
* **kwargs - keyword arguments

We want a way to accept an arbitrary number of *args and **kwargs

```python
def myfunc(a, b):
  # Returns 5% of the sum of a and b
  return sum((a, b)) * 0.05

myfunc(40, 60) # 5.0
```

In the example above, myfunc() only takes in 2 positional arguments. How do we make this work for n arguments?

```python
def myfunc(*args):
  # Returns 5% of the sum of n arguments
  return sum(args) * 0.05
```

How do we do this for dictionaries?

```python
def myfunc(**kwargs):
  if "fruit" in kwargs:
    print("My fruit of choice is {}". format(kwargs["fruit"]))
  else:
    print("I did not find my fruit here")
```

We can also pass in both *args and **kwargs:

```python
def myfunc(**args, **kwargs):
  print(args)
  print(kwargs)
  print("I would like {} {}".format(args[0], kwargs["food"]))
```
## Lambda Expressions, Map, and Filter Functions

Lambda expressions are used only once and typically do not have a name. Lambda expressions are also known as anonymous functions as they do not have a name.

The [map](http://book.pythontips.com/en/latest/map_filter.html) function takes another function and applies it to some element(s).

The [filter](http://book.pythontips.com/en/latest/map_filter.html) function creates a list of elements for which a function returns true.

## Nested Statements and Scope

LEGB Rule:
* L: Local - Names assigned in any way within a function (def or lambda), and not declared in that function.
* E: Enclosing function locals - Names in the local scope of any and all enclosing functions (def or lambda), from inner to outer.
* G: Global (module) - Names assigned at the top-level of a module file, or declared gloabl in a def within the file.
* B: Built-in (Python) - Names preassigned in the built-in names module: open, range, SyntaxError,...
