# Conditional Statements and Functions in Python

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

- [Conditional Statements](#conditional-statements)
  * [Operator Review](#operator-review)
  * [`'if` Statements](#if-statements)
  * [`if` Statements and Strings](#if-statements-and-strings)
  * [`if-else` Statements](#if-else-statements)
  * [Additional Work With `if` Statements](#additional-work-with-if-statements)
- [Control Flow](#control-flow)
- [Loops](#loops)
  * [`for` Loops](#for-loops)
    * [`for` Loops and Lists of Numbers](#for-loops-and-lists-of-numbers)
    * [`for` Loops and Strings](#for-loops-and-strings)
    * [Other `for` Loop Functions](#other-for-loop-functions)
      * [`range()`](#range)
      * [`enumerate()`](#enumerate)
    * [Other `for` Loop Considerations](#other-for-loop-considerations)
    * [`for` Loops: Putting It All Together](#for-loops-putting-it-all-together)
    * [Conditional Statements and `for` Loops](#conditional-statements-and-for-loops)
      * [`for` Loop Example A](#for-loop-example-a)
      * [`for` Loop Example B](#for-loop-example-b)
    * [OPTIONAL: Additional Practice With `For` Loops](#optional-additional-practice-with-for-loops)
  * [`while` Loops](#while-loops)
    * [`while` Loop Examples](#while-loop-examples)
      * [`while` Loop Example A](#while-loop-example-a)
      * [`while` Loop Example B](#while-loop-example-b)
      * [`while` Loop Example C](#while-loop-example-c)
    * [Additional `while` Loop Considerations](#additional-while-loop-considerations)
      * [`while` Loops and Nested Conditional Statements](#while-loops-and-nested-conditional-statements)
      * [`break`](#break)
      * [`continue`](#continue)
  * [Additional Work With Loops](#additional-work-with-loops)
- [Functions](#functions)
  * [Built-In Functions](#built-in-functions)
  * [Named Functions](#named-functions)
    * [How Named Functions Work](#how-named-functions-work)
    * [Name Function Examples](#named-function-examples)
      * [Function Example A](#function-example-a)
      * [Function Example B](#function-example-b)
    * [Additional Function Considerations](#additional-function-considerations)
      * [Fruitful Versus Void Functions](#fruitful-versus-void-functions)
      * [Parameters](#parameters)
      * [Scoping](#scoping)
      * [Docstrings](#docstrings)
  * [Why Functions](#why-functions)
  * [Additional Work With Functions](#additional-work-with-functions)
- [Lab Notebook Questions](#lab-notebook-questions)

# Conditional Statements

1. So far, all the programs we have written work by executing each statement in the program in order, from top to bottom. 

2. To write programs that solve more complex problems, we need mechanisms that will allow statements to be executed in more complex ways. 

3. For example, we might like to execute some statements under some conditions but not others, or we might like to execute some statements multiple times. 

4. Behold- conditional statements!

5. We can use conditional statements to change the behavior of a program based on whether specific conditions are or are not met.

6. To put this another way, conditional statements check boolean expressions (i.e. conditions), and change the behavior of the program accordingly.

## Operator Review

7. Operators used to compare two objects:
- `==`    equal to
- `==`    equal to
- `!=`    not equal to
- `>=`    greater than or equal to
- `>`     greater than
- `<`     less than
- `<=`    less than or equal to

8. Boolean logical operators:
- `and`   both must be true
- `or`    one or both must be true
- `not`   reverses the truth value

9. We can use and test for conditions in a few key ways, specifically through `if` statements and `loops`.

10. More on loops later, but for now...

## `if` Statements

11. Python's comparison operators serve as conditional tests that return a True or False.
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

12. `if` statements use the `if` keyword to test if a condition is true.

13. `if` statements are conditional, meaning that there is a test to determine if a statement is true or false, and then the computer takes some defined action.

14. The basic syntax for an `if` statement:

```Python
if condition:
 statement(s)
```

15. The `if` statement tests if a particular condition is true. And if so, executes the command nested under the initial `if` statement.

16. To illustrate that another way:

```Python
if this condition is true:
 then do this thing
```

17. A couple things to note about this syntax:
- A colon always follows the first line of an `if` statement
- The code that will run if the statement is true is nested or intented beneath the `if` keyword

18. For example, let's say we have a Python program where the variable `n` equals `0`.

19. We want to write a program that, if `n` equals `0`, prints the message `n is zero`.

20. We can do that using an `if` statement.

```Python
n = 0

if n == 0:
 print('n is zero')
```

21. Let's see another `if` statement in action.

22. This time, we are going to ask the user for an input, and use that input in an `if` statement.

```Python
number = int(input("Enter a number: "))
if number > 0:
  print("That number is positive.")
```

<blockquote>Be sure to double check indentation in your code.</blockquote>

23. See what happens when you enter different number values.

24. If you enter a positive number, the `That number is positive` message will print. 

25. If you enter a negative number or zero, no message is printed. 

26. Now let's add a second `print` statement (a message of your choosing) at the end of the program.

27. The indentation for this second `print` statement needs to match `print("That number is positive.")` in the previous example.

```Python
number = int(input("Enter a number: "))
if number > 0:
  print("That number is positive.")
  print('Second print statement goes here')
```

28. How does entering different values affect the program output?

29. Now, let's change the indentation for the second`print` statement.

30. This time, instead of matching the `print("That number is positive.")` indentation, the second print statement will be aligned with the `if` statement.

```Python
number = int(input("Enter a number: "))

if number > 0:
  print("That number is positive.")

print('Second print statement with modified indentation')
```

31. How does modifying the indentation affect the program output?

32. When Python encounters an `if` statement it checks whether the associated condition (in this case, `number > 0`) is true. 

33. If the condition is true, Python executes all statements that immediately follow AND are indented beneath the `if` clause. 

34. If the condition is false, no commands indented beneath the `if` clause are skipped. 

35. In either case, execution will then continue with the next un-indented statement. 

## `if` Statements and Strings

36. The `if` statement and comparison operators work for comparing strings just like they do for comparing numbers.

37. Let's write a program that asks the user to enter a color name.

```Python
color = input("Enter a color name")

print("You entered the color " + color)
```

38. Now, you want to use an `if` statement to print a message telling the user if the color they entered is your favorite color.

39. If the color entered by the user is not your favorite color, no printed response is needed.

40. Now, add a final line to your program that will print `Goodbye!` whenever the program ends, regardless of the color entered.

41. Test your program to see if it works.

42. Note- to checking whether your program works, you will have to run it at least twice, entering colors that test both possible outcomes.

<blockquote>Q1: Provide your code + comments for steps 37-42.</blockquote>

<blockquote>Q2: Describe how you approached writing the program for Q1.</blockquote>

## `if-else` Statements

43. Suppose we want to print one message when the condition (`number > 0`) is true, and a different message when the condition is false. 

44. We can do that by using an `else` clause along with an `if` keyword.

45. The basic syntax for `if-else`:

```Python
if condition:
 statement(s)
else:
 statement(s)
```

46. The statement indented beneath the `if` keyword will only run when the `if` condition is true.

47. In an `if-else` statement, the statement indented beneath `else` will only run if the `if` condition is not true (or false).

48. An example that illustrates this logic:

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

<blockquote>Q3: Return to the program you wrote for Q1 and Q2. Modify this program so it prints one message if the user enters your favorite color, and a different message if not. In addition, your program should print a final message for every user, regardless of what they entered. Include code + comments.</blockquote>

## Additional Work With `if` Statements

49. We can also test for values in a list.
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

<blockquote>Q4: Explain what this program will output and why.</blockquote>

50. We can check more than one condition using chained conditional statements (or chained conditionals).
- Key term: *chained conditionals*

```Python
a = 200
b = 33
c = 500

if a > b or a > c:
 print("At least one of the conditions is True")
```

51. We can also nest conditional statements inside another conditional statement.
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

52. NOTE: Python works from left to right evaluating a logical expression or conditional statement. Python stops evaluating when it finds the expression is `True` or `False` based on the conditional statement.

53. Syntax errors will interrupt program execution.

<blockquote><a href="https://www.w3schools.com/python/python_conditions.asp">Click here</a> to learn more about conditional statements in Python, via W3Schools.</blockquote>

# Control Flow

54. In programming languages, control flow governs the order in which a program executes.

55. In Python, control flow is regulated through conditional statements, loops, and function calls- all things we will be covering in this lab!

56. Examples include:
- `if` statements
- `for` and `while` loops
- Functions

57. A few examples of control flow and conditional execution in action.

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

58. The previous section of the lab focused on the `if` and `if..else` keywords.

59. We can also use the `elif` keyword along with the `if` keyword to introduce a new condition. 

60. Python will test the `elif` condition if previous conditions are not true.

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

61. Loop statements are a type of conditional statement that rely on the underlying logic of conditional execution.

62. In Python, loops repeatedly execute a series of tasks.
- Key term: *loop(s), looping*

63. Each time through the body of a loop is called an iteration.
- Key term: *iteration*

64. An iteration can involve things like iterating through items in a list or testing if specific conditions are met, and then doing “something” as the result or endpoint for the loop.

65. Loops normally contains a variable that changes within the body of the loop so that we can eventually exit the loop. 

66. If a loop never exits, then this is called an infinite loop.
- Key term: *infinite loop*

67. In short, the computer will continue to follow the loop instructions, until it can’t perform that function any longer. 

## `for` Loops

68. `for` loops let us iterate through a definite set of objects.

69. In each iteration through the `for` loop, Python will:
- Extract one element from the dataset
- Execute the body of the `for` loop using the item bound to the element
- Go back to the first step
- Keep iterating through the loop until reaching the end of the dataset

70. The basic syntax in a `for` loop:

```Python
for item in dataset:
 statement(s)
```

71. In this syntax, `item` is a placeholder for each element in `dataset`. 

72. You can replace `item` with another word or letter character.

```Python
for i in dataset
```

73. In this syntax, `dataset` stands for the list of items we want Python to iterate over.

74. That list of items could be a list variable, a list of numbers, a string of characters, etc.

### `for` Loops and Lists of Numbers

75. Let's say we have a list of numbers, and we want Python to iterate through each number in the list and print the number.

```Python
for i in [0, 1, 2, 3]:
 print(i)
```

76. Alternatively, we could create a variable for our list of numbers.

```Python
# create list of numbers
number_list = [0, 1, 2, 3]

# for loop
for i in number_list:
 print(i)
```

77. The loop command steps through the list one value at a time. 

78. The loop continues until it reaches the end of the list. 

### `for` Loops and Strings

79. We can also use a `for` loop to iterate over a list of strings.

80. Let's say we have a list of pepper types.

```Python
peppers = ["bell", "poblano", "jalapeno", “banana”, “chile”, “cayenne”]
```

81. We can use a `for` loop to iterate over each string in the list.

```Python
peppers = ["bell", "poblano", "jalapeno", “banana”, “chile”, “cayenne”]

for x in peppers:
 print(x)
```

82. We can also use a `for` loop to iterate through characters in a single string.

83. Let's say we want to iterate over the characters in the string `elements`.

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

### Other `for` Loop Functions

#### `range()`

84. We can use the `range()` function to generate a list of numbers.

```Python
range(0, 3)
```

85. We can use the `range()` function as part of a `for` loop.

```Python
for i in range(0, 3):
 print(i)
```

#### `enumerate()`

86. In a previous lab, we talked about how each item in a list has an index, or a number that indicates its position in the list.

87. We can use the `enumerate()` function to generate a list of pairs containing each item in the list and its index.

```Python
list(enumerate(['a','b','c'])
```

88. We can use the `enumerate()` function as part of a `for` loop.

```Python
for index, letter in enumerate('abc'):
 print(index, letter)
```

89. In this last example, `for index, letter` instructed Python to iterate over both components in the `enumerate()` output.

90. `print(index, letter)` instructed Python to print both components for each element.

### Other `for` Loop Considerations

91. Let's say we have a nested list, or a list that contains sub-lists.

```Python
numlist = [[0, 42], [67543, -987654]]
```

<blockquote>Q5: What do you think will happen if we write a for loop for numlist? What would be a single element in the list?</blockquote>

92. Remember in a nested list, or a list with sub-lists, each sub-list is an item or element in the list.

<blockquote><a href="https://www.w3schools.com/python/python_for_loops.asp">Click here</a> to learn more about <code>for</code> loops in Python, via W3Schools.</blockquote>

### `for` Loops: Putting It All Together

93. Let's start combining `for` loops with some of the concepts covered in previous labs.
```Python
#loops through a list of the members of the House Stark.

characters = ['Arya', ' Benjen', 'Bran', 'Catelyn', 'Eddard', 'Rickon', 'Robb', 'Sansa']

for character in characters:
  print(character.title() + "Stark")
```

<blockquote>Note the use of the plural for the name of the list and the singular for the individual item is not required. We are just declaring variables here. We can use anything to name the individual items (e.g. for person in characters). All this does is set a new variable for the individual item. Standard convention is to use the plural and singular terms so that the person reading the code can interpret what it is doing.</blockquote>

94. Remember the loop command steps through the list one value at a time. The loop continues until it reaches the end of the list. 

95. In this case, for each item in the list called `“characters”` the program prints the value of each `“character”` in the list concatenated with the string `" Stark”`. 

96. This produces the output:
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

97. Now let's look at a different loop.
```Python
characters = ['Arya', ' Benjen', 'Bran', 'Catelyn', 'Eddard', 'Rickon', 'Robb', 'Sansa']
print('Members of the House Stark:')
for character in characters:
  print(character.title() + " Stark")
print(characters[0].title() + " is my favorite.")
```

<blockquote>Q6: What do you expect this code to output? Explain how this program works in your own words.</blockquote>

98. Comments that walk through each line of this program:
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

### Conditional Statements and `for` Loops

99. We can also use nested conditional statements as part of `for` loops.

#### `for` Loop Example A

100. For example, let's say we have `message = 'Hello World!'`, and we want to see in which positions the letter `l` appears.

101. Our program would need to...
- Iterate over each character in the string
- Check to see if that character matches `l`
- If the character matches `l`, output some kind of message that indicates the position

<blockquote>Q7: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?</blockquote>

<blockquote>Q8: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?</blockquote>

102. Here is one approach to this program.

103. First, we could create a variable with our `Hello World!` string.

```Python
message = 'Hello World!'
```

104. Then, we could use a `for` loop with the `enumerate()` function to access each element in the string and its index.

```Python
for entry in enumerate(message):
 print(entry)
```

105. This gets us each character in the string and its index.

106. Next, we could use a conditional statement to test for equality.

```Python
if entry[1] == 'l':
 print(f'Found an 'l' at position {entry[0]}')
```

107. In this block of code, we are accessing the second value in the `enumerate()` output for each character in the string.

<blockquote>Remember: Python starts counting at zero (0).</blockquote>

108. Each iteration through the loop tests if the `entry` character matches `l`.

109. If the conditional statement is true, then the `print()` message will output the position index.

110. To put that all together:

```Python
message = 'Hello World!'

for entry in enumerate(message):
 print(entry)
 
 if entry[1] == 'l':
  print(f'Found an 'l' at position {entry[0]}')
```

111. You can modify this code to include other messages or test for other characters.

<blockquote>Q9: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?</blockquote>

#### `for` Loop Example B

112. Let's work through another example.

113. This time, let's say we have a list of names that might be used to refer to Notre Dame's Department of Computer Science and Engineering.

```Python
#here is a list of names
names=['department of computer science and engineering', 'computer science department', 'cse']
```

114. We want to write a program that prints out `cse` in all upper-case letters, but prints out any other list element in title case.

115. Our program would need to...
- Iterate over each element in the list
- Check to see if that element matches `cse`
- If so, print out that element in upper case
- Otherwise, print out that element in title case

<blockquote>Q10: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?</blockquote>

<blockquote>Q11: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?</blockquote>

116. Here is one approach to this program.

117. First, we could use a `for` loop to iterate through each item in the list.

```Python
for name in names:
 SOMETHING WILL GO HERE
```

118. Then, we could use an `if` statement to test if the element equals `cse`

```Python
if name == 'cse':
 DO SOMETHING 
```

119. Now remember if the element matches `cse`, we want to print the element in upper-case letters.

120. So we could finish the `if` statement.

```Python
if name == 'cse':
 print(name.upper())
```

121. If the element does not match `cse`, we want to print the element in title-case letters.

122. We can use an `else` statement combined with a `print()` statement.

```Python
else:
 print(name.title())
```

123. To put that all together:

```Python
names=['department of computer science and engineering', 'computer science department', 'cse']

for name in names:
  if name == 'cse':
    print(name.upper())
  else:
    print(name.title())
```

124. This program returns the output
```Python
`Department of Computer Science and Engineering`
`Computer Science Department`
`CSE`
```

<blockquote>Q12: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?</blockquote>

### OPTIONAL: Additional Practice With `for` Loops

125. Some tasks if you are wanting additional practice with `for` loops:
- Sum all of the odd numbers between 0 and 100.
- Find the smallest item in a list of numbers.
- Simulate rolling a die until we reach a 5.

## `while` Loops

126. Another way to modify the control flow of a program is to have it execute one or more statements repeatedly.

127. A `while` loop will test for an initial condition and continue iterating through the loop until the condition is `False`.

128. In each iteration through the `while` loop, Python will:
- Evaluate the initial condition (which is a Boolean true/false expression)
- If the condition is `False`, exit the loop and continue the program
- If the condition is `True`, then execute other statements in the body of the loop and return to the beginning of the loop

129. The basic syntax for a `while` loop:

```Python
while condition:
 statement(s)
```

130. To express this logic another way:

```Python
while THIS CONDITION IS TRUE
 DO THIS THING
```

### `while` Loop Examples

#### `while` Loop Example A

131. Let's look at a sample `while` loop that uses the `<` (less than) comparison operator.

```Python
n = 0

while n < 10:
 print(n)
 n = n +1
```

132. To walk through what is happening in each line of this program...

133. `n=0` assigns the value zero (0) to the variable `n`.

134. `n < 10` is a conditional statement that will return `True` as long as `n` is less than `10`.

135. So `while n < 10` sets up a `while` loop in which the body of the loop (the lines of code nested or indented beneath the first line of the loop) will run as long as the initial condition is `true`.

136. The first line in the body of the loop `print(n)` prints the value of `n` for that iteration.

137. The second line in the body of the loop `n = n+1` reassigns the value of `n` to be `n + 1`.

138. After executing both lines in the body of the loop, the next iteration of the loop begins by evaluating the `n < 10` conditional statement.

<blockquote>Q13: What is the value of <code>n</code> in the first iteration of the loop? What happens to the value of <code>n</code> in each iteration of the loop?</blockquote>

<blockquote>Q14: What is the endpoint for this loop, or when will this loop end?</blockquote>

139. REMINDER: Loops that have no endpoint are called *infinite loops*.

#### `while` Loop Example B

140. Another example of a `while` loop.

```Python
# assign x variable
x = 10

# looping structure using greater than or equal to conditional statement
while x >= 0:
 print(x)
 x = x-1

# message to print once loop has completed
print('I'm done!')
```

<blockquote>Q15: Now it's your turn. Describe what is happening in each line of this program. You can use the explanations for the previous example as a model.</blockquote>

<blockquote>Q16: What is the value of <code>x</code> in the first iteration of the loop? What happens to the value of <code>x</code> in each iteration of the loop?</blockquote>

<blockquote>Q17: What is the endpoint for this loop, or when will this loop end?</blockquote>

#### `while` Loop Example C

141. Let's look at a `while` loop that includes strings and integers.

```Python
count = 1
while count <= 5:
   print ("Notre")
   print ("Dame")
   count = count + 1
print ("Done")
```

142. On the first line (`count = 1)` we create a variable named `count` and set it equal to one. 

143. The next statement (`while count <= 5:`) contains a condition `count <= 5`. 

144. This condition will be evaluated, and if it is true, the statements indented beneath it will be executed. 

145. Once that has happened, execution returns to the top of the `while` loop, where the condition is checked again. 

146. This process will continue, with the indented statements being executed repeatedly as long as (i.e., `while`) the condition continues to be true. 

147. If the condition is ever false when it gets checked, execution will jump to the first statement after those associated with the loop (the first un-indented statement).

<blockquote>Q18: What will happen if you remove the statement <code>count = count + 1</code> from this program? Remove the statement to verify your prediction.</blockquote>

<blockquote>Q19: Modify the program from step 141 so that it prints some word or phrase nine times, and also prints a line number at the beginning of each line. Answer will include code + comments.</blockquote>

148. For example, your output might look like the following: 

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

### Additional `while` Loop Considerations

#### `while` Loops and Nested Conditional Statements

149. As with `for` loops, `while` loops let us nested conditional statements.

150. We can place any valid python statement within either a while-loop or an if-statement. 

151. Among other things, this means that we can place loops within loops, or if-statements within if-statements. 

152. Similarly, we can place if-statements within loops, and vice-versa. This flexibility allows us to solve many complex problems.

153. By placing an if-statement within a loop, we can solve problems that require us to make a given decision multiple times. 

154. An example:

```Python
# assign i variable
i = 1

# while loop
while i < 200:
 if i > 150:
  print('Expression value is greater than 150')
 elif i > 100:
  print('Expression value is greater than 100')
 elif i > 50:
  print('Expression value is greater than 50')
 elif i < 50:
  print('Expression value is less than 50')
 i += 10

print("That's all, folks!")
```

155. In this example, we have a `while` loop that includes four nested conditional statements.

156. NOTE: `i += 10` in the last line of the `while` loop reassigns the value of `i` through an expression equivalent to `i = i + 10`.

<blockquote>Q20: Now it's your turn. Describe what is happening in each line of this program. You can use explanations for previous examples as a model.</blockquote>

<blockquote>Q21: What is the value of <code>i</code> in the first iteration of the loop? What happens to the value of <code>i</code> in each iteration of the loop?</blockquote>

<blockquote>Q22: What is the endpoint for this loop, or when will this loop end?</blockquote>

#### `break`

157. We can exit a loop immediately by using the `break` statement.

158. `break` will stop the `while` loop even if the condition is true.

159. For example:

```Python
# assign i variable 
i = 1

# while loop
while i < 6:
 print(i)
 if i == 3:
  break
 i += 1
```

160. In this example, the loop breaks as soon as the `i == 3` condition is `True`.

<blockquote>Q23: Describe what would happen in each iteration of this loop. How many iterations would it take for the <code>break</code> statement to come into effect?</blockquote>

#### `continue`

161. We can skip the rest of the body of a loop and move on to the next iteration using `continue`.

162. For example:

```Python
# assign the i variable
i = 0

# while loop
while i < 6:
 i += 1
 if i ==3:
  continue
 print(i)
```

163. In this example, the current iteration of the loop will stop when `i == 3` is true.

164. Unlike with `break`, the loop will not end.

165. Instead when `i == 3` is true, the loop will skip over the final nested `print` statement and return to the beginning of the loop for a new iteration.

<blockquote>Q24: Describe what would happen in each iteration of this loop. How many iterations would it take for the <code>break</code> statement to come into effect?</blockquote>

<blockquote>Q25: What is the endpoint for this loop, or when will this loop end?</blockquote>

## Additional Work With Loops

166. The following lab notebook questions can use `for` or `while` loops, a variety of conditional statements and comparison operators, and other Python concepts covered thus far.

### Lab Notebook Question 26

Q26: Write a loop that prints out all numbers from 0 to 10. Include your code + comments that document how the code works.
  
### Lab Notebook Question 27

Q27: Convert the following Python code to use a while loop instead of a for loop. Include your modified code with comments.

```Python
numbers = [5, 4, 7, 0, 1]
count   = 0

for number in numbers:
    if not number:
        break
    count += 1

print(count)
```

### Lab Notebook Question 28

Q28: Write a program that prints a list of the first nine positive integers and their squares. Include code + comments.

Your output should look similar to the following:
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

### Lab Notebook Question 29

Q29: Write a program that counts from 10 down to 1, and then prints "Blastoff!" 

Your output should similar to the following:
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

### Lab Notebook Question 30

Q30: Write a program that asks the user to enter three numbers: a starting value, an ending value, and an increment. Your program should then "count" based on these criteria, as shown in the sample output below. Include code + comments.

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

### Lab Notebook Question 31

Q31: Write a program that uses a while-loop to print the output shown below. Include code + comments.
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

The program should print the numbers 1 through 10, except that between 7 and 8 it should print the word "happy". This can be accomplished by placing an `if` statement within the `while` loop to do something special for the `lineNumber == 7` case.

### Lab Notebook Question 32

Q32: Write a program that plays a familiar guessing game.
- First your program will set some number to be the "correct answer"
- Then your program will ask the user to guess this answer until they get it right. 
- For each guess your program should give a hint based on whether the guess was too high or too low.

For example, the output for a session with your program may look like the following:
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

Things to consider:
- Begin your program with a line similar to: answer = 82. In a real game we would want to begin with a random number, but for today let's pick a single number that will always be the correct answer.
- This program will require a loop with some if-statements inside it.
- Each time through the loop, you must accept a new guess from the user. This can be done by using the function input inside the loop.

### Lab Notebook Question 33

Q33: Write a program that reads in three strings and prints them out in alphabetical order. Include code + comments.

Sample output for this program:
```Python
Enter a word: hello
Enter a word: goodbye
Enter a word: zebra
In alphabetical order: goodbye hello zebra
```

Things to consider:
- String comparisons, such as word1 < word2, work by comparing the ASCII values of the characters in the two strings. This means that word1 will be considered "less than" word2 if it comes first alphabetically. (Well almost. The ordering can be surprising if we compare capital letters to lower-case letters because all ASCII codes for capitals precede all codes for lower-case letters. I suggest you only enter lower-case words when running your program.)
- Be sure to test your program using a variety of words in different orders. How many different combinations do you need to test to know that your program is correct? 
- This problem only requires if-statements, but your condition will need to be more complex than we have used before. A compound condition is one that includes multiple parts. Here are two examples. You may find that something similar will be useful in this program.

```Python
if number > 2 and number < 10:
  **do something interesting here**

if word1 > word2 and word2 > word 3:
  **do something interesting here**
```

### Additional Lab Notebook Questions

Q34: In your own words, what is iteration?

Q35: In your own words, what is the difference between a `for` loop and a `while` loop?

# Functions

166. In Python, a function is a named sequence of statements that performs a computation.
- Key term: *function*

167. To execute a function, we call it by name and pass it an appropriate set of input arguments.
- Key terms: *function call, input argument*

168. A function takes zero or more arguments as inputs and returns zero or more outputs as a result.

169. The output or result of a function is called the return value.
- Key terms: *function output or return value*

170. Data, parameters, or arguments can be passed into a function.

171. Functions can also return data.

## Built-In Functions

172. We have actually already been working with a number of Python's built-in functions.

173. These include `print()`, `dict()`, `input()`, `int()`, and `len()`.

174. We call built-in functions using the function name, followed by parenthesis.
- `print()`
- `dict()`
- `input()`
- `int()`
- `len()`

## Named Functions

175. But Python also allows you to create (and name) your own functions.
- Key term: *named function(s)*

176. We can define or name a function using the `def` keyword.

177. A function definition includes a few core components:
- The name of the new function
- The list of function arguments
- The sequence of statements to execute when the function is called

178. The core syntax for defining your own function:

```Python
# use def keyword to define function name
def function_name(argument):
 statement(s)
 return result
```

179. Let's unpack each of those components.

180. `def function_name()` is the name you are giving to the function you create- this is the header for the function definition.

181. Function names have many of the same rules as variable names- no spaces or special characters.

182. `argument` is the argument that will be passed to the function.

183. When we are initially defining the function, the `argument` value is typically a placeholder.

184. Later in the program when we call the named function, the argument being passed to the function goes in these parenthesis.

185. The nested or indented line `statement(s)` is the body of the function definition.

186. It includes a sequence of statements to execute when the function is called.

187. The nested or indented line `return result` is a placeholder for the function output or endpoint- it is also part of the body of the function definition.

### How Named Functions Work

188. So what happens when we use the `def` keyword to create a named function?

189. Programs are always executed sequentially, one statement at a time.

190. Function definitions create new functions, but do not execute the bodies or statements within the functions UNTIL the functions are called.

191. When we call a named function, the program jumps to the definition for the function being called, executes the function's body, and then returns to the point in the program where the function was called and resumes executing the program.

192. Let's look at some examples.

#### Named Function Examples

##### Function Example A

193. Let's say we want to create a function that prints an input string three times.

```Python
def printThreeTimes(string):
 for x in range(3):
  print(string)
```

194. To walk through what is happening in this function definition...

195. `def printThreeTimes(string)` assigns the function name (`printThreeTimes`).

196. This is the name we will use when calling this function elsewhere in the program.

197. `for x in range(3)` is part of the body of the function.

198. This line of code uses a `for` loop to say "for each integer value in the range leading up to but not including 3," do.....something!

199. That "something" is the `print` statement nested in the `for` loop.

200. That `print` statement will output the `string` value each time through the `for` loop.

201. Now let's see this named function in action.

```Python
string = "There's no place like home."

printThreeTimes(string)
```

202. We wouldn't need to assign the string to a variable- we could pass it directly to the function.

```Python
printThreeTimes("There's no place like home.")
```

##### Function Example B

203. Let's look at another example.

204. Here, we want to create a function that prints an input string a specific number of times.

<blockquote>Q36: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?</blockquote>

<blockquote>Q37: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?</blockquote>

205. Here is one approach to this task.

206. First, we want to define the name of our function, as well as what input arguments it will take.

207. We know that we need to pass a string to be printed AND an integer for the number of times to the named function.

208. For now, let's call the string `string` and the integer `times`.

209. So the function header could look like:
```Python
def printNTimes(string, times):
```

210. We've named the `printNTimes` function and established we will be passing two arguments to the function.

211. Next, we could us a `for` loop in combination with the `range()` function to accomplish a specific task for a specific number of iterations.

```Python
for x in range(times)
```

212. As in the previous named function example, we can think of the `for` loop as saying "for each integer value in the range leading up to but not including the `times` value," do.....something!

213. That "something" is the `print` statement nested in the `for` loop.

214. That `print` statement will output the `string` value each time through the `for` loop.

215. Putting that all together:

```Python
def printNTimes(string, times):
 for x in range(times):
  print(string)
```

216. So now we have a function that prints our string a number of times specified by the `times` value in combination with the `range()` function.

<blockquote>Q38: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?</blockquote>

<blockquote>Q39: How would you write a program that calls the function you have created? Include code + comments.</blockquote>

<blockquote><a href="https://www.w3schools.com/python/python_functions.asp">Click here</a> for more information on named functions in Python, via W3Schools.</blockquote>

### Additional Functions Considerations

#### Fruitful Versus Void Functions

217. Functions that yield a result are considered fruitful.
- Key term: *fruitful function(s)*

218. To output a result, a function uses the return statement to pass results back to the function call.

219. Functions that perform a computation but do not yield a result are considered void.
- Key term: *void function(s)*

220. By default, the return value for void functions is `None`.

#### Parameters

221. Inside a function, the arguments are assigned to local variables, or placeholder variables.

222. These local variables are called parameters.
- Key term: *parameter*

#### Scoping

223. The name of the parameter inside the function is separated or isolated from the name outside the function.

224. This separation of namespaces is called scoping.
- Key term: *scoping*

225. An example of scoping:

```Python
# assign x variable
x = 1

# function definition
def print_number(x):
 print(x)
 
# print x variable
print(x)

# call named function
print_number(2)
```

226. In short, the placeholder variables (or parameters) we use inside the function definition are separated or isolated from any instance where a variable or parameter with the same name is used outside the function definition.

<blockquote><a href="https://www.w3schools.com/python/python_scope.asp">Click here</a> to learn more about scope in Python, via W3Schools.</blockquote>

#### Docstrings

227. We can add comments to a function definition by including a docstring under the function header.
- Key term: *docstring*

228. As we've learned previously, single-line comments in Python are declared using the `#` symbol, and multi-line comments in Python are declared using the <code>'''</code> symbol.

229. Docstrings are declared using triple single quotes (<code>'''</code>) or triple double quotes (`"""`).

230. Best practice is to start the docstring just below the function header.

231. Another best practice for docstrings is to begin with a capital letter and end with a period.

232. The docstring should briefly describe what the function does.

233. Let's see this in action with an example from earlier in the lab.

```Python
def printThreeTimes(string):
 '''Prints an input string three times'''
 for x in range(3):
  print(string)
```

234. We have a couple options for accessing the contents of the docstring elesewhere in the program.

235. We can use the `_doc_` method (underscore, doc, underscore).
```Python
print(Using _doc_:")
print(printThreeTimes._doc_)
```

236. Or we can use the `help()` function.
```Python
print("Using help:")
help(printThreeTimes)
```

237. Multi-line docstrings can be used to provide additional description about the named function, including information about parameters, arguments, and returns.

<blockquote><a href="https://www.python.org/dev/peps/pep-0257/">Click here</a> to learn more about docstrings in Python, via Python.org documentation.</blockquote>

## Why Functions

238. By this point in the lab, your brain might be hurting. Mine is.

239. Let's take a step back and think about *why* we would want or need to use functions in our code.

<p align="center"><a href="https://github.com/kwaldenphd/python-conditional-statements-functions/blob/main/Python_Function_Meme.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/python-conditional-statements-functions/blob/main/Python_Function_Meme.png?raw=true" /></a></p>

240. Python functions can help with programming tasks in a number of key ways.

241. They help yield **more concise code*** by eliminating the need to write out code for the same task multiple times.

242. In doing so, they also **improve code readability**.

243. Functions also help us **more effectively test and debug code**.

244. Again, because we are creating reusable pieces or building blocks of code, we can more readily pinpoint where things are going wrong or not working in our code.

245. By allowing us to define and call functions for common tasks, they **promote code reuse and modularity**.

## Additional Work With Functions

Q40: Write a function `is_even` that determines whether or not a number `n` is even. Include code + comments for the function definition as well as a sample function call.

Q41: Write a function `average` that determines the average value of a list. Include code + comments for the function definition as well as a sample function call.

Q42: Write a function `uniq` that takes a list and returns a new list containing only unique values. Include code + comments for the function definition as well as a sample function call.

Q43: The Python code below is suppose to create a function that determines if the given list of numbers is sorted. That is, the function should return `True` if each item in the list is less than the next item. Unfortunately, there are a few errors in the code below. Identify the errors and fix the code. Include your modified code with comments that document what changes you made to address the errors.

```Python
is_sorted([1, 2, 3, 4, 2])

def is_sorted(numbers):
    ''' Return whether or not the list of numbers is sorted '''
    for i in range(len(numbers) - 1):
        if numbers[i] > numbers[i + 1]:
            return False
    return True
```

Q44: In your own words, what is a function?

Q45: In your own words, how do we create a function?

Q46: In your own words, what is an argument or parameter?

Q47: In your own words, what is a return value?

Q48: Why would we use functions, or what is the value of functions?

# Lab Notebook Questions

Q1: Provide your code + comments for steps 37-42.

Q2: Describe how you approached writing the program for Q1.

Q3: Return to the program you wrote for Q1 and Q2. Modify this program so it prints one message if the user enters your favorite color, and a different message if not. In addition, your program should print a final message for every user, regardless of what they entered. Include code + comments.

Q4: Explain what this program will output and why.

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

Q5: What do you think will happen if we write a `for` loop for `numlist`? What would be a single element in the list?

```Python
numlist = [[0, 42], [67543, -987654]]
```

Q6: What do you expect this code to output? Explain how this program works in your own words.

```Python
characters = ['Arya', ' Benjen', 'Bran', 'Catelyn', 'Eddard', 'Rickon', 'Robb', 'Sansa']
print('Members of the House Stark:')
for character in characters:
  print(character.title() + " Stark")
print(characters[0].title() + " is my favorite.")
```

Q7: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?

Q8: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?

Q9: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?

Q10: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?

Q11: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?

Q12: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?

Q13: What is the value of n in the first iteration of the loop? What happens to the value of n in each iteration of the loop?

Q14: What is the endpoint for this loop, or when will this loop end?

Q15: Now it's your turn. Describe what is happening in each line of this program. You can use the explanations for the previous example as a model.

Q16: What is the value of x in the first iteration of the loop? What happens to the value of x in each iteration of the loop?

Q17: What is the endpoint for this loop, or when will this loop end?

Q18: What will happen if you remove the statement count = count + 1 from this program? Remove the statement to verify your prediction.

Q19: Modify the program from step 141 so that it prints some word or phrase nine times, and also prints a line number at the beginning of each line. Answer will include code + comments.

Q20: Now it's your turn. Describe what is happening in each line of this program. You can use explanations for previous examples as a model.

```Python
# assign i variable
i = 1

# while loop
while i < 200:
 if i > 150:
  print('Expression value is greater than 150')
 elif i > 100:
  print('Expression value is greater than 100')
 elif i > 50:
  print('Expression value is greater than 50')
 elif i < 50:
  print('Expression value is less than 50')
 i += 10

print("That's all, folks!")
```

Q21: What is the value of i in the first iteration of the loop? What happens to the value of i in each iteration of the loop?

Q22: What is the endpoint for this loop, or when will this loop end?

Q23: Describe what would happen in each iteration of this loop. How many iterations would it take for the break statement to come into effect?

```Python
# assign i variable 
i = 1

# while loop
while i < 6:
 print(i)
 if i == 3:
  break
 i += 1
```
 
Q24: Describe what would happen in each iteration of this loop. How many iterations would it take for the break statement to come into effect?

```Python
# assign the i variable
i = 0

# while loop
while i < 6:
 i += 1
 if i ==3:
  continue
 print(i)
```

Q25: What is the endpoint for this loop, or when will this loop end?

Q26: Write a loop that prints out all numbers from 0 to 10. Include your code + comments that document how the code works.

Q27: Convert the following Python code to use a while loop instead of a for loop. Include your modified code with comments.

```Python
numbers = [5, 4, 7, 0, 1]
count   = 0

for number in numbers:
    if not number:
        break
    count += 1

print(count)
```

Q28: Write a program that prints a list of the first nine positive integers and their squares. Include code + comments.

Q29: Write a program that counts from 10 down to 1, and then prints "Blastoff!"

Q30: Write a program that asks the user to enter three numbers: a starting value, an ending value, and an increment. Your program should then "count" based on these criteria, as shown in the sample output below. Include code + comments.

Q31: Write a program that uses a `while` loop to print the output shown below. Include code + comments. The program should print the numbers 1 through 10, except that between 7 and 8 it should print the word "happy". This can be accomplished by placing an `if` statement within the `while` loop to do something special for the `lineNumber == 7` case.

```
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

Q32: Write a program that plays a familiar guessing game.
- First your program will set some number to be the "correct answer"
- Then your program will ask the user to guess this answer until they get it right.
- For each guess your program should give a hint based on whether the guess was too high or too low.

Q33: Write a program that reads in three strings and prints them out in alphabetical order. Include code + comments.

Q34: In your own words, what is iteration?

Q35: In your own words, what is the difference between a for loop and a while loop?

Q36: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?

Q37: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?

Q38: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?

Q39: How would you write a program that calls the function you have created? Include code + comments.

Q40: Write a function is_even that determines whether or not a number n is even. Include code + comments for the function definition as well as a sample function call.

Q41: Write a function average that determines the average value of a list. Include code + comments for the function definition as well as a sample function call.

Q42: Write a function uniq that takes a list and returns a new list containing only unique values. Include code + comments for the function definition as well as a sample function call.

Q43: The Python code below is suppose to create a function that determines if the given list of numbers is sorted. That is, the function should return True if each item in the list is less than the next item. Unfortunately, there are a few errors in the code below. Identify the errors and fix the code. Include your modified code with comments that document what changes you made to address the errors.

```Python
is_sorted([1, 2, 3, 4, 2])

def is_sorted(numbers):
    ''' Return whether or not the list of numbers is sorted '''
    for i in range(len(numbers) - 1):
        if numbers[i] > numbers[i + 1]:
            return False
    return True
```

Q44: In your own words, what is a function?

Q45: In your own words, how do we create a function?

Q46: In your own words, what is an argument or parameter?

Q47: In your own words, what is a return value?

Q48: Why would we use functions, or what is the value of functions?
