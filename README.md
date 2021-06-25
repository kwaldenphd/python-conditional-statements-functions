# Conditional Statements in Python

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Objectives

By the end of this lab, students will be able to
- Define conditional statements and conditional execution
- Use Boolean operators and logical expressions to build conditional statements
- Describe the differences between a while and for loop
- Write programs that use iteration and loops to accomplish specific task prompts
- Convert programs written using a for loop to a while loop
- Write functions that accomplish specific tasks prompts

## Acknowledgements

Elements of this lab procedure were adapted from materials developed by [Dr. Peter Bui](http://www3.nd.edu/~pbui/) for the [CSE 10101 "Elements of Computing I" course](https://www3.nd.edu/~pbui/teaching/cdt.30010.fa16/).
- [Conditional and Alternative Execution](http://nbviewer.jupyter.org/urls/gitlab.com/snippets/25773/raw)
- [Loops](http://nbviewer.jupyter.org/urls/gitlab.com/snippets/26115/raw)
- [Functions](http://nbviewer.jupyter.org/urls/gitlab.com/snippets/26619/raw)

Elements of this lab procedure were adapted from materials developed by [Dr. Janet Davis](https://cs.whitman.edu/~davisj/) for the the [CSC 105 "The Digital Age" course](https://www.cs.grinnell.edu/~davisjan/csc/105/2012S/). 
- [Laboratory: Programming in Python (Decisions and Repetition)](http://www.cs.grinnell.edu/~davisjan/csc/105/labs/python3.html)

Elements of this lab procedure were adapted from materials developed by [Dr. Corey Pennycuff](https://www3.nd.edu/~cpennycu/) for the [CSE 10101 Elements of Computing (Fall 2019)](https://www3.nd.edu/~cpennycu/2019/fa-CSE10101-CDT30010.html).
- [Control flow structures](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.09.03.ipynb)
- [Looping structures](https://www3.nd.edu/~cpennycu/2019/fa-CSE10101-CDT30010.html)
- [Functions](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.09.19.ipynb)
- [String functions and manipulation](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.10.01.ipynb)

Elements of this lab procedure were adapted from materials developed by [Lindsay K. Mattock](http://lindsaymattock.net/) for the the [SLIS 5020 Computing Foundations course](http://lindsaymattock.net/computingfoundations.html). 

# Table of Contents

- [Conditional execution and `if` statements](#conditional-execution-and-if-statements)
  * [Review of logical conditions](#review-of-logical-conditions)
  * [Working with `if` statements](#working-with-if-statements)
  * [`if` statements and strings](#if-statements-and-strings)
  * [Conditional statements and `if`](#conditional-statements-and-if)
  * [Additional work with `if` statements](#additional-work-with-if-statements)
- [Working with loops](#working-with-loops)
  * [`for` loops](#for-loops)
  * [`while` loops](#while-loops)
  * [Additional work with loops](#additional-work-with-loops)
    * [Additional practice with loops (optional)](#additional-practice-with-loops-optional)
  * [Nesting within loops](#nesting-within-loops)
- [Working with functions](#working-with-functions)
- [Lab Notebook Questions](#lab-notebook-questions)


# Conditional Statements

1. So far, all the programs we have written work by executing each statement in the program in order, from top to bottom. 

2. To write programs that solve more complex problems, we need mechanisms that will allow statements to be executed in more complex ways. 

3. For example, we might like to execute some statements under some conditions but not others, or we might like to execute some statements multiple times. 

Behold- conditional statements!

We can use conditional statements to change the behavior of a program based on whether specific conditions are or are not met.

To put this another way, conditional statements check boolean expressions (i.e. conditions), and change the behavior of the program accordingly.

## Operator Review

Operators used to compare two objects:
- `==`    equal to
- `==`    equal to
- `!=`    not equal to
- `>=`    greater than or equal to
- `>`     greater than
- `<`     less than
- `<=`    less than or equal to

Boolean logical operators:
- `and`   both must be true
- `or`    one or both must be true
- `not`   reverses the truth value

We can use and test for conditions in a few key ways, specifically through `if` statements and `loops`.

More on loops later, but for now...

## `if` statements

Python's comparison operators serve as conditional tests that return a True or False.
```Python
#set the variable number to 10
number = 10

#the following statements will return true or false

# EQUAL !==
print(number == 15)
print(number ==10)

# GREATER THAN >
print(number > 10)
print(number > 4)

# LESS THAN <
print(number < 10)
print(number < 15)

# GREATER THAN OR EQUAL TO >=
print(number >= 15)
print(number >= 10)

# LESS THAN OR EQUAL TO <=
print(number <= 4)
print(number <= 10)

#TESTING MULTIPLE CONDITIONS

#AND
print(number > 1 and number <20)

#OR
print(number ==10 or number ==20)
```

`if` statements use the `if` keyword to test if a condition is true.

`if` statements are conditional, meaning that there is a test to determine if a statement is true or false, and then the computer takes some defined action.

The basic syntax for an `if` statement:

```Python
if condition:
 statement(s)
```

The `if` statement tests if a particular condition is true. And if so, executes the command nested under the initial `if` statement.

To illustrate that another way:

```Python
if this condition is true:
 then do this thing
```

A couple things to note about this syntax:
- A colon always follows the first line of an `if` statement
- The code that will run if the statement is true is nested or intented beneath the `if` keyword

For example, let's say we have a Python program where the variable `n` equals `0`.

We want to write a program that, if `n` equals `0`, prints the message `n is zero`.

We can do that using an `if` statement.

```Python
n = 0

if n == 0:
 print('n is zero')
```

Let's see another `if` statement in action.

This time, we are going to ask the user for an input, and use that input in an `if` statement.

```Python
number = int(input("Enter a number: "))
if number > 0:
  print("That number is positive.")
```

<blockquote>Be sure to double check indentation in your code.</blockquote>

See what happens when you enter different number values.

If you enter a positive number, the `That number is positive` message will print. 

If you enter a negative number or zero, no message is printed. 

Now let's add a second `print` statement (a message of your choosing) at the end of the program.

The indentation for this second `print` statement needs to match `print("That number is positive.")` in the previous example.

```Python
number = int(input("Enter a number: "))
if number > 0:
  print("That number is positive.")
  print('Second print statement goes here')
```

How does this affect the output of your program when you enter various values?

Now, let's change the indentation for the second`print` statement.

This time, instead of matching the `print("That number is positive.")` indentation, the second print statement will be aligned with the `if` statement.

```Python
number = int(input("Enter a number: "))

if number > 0:
  print("That number is positive.")

print('Second print statement with modified indentation')
```

How does this affect the program's output?

When python encounters an `if` statement it checks whether the associated condition (in this case, `number > 0`) is true. 

If the condition is true, Python executes all statements that immediately follow AND are indented beneath the `if` clause. 

If the condition is false, no commands indented beneath the `if` clause are skipped. 

In either case, execution will then continue with the next un-indented statement. 

## `if` statements and strings

The `if` statement and comparison operators work for comparing strings just like they do for comparing numbers.

Let's write a program that asks the user to enter a color name.

```Python
color = input("Enter a color name")

print("You entered the color " + color)
```

Now, you want to use an `if` statement to print a message telling the user if the color they entered is your favorite color.

If the color entered by the user is not your favorite color, no printed response is needed.

Now, add a final line to your program that will print `Goodbye!` whenever the program ends, regardless of the color entered.

Test your program to see if it works.

Note- to checking whether your program works, you will have to run it at least twice, entering colors that test both possible outcomes.

<blockquote>Q3: Provide your code + comments for steps 13-18.</blockquote>

<blockquote>Q4: Describe how you approached writing the program for Q3.</blockquote>

## `if-else` statements

Suppose we want to print one message when the condition (`number > 0`) is true, and a different message when the condition is false. 

We can do that by using an `else` clause along with an `if` keyword.

The basic syntax for `if-else`:

```Python
if condition:
 statement(s)
else:
 statement(s)
```

The statement indented beneath the `if` keyword will only run when the `if` condition is true.

In an `if-else` statement, the statement indented beneath `else` will only run if the `if` condition is not true (or false).

An example that illustrates this logic:

```Python
# ask user to enter a number
number = input("Enter a number: ")

# test if number is greater than zero
if number > 0:
  print ("That number is positive.")

# if number is not greater than zero
else:
  print ("Definitely NOT positive.")

# message that prints at end of program
print ("This message prints every time.")
```

<blockquote>Q7: Modify the program included above to test for different conditions and output different messages. Include comments that describe what the code is doing.</blockquote>

<blockquote>Q8: Return to your Q3 program and modify so it prints one message if the user enters your favorite color, and a different message if not. In addition, your program should print a final message for every user, regardless of what they entered. Answer will include your modified code + comments that explain/describe what the code is doing.</blockquote>

## Additional Work With `if` Statements

We can also test for values in a list.
```Python
fruits = ['apple', 'pear', 'orange']

#a test to see if apple is on the list
if 'apple' in fruits:
  print('Would you like an apple?')
else:
  print('Sorry, we are all out of apples.')

#a test to see if banana is NOT on the list
if 'banana' not in fruits:
  print('Yes, we have no bananas')
else:
  print('Would you like a banana?')
```

<blockquote>Q6: Explain what this program will output and why.</blockquote>



We can check more than one condition using chained conditional statements (or chained conditionals).
- Key term: *chained conditionals*

```Python
a = 200
b = 33
c = 500

if a > b or a > c:
 print("At least one of the conditions is True")
```

We can also nest conditional statements inside another conditional statement.
- Key term: *nested conditionals*

```Python
x = 41

if x > 10:
  print("Above ten,")
  if x > 20:
    print("and also above 20!")
  else:
    print("but not above 20.") 
```

NOTE: Python works from left to right evaluating a logical expression or conditional statement. Python stops evaluating when it finds the expression is `True` or `False` based on the conditional statement.

Syntax errors will interrupt program execution.

<blockquote><a href="https://www.w3schools.com/python/python_conditions.asp">Click here</a> to learn more about conditional statements in Python, via W3Schools.</blockquote>

# Control Flow

In programming languages, control flow governs the order in which a program executes.

In Python, control flow is regulated through conditional statements, loops, and function calls- all things we will be covering in this lab!

Examples include:
- `if` statements
- `for` and `while` loops
- Functions

A few examples of control and conditional execution in action.

```Python
# if statement example 

# declares a variable
a = 2019

# declares b variable
b = 2000

# ‘if’ conditional statement that compares the two variables and prints the output if the condition is met    
if b > a:
 print("b is greater than a")
```

```Python
# if..else statement example

# declares x variable
x = .01

# reassigns x variable
x = x + .01

# reassigns x variable a second time
x = x * 50

# conditional statement using if--else
if x == 1:
 print('Yes')
else:
 print('No')
```

The previous section of the lab focused on the `if` and `if..else` keywords.

We can also use the `elif` keyword along with the `if` keyword to introduce a new condition. 

Python will test the `elif` condition if previous conditions are not true.

```Python
# elif statement example

# declares x variable
x = 1

# block of code that runs if x is less than 0
if x < 0:
 print("x is less than 0")

# block of code that runs if x equals zero
elif x == 0:
 print("x is equal to 0")

# block of code that runs if x is greater than 0
else:
 print("x is greater than 0")
```

```Python
# another elif example

# assign a variable 
a = 33

# assign b variable 
b = 33

# conditional statement using if
if b > 1:
 print("b is greater than a")
 
# conditional statment using elif to test, only when if statement is false
elif a == b:
 print("a and b are equal")
```

```Python
# example using chained conditional statements

# assign a variable
a = 2020

# assign b variable
b = 2019

# assign c variable
c = 2018

# chained conditional statements using and
if a > b and c > a:
 print("Both conditions are True")
 
# chained conditional statements using or
if a > b or a > c:
 print("At least one of these conditions is true")
```  

# Loops

Loop statements are a type of conditional statement that rely on the underlying logic of conditional execution.

In Python, loops repeatedly execute a series of tasks.
- Key term: *loop(s), looping*

Each time through the body of a loop is called an iteration.
- Key term: *iteration*

An iteration can involve things like iterating through items in a list or testing if specific conditions are met, and then doing “something” as the result or endpoint for the loop.

Loops normally contains a variable that changes within the body of the loop so that we can eventually exit the loop. 

If a loop never exits, then this is called an infinite loop.
- Key term: *infinite loop*

In short, the computer will continue to follow the loop instructions, until it can’t perform that function any longer. 
Working with loops


## `for` loops

`for` loops let us iterate through a definite set of objects.

In each iteration through the `for` loop, Python will:
- Extract one element from the dataset
- Execute the body of the `for` loop using the item bound to the element
- Go back to the first step
- Keep iterating through the loop until reaching the end of the dataset

The basic syntax in a `for` loop:

```Python
for item in dataset:
 statement(s)
```

In this syntax, `item` is a placeholder for each element in `dataset`. 

You can replace `item` with another word or letter character.

```Python
for i in dataset
```

In this syntax, `dataset` stands for the list of items we want Python to iterate over.

That list of items could be a list variable, a list of numbers, a string of characters, etc.

### `for` loops and lists of numbers

Let's say we have a list of numbers, and we want Python to iterate through each number in the list and print the number.

```Python
for i in [0, 1, 2, 3]:
 print(i)
```

Alternatively, we could create a variable for our list of numbers.

```Python
# create list of numbers
number_list = [0, 1, 2, 3]

# for loop
for i in number_list:
 print(i)
```

The loop command steps through the list one value at a time. 

The loop continues until it reaches the end of the list. 

### `for` loops and strings

We can also use a `for` loop to iterate over a list of strings.

Let's say we have a list of pepper types.

```Python
peppers = ["bell", "poblano", "jalapeno", “banana”, “chile”, “cayenne”]
```

We can use a `for` loop to iterate over each string in the list.

```Python
peppers = ["bell", "poblano", "jalapeno", “banana”, “chile”, “cayenne”]

for x in peppers:
 print(x)
```

We can also use a `for` loop to iterate through characters in a single string.

Let's say we want to iterate over the characters in the string `elements`.

```Python
for x in 'elements':
 print(x)
```

```Python
# another example of iterating over characters in a string

string = 'elements'

for x in string:
 print(x)
```

### Other functions that can be used with `for` loops

#### `range()`

We can use the `range()` function to generate a list of numbers.

```Python
range(0, 3)
```

We can use the `range()` function as part of a `for` loop.

```Python
for i in range(0, 3):
 print(i)
```

#### `enumerate()`

In a previous lab, we talked about how each item in a list has an index, or a number that indicates its position in the list.

We can use the `enumerate()` function to generate a list of pairs containing each item in the list and its index.

```Python
list(enumerate(['a','b','c'])
```

We can use the `enumerate()` function as part of a `for` loop.

```Python
for index, letter in enumerate('abc'):
 print(index, letter)
```

In this last example, `for index, letter` instructed Python to iterate over both components in the `enumerate()` output.

`print(index, letter)` instructed Python to print both components for each element.

### Other `for` loop considerations

Let's say we have a nested list, or a list that contains sub-lists.

```Python
numlist = [[0, 42], [67543, -987654]]
```

<blockquote>QX: What do you think will happen if we write a for loop for numlist? What would be a single element in the list?</blockquote>

Remember in a nested list, or a list with sub-lists, each sub-list is an item or element in the list.

<blockquote><a href="https://www.w3schools.com/python/python_for_loops.asp">Click here</a> to learn more about <code>for</code> loops in Python, via W3Schools.</blockquote>

### `for` loops: putting it all together

29. Let's start combining `for` loops with some of the concepts covered in previous labs.
```Python
#loops through a list of the members of the House Stark.

characters = ['Arya', ' Benjen', 'Bran', 'Catelyn', 'Eddard', 'Rickon', 'Robb', 'Sansa']

for character in characters:
  print(character.title() + "Stark")
```

<blockquote>Note the use of the plural for the name of the list and the singular for the individual item is not required. We are just declaring variables here. I could have used anything to name the individual items (e.g. for person in characters). All you are doing with this step is setting a new variable for the individual item. It is standard convention to use the plural and singular terms so that the person reading the code can interpret what it is doing.</blockquote>

30. Remember the loop command steps through the list one value at a time. The loop continues until it reaches the end of the list. 

31. In this case, for each item in the list called `“characters”` the program prints the value of each `“character”` in the list concatenated with the string `" Stark”`. 

32. This produces the output:
```
Arya Stark
Benjen Stark
Bran Stark
Catelyn Stark
Eddard Stark
Rickon Stark
Robb Stark
Sansa Stark
```

33. Now let's look at a different loop.
```Python
characters = ['Arya', ' Benjen', 'Bran', 'Catelyn', 'Eddard', 'Rickon', 'Robb', 'Sansa']
print('Members of the House Stark:')
for character in characters:
  print(character.title() + " Stark")
print(characters[0].title() + " is my favorite.")
```

<blockquote>Q9: What do you expect this code to output? Explain how this program works in your own words.</blockquote>

34. Comments that walk through each line of this program:
```Python
#this line creates the list of character names
characters = ['Arya', ' Benjen', 'Bran', 'Catelyn', 'Eddard', 'Rickon', 'Robb', 'Sansa']

#this first print command prints a header for my list "Members of the House Stark"
print('Members of the House Stark:')

#here is the loop from the previous example
for character in characters:
  #the indentation is important here. This indent indicates that this print command is part of the loop
  print(character.title() + " Stark")
  
#this line is not indented, so it is executed after the loop is complete.  
print(characters[0].title() + " is my favorite.")
```

### Conditional statements and `for` loops

We can also use nested conditional statements as part of `for` loops.

#### Example A

For example, let's say we have `message = 'Hello World!'`, and we want to see in which positions the letter `l` appears.

Our program would need to...
- Iterate over each character in the string
- Check to see if that character matches `l`
- If the character matches `l`, output some kind of message that indicates the position

<blockquote>QX: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?</blockquote>

<blockquote>QX: See where you can get with writing this program? What parts of the program were you able to get working? Where did you run into challenges?</blockquote>

Here is one approach to this program.

First, we could create a variable with our `Hello World!` string.

```Python
message = 'Hello World!'
```

Then, we could use a `for` loop with the `enumerate()` function to access each element in the string and its index.

```Python
for entry in enumerate(message):
 print(entry)
```

This gets us each character in the string and its index.

Next, we could use a conditional statement to test for equality.

```Python
if entry[1] == 'l':
 print(f'Found an 'l' at position {entry[0]}')
```

In this block of code, we are accessing the second value in the `enumerate()` output for each character in the string.

<blockquote>Remember: Python starts counting at zero (0).</blockquote>

Each iteration through the loop tests if the `entry` character matches `l`.

If the conditional statement is true, then the `print()` message will output the position index.

To put that all together:

```Python
message = 'Hello World!'

for entry in enumerate(message):
 print(entry)
 
 if entry[1] == 'l':
  print(f'Found an 'l' at position {entry[0]}')
```
You can modify this code to include other messages or test for other characters.

<blockquote>QX: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking different (if at all) about how to approach this type of program?</blockquote>

#### Example B

Let's work through another example.

This time, let's say we have a list of names that might be used to refer to Notre Dame's Department of Computer Science and Engineering.

```Python
#here is a list of names
names=['department of computer science and engineering', 'computer science department', 'cse']
```

We want to write a program that prints out `cse` in all upper-case letters, but prints out any other list element in title case.

Our program would need to...
- Iterate over each element in the list
- Check to see if that element matches `cse`
- If so, print out that element in upper case
- Otherwise, print out that element in title case

<blockquote>QX: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?</blockquote>

<blockquote>QX: See where you can get with writing this program? What parts of the program were you able to get working? Where did you run into challenges?</blockquote>

Here is one approach to this program.

First, we could use a `for` loop to iterate through each item in the list.

```Python
for name in names:
 SOMETHING WILL GO HERE
```

Then, we could use an `if` statement to test if the element equals `cse`

```Python
if name == 'cse':
 DO SOMETHING 
```

Now remember if the element matches `cse`, we want to print the element in upper-case letters.

So we could finish the `if` statement.

```Python
if name == 'cse':
 print(name.upper())
```

If the element does not match `cse`, we want to print the element in title-case letters.

We can use an `else` statement combined with a `print()` statement.

```Python
else:
 print(name.title())
```

To put that all together:

```Python
names=['department of computer science and engineering', 'computer science department', 'cse']

for name in names:
  if name == 'cse':
    print(name.upper())
  else:
    print(name.title())
```

20. This program returns the output
`Department of Computer Science and Engineering`
`Computer Science Department`
`CSE`

<blockquote>QX: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking different (if at all) about how to approach this type of program?</blockquote>



# `while` loops

35. Another way to modify the control flow of a program is to have it execute one or more statements repeatedly.

36. Run the following program and see what happens. 

37. You should find that it prints both "Notre" and "Dame" five times, and then it prints "Done" once.
```Python
count = 1
while count <= 5:
   print ("Notre")
   print ("Dame")
   count = count + 1
print ("Done")
```

38. Now let's walk through the program to understand how it works. 

39. On the first line (`count = 1)` we create a variable named `count` and set it equal to one. 

40. The next statement (`while count <= 5:`) contains a condition `count <= 5`. 

41. This condition will be evaluated, and if it is true, the statements indented beneath it will be executed. 

42. Once that has happened, execution returns to the top of the `while` loop, where the condition is checked again. 

43. This process will continue, with the indented statements being executed repeatedly as long as (i.e., `while`) the condition continues to be true. 

44. If the condition is ever false when it gets checked, execution will jump to the first statement after those associated with the loop (the first un-indented statement).

45. The careful reader will notice that it is important for something about the condition to change on each pass through the loop. 

47. Predict what will happen if you remove the statement `count = count + 1`. Remove the statement to verify your prediction.

48. If all went "well", you should have discovered what we call an infinite loop. This means your program will continue running forever, unless you stop it from outside. 

<blockquote>Q10: Modify the program from steps 35-48 so that it prints some word or phrase nine times, and also prints a line number at the beginning of each line. Answer will include code + comments.</blockquote>

49. For example, your output might look like the following: 
```Python
1 Python
2 Python
3 Python
4 Python
5 Python 
6 Python
7 Python
8 Python
9 Python
IS FUN!
```

<blockquote>Q11: In your own words, what is iteration?</blockquote>

<blockquote>Q12: In your own words, what is the difference between a <code>while</code> loop and a <code>for</code> loop?</blockquote>

## Additional work with loops

<blockquote>Q13: Write a loop that prints out all numbers from 0 to 10. Include your code + comments that document how the code works.</blockquote>
  
50. Convert the following Python code to use a while loop instead of a for loop.
```Python
numbers = [5, 4, 7, 0, 1]
count   = 0

for number in numbers:
    if not number:
        break
    count += 1

print(count)
```
<blockquote>Q14: Include your modified code for step 50, including commments that document what changes you made.</blockquote>

51. The Python code below is suppose to determine if the given list of numbers is sorted. That is, it should return True if each item in the list is less than the next item. 

52. Unfortunately, there are a few errors in the code below. 

53. Identify the errors and fix the code.
```Python
is_sorted([1, 2, 3, 4, 2])

def is_sorted(numbers):
    ''' Return whether or not the list of numbers is sorted '''
    for i in range(len(numbers) - 1):
        if numbers[i] > numbers[i + 1]:
            return False
    return True
```
<blockquote>Q15: Include your modified code for steps 51-53, including commments that document what changes you made to address the errors.</blockquote>

54. Write a program that prints a list of the first nine positive integers and their squares. 

55. Once again, be careful to include the colon at the end of the while statement, or Python will complain.

56. Your output should look similar to the following:
```Python
Number Square
1        1
2        4
3        9
4        16
5        25
6        36
7        49
8        64
9        81
```

<blockquote>Q16: Include your program for steps 54-56, including commments that document what the code is doing.</blockquote>

57. Write a program that counts from 10 down to 1, and then prints "Blastoff!" 

58. Your output should look like this:
```Python
10
9
8
7
6
5
4
3
2
1
Blastoff!
```
<blockquote>Q17: Include your program for steps 57-58, including commments that document what the code is doing.</blockquote>

59. Write a program that asks the user to enter three numbers: a starting value, an ending value, and an increment. 

60. Your program should then "count" based on these criteria, as shown in the example below.
```Python
This program counts for you.
Enter the starting value: 3
Enter the ending value: 13
Enter the increment: 2
3
5
7
9
11
13
```

<blockquote>Q18: Include your program for steps 59-60, including commments that document what the code is doing.</blockquote>

### Additional practice with loops (optional)

61. Use programs that use `for` loops to accomplish the following tasks:
- Sum all of the odd numbers between 0 and 100.
- Find the smallest item in a list of numbers.
- Simulate rolling a die until we reach a 5.

## Nesting within loops

62. We can place any valid python statement within either a while-loop or an if-statement. 

63. Among other things, this means that we can place loops within loops, or if-statements within if-statements. 

64. Similarly, we can place if-statements within loops, and vice-versa. This flexibility allows us to solve many complex problems.

65. By placing an if-statement within a loop, we can solve problems that require us to make a given decision multiple times. 

66. Write a program that uses a while-loop to print the output shown below. 
```Python
1
2
3
4
5
6
7
happy
8
9
10
```

67. As you can see, the program should print the numbers 1 through 10, except that between 7 and 8 it should print the word "happy". 

68. This can be accomplished by placing an if-statement within the while-loop to do something special for the lineNumber == 7 case.

<blockquote>Q19: Include your program for steps 65-68, including commments that document what the code is doing.</blockquote>

69. Write a program that plays a familiar guessing game.
- First your program will set some number to be the "correct answer"
- Then your program will ask the user to guess this answer until they get it right. 
- For each guess your program should give a hint based on whether the guess was too high or too low.

70. For example, a session with your program may look like the following:
```Python
Enter your guess: 46
Your guess is too low

Enter your guess: 97
Your guess is too high

Enter your guess: 62
Your guess is too low

Enter your guess: 88
Your guess is too high

Enter your guess: 82
CORRECT! You Win!
```

71. Things to consider:
- Begin your program with a line similar to: answer = 82. In a real game we would want to begin with a random number, but for today let's pick a single number that will always be the correct answer.
- This program will require a loop with some if-statements inside it.
- Each time through the loop, you must accept a new guess from the user. This can be done by using the function input inside the loop.

<blockquote>Q20: Include your program for steps 69-71, including commments that document what the code is doing.</blockquote>

72. Write a program that reads in three strings and prints them out in alphabetical order. 

74. For example:
```Python
Enter a word: hello
Enter a word: goodbye
Enter a word: zebra
In alphabetical order: goodbye hello zebra
```

75. Things to consider:
- String comparisons, such as word1 < word2, work by comparing the ASCII values of the characters in the two strings. This means that word1 will be considered "less than" word2 if it comes first alphabetically. (Well almost. The ordering can be surprising if we compare capital letters to lower-case letters because all ASCII codes for capitals precede all codes for lower-case letters. I suggest you only enter lower-case words when running your program.)
- Be sure to test your program using a variety of words in different orders. How many different combinations do you need to test to know that your program is correct? 
- This problem only requires if-statements, but your condition will need to be more complex than we have used before. A compound condition is one that includes multiple parts. Here are two examples. You may find that something similar will be useful in this program.

```Python
if number > 2 and number < 10:
  **do something interesting here**

if word1 > word2 and word2 > word 3:
  **do something interesting here**
```
<blockquote>Q21: Include your program for steps 72-75, including commments that document what the code is doing.</blockquote>

# Working with functions

<blockquote>Q22: In your own words, what is a function?</blockquote>

<blockquote>Q23: How do we create a function?</blockquote>

<blockquote>Q24: In your own words, what is an argument or parameter?</blockquote>

<blockquote>Q25: In you own words, what is a return value?</blockquote>

<blockquote>Q26: Why would we use functions?</blockquote>

76. Function syntax:
```Python
def function_name(arguments):
    statement(s)
    return result
 ```
 
77. We've already worked with a number of Python's built in named-functions, like `print()`, `dict()`, `input()`, `int()`, and `len()` in previous labs.

78. We define or name a function using the def keyword.
```Python
def my_function()
```

<blockquote>Q27: Write a function <code>is_even</code> that determines whether or not a number <code>n</code> is even. Answer includes your code + comments.</blockquote>

<blockquote>Q28: Write a function <code>average</code> that determines the average value of a list. Answer includes your code + comments.</blockquote>

<blockquote>Q29: Write a function <code>uniq</code> that takes a list and returns a new list containing only unique values.</blockquote>

# Lab Notebook Questions

Q1: In your own words, what is a boolean/logical expression?

Q2: In your words, what is as conditional statement (or conditional execution)?

Q3: Provide your code + comments for steps 13-18.

Q4: Describe how you approached writing the program for Q3.

Q5: Did the program return the results that you expected? Explain the output in your own words.

Q6: Explain what this program will output and why.

Q7: Include your modified code for step 26, including comments that describe what the code is doing.

Q8: Return to your Q3 program and modify so it prints one message if the user enters your favorite color, and a different message if not. In addition, your program should print a final message for every user, regardless of what they entered. Answer will include your modified code + comments that explain/describe what the code is doing.

Q9: What do you expect this code to output? Explain how this program works in your own words.

Q10: Modify the program from steps 35-48 so that it prints some word or phrase nine times, and also prints a line number at the beginning of each line. Answer will include code + comments.

Q11: In your own words, what is iteration?

Q12: In your own words, what is the difference between a `while` loop and a `for` loop?

Q13: Write a loop that prints out all numbers from 0 to 10. Include your code + comments that document how the code works.

Q14: Include your modified code for step 50, including commments that document what changes you made.

Q15: Include your modified code for steps 51-53, including commments that document what changes you made to address the errors.

Q16: Include your program for steps 54-56, including commments that document what the code is doing.

Q17: Include your program for steps 57-58, including commments that document what the code is doing.

Q18: Include your program for steps 59-60, including commments that document what the code is doing.

Q19: Include your program for steps 65-68, including commments that document what the code is doing.

Q20: Include your program for steps 69-71, including commments that document what the code is doing.

Q21: Include your program for steps 72-75, including commments that document what the code is doing.

Q22: In your own words, what is a function?

Q23: How do we create a function?

Q24: In your own words, what is an argument or parameter?

Q25: In you own words, what is a return value?

Q26: Why would we use functions?

Q27: Write a function `is_even` that determines whether or not a number n is even. Answer includes your code + comments.

Q28: Write a function `average` that determines the average value of a list. Answer includes your code + comments.

Q29: Write a function `uniq` that takes a list and returns a new list containing only unique values.
