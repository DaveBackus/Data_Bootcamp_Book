# Python fundamentals 1


---
**Overview.**  Time to start programming!  We work our way through the essentials of Python's core language.  Part 1 of 2.  

**Python tools.**  Syntax, Spyder, calculations, assignments, strings, lists, built-in functions, objects, methods, tab completion, object inspector.  

**Buzzwords.** Isn't that enough?  

**Trigger warning.**  Technical content, cannot be mastered without effort.  

**Code.**  [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_fundamentals_1.py).

---

We're now ready to explore the rudiments of Python.  We'll run across terms like "strings," "objects," and "methods."  Don't panic, it's just jargon.  This is Python, of course, but similar concepts show up in pretty much any modern programming language.  We aren't ready yet to do anything of real interest, but the same logic and concepts will reappear when we start working with data.  

The beauty and challenge of writing computer programs is that we need to be precise.  If we mistype anything, the program won't work.  Or it might seem to work, but the output won't be what we expect.  In formal terms, the **syntax** -- the set of rules governing the language -- is less flexible than natural language (English, for example).  

We mix Python concepts with an introduction to Spyder, the Python coding environment we described earlier.  Your first job is to **start up Spyder**.  If you don't know what that means, return to the previous chapter. Once it's running,  we'll work our way through the fundamentals of Python, the core of the language.  The distinction here is with "modules," "packages," or "libraries" that allow Python to do more advanced things -- data management and graphics, for example.  Think of them as plug-ins or extensions that we can call on when needed. We'll deal with them later.  


## The logic of Python programs

In a spreadsheet program such as Excel, we can connect cells to other cells.  Then when we change one cell, any other cells connected to it update automatically.  

Most computer programs, including Python programs, don't work that way.  They run one line at a time, starting at the top of the program and working through the list of instructions until they reach the end or stop for some other reason.  A program is just a detailed list of things we want the computer to do.  

Most of the programs in this course have the structure:  

* Input data.  
* Manipulate the data until it's in the form we want. 
* Produce some graphics that summarize the data in a compelling way.  

Each of these bullet points is typically associated with a number of lines of code, possibly a large number, but that's the general idea.

<!-- 
Reminders:  Spyder, IPython...  
-->

## Calculations in Spyder's IPython console 

One of the things we'll do repeatedly in Python is calculations with numbers.  That's a lot of what managing data is all about: adding things up, dividing one thing by another, and so on. We'll do this initially in Spyder's **IPython console**, typically located in the upper right corner (look for a tab with this label).

To see how calculations work in Python, type these expressions in Spyder's IPython console one at a time:
```python 
2*3
2 * 3
2/3
2^3 
2**3
log(3) 
```
Type each one into the console, hit return, and look to see what happens.  The first one multiplies 2 times 3, and (hopefully) gives us 6 as the answer.  The input and output look like this in the console:
```python 
In [1]: 2*3
Out[1]: 6
```
The first line is our input, we typed it.  The number in brackets `[1]` is a line number.  We don't type it, it's there in the console to begin with.  As we proceed the number [1] increases to [2], [3], and so on.  The second line is the response or output Python produces.  

The second calculation, `2 * 3`, does the same thing.  The spaces around the * don't change the output.  As a general rule, we can put spaces wherever we think they make the code more readable.  

The third calculation is division.  The input and output are 
```python 
In [3]: 2/3
Out[3]: 0.6666666666666666
```
The fourth calculation, `2^3`, gives us 
```python 
In [4]: 2^3
Out[4]: 1
```
We might have expected the answer to be 8 (2 to the power 3), but evidently it's not.  What's going on?  The short answer is that the hat symbol `^` doesn't do powers in Python, as it does in Excel.  It does something else (mtyn).  

This is a good opportunity to practice our **Google fu**:  

**Exercise.** Use Google to search for "python exponents."  How do we compute 2 to the power 3? 

We find (after wading through the links) that exponents in Python are done this way: 
```python 
In [4]: 2**3
Out[4]: 8
```

Our last calculation is the log function.  Entering `log(3)` generates the message:  `NameError: name 'log' is not defined`.   We can use functions like `log` and `sqrt` in Python, just as we do in Excel, but we need to import them specially.  (And we will, but not yet.)  This is an example of a **syntax error**:  we have used language that Python doesn't understand.  Here the message is pretty clear:  it doesn't know what `log` means.  In other cases, the error message may be more mysterious.  

**Exercise.**  What happens if you try to calculate the square root of 2 with `sqrt(2)`, as you would in Excel?  Do any alternatives come to mind?  (Speak to your neighbors, see if they have any ideas.)


## Assignments 

Or maybe we should say "assignments" in scare quotes.  We say we "assign" numbers to "variables," names we use to store information.  Here are three examples;  type them into the IPython console one at at time. 
```python 
x = 2 
y = 3 
z = x/y 
```
What's going on here?  The first line takes the value 2 and stores it in `x`, which we refer to as a "variable."  We say we "assigned" the numerical value 2 to the variable `x`, which is now available for future calculations.  That's really helpful, because we can call on `x` whever we need to use it.  In Excel, we could put something in a cell (say, b7) and refer to it that way, but giving it a name is simpler for many purposes.  

Continuing:  The second line assigns the value 3 to a new variable `y`. The last line takes `x`, divides it by `y`, and stores the result in `z`.   All of these lines are "assignments."  

**Exercise.** Type `w = 7` in the IPython console.  What does the code `w = w + 2` do?  Why is it not a violation of basic mathematics?  

**Exercise.**  Suppose we borrow 200 for one year at an interest rate of 5 percent.  If we pay interest plus principal at the end of the year, what is our total payment?  Compute this using the variables `principal` and `i`.  How does your answer change if the interest rate rises to 7 percent?  

**Exercise.** Real GDP in the US (the total value of things produced) was 15.58 trillion in 2013 and 15.96 trillion in 2014.  What was the growth rate?  

**Exercise.**  Suppose we have two variables, `x` and `y`.  How would you switch their values, so that `x` takes on `y`'s value and `y` takes on `x`'s?  

<!--
This is mtyn, but you can also do multiple assignments in the same line.  The first two lines above can be rewritten together as 
```python 
x, y = 2, 3 
```
This is sometimes helpful, sometimes confusing.  

Here's good advice from a friend:  **If you find it confusing, don't do it!**  That's a general rule:  Write code that's easy to understand.  Your friends will thank you.  And you'll thank yourself when you come back to your own code later.  
-->


## The `print()` function

Many of our programs will contain code of the form 
```python 
In [7]: print(z)
0.6666666666666666
```
Evidently what this has done is display the value of `z`, namely `0.6666666666666666`.  This is really helpful, because Python typically computes what we ask it to compute, but doesn't report the answer back to us.  That's how Python -- and other languages -- typically work.  If we want to report the result, we need to say so.  

The simplest way to do this is with the print function.  The print function displays whatever we include in parentheses after the word print:  for example, ``print(x)`.  If we want to print more than one thing, we separate them with commas; for example, `print(x, y)`. That's the **general structure of functions** in Python:  a function name (in this case `print`) followed by inputs (known as "arguments") in parentheses that are separated by commas.   

As we have seen, if we want to verify the calculation of `z`, we can type `print(z)` in the IPython console.  If we want to print all the calculations from the previous section, we could type `print(x, y, z)`:  
```python
In [8]: print(x, y, z)
2 3 0.6666666666666666
```

<!--
The spaces in output generated by the print statement are a matter of taste, we can change them to anything we like using the `sep` argument.  For example, to change them to (comma, space), we would type `print(x, y, z, sep=', ')`.  Try it and see.  

We'll talk more about getting help shortly, but in the meantime you might type `print?` in the IPython console.  What do you see?  What do you think it means?  Write down any questions you have.
-->  

**Exercise.**  How would you print `x`, `y`, and `z` separated by colons (:)?  Add space to make the output look better.  


**Getting help in Spyder.**  If you want to know more about the print function, here are two good ways to do it in Spyder:  

* Type `print?` in the IPython console.  
* Type `print` in the Object inspector.  

We use them both a lot.  If they fail, either because there's no help or the help is incomprehensible, we fall back on Google fu.  


**Exercise.**  What do the `sep` and `end` arguments do?  What does `end='\n'` do?  Try some examples to verify your guess. 

<!-- ?? One last thing.  You'll note that ?? Escapes... \n, \t, etc -->


## Strings 

We also want to to be able to work with non-numerical data, collections of characters that might include letters, numbers, or other symbols.  Such things show up a lot in data work, as variable names (GDP, Income, Volatility) and even as data (country or customer names, for example).  We refer to such constructs as **strings**. No, not the stuff we tie up packages with, but a "string" of characters like letters or numbers.  It's one of many mysterious uses of ordinary words we'll run across as we learn to code.  For more on this one, see [here](http://stackoverflow.com/questions/880195/the-history-behind-the-definition-of-a-string).  

We create strings with quotation marks:  'Chase', "Spencer", 'Sarah', "apple", and even '12' are all strings.  Single and double quotes both work.  The last example is a confusing one, because it looks like a number.  It's not.  If we try to use it as a number, it doesn't work.  Try, for example, `'12'/3`.  This generates the error:  `TypeError: unsupported operand type(s) for /: 'str' and 'int'`.  What this means is that we tried to divide a string by an integer.  It's no different to Python than trying to divide your name by three, it can't make sense of it.  

Thus we see that `12` is a number, but `'12'` is a string.  

Here are some other examples, which we assign to variable names for later use. Type them into Spyder's IPython console **one at a time**:  
```python 
a = 'some'
b = 'thing' 
c = a + b 
d = '11.32'
```
What do you see?  The first two are probably obvious:  we assign the characters in single quotes on the right to the variables on the left.  The third line is something new:  we add the string `some` to the string `thing`.  What would you expect to get?  Try `print(c)` to see.  The answer is `c = 'something'`.  We've simply stitched the two strings together, one after the other.  We'll see that operations like this are extremely helpful when we're working with data. 

Strings also allow us to produce better-looking output.  For example, in the previous section we can change the statement `print(z)` to `print('The value of z is ', z)`.  The first argument (or input), `'The value of z is '`, is a string.  The second argument, `z`, is a variable.  Together they produce the output `The value of z is  0.6666666666666666`, which is clearer than the number `0.6666666666666666` on its own.  Here's the same thing spread over two lines:
```python
message = 'The value of z is'
print(message, z)
```
Here we've taken the components of the previous print statement and expressed them in two statements to make it more readable.  (You might ask yourself:  Which do you prefer?  Why?)  

**Exercise.** What is a string?  How would you explain it to a friend?  

**Exercise.** This one's a little harder.  Assign your first name as a string to the variable `firstname` and your last name to the variable `lastname`.  Use them to construct a new variable equal to your first name, a space, then your last name.  

**Exercise.** What happens when you type `a * 3` into the console? What about `d * 3`?  What is going on here?  

## Single, double, and triple quotes

We typically define strings by putting characters between single quotes, as in `a = 'some'`.  That will be our standard practice, but **Python treats single and double quotes the same**.  We could have typed `a = "some"` (that is, with double quotes) with the same effect.  The main reason for using single quotes is laziness: we don't have to hit the shift key.  We're not ones to disparage laziness, but the point is that there's little difference between the two.  

<!--
There are, however, some special cases where double quotes come in handy.  On occasion, we use double quotes if the string includes a single quote: 
```python
f = "I don't believe it"
print(f)
```
The output of the print statement is `I don't believe it`, which includes a single quote as an apostrophe. This doesn't come up very often, in our experience, but there it is just in case.  
-->


Triple quotes are similar, but they can be used to define strings that go over multiple lines: 
```python
longstring = """
Four score and seven years ago 
Our fathers brought forth. """
print(longstring)
```
This produces the output 
```python

Four score and seven years ago
Our fathers brought forth ... 
```
The blank line comes from the empty space to the right of the first triple quote.  And yes: you can make triple quotes from single quotes, and all of  this is mtyn.


## Comments 

One of the rules of good code is that **we explain what we've done -- in the code**.  In this class, we might think about writing code that one of our classmates can understand without help.  That generally means we should include some explanation -- in the code -- of what we've done.  These explanations are referred to as comments.  

The simplest way to add a comment is to use the hash character (#).  Anything in a line after a hash is a comment, meaning it's ignored by Python.  We can make short comments by putting hashes in the middle of lines, or longer comments by putting a hash in the first column of a line.  Here are some examples: 
```python
# we're going to add 4 and 5
4 + 5  			# here we're computing it 
print(4+5)  	# here we're printing it 
```
We often put comments like this in our class code.  

If you have long comment, there's another method -- one of our favorites:  use triple quotes.  Officially triple quotes define strings just as single and doublt quotes do, with one exception:  they can go over multiple lines.  Unofficialy they're often use for longer comments.  Here's an example from the start of our test program: 
```python 
"""
Data Bootcamp test program checks to see that we're running Python 3.  
Written by Dave Backus, March 2015  
Created with Python 3.4 
"""
```
We recommend putting something like this at the top of every program you write.  You'll thank us later, when you go back and try to figure out what it is you did a few months ago.  


## Running programs in Spyder 

If we're writing longer programs, it's generally easier to type them into an editor where we can correct any mistakes we make, just as we do in a word processing program.   


Let's give it a try.  Copy these commands into a new file in the Spyder editor:  
```python 
a = 'some'
b = 'thing' 
c = a + b 
print('c =', c')
```
(If you don't recall how to open a new file in Spyder, see the previous chapter.) 


To run this code, we need to save it in a file.  In Spyder's editor, click on "File" in the upper left corner and choose "Save.""  To set the file name (the default `Untitled0.py` isn't all that informative), we choose "Save as" and pick a file name like `somename.py`.  The last part is important, it identifies it as a Python fgile.  Once we've done this, we can run the file in Spyder by clicking on the green arrow at the top of the editor window.  

The first three lines produce no output.  The last one produces the output `c =  something` in the IPython console.  


## Code cells in Spyder 

Spyder has a cool feature we haven't seen in other Python editors:  we can carve out blocks of code ("cells") and run them separately.  That comes naturally in IPython notebooks, as we'll see later, and it's a useful feature of Spyder as well.  

The idea is to put the separator `#%%` (hash, percent, percent) between blocks of code, called **cells**, so that we can run them separately.  Consider the code:  
```python 
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
The separator `#%%` in the middle divides this set of commands into two cells that we can run one at a time.  That allows us to run and test blocks of code without running the whole program.  It doesn't make much difference with code this simple, but in longer programs it can be a real time saver.   

Here's how it works:   
* In the Spyder editor, click on a code cell.  The cell will indicate its selection with a darker background than the other cells.  
* Now go to the toolbar above the editor.  The large green triangle runs the whole program. The one to its right displays the text "Run current cell" if you move the cursor to it.  Click on it to run the selected cell.  

**Exercise.** Copy the code above into your Python program.  Run each cell.  Check the output to make sure it worked.  

**Exercise.** Add comments to the code you just wrote.  Do it now, while you're still thinking about it.  

## Lists

Lists are one of the fundamental Python **data structures**, a term that means a specific organization of data.  A Python list is what it sounds like:  an ordered collection of items.  The items can be lots of things:  numbers, strings, variables, or even other lists.  We create them by putting square brackets around a collection of items separated by commas.  Here are some examples:  
```python 
numberlist = [1, 5, -3]
a = 'some'
b = 'thing'
c = a + b 
stringlist = [a, b, c]		
```
Copy this code into Spyder and run it.  What do you see if you type `print(numberlist)` in the IPython console?  

We can combine lists (literally) by adding them.  The statement `biglist = numberlist + stringlist` produces a list containing all the elements of `numberlist` and all the elements of `stringlist`, so we have six items altogether.  Type `print(biglist)` to make sure that's the case.  

In contrast, the statement `biglist2 = [numberlist, stringlist]` produces a new list with two items:  the lists `numberlist` and `stringlist`.  It's what we might call a "list of lists."  That's not something we're likely to do, to be honest.  (We did it once, but it was an accident.)  The point is simply that lists are flexible objects. 


**Exercise.** Run the statements 
```python 
mixedlist = [a, b, c, numberlist]
print(mixedlist)
```
What is the output?  How would you explain it to your classmates?  


**Exercise.** Suppose `x = [1, 2, 3]` is a list.  What is `2*x`?  Try it and see.  


## Slicing strings and lists 


We can access the elements of strings and lists by specifying the item number in square brackets. This operation is referred to as **slicing**, probably because we're slicing off pieces, like a cake.  The only tricky part of this is remembering that Python starts numbering at zero.  

**Exercise.**  Take the string `a = 'some'`.  What is `a[1]`?  Why?  Do the same with the list `letters = 'a', 'b', 'c', 'd']`.  What is `letters[2]`?  Why?  


**Slicing strings.** What just happened?  Python starts numbering at zero.  If we want the first item/letter, we type `a[0]`.  If we want the second, we type `a[1]`.  And so on.  We can summarize the numbering convention by writing the word `some` on a piece of paper with room between the letters.  Below them, write the numbers, in order:  0, 1, 2, 3.  Label this row "counting forward."   

We can also count backward, but again Python has its own numbering convention.  If we want the last letter, we type `a[-1]`.  And if we want the one before the last one, we type `a[-2]`.  In this case we get the same answer if we type `a[2]`.  Both give us `'m'`.  

Let's track this "backward" numbering system in our example.  Below the "counting forward" numbers, start another row.  Below the letter `e` write -1.  As we move to the left, we type, -2, -3, -4.  Label this row "counting backward."


**Exercise.** Take the string `firstname = 'Monty'` and write below it the forward and backward counting conventions.  What is the third letter -- `n` -- in each system?   

<!--
We can also slice off sequences of characters, but there's another tricky convention to deal with.  Let's see what the following commands do:  
```python 
c = 'something'
print('c[1] is', c[1])
print('c[1:2] is', c[1:2])
print('c[1:3] is', c[1:3])
print('c[1:] is', c[1:])
```
The first print statement gives us `o`, the second letter of `something`.  We label it element 1 because we start numbering at zero.  The next one does the same.  Why?  The convention is to stop one before the second number, so this goes from 1 to 1, which is the second letter.  The next line gives us `om`, the second and third letters.  Why third?  Stick with us now, but here's the logic:  we go from 1 to 2 (one less than the second number), which is the second and third letters (we started counting at zero).  

The last line has no second number.  By convention it goes to the end.  So the slice `c[1:]` goes from the second letter (the first number 1) to the end, giving us `omething`.  

Are you dizzy yet?  To summarize, the counting conventions for a slice like `c[n1:n2]` work like this:

* We start at zero, so `n1` is really `n1+1`. That means `c[3]` is the fourth character.  
* We end at `n2-1`, so `c[3:7]` includes characters 4, 5, and 6.   

Some practice examples:  
-->  

**Exercise.** Find the last letter of the string `lastname = 'Python'`.  Find the second to last letter using both the forward and backward counting conventions.  

<!--
**Exercise.** Extract the string `'thon'` from `python`. 
-->

**Slicing lists.**  We count the same way we did with strings, but the objects here are items in lists rather than characters in strings.  Let's see if we can teach ourselves.  

**Exercise.** Take the list `numberlist = [1, 5, -3]`.  Use slicing to set a variable `first` equal to the first item.  Set another variable `last` equal to the last item.  


## Python's built-in functions

We now have several kinds of **objects** to work with:  numbers, strings, and lists.  There are more on the way, but that's a good start.  And yes, the formal term is really **objects**.  But what can we do with them?  Python has two basic ways to do things:  **functions** and **methods**.  We'll talk about functions in this section and methods in the next one.  We can identify functions because they come with inputs -- more formally, arguments -- in parentheses.  You may recall this from our use of the print function:  `print(x, y, z)`, for example.  

**Common functions.** Python has a lot of basic "built-in" functions.  We won't use most of them, but here are some we've found useful, Try each of them in the Python file we created earlier.   

* `type()`.  This tells us what kind of object we have.  To see how it works, type the following into the IPython console:  
```python 
type(2)
type(2.5)
type(c) 
type(stringlist)
type('12')
```
Think about this on your own for a minute.  What do you get?  What do you think the output means?  

     Not to kill the suspense, but here's what we should get.  The first one gives us the output `int`, which stands for integer:  a whole number like 1, 2, 3, and so on.  The second one gives us `float`, a so-called "floating point number" like most of those we run across in Excel -- not a whole number.  The third one gives us `str`, which tells us that it's a string.  The fourth one is a list.  What's the last one?  That's a trick question:  it's a string, too, even though it looks like a number. 

    The type function is more helpful than you might guess.  A lot of what we do in programming is deal with objects of different types and, when necessary, convert one type to another.  The first step is to identify the type of the object of interest.  That will determine what we can do with the object later.   

* `len()` (length).  This tells us the length of an object.  To see how it works, type the following in the IPython console:  
```python 
len(a)
len(c)
len(numberlist)
```
The first one gives us the number of characters in the string `a = 'some'`, namely 4.  The second one does the same for the string `c = 'something'` (7).  The last one tells us the length of the list `numberlist` (3). Note that for strings, `len` gives us the number of characters. For lists, it gives us the number of items in the list.  

*  Type conversions.  Suppose we have an object of one type (the string `11.32`) and want to convert it to another (the floating point number `11.32`).  We could use the code 
```python 
d = '11.32'
d_flt = float(d)
```
The new variable `d_flt` has type `float`.  Similarly, we can convert it back to a string with the statement `d_str = str(d_num)`. We'll see a lot of this kind of thing when we start working with data.  

<!-- ??  https://www.reddit.com/r/Python/comments/3c344g/so_apparently_type_is_of_type_type/ -->


**Exercise.**  What is the length of the string `d = '11.32'`?  Does the answer make sense to you?  
**Exercise.** What happens if we apply the function `float` to `a = 'some'`?  

**Exercise.** What do the functions `min()` and `sorted()` do?  (It's conventional to include the parentheses to remind us that they're functions.  When we use them, the parentheses are required.)  Apply them to `'some'` and see what happens.  

**Exercise.** Are there other functions that interest you?  See [here](https://docs.python.org/3.4/library/functions.html) for the official list.  Pick one and construct an example that uses it.  

**Exercise.**  This one is tricky, but it came up in some work we were doing.  Suppose `year` is a string containing the year of a particular piece of data.  How would we construct a string containing the following year?  

**Exercise.** This one also came up in our work and takes some thought.  Suppose we have a variable `z = '12,345.6'`.  What is its type?  Can we convert it to a floating point number without the comma?  Hint:  What method can we use to get rid of the comma?    

<!-- z = z.replace(',', '') -->



## Objects and methods

As we noted, lots of things in Python are **objects**.  (Experts might say at this point:  an object is an "instance" of a "class."  Ignore them.)   **Methods** are ready-to-go things we can do with them.  The available methods depend on the object.  A lot of Python is "object-oriented," which means we apply methods to objects to accomplish what you might think you need a function for.  Trust us, the jargon is more difficult than just doing it.  

What methods are available to work with a given object?  Take, for example, the list `numberlist = [1, 5, -3]`.  To get the list of available methods, we use the IPython console and type:  `numberlist.[tab]`.  This wonderful piece of technology is referred to as **tab completion**.  The ingredients here are the object (here ``numberlist`), the period or dot, and the tab key.  When you hit tab, a window will pop up with a list of methods in alphabetical order.  In our example, the list starts like this:  
```python
numberlist.append
numberlist.clear
numberlist.copy
numberlist.count
```
If we want more information, we type the relevant method into the object inspector.  For the method `numberlist.append`, we get the description
```python 
Definition:  append(object)
Type:  Function of None module 
L.append(object) -> None -- append object to end.
```
Well, that's pretty opaque, maybe we oversold this approach.  What `append` does is add an item to the end of a list.  The statement `numberlist.append(7)` adds `7` to the end of the list, changing `numberlist` from `[1, 5, -3]` to `[1, 5, -3, 7]`.  


**Example.** Set `firstname = 'Chase'`.  The method `lower` converts it to lower case.  If we type `firstname.lower` into the object inspector, we see that it's a function and comes with parentheses.  If we type `firstname.lower()` into the IPython console, the response is `'chase'`.  Without the parentheses, it doesn't work.  


**Exercise.** Find a method to convert `firstname` to all upper case letters.  

**Exercise.**  Run the commands 
```python 
firstname = 'John'
lastname  = 'Lennon'
firstlast = firstname + ' ' + lastname 
```
Find a method to replace the n's in `firstlast` with asterisks.  

In summary, we have a function when we see something like `function(object)`.  And we have a method when we see `object.method`.  


** ?? more about methods and functions ?? **


## Python 2 and 3

There's a lot of code around written in earlier versions of Python, most commonly Python 2.7.  It's there because the people who wrote it started before Python 3 was up and running.  Since we're starting from scratch, we are planting ourselves firmly in Python 3 territory.  Still, you're likely to run across examples of Python 2 on the internet. The easiest way to tell the difference is the print command:  `print(x)` in Python 3 was `print x` (no parentheses) in Python 2.  There are lots of other differences, which is why it's essential we all use Python 3.  


## Resources  

**Warning.** We thought it would be useful to list our favorites sources of information on the same topics, but keep in mind that there's more here than a reasonable person could want.  It's there if you need it, but we think you're better off going into depth with one or two and ignoring the rest.  

With that out of the way, here are some good introductions to basic Python and related topics with our favs on top:  

* Codecademy has an excellent [Introduction to Python](http://www.codecademy.com/en/tracks/python).  You run Python in their online environment, which is really helpful when you're starting out. It uses Python 2, so the print statement has the form `print x` rather than `print(x)`.  If we were to recommend one outside resource, this would be it.  You should think seriously of working your way through it in parallel with this course.  If you do, you can stop (as far as this course in concerned) when you get to Advanced Topics.    

* Here's a [list of free tutorials](http://noeticforce.com/best-free-tutorials-to-learn-python-pdfs-ebooks-online-interactive), but we think you can stop with the first one, Codecademy. 

* The official [Python tutorial](\href{https://docs.python.org/3.4/tutorial/introduction.html) is very good.  It's also a good idea to get used to reading official documentation like this.  There are times when it's unavoidable.  

* Mark Lutz's [Learning Python](http://www.amazon.com/Learning-Python-5th-Mark-Lutz/dp/1449355730/) is a 1600-page monster that covers lots of things we won't use.  But it's clear and thorough, and comes with the elusive Glenn Okun stamp of approval.  He tells us the Kindle version comes with free updates. 

* Sebastian Raschka has more than you'll ever need  about the [differences between Python 2 and 3](http://sebastianraschka.com/Articles/2014_python_2_3_key_diff.html).   

These sources go well beyond what we do in this chapter, but we'll catch up with some of it in the next chapter. The rest we don't need, but if you're interested feel free to charge ahead anyway.  

<!-- http://tutorial.djangogirls.org/en/python_introduction/index.html -->


