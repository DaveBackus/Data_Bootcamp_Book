# Python fundamentals


---
**Overview.**  An introduction to core(?) Python. It's not enough to do anything interesting yet, but the same tools and ideas will show up throughout the course.

**Python tools.**  Core Python, data types (numbers, strings), lists, functions, objects and methods.


**Applications.**  String and list manipulation.  (That may sound like gibberish now, but it will help us later.)

---

Basic programming.  Not enough to do anything interesting, but a good foundation for what follows.


## The logic of Python programs

work through a set of commands in order, not like Excel

Lines.  Each line is a new command.
Unlike Excel, the program goes through the lines one at a time.

Continuation automatic if you have parens or brackets that need to be closed (``implicit'').
Blank lines fine, often helpful in making code easier to read.

More
\href{https://docs.python.org/3.4/reference/lexical_analysis.html#line-structure}{here}
and \href{http://stackoverflow.com/questions/53162/how-can-i-do-a-line-break-line-continuation-in-python}
{here}.


## Operations with numbers

Operations:  2*3, 2 * 3, 2/3, 2^3, 2**3, log(3), etc

Assignments:  x = 2, y = 3.5, z = x/y, etc


## Comments and printing

Comments:  , """, #%%, print(x), etc. :

%[?? more on print?]


## Strings:  a = 'some', b = 'thing', c = a+b, d = '11.32', etc.


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

## References

* Codecademy...

* Sargent-Stachurski...

*  {Python tutorial},
\href{https://docs.python.org/3.4/tutorial/introduction.html}{Section 3}.

\item ** check this out:  \url{https://wiki.python.org/moin/SimplePrograms}

This is a test
