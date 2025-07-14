# In Python, comments and docstrings serve different purposes:

_Comments_ are used to explain specific lines or blocks of code. They are meant for developers to understand the logic and intent behind the code. They are not executable. Use comments to clarify complex code, note assumptions, and highlight important points.

_Docstrings_ take a broader view of different components of your code and are used to provide documentation at a more macro level. They are accessible via the help() function and are meant to describe the overall purpose and usage of the code. According to the Python Style Guide, each script and all publicly accessible pieces of code should have a docstring at the beginning to guide users on how to use the code effectively.

# Understanding String Slicing in Python

This document provides a comprehensive guide to string slicing in Python, covering basic slicing, slicing with a step, reverse slicing, partial slicing, and slicing by character.

## What is String Slicing?

String slicing is the technique of extracting a portion of a string by using its indices. It's a powerful tool with applications in data processing, cleaning, web scraping, tokenization, and feature extraction.

## Basic Slicing

The basic syntax for string slicing is:

```python
string[start:end]
```

- `start`: The index where the substring begins (inclusive).
- `end`: The index where the substring ends (exclusive). The character at this index is _not_ included in the slice.

**Example:**

```python
my_string = "This is MY string!"
print(my_string[0:4])  # Output: This
print(my_string[1:7])  # Output: his is
print(my_string[8:len(my_string)])  # Output: MY string!
```

**Explanation:**

- `my_string[0:4]` extracts characters from index 0 up to (but not including) index 4.
- `my_string[1:7]` extracts characters from index 1 up to (but not including) index 7.
- `my_string[8:len(my_string)]` extracts characters from index 8 to the end of the string. `len(my_string)` provides the length of the string, ensuring all characters from index 8 onwards are included.

**Important Note:** Accessing `my_string[len(my_string)]` would result in an `IndexError` because valid indices range from 0 to `len(my_string) - 1`. However, in slicing, the `end` index is exclusive, so no out-of-range error occurs.

## Slicing with a Step

You can also specify a step value to skip characters during slicing:

```python
string[start:end:step]
```

- `step`: The increment between indices. The default step is 1.

**Example:**

```python
my_string = "This is MY string!"
print(my_string[0:7])    # Output: This is (step of 1)
print(my_string[0:7:2])  # Output: Ti s (step of 2)
print(my_string[0:7:5])  # Output: Ti (step of 5)
```

**Explanation:**

- `my_string[0:7:1]` extracts characters from index 0 up to (but not including) index 7, taking each character (step of 1).
- `my_string[0:7:2]` extracts characters from index 0 up to (but not including) index 7, taking every second character (step of 2).
- `my_string[0:7:5]` extracts characters from index 0 up to (but not including) index 7, taking every fifth character (step of 5).

## Reverse Slicing

To extract substrings in reverse order, use a negative step. The `start` and `end` indices need to be adjusted accordingly:

```python
string[start:end:step]  # step is negative
```

**Example:**

```python
my_string = "This is MY string!"
print(my_string[13:2:-1])  # Output: rts YM si s
print(my_string[17:0:-2])  # Output: !nrsY ish
```

**Explanation:**

- `my_string[13:2:-1]` starts at index 13 and moves backward to (but not including) index 2, taking each character (step of -1).
- `my_string[17:0:-2]` starts at index 17 and moves backward to (but not including) index 0, taking every second character (step of -2).

## Partial Slicing

You can omit the `start` or `end` index for partial slicing:

- `string[:end]`: Extracts from the beginning of the string up to (but not including) index `end`.
- `string[start:]`: Extracts from index `start` to the end of the string.
- `string[:]`: Extracts the entire string.
- `string[::-1]`: Reverses the entire string (step of -1).

**Example:**

```python
my_string = "This is MY string!"
print(my_string[:8])   # Output: This is
print(my_string[8:])   # Output: MY string!
print(my_string[:])    # Output: This is MY string!
print(my_string[::-1]) # Output: !gnirts YM si sihT
```

## Slicing by Character (Using `index()`)

The `index()` method finds the index of the first occurrence of a specific character or substring. This can be combined with slicing for more dynamic extraction.

**Example:** Extracting the protocol from a URL

```python
url1 = "https://www.example.com"
url2 = "ftp://ftp.example.org"
url3 = "http://api.example.net"

protocol1 = url1[:url1.index(':')]
protocol2 = url2[:url2.index(':')]
protocol3 = url3[:url3.index(':')]

print("Protocol 1:", protocol1)  # Output: Protocol 1: https
print("Protocol 2:", protocol2)  # Output: Protocol 2: ftp
print("Protocol 3:", protocol3)  # Output: Protocol 3: http
```

**Explanation:**

`url1.index(':')` finds the index of the first colon (`:`) in the string `url1`. The slice `url1[:url1.index(':')]` extracts the substring from the beginning of `url1` up to (but not including) the colon, effectively extracting the protocol.

## Answer to the Question

How can we only extract the file extension (the substring after the dot) from the given file name string using slicing and the `index()` function?

```python
filename = "data_2022_01_15.csv"
extension = filename[filename.index('.') + 1:]
print(extension)  # Output: csv
```

**Explanation:**

1.  `filename.index('.')` finds the index of the first dot (`.`) in the filename.
2.  `filename.index('.') + 1` calculates the index immediately _after_ the dot.
3.  `filename[filename.index('.') + 1:]` extracts the substring starting from the index after the dot to the end of the string, which is the file extension.

**Floor division**
In floor division, the result is floored to the nearest smaller integer. It is also known as integer division. For floor division, we must use the // operator.

print(43 // 10)

**Identity operators**
In Python, the is and is not operators are used to compare the memory locations of two objects. They help determine if two variables reference the same object in memory. Here’s an example demonstrating how is and is not operators are used and how they differ from the equality operator.

num = 10
num1 = 20

print(num is num1);
print(num is not num1);

**Multiple Assignment**

var1 = var2 = var3 = 10

**Logical Operator**

| Operator | Purpose                                                                                                          |
| -------- | ---------------------------------------------------------------------------------------------------------------- |
| not      | Inverts the boolean value of its operand; returns True if the operand is False, and False if the operand is True |
| and      | Returns True if both operands are True, otherwise returns False                                                  |
| or       | Returns True if at least one of the operands is True, otherwise returns False                                    |

**Adding bits**

print(10 + True) //11
print(10 + False) //10
print (True + False) //1

_False and (False or True)_
Evaluation order:

First, evaluate the inner parentheses (False or True)

False or True = True

Then evaluate the full expression: False and True = False

So the result will be: False

Here's a detailed breakdown of boolean logic:

- Step 1: Evaluate inside parentheses
  (False or True) = True
- Step 2: Evaluate the full expression
  False and True = False
  Truth table explanation:

or returns True if any operand is True
and returns True only if both operands are True
 
I'll create a comprehensive Markdown file explaining Bitwise Operators in Python. Here's a detailed guide:

# Bitwise Operators in Python 🖥️

## 🌟 Introduction to Bitwise Operators

Bitwise operators allow you to manipulate individual bits of integer values at the binary level. They operate directly on the binary representation of numbers.

## 📊 Types of Bitwise Operators

### 1. Bitwise AND (&)
- Compares each bit of two numbers
- Returns 1 if both bits are 1, otherwise 0

```python
# Example
a = 5  # Binary: 0101
b = 3  # Binary: 0011
result = a & b  # Result: 0001 (1 in decimal)
```

### 2. Bitwise OR (|)
- Compares each bit of two numbers
- Returns 1 if at least one bit is 1

```python
a = 5  # Binary: 0101
b = 3  # Binary: 0011
result = a | b  # Result: 0111 (7 in decimal)
```

### 3. Bitwise XOR (^)
- Compares each bit of two numbers
- Returns 1 if bits are different

```python
a = 5  # Binary: 0101
b = 3  # Binary: 0011
result = a ^ b  # Result: 0110 (6 in decimal)
```

### 4. Bitwise NOT (~)
- Inverts all bits of a number
- Flips 0s to 1s and 1s to 0s

```python
a = 5  # Binary: 0101
result = ~a  # Inverts all bits
```

### 5. Left Shift (<<)
- Shifts bits to the left
- Adds zeros on the right
- Effectively multiplies by 2^n

```python
a = 5  # Binary: 0101
result = a << 1  # Result: 1010 (10 in decimal)
```

### 6. Right Shift (>>)
- Shifts bits to the right
- Removes rightmost bits
- Effectively divides by 2^n

```python
a = 5  # Binary: 0101
result = a >> 1  # Result: 0010 (2 in decimal)
```

## 🚀 Practical Applications

### 1. Checking Even/Odd
```python
def is_even(num):
    return (num & 1) == 0  # Returns True for even numbers
```

### 2. Bit Manipulation Techniques
```python
# Set a specific bit
def set_bit(num, pos):
    return num | (1 << pos)

# Clear a specific bit
def clear_bit(num, pos):
    return num & ~(1 << pos)

# Toggle a specific bit
def toggle_bit(num, pos):
    return num ^ (1 << pos)
```

### 3. Compound Assignment Operators
```python
a &= b   # Bitwise AND assignment
a |= b   # Bitwise OR assignment
a ^= b   # Bitwise XOR assignment
a <<= 2  # Left shift assignment
a >>= 2  # Right shift assignment
```

## 💡 Advanced Bit Tricks

### Check Power of 2
```python
def is_power_of_two(n):
    return n > 0 and (n & (n - 1)) == 0
```

### Binary Representation
```python
# Convert to binary string
print(bin(10))  # Output: 0b1010
```

## 🔢 Operator Precedence (Highest to Lowest)
1. Parenthesis `()`
2. Exponentiation `**`
3. Unary operators `~, +, -`
4. Multiplication/Division `*, /, %`
5. Addition/Subtraction `+, -`
6. Bitwise Shifts `<<, >>`
7. Bitwise AND `&`
8. Bitwise XOR `^`
9. Bitwise OR `|`
10. Comparison `==, !=, >, <`
11. Logical NOT `not`
12. Logical AND `and`
13. Logical OR `or`
14. Assignment `=`


# String Operations & Grouping Values in Python

---

## String Operations

Learn about key string operations, including comparison, concatenation, replication, and substring searching.

### Comparison Operators

Strings in Python can be compared using comparison operators (`<`, `>`, `<=`, `>=`, `==`, `!=`). Each character has a Unicode value, and strings are compared lexicographically—character by character, just like words in a dictionary.

- If strings are equal up to the length of the shorter string, the shorter string is considered lexicographically smaller.

#### Example: Lexicographical String Comparison

```python
print('a' < 'b')  # True

house = "Gryffindor"
house_copy = "Gryffindor"
house_copy_longer = "Gryffindor_"
new_house = "Slytherin"

print(house == house_copy)             # True
print(house == new_house)              # False
print(new_house <= house)              # False
print(new_house >= house)              # True
print(house_copy <= house_copy_longer)  # True
```

---

### Concatenation

The `+` operator merges two strings.

```python
first_half = "Bat"
second_half = "man"
full_name = first_half + second_half  # "Batman"
print(full_name)
```

**Important:** Concatenating strings with integers directly causes a `TypeError`. Convert integers to strings with `str()` first:

```python
age = 30
name = "Batman"
# print(name + age)  # Error

print(name + str(age))  # "Batman30"
```

---

### String Replication

The `*` operator repeats a string multiple times:

```python
print("Ha" * 3)  # "HaHaHa"
```

---

### Searching in Strings

Use the `in` keyword to check for substring presence. The `not in` keyword checks for absence.

```python
message = "Hello, World!"
print("World" in message)       # True
print("Python" not in message)  # True
```

`in` and `not in` are called membership operators.

---

## Quiz Challenge: String Concatenation

What is the output of the following?

```python
Hello = "Hello"
Hello = Hello + Hello
print(Hello)
```

- A. Hello2  
- B. HelloHello  
- C. Hello 2 times  
- D. Error  

*Answer: B. HelloHello*

---

## Coding Exercise: Generating Email Addresses

Given a list with first, middle, and last names, create an email of the form:

`FirstName.MiddleInitial.LastName@educative.io`

---

# Grouping Values Using Lists

---

## Lists in Python

Lists are versatile, mutable containers where you can store ordered collections of any data type, including other lists.

- Lists are enclosed in square brackets `[]`, elements separated by commas.
- Indexing starts at 0.
- Lists can be indexed, sliced, and modified.

---

## Creating a List

```python
my_list = [True, 1, 2.5, "A string"]
print(my_list)
# Output: [True, 1, 2.5, 'A string']
```

---

## Accessing List Elements

Lists behave like strings but can contain different data types.

```python
my_list = [True, 1, 2.5, "A string"]
print(my_list[2])         # 2.5
print(len(my_list))       # 4
my_list[0] = "hello"      # Change first element
print(my_list)            # ['hello', 1, 2.5, 'A string']
```

*Note:* Accessing `my_list[len(my_list)]` raises an IndexError because indexing is 0-based.

---

## Indexing String Elements Within a List (Nested Indexing)

Lists can contain strings, and characters within those strings can be accessed with double indexing:

```python
my_list = ["hello", "world", "Educative"]
print(my_list[0][1])  # 'e' - second character of first string
print(my_list[2][3])  # 'c' - fourth character of third string
```

---

## Explanation on String Immutability in Lists

- You can replace entire elements in a list:

  ```python
  my_list[0] = "Hi"  # OK
  ``` 

- You **cannot** change individual characters of a string inside a list directly because strings are immutable:

  ```python
  # my_list[0][0] = "J"  # Error!
  ```

---

## Reinforce Your Understanding: Initials Extraction

Given a list of names, extract the initials and display them.

```python
name_list = ["John", "Doe", "Smith"]  # first, middle, last names

first_initial = name_list[0][0]   # Extract first character of first name
middle_initial = name_list[1][0]  # Extract first character of middle name
last_initial = name_list[2][0]    # Extract first character of last name

initials_list = [first_initial, middle_initial, last_initial]

print(initials_list)  # ['J', 'D', 'S']
```

---

# Summary

- Strings use Unicode and compare lexicographically.
- Use `+` for string concatenation, with explicit conversion for numbers.
- Use `*` to replicate strings.
- The `in` keyword checks substring membership.
- Lists store ordered, mutable collections of varied data types.
- Lists can be indexed and sliced like strings.
- Nested indexing allows access to string characters within lists.
- Strings inside lists remain immutable.

---



