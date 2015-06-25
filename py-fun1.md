# Python fundamentals


---
**Overview.**  We work our way through some Python basics. It's not enough to do anything interesting, but the same concepts show up in other situations.    

**Python tools.**  numbers, strings, lists, functions, objects and methods.

**Buzzwords.** Isn't that enough?  

---

We work our way through the rudiments of Python programming.  You'll hear terms like "floats" and "strings,"" and "objects" and "methods.""  Don't panic, it's just jargon.  We are doing this in Python, of course, but most of the concepts show up in pretty much any modern programming language.  We aren't ready yet to do anything of real interest, but the same logic and concepts will reappear in more practical settings.  

Your first job is to start up Spyder.  If you don't know what that means, return to the previous chapter. Once you've done that,  we'll work our way through the fundamentals of Python, the core of the language.  The distinction here is with "modules" or "packages" that allow Python to do more advanced things -- data management and graphics, for example.


## The logic of Python programs

In a spreadsheet program, such as Excel, we can connect cells to other cells.  When we change one, any other cells conected to it adjust automatically.  

Most computer programs, including Python programs, don't work that way.  They run one line at a time, starting at the top of the program and following instructions until they reach the end or stop for some other reason.  A program is just a detailed list of things we want the computer to do.  Most of the programs in this course have the structure:  

* Input data.  
* Manipulate the data until it's in the form we want. 
* Produce some graphics that summarize the data in a compelling way.  

Each of these bullets would be associated with a number of lines of code, but that's the basic idea:  do one thing at a time until we have something useful. 

"One thing at a time" is also good advice.  As you learn to write more complex programs, it's good practice to break a long program into smaller manageable pieces.  You'll see how that works as we go along.  


## Calculations with numbers

One of the things we can do in Python is numerical calculations.  which is a good thing:  that's a lot of what managing data is all about, diving one thing by another, adding things, up, and so on. Here are some simple calculations you can type into Spyder's IPython console one at a time.  For each one, pay attention to what happens:  

* 2*3
* 2 * 3
* 2/3
* 2^3 
* 2**3
* log(3) 

The first one multiplies 2 times 3, and gives us 6 as the answer.  The input and output for the first one look like this in the console:
```
In [1]: 2*3
Out[1]: 6
```
As we continue, the number [1] increases to [2], [3], and so on.  The second calculation, ```2 * 3```, does the same thing.  The point is that space around the * doesn't change the output.  The third one is division.  The input and output are 
```
In [3]: 2/3
Out[3]: 0.6666666666666666
```
The fourth one, which we might guess is 2 to the power 3, gives us 
```
In [4]: 2^3
Out[4]: 1
```
We expected this to give us 8, what's going on?  The short answer is that this doesn't do powers, it does something else (mtyn).  If we want to do exponentiation, we do it this way:
```
In [4]: 2**3
Out[4]: 8
```
The last one is the log function.  It gives us (among other things) the message:  ```NameError: name 'log' is not defined`'``.   We can use functions like ```log`` and ``sqrt``, just as we do in Excel, but we need to import them specially.  



## Assignments

  x = 2, y = 3.5, z = x/y, etc

More
\href{https://docs.python.org/3.4/reference/lexical_analysis.html#line-structure}{here}
and \href{http://stackoverflow.com/questions/53162/how-can-i-do-a-line-break-line-continuation-in-python}
{here}.


## Comments and printing

Comments:  , """, #%%, print(x), etc. :

%[?? more on print?]


## Strings
 a = 'some', b = 'thing', c = a+b, d = '11.32', etc.


## Quotes

Single, double...

[??] triple quotes can go over several lines,

we use them for multi-line comments \\
\url{https://docs.python.org/3/tutorial/introduction.html#strings} \\

Also used to supply docs for functions
\url{http://stackoverflow.com/a/7057988/804513} **

## Data types and conversions

[??]  {\tt len} and {\tt type}:
{\tt len(first), len(x), type(first), type(x)}.

Type conversions.
There are lots of occasions when we want --- or need -- to change type.
Suppose, for example, we want to convert {\tt year = '2011'},
which is defined as a string, to a number.
We can do that with {\tt int(year)}.  (Or {\tt float}, but we have something else in mind.

## Functions and methods

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

## Slicing

Find an element of {\tt a}: {\tt a[1], a[0], a[1:3], a[-1], a[:2], a[1] = 'z', etc.}

\item {\bf Exercise.}  Set {\tt first} equal to your first name, {\tt last} equal to your last name.

\begin{enumerate}[label=(\alph*)]
\item Set {\tt full} equal to your first and last names together with a space between them.
\item Set {\tt lastfirst} equal to your last name, comma, space, first name.
\end{enumerate}

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

## Lists

Collections of things, possibly different, defined by square brackets
{\tt []} with commas between items.
Slicing conventions similar to strings.
Examples:  {\tt numbers = [x, y, z], type(numbers),
print(numbers),
strings = [a, b, c, d],
all = numbers + strings, type(all),
print(all),
all[0], all[-1], all[3:], etc.}


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


\item {\bf Other data structures.\/} [??]
The term data structure refers to the organization of a collection of data.
A list is a data structure.  ...

\url{http://en.wikipedia.org/wiki/Data_structure}

Examples: tuples, dictionaries, and sets.  We'll cover them later as needed.
If you run across one of these terms, keep in mind it's just a different form
of organization, we can look up its properties when we need to.


##  Exercises

??

## Resources 

Here are some online resources we have found helpful:  

* Codecademy has an excellent [introduction to Python](http://www.codecademy.com/en/tracks/python).

* Sargent-Stachurski...

*  {Python tutorial},
\href{https://docs.python.org/3.4/tutorial/introduction.html}{Section 3}.

\item ** check this out:  \url{https://wiki.python.org/moin/SimplePrograms}

This is a test
