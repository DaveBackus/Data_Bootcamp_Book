# Python fundamentals 2 


---
**Overview.**   

**Python tools.**  

**Buzzwords.** 

**Code.**  [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_fundamentals_2.py).

---


We continue our overview of Python's core language.  That's not what we'll use, for the most part, but the same concepts show up in in pretty much all applications.  We can go through the material quickly, since we're more interested in the general ideas than the details.  

## Reminders 

Two things we'll use repeatedly:

* The `type` function.  The command `type(x)` tells us what kind of object `x` is.  Past examples include integers, floating point numbers, and lists.  

* Methods and tab completion.  It's common, even standard, in Python to work with objects using methods.  (If these words are confusing, go back to the previous chapter.)  To see what methods are available for a hypothetical object `x`, write `x.[tab]` in Spyder's IPython console -- or in an IPython notebook -- to get a list.  

And while we're reviewing:   Save the code file for this chapter in your `Data_Bootcamp` directory and open it in Spyder.  


## Logical expressions 

There are lots of times we will want to do one thing if a condition is true, another if it's false.  For example, we might want to use observations for which the date is after January 1980, the country is India, or the population is greater than 5 million.  

Python -- like all modern programming languages -- has a collection of logical expressions that we use to do things like this.  We refer to these expressions as **comparisons** because they involve the comparison of one thing with another; for example, the date of an observation and the date January 1980.  The result of a comparison is either `True` or `False`.  We refer to true/false variables like this as **Boolean**, a name derived from the 18th century mathematician and logician [George Boole](https://en.wikipedia.org/wiki/George_Boole).  


**Comparisons.**  Run the code 
```python
x = 2*3
y = 2**3 
test = x >= y
print('test = ', test)
print('test has type ', type(test))
```
What value does `test` have?  What type is it?  Here `x` is 6 and `y` is 8.  The expression `x >= y` (`x` greater than or equal to `y`) is false.  If we print `test`, we find that its value is indeed `False`.  If we ask what `type` it has, Python tells us `bool` (that is, Boolean).  

We could, of course, have skipped the assignments here. The statement `x >= y` equals `False` whether we assign it to `test` or not.  Similarly, we can run `type(x>=y)` to find its type.  

Other comparison (or Boolean) operations include `==` (equals), `>` (greater than), `>=` (greater than or equals), and `!=` (not equals).  You can find the complete set in the [Python documentation](https://docs.python.org/3.4/library/stdtypes.html).  We can also reverse comparisons with the word `not`.  For example, `not_test = not test` is `True`.  


**Exercise.** What do you think this code produces?  
```python
name1 = 'Chase' 
name2 = 'Spencer' 
check =  name1 >= name2 
print(check)
```
Run it and see if you're right.  What is the value of the variable `check`?  What does the comparison mean here?  



**Multiple comparisons.**  We can string together two comparisons with the words `and` and `or`.  Consider the code 
```python 
x = 2*3 
test1 = x >= 0 and x <= 5
test2 = x >= 0 or x <= 5
```
What are the values of `test1` and `test2`?  Can you explain to your neighbor how this works?  


**Warning.** The place we most often use multiple comparisons is in Pandas, Python's data management package.  For complicated reasons that we won't go into, Pandas uses a different syntax:  `&` for `and `and `|` for `or`.  


## Conditionals (`if` and `else`)

Now that we know what's true and what's false, we can build that into our code.  Conditional statements allow us to do different things depending on the result of a condition or Boolean variable:  

	if something is true, then do something.  
	If something not true, do something else.  

Something here is a Boolean variable, either true or false.  	

A really simple example prints the square of a number if the number is greater than six (that's the condition):
```python
x = 7       # we can change this later and see what happens
if x > 6:
    square = x**2
    print(square)

print('Done!')
``` 
The essential ingredient here is the comparison `x>6`, which in this case has the value `True`.  The `if` statement then directs the program to compute and print the square of `x`.  The key elements of the code are:

* The initial `if` statement ends with a colon. That's standard Python syntax, we'll see it again.
* The following statements are indented four spaces.  Spyder will do this automatically for you.  It's not optional. 
* The end of the code block is signalled by the end of the indentation.
* The space before the next line -- `print('Done!')` -- isn't necessary, but it's common practice because it makes the code easier to read.


**Exercise.** What happens if we set `x=4` at the top?  How do we know?  

Suppose we want to do one thing if the condition is true, and another if it's false.  The second part was missing in our previous example.  We can do that by adding an `else statement: 
```python 
if x > 6:
    square = x**2
    print('x**2 =', square)
    print(x>6)
else:
    print('x is not > 6 ( x =', x, ')')
    print(x>6)
```

Try this with `x=4` and `x=7`.  We've added print statements for the condition `x>6` to show what they look like.  


**Exercise.** Start with the assignments
```python 
name1 = 'Dave'
name2 = 'Glenn'
```
(The names on the right can be anything, but let's start with these.)  Write a program using `if` and `else` that prints out the name that comes first in alphabetical order.  


**Exercise.**  ??


## Loops 

There are lots of times you want to do the same thing many times, either on one object or to many similar objects.  An example of the former is to find an answer to progressively higher degrees of accuracy.  We repeat as many time as we need to get a desired degree of accuracy.  An example of the latter is to print out a list of names, one at a time.  Both situations come up a lot.

Here's an example:  compute and print the squares of whole numbers (integers) up to ten.   We can do that with a `for` loop:
```python 
for number in range(11):
    square = number**2
    print(square)
```
What does this do?  The variable name `number` is arbitrary, we can use any name we like.   The expression `range(n)` is new.  It's a built-in Python function that sets up a sequence of integers of length `n`.  With standard Python logic, it goes from zero to `n-1`.  The command `for` tells the program to do the commands that follow for all the values of `number` specified by `range(11)`;  that is, for integer values between zero and ten:  0, 1, 2, 3, ..., 10.  The print statement reports the result.  


The syntax is similar to conditionals:

* The initial `for` statement ends with a colon.
* The following statements are indented (exactly) four spaces.
* The end is signalled by the end of the indentation. 
* A space after the last line makes the code easier to read.


**Example.** 
Use a {\tt for} loop to compute the mean of the elements of the list:  {\tt x = [5, 7, 3, 6]}.

\item {\bf Exercise.}
Write a program that computes the sum
$ 1 + 2 + 3 + \cdots + 10 $.
Then modify it to compute the sum up to any positive integer $n$.



**Example.** Bond prices.  

**Example.** Bond yields.  (use function?)


**Loops with conditions, further indenting** 



More than you need.  plus/equals, etc.  [??]



**Example.** Use a {\tt for} loop to verify that $ 1/(1+y/k)^k $ converges to $\exp(-ky)$ as we increase $k$.  


**For loop with condition for ending**


**`while` loops.** ??


**Loops over lists and strings.**  We can also loop over lists and strings (they're sometimes called "iterables").  In each case we run through their elements one at a time.  Here's an example for a list:
```python 
fruit = ['apples', 'bananas', 'cherries']
for item in fruit:
    print(item)
```

[??] Find smallest number in list


**Exercise.**  
Start with list of names.  Find first one in alphabetical order.  [??]


**Exercise.**  This goes a little beyond what we've covered, but what do you think this program does?  What features are new to you?
```python 
vowels = 'aeiouy'
word   = 'anything'
for letter in word:
    if letter in vowels:
        print(letter)
```
You should describe what every line does as well as the overall result.  (This one is adapted from SciPy lecture 1.2.)

**Example.** What about the consonants?  Note the word `not` below:
```python 
vowels = 'aeiouy'
word   = 'anything'
for letter not in word:
    if letter in vowels:
        print(letter)
```


Extra credit:  How would you change the program to replace the consonants with asterisks?


**Exercise.**
Take the list `stuff = ['cat', 3.7, 5, 'dog']`. 

* Write a program that tells us the `type` of each element of `stuff`.  
* Write a program that prints out the elements of `stuff`.
* Write a program that goes through the elements of `stuff` and prints only the elements that are strings; that is, the function `type` returns the value `str`.


**Exercise.** Convert list of strings to list with number of letters in each.  See [reddit](http://www.reddit.com/r/Python/comments/35ubwo/newbie_for_programming_i_am_working_on_this/).  


%stuff = ['cat', 3, 5.7, 'dog']
%for item in stuff:
%    if type(item) == str:
%        print(item)



**List comprehensions.**  That's a mouthful of jargon, but the idea is that we can use implicit loops with lists.  (This is another thing that doesn't work in Python 2, so make sure you have Python 3 installed.)  Consider, for example, the loop above that prints out the elements of the list {\tt fruit} one at a time.  A list comprehension is a more compact syntax for the same thing:  `[print(item) for item in fruit]`.  As with loops, the variable `item` is a dummy:  we can use any name we wish.



**Exercise.** 


## Defining our own functions

It's easy to create our own functions -- experienced programmers do it all the time.  A common view of programmers is that you should never copy lines of code.  If you're copying, that means you're repeating yourself.  What you should do instead is write a function once and use it twice.  More than that, breaking a long program into a small number of functions makes code easier for others to read, which is always a good thing.  

A function has three components:  a name (what we call it), its input (a list of arguments), and its output (what it produces from the input).  Here's a classic example:    

```python 
def hello(firstname):  
    print('Hello,', firstname)    

somename = 'Chase'   
hello(somename) 
```    
The initial `def` statement defines the function, names it `hello`, identifies the input as `firstname`, and ends with a colon (:). The following statements are **indented by exactly four spaces** and specify what the function does.  In this case, it prints `Hello,` followed by whatever `firstname` hapens to be.  The indentation isn't optional, it's an essential part of the syntax.  Python understands that the function ends when the indentation ends.  The last two lines in our code block define the string `somename = 'Chase'` and call the function with `somename` as the input argument.  Note that the name in the function's definition and its use need not be the same. 

By convention (but not necessity), Python aficionados put two blank lines before and after function definitions to make then stand out more clearly.  We used one to save space, but would use two in a real program.  


Our function `hello` has a name (`hello`) and an input argument (`firstname`), but returns no output.  It simply prints the input.  In other cases, we might want to send output back to the main program.  We do that with the `return` command.  Here's an example:  
```python 
def combine(first, last): 
	"""
	Function takes strings 'first' and 'last' and returns new string 'last, first'
	"""
	lastfirst = last + ', ' + first 
    return lastfirst 

first = 'Chase' 
last = 'Coleman'
both = combine(first, last)
print(both)
```   
Note the comment in triple quotes. 

**Exercise.**  What do you think this code does?  Run it and see.  

**Exercise.**  Write a function that takes an integer as an input (say, 2010) and returns a string of the next year (say, 2011).  


## Other things (??) 

**Assignments and copies.**  This is what programmers call a ``gotcha,'' an unexpected or counterintuitive feature.  This one has gotten all of us at one time or other.  It shows up in Numpy and Pandas, too.  The following was adapted from [Stack Overflow](http://stackoverflow.com/a/10844760/804513): 
```python 
a = [1,2,3]
b = a
b[0] = 'WHOA!'
print(a)
```
This returns [??] 

Similar to Excel!

See the [Python documentation](https://docs.python.org/3.4/library/copy.html).  



##  Other data structures

This whole section is mtyn:  we recommend you skim it, but don't worry about the details, you can come back to them if needed.  

The term **data structure** refers to the organization of a collection of data.  A list is a data structure.  ...  

http://en.wikipedia.org/wiki/Data_structure

Examples: tuples, dictionaries, and sets.  We'll cover them later as needed.
If you run across one of these terms, keep in mind it's just a different form
of organization, we can look up its properties when we need to.


## Programming style  

Yes, style counts.  

PEP8 etc \\
\url{https://google-styleguide.googlecode.com/svn/trunk/pyguide.html}

https://www.python.org/dev/peps/pep-0008/

Examples:  \\
\url{http://www.reddit.com/r/Python/comments/3639nl/what_is_the_most_beautiful_piece_of_python_code/}\\
\url{https://github.com/mitsuhiko/werkzeug/blob/master/werkzeug/routing.py} \\



## Resources 


See the resources in the previous chapter.  

Also 

Conditionals:  https://docs.python.org/3.4/tutorial/controlflow.html


Stanford guy's problems?  

See also:  https://docs.python.org/3.4/library/stdtypes.html#boolean-operations-and-or-not


https://github.com/donnemartin/interactive-coding-challenges 
http://www.codewars.com/
http://www.pythonchallenge.com/
https://projecteuler.net/
http://www.checkio.org/