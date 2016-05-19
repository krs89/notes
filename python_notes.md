# Week 3 (self study) 9-15 May 2016

----------------------------------

[source](http://blog.trinket.io/why-python/)

## Why Python is a great first language
- great experience from day 1 (clear code)
- can be used for web programming
- can be used for desktop programming
- marketable professional skill, easier to learn other languages after it
- good community (supportive, welcoming)

## Style guide
- `CamelCase` for classes and `lower_case_with_underscores` for functions and method
- put comments on a line of their own
- Wrap lines so that they don’t exceed 79 characters
- Use 4-space indentation, and no tabs

## Running python

- quit python interpreter: `^D` or `quit()`
- `chmod +x my_first_simple_script.py`
- `chmod 755 scriptname`

## Variables

- variable: poiting to an object (the value of the variable)
- object: data (built in/from extension library/created in the program)
- `id(variable)`: the unique ID number of the object the variable is ponting to
- variable/identifier name can be [a-zA-z0-9_], but first char can not be [0-9]
- keywords:
  ```
  and, as, assert, break, class, continue, def, del, elif, else, except, False, finally, for, from, global, if, import, in, is, lambda, None, nonlocal, not, or, pass, raise, return, True, try, while, with, yield
  ```

## Data types
- numerics
  - integer
    - normal
    - octal
    - hexadecimal
    - binary
  - floating point
  - complex
- sequences
  - strings
  - byte sequences
  - byte arrays
  - lists
  - tuples
  - range objects
- mappings
- files
- instances
- exceptions

### Numbers
- `int()`, `float()`, `complex()` to convert between types
- __integer__: unlimited size,
  `type(x)`, `isinstance(x, complex)`
  *normal*
  - *octal*: prefix `0o` or `0O`
  - *hexadecimal*: prefix `0x` or `0X`
  - *binary*: prefix `0b` or `0B`
  - `hex()`, `oct()`, `bin()`, `int()` to convert (to string)
- long integer: only used in Python2
- __floating-point__: for example: `42.11`, `3.1415e-10`, accurate only up to 15 decimals
- __complex__: `<real part> + <imaginary part>j`
- integer division `10/3` is floor division in Python2 but true division in Python3 where `10//3` is floor division (truncating fractional digits)
### Strings
- `s = 'It doesn\'t matter!'` OR `"He said: \"It doesn't matter\""`
- `s = '''multiple line string'''` OR `s = """multiple line string"""`
- `s[0]` first char of string, `s[len(s)-1]` OR `s[-1]` last char of string,
- concatenation `+`, repetion `*`, indexing `s[0]`, slicing `s[2:4]`, size `len(s)`
- __immutable__, not possible to replace individual characters
- `a is b` -> `True` if they point to the same object ID (if assigned separately they get the same ID if hyphen is not part of the string)
- escape characters with \
- string objects: stored as a sequence of characters
### Byte strings
- stored as a sequence of bytes (just as date objects)
- `x = b"Hello"`
- `s = str(x)` -> convert to string
### Lists
`x = []`, `x = [1, 1.0, "hello", [1, 2, 3]]` empty, mixed types, nested
`x[2][1]` nested indexing, from the above list it yields "e"
- negative indexing: counting from the end backwards
- slicing: `x[begin: end: step]`
- mutable `x[0] = 3`
- add 1 item: `x.append(7)`, add more items: `x.extend([5, 6, 7])`
- concatenation `+`, repetition `*` creates more references to the same list and concatenates them!
- insert 1 element to position [1]: `x.insert(1, "hello")`
- squeeze more elements to position starting at [2]: `x[2:2] = ["szia", "mia"]`
- `del x[2]`, `del x[2:4]`, `del x` to delete the entire list
- `x.remove("hello")` first occurrence, `x.pop(3)` return and delete `x[3]`, x.pop()` return and delete last element `x[-1]`
- `x.clear()` empty the list. `x[2:5] = []`
- `x.index("hello")` what is the index of first occurrence of "hello" in x
- `x.count("hello")` how many occurrences
- `sort()`, `reverse()` ascending order, reverse order
- `copy()` return a shallow copy of the list
### Tuples
- `t = (1, 2, 3)` define with parentheses
- immutable, can be used as keys in dictionaries
## List methods


## Flow control
```python
while <condition>:
    <statement>
else:
    <statement>
```
```python
for <variable> in <sequence>:
    <statements>
else:
    <statements>
```
`range(<begin>, <end>, <step>)`

-  if statement
  - colon, indentation
  - false: `0`, `None`, `False`, true: non-zero value, `True`
  - if...elif...elif...elif...else

```python
#!/usr/bin/env python3

gender = input("Gender? ")
if gender == "male" or gender == "Male":
    print("Your cat is male")
else:
    print("Your cat is female")

age = int(input("Age of your cat? "))
if age < 5:
    print("Your cat is young.")
else:
    print("Your cat is adult.")
```
- for loop
- while loop
- break and continue
- pass

## Operators:
- `==`, `<=`, `>=`, `!=`, `<`, `>`
- `and`, `or`, `not`
- `~x`, `|`, `&`, `^`: bitewise negation, OR, AND, XOR
- `<<`, `>>`: shift operators
- `in`: "element of"
- `**` exponential, `%` modulo, `//` truncation division, `+`, `-`, `*`, `/`

## Functions
```python
def function_name(parameter1, optional_parameter="defaul value", *arbitrary_number_of_values):
    """the text of the docstring"""
    statements
    global x # make variable defined inside the function global
    return # optional, gives None if not specified
print (function_name.__doc__)
```
`call_function(*x)` to unpack the list x

## Files
`f = open('workfile', 'w')`
- `'r'`: read only (default), `'w'`: write only, `'a'`: append, `'r+'`: read-write
- append `'b'` to above options to open as binary for all non-text files
- `f.read(<size>)`, `f.read()`, `f.readline()`, `f.readlines()` list of lines
- `f.write(string)`. `f.writelines("a", "b", "another line")`
- `f.close()`
```python
with open('workfile', 'r') as f:
    read_data = f.read()
f.closed # this tests if f has been closed (should return True)
```
`f.mode`, `f.name`
## Code examples
`print(value1, ..., sep=' ', end='\n', file=sys.stdout, flush=False)`
`input("prompt: ")` returns a string (can be used with `eval()`, `int()` etc.)

```python
#!/usr/bin/env python3
#!/usr/local/bin/python3.5
# -*- coding: encoding -*-

print("Hello, World!")

"""
this is a multiline comment
"""

if gender == "male" or gender == "Male":
    command
else:
    other command
command outside of condition




```
