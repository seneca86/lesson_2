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
| 