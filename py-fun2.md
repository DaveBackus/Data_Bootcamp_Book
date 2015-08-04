# Python fundamentals 2 


---
**Overview.**   More core Python.

**Python tools.**  Comparisons and Boolean variables, conditionals (if, else), loops, functions.  

**Buzzwords.** List comprehensions, data structures, gotchas, PEP8.  

**Code.**  [Link here](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_fundamentals_2.py).

---


We continue our overview of Python's core language.  That's not what we'll use, for the most part, but the same concepts show up in other places.  We go through the material quickly, since we're more interested in the general ideas than the details.  


## Reminders 

Some things we'll use repeatedly:

* The `type` function.  The command `type(x)` tells us what kind of object `x` is.  Past examples include integers, floating point numbers, and lists.  

* Methods and objects.  It's common, even standard, in Python to work with objects using methods.  (If these words are confusing, go back to the previous chapter.)  We apply the method `bar` to the object `foo` by typing `foo.bar`.  

* Tab completion.  To find the list of methods available for a hypothetical object `x`, type `x.[tab]` in Spyder's IPython console -- or in an IPython notebook -- to get a list.  That's referred to as "tab completion." 


And while we're reviewing:   Save the code file for this chapter in your `Data_Bootcamp` directory and open it in Spyder.  


## Logical expressions 

Sometimes want to do one thing if a condition is true, another if it's false.  For example, we might want to use observations for which the date is after January 1980, the country is India, or the population is greater than 5 million -- and not otherwise.  

Python -- like all modern programming languages -- has a collection of logical expressions to do things like this.  We refer to such expressions as **comparisons** because they involve the comparison of one thing with another; for example, the date of an observation and the date January 1980.  The result of a comparison is either `True` or `False`.  We refer to true/false variables like this as **Boolean**, a name derived from the 18th century mathematician and logician [George Boole](https://en.wikipedia.org/wiki/George_Boole).  


**Comparisons.**  Suppose we want to compare the values of variables `x` and `y`.  Which one is bigger?  To see how this works in Python, run the code 
```python
x = 2*3
y = 2**3 
test = x >= y
print('test = ', test)
print('test has type ', type(test))
```
What value does `test` have?  What type is it?  Here `x` is 6 and `y` is 8.  The expression `x >= y` (`x` greater than or equal to `y`) is false.  If we print `test`, we find that its value is indeed `False`.  If we ask its `type`, Python tells us `bool` (that is, Boolean).  

We could, of course, have skipped the assignments here. The expression `x >= y` equals `False` whether we assign it to `test` or not.  Similarly, we can use `type(x>=y)` to find its type.  

Other comparison (or Boolean) operations include `==` (equals), `>` (greater than), `<=` (less than or equals), and `!=` (not equals).  You can find the complete set in the [Python documentation](https://docs.python.org/3.4/library/stdtypes.html).  We can also reverse comparisons with the word `not`.  For example, `not_test = not test` is `True`.  (Think about that for a minute.) 


**Exercise.** What do you think this code produces?  
```python
name1 = 'Chase' 
name2 = 'Spencer' 
check =  name1 >= name2 
print(check)
```
Run it and see if you're right.  What is the value of the variable `check`?  What does the comparison mean here?  

**Exercise (continued).** Suppose we add the commands 
```python 
not_check = not check 
print(not_check)
```
What is the value of `not_check`?  Explain the logic to your neighbor.  



**Multiple comparisons.**  We can string together two comparisons with the words `and` and `or`.  Consider the code 
```python 
x = 2*3 
test1 = x >= 0 and x <= 5
test2 = x >= 0 or x <= 5
```
What are the values of `test1` and `test2`?  Can you explain to your neighbor how this works?  


**Warning.** In our work, we use multiple comparisons most often in Pandas, Python's data management package.  For reasons we won't go into, Pandas uses a different syntax:  `&` for `and `and `|` for `or`.  



## Conditionals (`if` and `else`)

Now that we know what's true and what's false, we can build that into our code.  Conditional statements allow us to do different things depending on the result of a comparison or Boolean variable:  

	if something is true, then do something.  
	if something is false, do something else.  

Here "something" is a comparison or Boolean variable and is either true or false.  	


Let's do an example.  We print the square of a number if the number is greater than six (that's the comparison or condition):
```python
x = 7       		# we can change this later and see what happens

if x > 6:
    square = x**2
    print(square)

print('Done!')
``` 
The essential ingredient here is the comparison `x>6`, which in this case has the value `True`.  The `if` statement then directs the program to compute and print the square of `x`.  The key elements of the code are:

* The initial `if` statement ends with a colon. That's standard Python syntax, we'll see it again.
* The following statements are indented four spaces.  Spyder does this automatically.  It's also standard syntax and is not optional. 
* The end of the code block is signalled by the end of the indentation.
* The space before the next line -- `print('Done!')` -- isn't necessary, but it's common practice because it makes the code easier to read.


**Exercise.** What happens if we set `x=4` at the top?  How do we know?  


Suppose we want to do one thing if the condition is true and another if it's false.  The second part was missing in our previous example.  We can add a second branch to our decision tree with an `else` statement: 
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


## Loops 

There are lots of times you want to do the same thing many times, either on one object or to many similar objects.  An example of the former is to find an answer to progressively higher degrees of accuracy.  We repeat an operation as many times as we need to get a desired degree of accuracy.  An example of the latter is to print out a list of names, one at a time.  Both situations come up a lot.

Here's an example:  compute and print the squares of whole numbers (integers) up to ten.  ([Paul Ford](http://www.bloomberg.com/graphics/2015-paul-ford-what-is-code/) adds:  "just the sort of practical, useful program that always appears in programming tutorials to address the needs of people who urgently require a list of squares.")   We can do that with a `for` loop:
```python 
for number in range(11):
    square = number**2
    print(square)
```
What does this do?  The variable name `number` is arbitrary, we can use any name we like.   The expression `range(n)` is new.  It's a built-in Python function that sets up a sequence of integers of length `n`.  With standard Python logic, it goes from zero to `n-1`.  The command `for` tells the program to do the commands that follow for all the values of `number` specified by `range(11)`;  that is, for integer values between zero and ten:  0, 1, 2, 3, ..., 10.  The print statement reports the result.  


The syntax is similar to `if` statements:

* The initial `for` statement ends with a colon.
* The following statements are indented (exactly) four spaces.
* The end is signalled by the end of the indentation. 
* A blank line at the end makes the code easier to read.


**Example.** Here's a loop that computes the sum of integers up to ten:  1 + 2 + 3 + ... + 10:
```python
sum = 0 
for num in range(11):
    sum = sum + num 

print(sum)
```
This includes the number zero in the sum, but, of course, that makes no difference.  We can change that by using `range(1,11)`, which ranges from 1 to 10.  (If this sounds strange to you, remind yourself how numbering works in Python.  Or go back to the subsection on slicing in the previous chapter.)


**Exercise.** Write a loop that computes the sum of integers up to some arbitrary number `n`.  


**Example (bond price).**  Consider a bond that pays annual coupons for a given number of years (the maturity) and a principal of 100 at the end.  The yield-to-maturity is the rate at which these payments are discounted.  Given values for the coupon and the yield, the price of the bond is 
```python
maturity = 10 			
coupon = 5 			 
ytm = 0.05 				# yield to maturity 

price = 0 
for year in range(1, maturity+1):
    price = price + coupon/(1+yield)**year

price = price + 100/(1+yield)**maturity 
print('The price of the bond is', price)
```
The answer is 100, which we might know because the coupon and yield are the same once we convert the latter to a percentage.  Python gives us `99.99999999999997`, which is close enough.  

**Digression.**  When we wrote this code, we used the variable name `yield` instead of `ytm`.  Spyder marked this as a "invalid syntax" with a warning sign to the left of the text.  Evidently the name `yield` is reserved for something else.  As general rule, it's a good idea to pay attention to the hints Spyder gives us.  


**Exercise.** In Portugal and Greece, policymakers have suggested reducing the debt by cutting the coupon payments and extending the maturity.  How much do we reduce the value of the debt if we reduce the coupons to 2 and increase the maturity to 20?  


**Loop with condition.**  Sometimes we want to go through a loop until some condition is met.  This combination of a loop and a condition requires an extra level of indenting, but is otherwise just a combination of things we've seen before.  

Here's an example.  Suppose we want to compute the sum of integers until the sum reaches 100.  We could use the code 
```python 
maxnum = 20 			# guess of number above our limit 

sum = 0 
for num in range(maxnum):
    sum = sum + num 
    if sum > 100:
        break  			# exit loop 

print('At num =', num, 'we had sum =', sum)
```
The `if` statement starts with a colon and the statement following it (`break`) is indented four spaces more (eight in total).  `break` is a special command that ends a loop early.  


**Loops over lists and strings.**  We can also loop over lists and strings (they're sometimes called "iterables").  In each case we run through their elements one at a time.  Here's an example for a list:
```python 
fruit = ['apples', 'bananas', 'cherries']
for item in fruit:
    print(item)
```
This prints each of the items in `fruit`.  


**Example.**  We use a loop to compute the sum of the elements of a list:
```python
numlist = [4, -2, 5] 

sum = 0
for num in numlist:
    sum = sum + num 
    
print(sum)     
``` 
The answer is 7.  

**Exercise.** Adapt the example to compute the mean of the elements of `numlist`.  

**Exercise.** Adapt the example to find the smallest number in the list.  

**Comment.** We typically wouldn't do things like this, because Python has methods that do them for us.  But this is what the methods must be doing for us.  


**Exercise.**  This goes a little beyond what we've covered, but what do you think this program does?  
```python 
vowels = 'aeiouy'
word   = 'anything'
for letter in word:
    if letter in vowels:
        print(letter)
```
Describe what each line does as well as the overall result.  (Adapted from [SciPy lecture 1.2](https://scipy-lectures.github.io/intro/language/control_flow.html#advanced-iteration).)

**Example.** What about the consonants?  Note the word `not` below:
```python 
vowels = 'aeiouy'
word   = 'anything'
for letter in word:
    if letter not in vowels:
        print(letter)
```
Extra credit:  How would you change the program to replace the consonants with asterisks?


**Exercise.**  Take the list `stuff = ['cat', 3.7, 5, 'dog']`. 

* Write a program that prints the elements of `stuff`.
* Write a program that tells us the `type` of each element of `stuff`.  
* Write a program that goes through the elements of `stuff` and prints only the elements that are strings; that is, the function `type` returns the value `str`.


<!-- See [reddit](http://www.reddit.com/r/Python/comments/35ubwo/newbie_for_programming_i_am_working_on_this/).  -->


**List comprehensions.**  That's a mouthful of jargon, but the idea is that we can use implicit loops with lists.  (This is another thing that doesn't work in Python 2, so make sure you have Python 3 installed.)  Consider, for example, the loop above that prints out the elements of the list {\tt fruit} one at a time.  A list comprehension is a more compact syntax for the same thing:  `[print(item) for item in fruit]`.  As with loops, the variable `item` is a dummy:  we can use any name we wish.



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

**Exercise (bond price).** Write a function that takes a bond's maturity, coupon, and yield as inputs and returns its price.  



##  Other data structures

This whole section is mtyn:  we recommend you skim it, but don't worry about the details, you can come back to them if needed.  

The term **data structure** refers to the organization of a collection of data.  A list is a data structure.  ...  

http://en.wikipedia.org/wiki/Data_structure

Examples: tuples, dictionaries, and sets.  We'll cover them later as needed.
If you run across one of these terms, keep in mind it's just a different form
of organization, we can look up its properties when we need to.


## Special Python functions 

This is all mtyn, but we find it interesting.  

lambda

filter, ...  



## Assignments and copies

This is what programmers call a "[gotcha][8]," an unexpected or counterintuitive feature of a language.  This one has gotten all of us at one time or other.  It shows up in Numpy and Pandas, too.  


[8]: https://en.wikipedia.org/wiki/Gotcha_(programming)


Let's think about how a spreadsheet program works.  


The following was adapted from [Stack Overflow](http://stackoverflow.com/a/10844760/804513): 
```python 
a = [1,2,3]
b = a
b[0] = 'WHOA!'
print(a)
```
This returns [??] 

Similar to Excel!

See the [Python documentation](https://docs.python.org/3.4/library/copy.html).  



## Programming style  

Yes, style counts.  

PEP8 etc \\
\url{https://google-styleguide.googlecode.com/svn/trunk/pyguide.html}

https://www.python.org/dev/peps/pep-0008/

Examples:  \\
\url{http://www.reddit.com/r/Python/comments/3639nl/what_is_the_most_beautiful_piece_of_python_code/}\\
\url{https://github.com/mitsuhiko/werkzeug/blob/master/werkzeug/routing.py} \\



## Resources 

See the resources in the previous chapter, especially the link to [Codecademy](https://www.codecademy.com/tracks/python).  If you work your way up to Advanced Topics, you'll be in good shape for anything that follows.  

Additional resources for specific topics:

* The [Python Tutorial](https://docs.python.org/3.4/tutorial/controlflow.html) has a nice introduction to "trol flow language," which includes comparisons, conditional statements, and loops.  
* The infamous [PEP8](https://www.python.org/dev/peps/pep-0008/) and [Google](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html) describe programming style.  
* Bernd Klein's [Python Course](http://www.python-course.eu/lambda.php) covers lambda functions, map, reduce, and filter.  

