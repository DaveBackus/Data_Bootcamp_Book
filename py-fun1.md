# Python fundamentals


---
**Overview.**  Time to start programming!  We work our way through some simple programs using Python's core language.  We don't cover enough ground to do serious data work, but it lays a solid foundation  to build on.  

**Python tools.**  Numbers, strings, Spyder, lists, objects, methods, object explorer.

**Buzzwords.** Isn't that enough?  

---

We're now ready to explore the rudiments of Python.  We'll run across terms like "strings," "objects," and "methods."  Don't panic, it's just jargon.  This is Python, of course, but most of the concepts show up in pretty much any modern programming language.  We aren't ready yet to do anything of real interest, but the same logic and concepts will reappear when we start working with data.    

We intersperse Python concepts with an introduction to Spyder, the Python coding environment we described earlier.  Your first job is to **start up Spyder**.  If you don't know what that means, return to the previous chapter. Once it's running,  we'll work our way through the fundamentals of Python, the core of the language.  The distinction here is with "modules," "packages," or "libraries" that allow Python to do more advanced things -- data management and graphics, for example.  We'll deal with them later.  


## The logic of Python programs

In a spreadsheet program such as Excel, we can connect cells to other cells.  Then when we change one cell, any other cells connected to it update automatically.  

Most computer programs, including Python programs, don't work that way.  They run one line at a time, starting at the top of the program and working through the list of instructions until they reach the end or stop for some other reason.  A program is just a detailed list of things we want the computer to do.  

Most of the programs in this course have the structure:  

* Input data.  
* Manipulate the data until it's in the form we want. 
* Produce some graphics that summarize the data in a compelling way.  

Each of these bullet points is typically associated with a number of lines of code, possibly a large number, but that's the general idea.

"Do one thing at a time" is also good advice for writing programs.  As you learn to write more complex programs, it's good practice to break long programs into smaller manageable pieces.  We'll see how that works as we go along.  


## Calculations in Spyder's IPython console 

One of the things we'll do repeatedly in Python is calculations with numbers.  That's a lot of what managing data is all about: adding things up, dividing one thing by another, and so on. We'll do this in the IPython console, typically located in lower right corner of Spyder (look for a tab with this label).

Here's how calculations work in Python.  Type these simple calculations in Spyder's IPython console one at a time:
```
2*3
2 * 3
2/3
2^3 
2**3
log(3) 
```
For each one, pay close attention to what happens.  The first one multiplies 2 times 3, and (hopefully) gives us 6 as the answer.  The input and output look like this in the console:
```
In [1]: 2*3
Out[1]: 6
```
The first line is our input, we typed it.  The second line is the response or output Python produces.  The numbers in square brackets []are sequential:  The number [1] increases to [2], [3], and so on, as we continue.  

The second calculation, `2 * 3`, does the same thing.  The space around the * doesn't change the output.  As a general rule, we can put spaces wherever we think they make the code more readable.  

The third calculation is division.  The input and output are 
```
In [3]: 2/3
Out[3]: 0.6666666666666666
```
The fourth calculation, `2^3`, gives us 
```
In [4]: 2^3
Out[4]: 1
```
We might have expected the answer to be 8 (2 to the power 3), but evidently it's not.  What's going on?  The short answer is that the hat symbol `^` doesn't do powers in Python, as it does in Excel.  It does something else (mtyn).  If we want to use an exponent (power), we do it this way: 
```
In [4]: 2**3
Out[4]: 8
```
Our last calculation is the log function.  Entering `log(3)` generates the message:  ```NameError: name 'log' is not defined```.   We can use functions like `log` and `sqrt` in Python, just as we do in Excel, but we need to import them specially.  (And we will, but not yet.)  

**Exercise.**  What happens if you try to calculate the square root of 2 with `sqrt(2)`, as you would in Excel?  Do any alternatives come to mind?  (Speak to your neighbors, see if they have any ideas.)


## Assignments 

We can also "assign" numbers to **variables**:  names we use to store information.  Try these examples by typing them into the IPython console one at at time:  
```
x = 2 
y = 3 
z = x/y 
```
The first line takes the value 2 and stores it in the variable `x`.  We say we assigned the numerical value 2 to the variable `x`.  We can use `x` later in other calculations.  The second line assigns the value 3 to a new variable `y`. The last line takes `x`, divides it by `y`, and stores the result in `z`.   

This is mtyn, but you can also do multiple assignments in the same line.  The first two lines above can be rewritten together as 
```
x, y = 2, 3 
```
This is sometimes helpful, sometimes confusing.  

Here's good advice from one of our friends:  **If you find it confusing, don't do it!**  That's a general rule:  write code that's easy to understand.  Your friends will thank you.  And you'll thank yourself when you come back to your own code several months later.  



## The `print()` function

In the previous section, we calculated `z = x/y`, but Python simply computed the answer, it didn't report it back to us.  If we want to verify the calculation, we need to tell Python to do so.  The simplest way to do this is with the print function.  The print function simply prints whatever we include in parentheses after the word print.  If we want to print more than one thing, we separate them with commas. That's the general structure of functions in Python:  a name (in this case `print`) followed by inputs (we call them arguments) in parentheses that are separated from each other by commas.

If we want to verify the calculation of `z`, we could type `print(z)` in the IPython console.  The input and output look like this:
```
In [7]: print(z)
0.6666666666666666
```
If we want to print all the calculations from the previous section, we type `print(x, y, z)`:  
```
In [8]: print(x, y, z)
2 3 0.6666666666666666
```
The spaces in the print statement are a matter of taste, you can skip them if you think it looks better.  


## Strings 

We also want to to be able to work with non-numerical data, collections of characters that might include letters, numerals, or other symbols.  Variable names are a common example (GDP, Income, Volatility).  We refer to such constructs as **strings**. No, not the stuff we tie packages with. (On the origin of the term, see [here](http://stackoverflow.com/questions/880195/the-history-behind-the-definition-of-a-string).) 

Type these examples into the IPython console, one at a time:  
```
a = 'some'
b = 'thing' 
c = a + b 
d = '11.32'
```
What do you see?  The first two are probably obvious:  we assign the characters in single quotes on the right to the variables on the left.  The third line is something new:  we add the string `some` to the string `thing`.  What would you expect to get?  The answer is `c = 'something'`.  We've simply stitched the two strings together, one after the other.  

Strings allows us to produce better-looking output.  For example, in the previous section we can change the statement `print(z)` to `print('The value of z is ', z)`.  The first argument (input), `'The value of z is '`, is a string.  The second argument, `z`, is a variable.  Together they produce the output `The value of z is  0.6666666666666666`, which is clearer than the number `0.6666666666666666` on its own.  Here's the same thing spread over two lines:
```
message = 'The value of z is '
print(message, z)
```
We've taken the components of the previous print statement and expressed them in two statements to make it more readable.  (You might ask yourself:  Which do you prefer?  Why?)

**Exercise.** What is a string?  How would you explain it to a classmate?  

**Exercise.** What happens when you type `a * 5` into the console? What about `d * 5`?  What is going on here?  

**Exercise.** This one's a little harder.  Assign your first name as a string to the variable `firstname` and your last name to the variable `lastname`.  Construct a new variable equal to your first name, a space, then your last name.  


## Single, double, and triple quotes

We defined strings by putting characters between single quotes, as in `a = 'some'`.  That's our standard practice, but Python treats single and double quotes the same.  We could have typed `a = "some"` instead with the same effect.  The main reason for using single quotes is laziness (you don't have to hit the shift key).  On occasion, we use double quotes if the string includes a single quote: 
```
f = "I don't believe it"
print(f)
```
The output of the print statement is `I don't believe it`, which includes the apostrophe. This doesn't come up very often, in our experience, but there it is just in case.  


Triple quotes are similar, but they can be used to define strings that go over multiple lines: 
```
longstring = """
Four score and seven years ago 
Our fathers brought forth. """
print(longstring)
```
This produces the output 
```

Four score and seven years ago
Our fathers brought forth
```
The blank line comes from the empty space to the right of the first triple quote.  And yes: you can make triple quotes from single quotes, and all of  this is mtyn.


## Comments 

One of the rules of good code is that **we explain what we've done -- in the code**.  In this class, we might think about writing code that one of our classmates can understand without help.  That generally means we should include some explanation -- in the code -- of what we've done.  These explanations are referred to as comments.  

You might have noticed in our test program the presence of the hash character (#).  Anything in a line after a hash is a comment, meaning it's ignored by Python.  We can make short comments at the end of lines, or longer comments by putting a hash in the first column of a line.  

Or -- and this is one of our favorites -- we can include an extensive comment by surrounding it with triple quotes.  Officially this defines a string, but it's a string we don't use except as a long comment.  Here's an example from the start of our test program: 
```
"""
Data Bootcamp test program checks to see that we're running Python 3.  
Written by Dave Backus, March 2015  
Created with Python 3.4 
"""
```
We recommend putting something like this at the top of every program you write.  You'll thank us later, when you go back and try to figure out what it is you did a few months ago.  


## Running programs in Spyder 

If we're writing longer programs, it's generally easier to type them into an editor where we can correct any mistakes we make, just as we do in a word processing program.   


To see how this works, copy these commands into a new file in the Spyder editor:  
```
a = 'some'
b = 'thing' 
c = a + b 
print('c = ', c')
```
(If you don't recall how to open a new file in Spyder, see the previous chapter.) 


To run this code, we need to save the file we copied it into.  In Spyder's editor, click on File in the upper left corner and choose Save.  To set the file name (the default `Untitled0.py` isn't all that informative), choose Save as and pick a file name you prefer. With, of course, the extension py. Once we've done this, we can run the file in Spyder by clicking on the green arrow at the top of the editor window.  

The first three lines produce no output.  The last one generates the output `c =  something` in the IPython console.  


## Cells in Spyder 

Spyder has a feature we haven't seen in other Python editors:  we can carve out blocks of code ("cells") and run them separately.  That comes naturally in IPython notebooks, as we'll see later, and it's a useful feature of Spyder as well.  

The idea is to put the separator `#%%` between blocks of code, called **cells**, so that we can run them separately.  Consider the code:  
```
x = 2
y = 3
z = x/y
print('z =', z)
#%%
a = 'some'
b = 'thing'
c = a + b 
print('c =', c)
```
The separator `#%%` in the middle divides this set of commands into two cells, which we can run separately.  That way we can run and test blocks of code without running the whole program.  It doesn't make much difference with code this simple, but in longer programs it can be a real time saver.   

Here's how it works.  In the Spyder editor, click on a code cell.  The cell will indicate its selection with a darker yellow background than the other cells.  Now go to the toolbar above the editor.  The large green triangle runs the whole program. The one to its right displays the text "Run current cell" if you move the cursor to it.  Click on it to run the selected cell.  

**Exercise.** Copy the code above into your Python program.  Run each cell.  Check the output to make sure it worked.  


## Lists

Lists are one of the fundamental Python **data structures**, a term that means a specific organization of data.  A Python list is what it sounds like:  an ordered collection of items.  The items can be lots of things:  numbers, strings, variables, or even other lists.  We can create them by putting square brackets around a collection of items separated by commas.  Here are some examples:  
```
numberlist = [1, 5, -3]

a = 'some'
b = 'thing'
c = a + b 
stringlist = [a, b, c]		
```
(We repeat the definitions of (a,b,c) for completeness, but they're not necessary if you have already defined them.)  Copy this code into Spyder and run it.  What do you see if you type `print(numberlist)` in the IPython console?  

We can combine lists in two ways.  The statement `biglist = numberlist + stringlist` produces a list containing all the elements of `numberlist` and `stringlist`, so we have six items altogether.  Type `print(biglist)` to verify that.  The statement `biglist2 = [numberlist, stringlist]` produces a new list with two items:  the lists `numberlist` and `stringlist`.  It's what you might call a "list of lists."  That's not something we're likely to do, to be honest.  The point is simply that lists are flexible objects.  


**Exercise.** Run the statements 
```
mixedlist = [a, b, c, numberlist]
print(mixedlist)
```
What is the output?  How would you explain it to your classmate?  


## Slicing strings and lists 


We can access the elements of strings and lists by specifying the item number in square brackets.  The only tricky part of this is remembering that Python (and some other programming languages, too) starts numbering at zero.  


**Slicing strings.** Take, for example, the string `a = 'some'`.  If we want the first item/letter, we would type `a[0]`.  Yes, that's the first item; remember, we start at zero.  If we want the second, we type `a[1]`.  And so on.  And here's a good one:  If we want the last letter, we type `a[-1]`.  And if we want the one before the last one, we type `a[-2]`.  Both give us `'m'`. 

We can summarize the numbering convention by writing the word `some` on a piece of paper with room between the letters.  Below them, write the numbers, in order:  0, 1, 2, 3.  Label this row "counting forward."  Below that, start from the right (below the `e`) and count backwards:  -1, -2, -3, -4.  Label this row "counting backwards."


**Exercise.** Print the third letter of the string `firstname = 'Monty'`.  

We can also access sequences of characters, but there's another tricky convention to deal with.  Let's see what the following commands do:  
```
c = 'something'
print('c[1] is', c[1])
print('c[1:2] is', c[1:2])
print('c[1:3] is', c[1:3])
print('c[1:] is', c[1:])
```
The first print statement gives us `o`, the second letter of `something`.  We label it element 1 because we start numbering at zero.  The next one does the same.  Why?  The convention is to stop one before the number, so this goes from 1 to 1, which is the second letter.  The next line gives us `om`, the second and third letters.  Why third?  Stick with us now, but here's the logic:  we go from 1 to 2 (one less than the second number), which is the second and third letters (we started counting at zero).  

Are you dizzy now?  Let's try a few more examples for practice.  


**Exercise.** Find the last letter of the string `python = 'Python'`.  Find the second to last letter using both the forward and backward counting conventions.  


**Exercise.** Extract the string `'thon'` from `python`. 


**Slicing lists.**  We count the same way we did with strings, but the objects here are items in lists not characters in strings.  Let's see if we can teach ourselves.  

**Exercise.** Take the list `numberlist = [1, 5, -3]`.  Use slicing to set a variable `first` equal to the first item.  Set another variable `last` equal to the last item.  Set a third variable `allbut` equal to the list without its last item.  


## Functions

We now have several kinds of "objects" to work with:  numbers, strings, and lists.  There are more on the way, but that's a good start.  But what can we do with them?  Python has two basic ways to do things:  functions and methods.  We'll talk about methods in the next section and talk about functions in this one.  We can identify functions because they come with arguments in parentheses -- the print function, for example.  

**Common functions.** Python has a lot of basic ("built-in") functions.  We won't use most of them, but here are some we've found useful:   

* `type`.  This tells us what kind of variable we have.  To see how it works, type the following into the IPython console:  
```
type(2)
type(2.5)
type(c) 
type(stringlist)
type('11.32')
```
Think about this on your own for a minute.  What do you get?  What do you think the output means?  

     Not to kill the suspense, but here's what we should get.  The first one gives us the output `int`, which stands for integer:  a whole number like 1, 2, 3, and so on.  The second one gives us `float`, a so-called floating point number like most of those we run across in Excel and life in general.  The third one gives us `str`, which tells us that it's a string.  The fourth one is a list.  The last one is a trick question:  it's a list, too, even though it looks like a number. 

    The type function is more helpful than you might guess.  A lot of what we do in programming is deal with data of different types and, in some cases, convert one type to another.  The first step is often to identify the type of the object of interest.  We don't see much of that because it deals with a limited set of inputs:  basically numbers and strings.  

* `len` (length).  This tells us the length of a piece of an object.  To see how it works, type the following into the IPython console:  
```
len(a)
len(c)
len(numberlist)
```
The first one gives us the number of characters in the string `a`, namely 4 (`'some'`).  The second one does the same for the string `c = 'something'` (7).  The last one tells us the length of the list `numberlist` (3).  

*  Type conversions.  Suppose we have an object of one type (the string `11.32`) and want to convert it to another (the floating point number `11.32`).  We could use the code 
```
d = '11.32'
d_flt = float (d)
```
The new variable `d_flt` has type `float`.  Similarly, we can convert it back to a string with the statement `d_str = str(d_num)`. 

<!-- ??  https://www.reddit.com/r/Python/comments/3c344g/so_apparently_type_is_of_type_type/ -->


**Getting help in Spyder.**  If you want to know more about a function called (say) `function`, there are several ways to learn more in Spyder:  

* Type `function?` in the IPython console.  
* Type `help(function)` in the IPython console.  
* Type `function` in the Object inspector.  

We use the latter a lot.  If it fails, either because there's no help or the help is inadequate, we're back to Google fu.  


**Exercise.**  What is the length of the string `d = '11.32'`?  Does the answer make sense to you?  


**Exercise.** Are there other functions that interest you?  See [here](https://docs.python.org/3.4/library/functions.html) for the official list.  

**Exercise.** What do the functions `min()` and `sorted()` do?  (It's conventional to include the parentheses to remind is that they're functions.)  Apply them to `'some'` and see what happens.  

**Exercise.**  This one is tricky, but it came up in some work we were doing.  Suppose `year` is a string containing the year of a particular piece of data.  How would we construct a string containing the following year?  



## Objects and methods

Lots of things in Python are referred to as "objects:" numbers, strings, variables, lists, and lots of other things.  (Experts may say at this point:  an object is an "instance" of a "class."  Ignore them.)  "Methods" are ready-to-go things we can do with them.  The available methods depend on the object.  A lot of Python is "object-oriented," which means we apply methods to objects to accomplish what you might think you need a function for.  Trust us, the jargon is more difficult than just doing it.  

Suppose we have an object.  How can we find the methods available to work with it?  Consider, for example, the list `numberlist = [1, 5, -3]`.  To find the list of methods, we can use the IPython console and type:  `numberlist.[tab]`.  This wonderful piece of technology is referred to as **tab completion.**  The inputs here are the object (here ``numberlist`), the period or dot, and the tab key.  That should pop up a window with a list of methods in alphabetical order.  In the example, that starts like this:  
```
numberlist.append
numberlist.clear
numberlist.copy
numberlist.count
```
For more information, we type the relevant method into the Object explorer.  For the method `numberlist.append`, we get the description
```
Definition:  append(object)
Type:  Function of None module 
L.append(object) -> None -- append object to end.
```
Well, that's pretty opaque, maybe we oversold this approach.  What `append` does is add an item to the end of a list.  The statement `numberlist.append(7)` adds `7` to the end of the list, changing `numberlist` to `[1, 5, -3, 7]`.  

**Example.** Set `firstname = 'Chase'`.  The method `lower` converts it to lower case.  If we type `firstname.lower` into the Object explorer, we see that it's a function and comes with parentheses.  If you type `firstname.lower()` into the IPython console, the response is `'chase'`.  Without the parentheses, it doesn't work.  


**Exercise.** Find a method to convert `firstname` to all upper case letters.  

**Exercise.**  Run the commands 
```
firstname = 'John'
lastname  = 'Lennon'
firstlast = firstname + ' ' + lastname 
```
Find a method to replace n's in `firstlast` with asterisks.  


## Python 2 and 3

There's a lot of code around written in earlier versions of Python, typically Python 2.7.  It's there because the people who wrote it started before Python 3 was up and running.  Since we're starting from scratch, we are planting ourselves firmly in Python 3 territory.  Still, you're likely to run across examples of Python 2 on the internet. The easiest way to tell the difference is the print command:  `print(x)` in Python 3 was `print x` (no parentheses) in Python 2.  There are lots of other differences, which is why it's essential we all use Python 3.  



## Resources 

Here are some online resources we have found helpful:  


* Codecademy has an excellent [introduction to Python](http://www.codecademy.com/en/tracks/python). It uses Python 2, but that's not essential for most things.  

* The official [Python tutorial](\href{https://docs.python.org/3.4/tutorial/introduction.html) is very good.  

<!-- http://tutorial.djangogirls.org/en/python_introduction/index.html -->


