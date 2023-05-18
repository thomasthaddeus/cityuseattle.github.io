---
layout: default
title: Python Basic
parent: Tutorial
nav_order: 1
---
1. TOC
{:toc}

---
# Python Installation


For Python installation follow <https://cityuseattle.github.io/docs/environment/python/>

# Variables
Variables are containers for storing data values. Unlike other programming languages, Python has no command for declaring a variable. A variable is created the moment you first assign a value to it.
A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume). Rules for Python variables include:
* A variable name must start with a letter or the underscore character
* A variable name cannot start with a number
* A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _)
* Variable names are case-sensitive (age, Age and AGE are three different variables)

To create the variable type

<pre><code>
message = “Hello World”
</code></pre>

## Multiple assignments 

Python allows you to assign values to multiple variables in one line and you can assign the same value to multiple variables in one line.

<pre><code>
print("\nMultiple assignments\n")
a, b, c = 5, 3.2, "Hello"
print ("a = ", a)
print ("b = " , b)
print ("c = ", c)
x = y = z = "Python"
print ("x ="+ x)
print ("y ="+ y)
print ("z ="+ z)
</code></pre>

# Data Types 
Data types are the classification or categorization of data items. Data types represent a kind of value which determines what operations can be performed on that data. Numeric, non-numeric, and Boolean (true/false) are the most used data types.

## Numeric 
A numeric data type is any representation of data which has a numeric value. Python identifies three types of numbers: 
* Integer: Positive or negative whole numbers (without a fractional part). For example: >>> x = 5 
* Float: Any real number with a floating-point representation in which a fractional component is denoted by a decimal symbol or scientific notation. For example: >>> y = 2.5 
* Complex number: A number with a real and imaginary component represented as x+yi. x and y are floats and i is -1 (the square root of -1 is called an imaginary number). For example:      
 <pre><code>
 z = 2 + 3i
</code></pre>

## Boolean 

A Boolean is data with one of two built-in values: True or False. Notice that 'T' and 'F' are capitalized. “true” and “false” are not valid Booleans and Python will throw an error for them. For example: 
 <pre><code>
print (10>9)  
</code></pre>
Result: *True*

## Sequence 
Type A sequence is an ordered collection of similar or different data types. Python has the following built-in sequence data types: 
* String: A string value is a collection of one or more characters put in single, double, or triple quotes. The string is initialized in the following ways: 
 <pre><code>
    message = “This is a string declaration”  
    message = ‘This is also a string declaration’
 </code></pre> 
* List: A list object is an ordered collection of one or more data items, not necessarily of the same type, put in square brackets. 
<pre><code>
    list1 = ['physics', 'chemistry', 1997, 2000]
 </code></pre> 
* Tuple: A Tuple object is an ordered collection of one or more data items, not necessarily of the same type, put in parentheses. A tuple is not mutable, i.e., it doesn't have any methods for changing its contents. 
<pre><code>
    tup1 = ('physics', 'chemistry', 1997, 2000)
 </code></pre>








