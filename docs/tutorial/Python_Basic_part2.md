---
layout: default
title: Python Basic Part 2
parent: Tutorial
nav_order: 2
---
2. TOC
{:toc}

---

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
</pre></code>

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
</pre></code>



