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
## Dictionary 
A dictionary object is an unordered collection of data in a key: value pair form. A collection of such pairs is enclosed in curly brackets. For example:
<pre><code>
{1:"Steve", 2:"Bill", 3:"Ram", 4: "Farha"}
</code></pre>

# String functions
Python has a set of built-in methods that you can use on strings.
<pre><code>
message = "this is also a string"
print("Title:" + message.title())
print("Uppercase: "+ message.upper())
print("Lowercase: "+ message. lower())
</code></pre>

The title() method returns a string where the first character in every word is upper case. If the word contains a number or a symbol, the first letter after that will be converted to upper case.
The upper() method returns a string where all characters are in upper case. Symbols and numbers are ignored.
The lower() method returns a string where all characters are lower case. Symbols and numbers are ignored.

## Concatenation:
In Python, there are a few ways to concatenate, or combine, strings. The new string that is created is referred to as a string object. This is because everything in Python is an object – which is why Python is an objected-oriented language.
<pre><code>
first_message =  "Hi!"
second_message =  "How are you ?"
full_message =  f"{first_message}  {second_message}"
print(full_message)
</code></pre>

Also called “formatted string literals,” f-strings are string literals that have an f at the beginning and curly braces containing expressions that will be replaced with their values. The expressions are evaluated at runtime and then formatted using the __format__ protocol.

# Numbers and operators
The Python language supports the following types of operators:
* Arithmetic Operators
* Comparison (Relational) Operators
* Assignment Operators
* Logical Operators
* Bitwise Operators
* Membership Operators
* Identity Operators

The commonly used operators are discussed below.

## Arithmetic Operators
Consider the values of a = 10 and b = 20.

  ![Arithmetic Operators](/assets/images/python/Arithmetic.jpg)
<pre><code>
print("\n FLoat\n")
a =2.2
b =2 
c = 0.1
print(" a+b = ",a+b)
print(" a+c = ",a+c)
print(" a*b = ",a*b)
print(" a*c = ",a*c)
</code></pre>

If we look at the answer of a + c and a ** b, it is displayed as an arbitrary number of decimal places. This happens in all languages and is of little concern. Python tries to find a way to represent the result as precisely as possible, which is sometimes difficult given how computers have to represent numbers internally.

## Comparison Operators
Consider the values of a = 10 and b = 20.

  ![Comparison Operators](/assets/images/python/Comparison Operators.jpg)

## Logical Operators
Consider the values of a = 10 and b = 20.

  ![Logical Operators](/assets/images/python/Logical Operators.jpg)

## Membership Operators
Python’s membership operators test for membership in a sequence, such as strings, lists, or tuples.

  ![Membership Operators](/assets/images/python/Membership Operators.jpg)

## Identity Operators 
Identity operators compare the memory locations of two objects.

  ![Identity Operators](/assets/images/python/Identity Operators.jpg)

# User Input 

To receive information through the keyboard, Python uses the input() function. This function has an optional parameter, commonly known as prompt, which is a string that will be printed on the screen whenever the function is called.
When the input() function is called, the program flow stops until the user enters the input via the command line. To enter the data, the user needs to press the ENTER key after inputting their string. While hitting the ENTER key usually inserts a newline character ("\n"), it does not in this case. The entered string will simply be submitted to the application.
The input() function, by default, will convert all the information it receives into a string.

<pre><code>
name = input("Please enter your name: ") 
print("\nWelcome to python," + name + "!")
print("The type of the variable name is", type(name)) 
age = input("\nEnter your age: ")
age = int(age)
print("\nENter Your age is" , age)
print("The type of the variable age is", type(age))
</code></pre>

age = int(age) converts the input value to a numerical representation. After this conversion, if you check the type of age, it is displayed as int (integer).

# Python Decision making

Decision making is the anticipation of conditions occurring while a program executes and specifying actions to take according to the conditions.
Decision structures evaluate multiple expressions which produce TRUE or FALSE as the outcome. You need to determine which action to take and which statements to execute if an outcome is TRUE or FALSE.
The Python programming language assumes any non-zero and non-null values are TRUE, and if they are either zero or null, then they are assumed to be FALSE.

## If-else

The if statement contains a logical expression in which data is compared and a decision is made based on the result of the comparison.
If the Boolean expression evaluates to TRUE, then the block of statement(s) inside the if statement is executed. If the Boolean expression evaluates to FALSE, then the first set of code after the end of the if statement(s) is executed.
An else statement can be combined with an if statement. An else statement contains the block of code that executes if the conditional expression in the if statement resolves to 0 or a FALSE value.
The else statement is an optional statement and there can only be one else statement following if.

  ![If-else](/assets/images/python/if-else.jpg)

## nested if statements
There may be a situation when you want to check for another condition after a condition resolves to true. In such a situation, you can use the nested if construct.
In a nested if construct, you can have an if...elif...else construct inside another if...elif...else construct.

  ![Nested-If-else](/assets/images/python/nested-if-else.jpg)


<pre><code>
print('How old are you?') 
age = int(input())
if age < 21:
    print('You are too young to have a drink.')
elif age >= 80:

    print('Ok, you will get a free drink.')
else:
    print('Sure, enjoy your drink.')
</code></pre>

# Loops
In general, statements are executed sequentially. The first statement in a function is executed first, followed by the second, and so on. There may be a situation when you need to execute a block of code several numbers of times.
Programming languages provide various control structures that allow for more complicated execution paths.
A loop statement allows us to execute a statement or group of statements multiple times.

## While loop
The while loop runs as long as, or while, a certain condition is true.

  ![while loop](/assets/images/python/whileloop.jpg)

Here, statement(s) may be a single statement or a block of statements. The condition may be any expression, and true is any non-zero value. The loop iterates while the condition is true. When the condition becomes false, program control passes to the line immediately following the loop.
In Python, all the statements indented by the same number of character spaces after a programming construct are part of a single block of code. Python uses indentation as its method of grouping statements.

<pre><code>
print('This program will sum up numbers from 1 to a number you enter.') 
print('Please enter the ending number: ')

num = int(input())
total = 0
while num >= 1:
    total += num
    num -= 1
print('The sum is:'    + str(total))
</code></pre>

### Infinite Loop - While

A loop becomes an infinite loop if a condition never becomes FALSE. You must use caution when using while loops because of the possibility that this condition never resolves to a FALSE value.
This results in a loop that never ends. Such a loop is called an infinite loop.
An infinite loop might be useful in client/server programming where the server needs to run continuously so that client programs can communicate with it as and when required. Look at the example below:

<pre><code>
x = 1 
while 
    x <= 5:
    print(x)
</code></pre>

The value of x will start at 1 but never change. As a result, the conditional test x <= 5 will always evaluate to True and the while loop will run forever, printing a series of 1s.

### Using else Statements with while 
When the else statement is used with a while loop, the else statement is executed when the condition becomes false.

<pre><code>
count = 0
while count < 5:
    print (count, "is less than 5") 
    count = count + 1
else:

    print (count, "is not less than 5")
</code></pre>

The value of count will be incremented each time and the condition is checked to see if the count is less than 5. While the count is less than 5, the while loop continuous, and when the condition becomes false, in the else part of the statement is executed.

## For loop
for loops are traditionally used when you have a block of code which you want to repeat a fixed number of times. The Python for statement iterates over the members of a sequence in order, executing the block each time.

  ![For loop](/assets/images/python/forloop.jpg)

If a sequence contains an expression list, it is evaluated first. Then, the first item in the sequence is assigned to the iterating variable iterating_var. Next, the statement(s) block is executed. Each item in the list is assigned to iterating_var, and the statement(s) block is executed until the entire sequence is exhausted.
<pre><code>
import random
for i in range(1, random.randint(5, 15)): 
    print('This for loop has already run'+ str(i) +' times.')
</code></pre>

### Iterating by Sequence Index 
An alternative way of iterating through each item is by index offset into the sequence itself. Look at the example below:
<pre><code>
fruits = ['banana', 'apple’, ‘mango'] 
for index in range(len(fruits)): 
    print ('Current fruit:', fruits[index])
</code></pre>

The len() built-in function provides the total number of elements in the tuple and the range() built-in function gives us the actual sequence to iterate over. So, the length of the fruit is 3 and the range starts from 0 to 2. When the range is 0, banana is printed, when the range is 1, apple is printed, and when the range is 2, mango is printed.

### Using else Statement with for 
When the else statement is used with a for loop, the else statement is executed when the loop has exhausted iterating the list.
<pre><code>
for num in range(10, 20):
    for i in range(2, num): 
        if num % i==0:
            j = num / i

            print('%d equals %d * %d' % (num, i, j))
            break
else:
    print(num, 'is a prime number')
</code></pre>

### Loop Control Statements 
Loop control statements change execution from its normal sequence. When execution leaves a scope, all automatic objects that were created in that scope are destroyed.

#### break statement 
The break statement terminates the current loop and resumes execution at the next statement. The most common use for break is when some external condition is triggered requiring a hasty exit from a loop. The break statement can be used in both while and for loops.
If you are using nested loops, the break statement stops the execution of the innermost loop and start executing the next line of code after the block.

<pre><code>
print("For-Break") 
for letter in "Python":
    if letter == 'h':
        break
    print("Current Letter:", letter)
print("\nwhile-Break")
var = 10
while var > 0:
    print ("Current variable value:", var)
    var =  var - 1
    if var==5:
        break

print("Good bye!")
</code></pre>

#### continue statement 
The continue statement returns the control to the beginning of the loop. The continue statement rejects all the remaining statements in the current iteration of the loop and moves the control back to the top of the loop.
<pre><code>
print("For-Continue")
for letter in "Python": 
    if letter == "h":
        continue
    print("Current Letter:", letter)
print("\nwhile-Continue")
var = 10
while var > 0:
    var = var - 1
    if var == 5:
        continue
    print("Current variable value:", var)
</code></pre>

## Data conversion
<pre><code>
price= 10
print('How many beers do you want?')
print('Your total price is: $' +str( price * int(input())))
</code></pre>

we use int() to convert the input value to an integer and use str() to convert the result of calculation back to a string. We also can use float() to convert a value to a float number.
