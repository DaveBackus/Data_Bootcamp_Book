# Python fundamentals


---
**Overview.**  Time to start programming!  We work our way throughe start writing some programs using Python's core language.  work our way through some Python basics. We don't cover enough ground to do serious data work, but it lays a solid foundation  to build on.  

**Python tools.**  Numbers, strings, lists, functions, objects, and methods.

**Buzzwords.** Isn't that enough?  

---

We're now ready to explore the rudiments of Python.  We'll run across terms like "strings," "objects," and "methods."  Don't panic, it's just jargon.  This is Python, of course, but most of the concepts show up in pretty much any modern programming language.  We aren't ready yet to do anything of real interest, but the same logic and concepts will reappear when we start working with data.    

We intersperse Python concepts with an introduction to Spyder, the Python environment we described earlier.  Your first job is to start up Spyder.  If you don't know what that means, return to the previous chapter. Once it's running,  we'll work our way through the fundamentals of Python, the core of the language.  The distinction here is with "modules" or "packages" that allow Python to do more advanced things -- data management and graphics, for example.  We'll deal with them later.  


## The logic of Python programs

In a spreadsheet program such as Excel, we can connect cells to other cells.  Then when we change one cell, any other cells conected to it update automatically.  

Most computer programs, including Python programs, don't work that way.  They run one line at a time, starting at the top of the program and working through the list of instructions until they reach the end or stop for some other reason.  A program is just a detailed list of things we want the computer to do.  

Most of the programs in this course have the structure:  

* Input data.  
* Manipulate the data until it's in the form we want. 
* Produce some graphics that summarize the data in a compelling way.  

Each of these bullet points is typically associated with a number of lines of code, but that's the general idea.

"Do one thing at a time" is also good advice.  As you learn to write more complex programs, it's good practice to break long programs into smaller manageable pieces.  We'll see how that works as we go along.  


## Calculations in the IPython console 

One of the things we'll do repeatedly in Python is calculations with numbers.  That's a lot of what managing data is all about: adding things up, dividing one thing by another, and so on. We'll do this in the IPython console, typically located in lower right corner of Spyder (look for a tab with this label).

Here's how that works in Python.  Type these simple calculations into **Spyder's IPython console** one at a time:
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
The first line is our input, we typed it.  The second line is the response or output Python produces.  The numbers are sequential:  The number [1] increases to [2], [3], and so on.  

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
We might have expected the answer to be 8 (2 to the power 3), but evidently it's not.  What's going on?  The short answer is that the hat symbol `^` doesn't do powers in Python, as it does in Excel, it does something else (mtyn).  If we want to use an exponent (power), we do it this way: 
```
In [4]: 2**3
Out[4]: 8
```
The last calculation is the log function.  Entering `log(3)` generates the message:  ```NameError: name 'log' is not defined```.   We can use functions like `log` and `sqrt` in Python, just as we do in Excel, but we need to import them specially.  (And we will, but not yet.)  


## Assignments 

We can also "assign" numbers to variables:  names we use to store information.  Try these examples by typing them into the IPython console one at at time:  
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
This is sometimes helpful, sometimes confusing.  If you find it confusing, here's good advice from one of our friends:  Don't do it!  



## The `print()` function

In the previous section, we calculated `z = x/y`, but Python simply computed the answer, it didn't report it back to us.  If we want to verify the calculation, we need to tell Python to do so.  The simplest way to do this is with the print function.  The print function simply prints whatever we include in parentheses after the word print.  If we want to print more than one thing, we separate them with commas. That's the general structure of functions in Python:  a name (in this case `print`) followed by inputs (we call them arguments) in parentheses that are separated from each other by parentheses.

If we want to verify the calculation of `z`, we might type the command `print(z)` in the IPython console.  The input and output look like this:
```
In [7]: print(z)
0.6666666666666666
```
If we want to print all the calculations from the previous section, we type `print(x, y, z)`:  
```
In [8]: print(x, y, z)
2 3 0.6666666666666666
```
The spaces here are a matter of taste, you can skip them if you think it looks better.  


## Strings 

We also want to to be able to work with non-numerical data, collections of characters that might include letters, numerals, or other symbols.  Variable names are a common example.  We refer to such constructs as **strings**. No, not the stuff we tie packages with.  

Type these examples into the IPython console, one at a time:  
```
a = 'some'
b = 'thing' 
c = a + b 
d = '11.32'
```
What do you see?  The first two are probably obvious:  we assign the characters in single quotes on the right to the variables on the left.  The third line is something new:  we add the string `some` to the string `thing`.  What would you expect to get?  The answer is `c = 'something'`.  We've simply stitched the two strings together, one after the other.  

Strings allows us to produce better-looking output.  For example, in the previous section we can change the statement `print(z)` to `print('The value of z is ', z)`.  The first argument (input), `'The value of z is '`, is a string.  It produces the output `The value of z is  0.6666666666666666`, which is easier to understand.  Here's the same thing spread over two lines:
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
Our fathers brought forth.. """
print(longstring)
```
This produces the output 
```

Four score and seven years ago
Our fathers brought forth
```
The blank line comes from the empty space following the first triple quote.  And yes: you can make triple quotes from single quotes, and all of  this is mtyn.


## Comments 

One of the rules of good code is that **we explain what we've done -- in the code**.  In this class, we might think about writing code that one of our classmates can understand without help.  That generally means we should include some explanation -- in the code -- of what we've done.  These explanations are referred to as comments.  

You might have noticed in our test program the presence of hash character (#).  Anything in a line after a hash is a comment, meaning it's ignored by Python.  We can make short comments at the end of lines, or longer comments by putting a hash in the first column of a line.  

Or -- and this is one of our favorites -- we can include an extensive comment by surrounding it by triple quotes.  Officially this defines a string, but it's a string we don't use except as a long comment.  Here's an example from the start of our test program: 
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


To run this code, we need to save the file we copied it into.  In Spyder's editor, click on File in the upper left corner and choose Save.  If you want to choose a new file name (the default `Untitled0.py` isn't all that informative), choose Save as and choose a file name you prefer. With, of course, the extension py. Once we've done this, we can run the file in Spyder by clicking on the green arrow at the top of the editor window.  

The first three lines produce no output.  The last one generates the output `c =  something` in the IPython console.  


## Cells 

Spyder has a feature that we haven't seen in other Python editors:  we can carve out blocks of code ("cells") and run them separately.  That comes naturally in IPython notebooks, as we'll see later, and it's a useful feature of Spyder as well.  

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
The separator `#%%` in the middle divides this set of commands into two cells, which we can run separately.  That way we can run and test a small block of code without running the whole program.  It doesn't make much difference with code this simple, but in longer programs it can be a real time saver.   

Here's how it works.  Click on a code cell in the Spyder editor defined by the separator.  The cell will indicate its selection with a darker yellow background than the other cells.  Now go to the toolbar above the editor.  The large green triangle runs the whole program. The one to its right displays the text "Run current cell" if you move the cursor to it.  Click on it to run the selected cell.  


## Lists

Lists are one of the fundamental Python **data structures**, a term that means a specific organization of data.  A Python list is what it sounds like:  an ordered collection of items.  The items can be lots of things:  numbers, strings, variables, or even other lists.  We can create them by putting square brackets around a collection of items separated by commas.  Here are some examples:  
```
numberlist = [1, 5, -3]

a = 'some'
b = 'thing'
c = a + b 
stringlist = [a, b, c]		

biglist = [numberlist, stringlist]
```
(We repeat the definitions of (a,b,c) for completeness, but they're not necessary if you have already defined them.)  Copy this code into Spyder and run it.  What do you see if you type `print(numberlist)` in the IPython console?  What if you type `print(biglist)`?  


**Exercise.** Explain the output of the command `print(biglist)`.


## Slicing strings and lists 


We can access the elements of strings and lists by specifying the item number in square brackets after the string.  The only tricky part of this is remembering that Python (and some other programming languages, too) starts numbering at zero.  


Take, for example, the string `a = 'some'`.  If we want the first item/letter, we would type `a[0]`.  Yes, that's the first item; remember, we start at zero.  If we want the second, we type `a[1]`.  And so on.  And here's a good one:  If we want the last letter, we type `a[-1]`.  


**Exercise.** Print the third letter of the string `a`.  

We can also access sequential elements, but there's another tricky convention to deal with.  Let's see what the following commands do:  
```
c = 'something'
print('c[1] is', c[1])
print('c[1:2] is', c[1:2])
print('c[1:3] is', c[1:3])
print('c[1:] is', c[1:])
```
First first print statement gives us `o`, the second letter of `something`.  The next one does the same.  Why?  The convention is to stop one before the number, so this goes from 1 to 1, which is the second letter.  The next line gives us `om`, the second and third letters.  Why third?  Stick with us now, but here's the reason:  we go from 1 to 2 (one less than the second number), which is the second and third letters (we started counting at zero).  

Are you dizzy now?  Let's try a few more examples for practice.  


Slicing conventions similar to strings.
Examples:  {\tt numbers = [x, y, z], type(numbers),
print(numbers),
strings = [a, b, c, d],
all = numbers + strings, type(all),
print(all),
all[0], all[-1], all[3:], etc.}

Examples:  Add first and list, first and last with space in middle.  

**Exercise.** 
Last comma first.  

**Exercise.** 
Convert to lower case.  Upper case.  
Last name upper case.  



## Functions

We'll see shortly that there are often two ways to do things:
functions and methods.
We can tell functions because they come with arguments in parentheses.
In some cases, we even use function() if we don't have any input.  [??]

Here's a \href{https://docs.python.org/3.4/library/functions.html}{list}.
print...  len...  [??]

**Exercise.**
Wbat do the functions ```float```, ```int```, and ```str``` do?
What other functions would you like to know about?
(We'll never use most of them, but you never know.)


**Exercise.**
Suppose ```year``` is a string containing the year of a particular piece of data.
How would we construct a string containing the following year?

## Data types and conversions

[??]  {\tt len} and {\tt type}:
{\tt len(first), len(x), type(first), type(x)}.

Type conversions.
There are lots of occasions when we want --- or need -- to change type.
Suppose, for example, we want to convert {\tt year = '2011'},
which is defined as a string, to a number.
We can do that with {\tt int(year)}.  (Or {\tt float}, but we have something else in mind.



## Objects and methods

Most things in Python are {\bf objects}
(for example, {\tt x, z, first}).
(Experts may say at this point:  an {\bf object} is an {\bf instance} of a {\bf class}.
Ignore them.)
{\bf Methods} are ready-to-go things we can do with them.
The available methods depend on the object.
To get a list of available methods for a given object,
type in the IPython console: {\tt object.[tab]}.
When you find a method you're interested in,
go to Spyder's Object explorer
and type {\tt object.method} for a description and syntax.

Examples:  first.find('a'), x.is_integer()

**Exercise.**
Take ```lastfirst```
 and see what methods are available.

* Use lastfirst.find to find the location of the comma and decompose {\tt lastfirst} into {\tt first} and {\tt last}.
* Find a method that converts {\tt last} to all lower case.


## Python 2 and 3

There's a lot of code around written in earlier versions of Python, typically Python 2.7.  It's there because the people who wrote it started before Python 3 was up and running.  Since we're starting from scratch, we are planting ourselves firmly in Python 3 territory.  Still, you're likely to run across examples of Python 2 on the internet. The easiest way to tell the difference is the print command:  ```print(x)``` in Python 3 was ```print x`` (no parentheses) in Python 2.  There are lots of other differences, which is why it's essential we all use Python 3.  


## Programming style

Yes, style counts.  

PEP8 etc \\
\url{https://google-styleguide.googlecode.com/svn/trunk/pyguide.html}

Examples:  \\
\url{http://www.reddit.com/r/Python/comments/3639nl/what_is_the_most_beautiful_piece_of_python_code/}\\
\url{https://github.com/mitsuhiko/werkzeug/blob/master/werkzeug/routing.py} \\


\item Assignment idea:  convert list of strings to list with number of letters in each.  \\
Do in class?  \\
\url{http://www.reddit.com/r/Python/comments/35ubwo/newbie_for_programming_i_am_working_on_this/}


##  Other data structures

This whole section is mtyn:  we recommend you skim it, but don't worry about the details, you can come back to them if needed.  

The term **data structure** refers to the organization of a collection of data.  A list is a data structure.  ...  

http://en.wikipedia.org/wiki/Data_structure

Examples: tuples, dictionaries, and sets.  We'll cover them later as needed.
If you run across one of these terms, keep in mind it's just a different form
of organization, we can look up its properties when we need to.


##  Exercises

??

## Resources 

Here are some online resources we have found helpful:  


* Codecademy has an excellent [introduction to Python](http://www.codecademy.com/en/tracks/python).

*  {Python tutorial},
\href{https://docs.python.org/3.4/tutorial/introduction.html}{Section 3}.


* check this out:  https://wiki.python.org/moin/SimplePrograms

* Django Girls...  http://tutorial.djangogirls.org/en/python_introduction/index.html
Django is for web development..



* Sargent-Stachurski...



This is a test
