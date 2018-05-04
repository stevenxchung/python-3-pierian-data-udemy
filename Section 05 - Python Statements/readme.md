# Section 5 Notes

This section covers python statements.

## If Elif and Else Statements in Python

Control flow allows certain code to execute only if a particular condition is met.

Here are some of the most common control flow keywords:
* if
* elif
* else

Here are some examples:

```python
# Example 1
if 3 > 2:
  print("True")

# Example 2
location = "Bank"

if location == "Auto Shop":
  print("Cars")
elif location == "Bank":
  print("Money")
elif location == "Grocery Store":
  print("Food")
else:
  print("N/A")
```

## For Loops in Python

Many objects in python are iterable - you can repeat a task for each element in an object.

A for loop is one way to accomplish this iteration.

```python
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Example 1
for num in arr:
  print(num)

# Example 2
for num in arr:
  # Check for even numbers
  if num % 2 == 0:
    print(num)
  else:
    print(f"Odd Number: {num}")

# Example 3
arr_sum = 0

for num in arr_sum:
  arr_sum += num
print(arr_sum)

# Example 4
for letter in "Hello World":
  print(letter)

# Example 5
arr = [(1, 2, 3), (4, 5, 6), (7, 8, 9)]

for a, b, c in arr:
  print(a)
  print(b)
  print(c)
```

When iterating through a dictionary we can unpack the variables just like a tuple:

```python
d = {"k1": 1, "k2": 2, "k3": 3}

for key, value in d.items:
  print(key)
  print(value)
```

## While Loops in Python

While loops will continue to execute a block of code while some condition remains true.

```python
x = 0

while x < 5:
  print(f"The current value of x is {x}")
  x += 1
else:
  print("x is not less than 5")
```

There are several of keywords that help us with our control flow:
* break: Breaks out of the current closest enclosing loop
* continue: Goes to the top of the closest enclosing loop
* pass: does nothing at all

```python
# Example 1
x = [1, 2, 3]

for item in x:
  # Comment
  pass
print("End of script")

# Example 2
for letter in "Steven":
  if letter == 'S' || 't':
    continue
  print(letter)

# Example 3
x = 5

while x < 5:
  if x == 2:
    break
  print(x)
  x += 1
```
## Useful Operators in Python

Here we will discuss some useful operators in python which can help enhance or improve programs.

```python
# Example 1: Range operator
# Prints numbers from 0-10
for num in range(10):
  print(num)

# Example 2: List operator
# Generate a list from 0 to 11 with 2 increments
list(range(0, 11, 2))

# Example 3: Enumerate operator
# Generate tuples with indexes and characters
for index, letter in enumerate("abcde"):
  print(index)
  print(letter)
  print('\n')

# Example 3: Zip operator
# Combine multiple lists into tuples
list1 = [1, 2, 3]
list2 = ['a', 'b', 'c']
list3 = ['x', 'y', 'z']

for item in zip(list1, list2, list3):
  print item

# Example 4: In operator
# Check if an item is within a set
"mykey" in {"mykey": 999} # True

# Example 5: Max/Min operator
# Find max or min of a list
arr = [1, 2, 3, 4, 5]

max(arr) # returns 5
min (arr) # returns 1

# Example 6: Random functionality
# Generates a randomly shuffled list
from random import shuffle
rand_list = shuffle(arr)

# Example 7: Input operator
# Accept user input and store as a string
result = input("What is your age?")
```

## List Comprehensions in Python

List comprehensions are a unique way of quickly creating a list with python.
They are a good alternative to using a for loop with .append() to create a list.

```python
# Standard append to array using for loop
mystring = "Hello"

arr = []

for letter in mystring:
  mylist.append(letter)

# List comprehension
arr = [letter for letter in mystring] # Returns arr = ['H', 'e', 'l', 'l', 'o']
```

Here is another example of converting temperatures from celcius to fahrenheit using both methods:

```python
# Standard append to array using for loop
celcius = [0, 10, 20, 30 , 40 , 50]
fahrenheit = []

for temp in celcius:
  fahrenheit.append( ((9/5) * temp + 32) )

# List comprehension
celcius = [0, 10, 20, 30 , 40 , 50]
fahrenheit = [((9/5) * temp + 32) for temp in celcius]
