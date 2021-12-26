# Lesson 2: data types in Python

## Objects

Python has various data _types_, which can contain certain _values_. In order to understand this system, we first need to understand the memory system of a computer.

It is useful to visualize the computer's memory as a huge warehouse with shelved. Each slot in a shelf is one byte wide (one byte equals eight bits).

Python can access this system with the permission of the operating system, with the purpose of storing the code itself and that data that it uses. For the computer, all bits are the same, but Python can keep track not only of _where_ the bits are but of _what_ data type they are.

This is possible because Python wraps each data value in memory as an _object_. We will see later on in the course how to define our own objects, but for the moment we will just talk about objects that handle the basic built-in data types.

We can visualize an object as a variable-sized box that occupies space on a shelf and contains the following:
* A type that defines what it can do (like a factory stamp on the box)
* A unique id (like the location on the shelf)
* A value that is consistent with its type (like the content)
* A reference count that tracks how often it is used (we will discuss later on)

![A visualization of an object consisting of an integer with value 7](diagram.draw)

## Data types

The following table shows the basic data types in Python, many of which may be familiar from other languages such as R.

| Name | Type | Examples |
|------|------|----------|
| Boolean | `bool` | `True`, `False`|
| Integer | `int` | `48`, `200` |
| Floating point | `float` | `3.14`, `3.7e3`|
| Complex |`complex`| `3j`, `5+9j`|
| Text string |`str`| `Hello`, `Goodbye`|
| List |`list`| `['spring', 'summer', 'fall', 'winter']`|
| Tuple |`tuple`|`(2,4,8)`|
| Bytes |`bytes`|`b'ab\xff`|
| ByteArray | `bytearray`|`bytearray(...)`|
| Set | `set` | `set([3,5,7])`|
| Frozen set | `frozenset`| `frozenset(['Anne', 'Bertie'])`|
| Dictionary | `dict` | `{'Yaris':'Toyota', 'S':'Tesla'}`|

We will work with most of them over the following chapters.

Python is a _strongly typed_ language, which means that the type of an object does not change. A separate property is _mutability_, which is the capacity of the data _value_ contained in an object to change. Think of a mutable object as a box with a lid whose value can be replaced.

## Literal and variables
Some computer science parlance: 
- a literal is notation for representing a fixed value, such as `42`
- a variable is storage location associated with a symbolic name ("pointed to"), such as `x`

In this example:
```Python
x = 42
^   ^
|   |--- literal
|------- variable
```

## Variables
Python let's you define variables and give them names that must comply with certain conditions:
- they can only contain letters, digits, and underscore
- they are case-sensitive
- they must not begin with a digit
- names that begin with an underscore are treated specially (we will come back on this later on)
- they cannot be one of Python's reserved words or _keywords_, with can be looked up with the following command:

```Python
help('keywords')
```

## Assignment
In Python, assignment is achieved with the `=` operator, instead of the operator `<-` that is used in, e.g. R. The "equal to" operator is `==`, so make sure you do not confuse them.

The assignment operator is quite intuitive:
```Python
x = 4
y = x * 3
print(y)
```

## Variables as names
An important nuance in Python is that variables are just names that we use to "tag" the object boxes we described. In other words, they are just a reference to the object, not the object itself. The main implication of this is that you may have two variables pointing to the same object:

```Python
a = 10
print(a)
b = a
print(b)
```

![Copying a name is equivalent to tagging and object twice](variables_as_names.draw)

This can lead to a surprising behavior in case the objects are mutable. This behavior is easy to follow:
```Python
x = 1
print(x)
y = x
print(y)
x = 10
print(x)
print(y)
```
... but this one may come up as a surprise:
```Python
a = [1, 2]
b = a
a[0] = 9
print(b)
```

## Checking the type
In order to check the type of a variable we may use the functions `type()` and `isinstance()`:

```Python
type(10)
isinstance(10, int)
type('Hello')
type(True)
type(5.0)
type(2+4.0)
```

