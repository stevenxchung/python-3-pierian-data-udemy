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
