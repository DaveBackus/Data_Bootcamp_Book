# Python fundamentals 2 

---
**Overview.**   More core Python. Part 2 of 2.  

**Python tools.**  Slicing, comparisons, Boolean variables, conditionals (if, else), loops (for), function definitions.  

**Buzzwords.**  Data structures, list comprehensions, gotchas, PEP8.  

**Code.**  [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_fundamentals_2.py).

---

<!--
**UNDER CONSTRUCTION**
-->

We continue our overview of Python's core language, which lays a foundation for the rest of the course.  We go through the material quickly, since we're more interested in the general ideas than the details.  


## Reminders 

Some things we'll use a lot:

* Assignments.  We say we assign what's on the right to the thing on the left:  `x = 17.4` assigns the number `17.4` to the variable `x`.  

* Strings and lists.  Strings are collections of characters in quotes:  `'this is a string'`.  Lists are collections of things in square brackets:  `[1, 'help', 3.14159]`. 

* The `type()` function.  The command `type(x)` tells us what kind of object `x` is.  Past examples include integers, floating point numbers, strings, and lists.  

* Methods and objects.  It's common in Python to work with objects using methods.  (If these words are confusing, go back to the previous chapter.)  We apply the method `justdoit` to the object `x` by typing `x.justdoit`.  

* Spyder.  An environment for writing Python programs.  The various windows include an editor, an IPython console, and the Object explorer.  If these terms are mysterious to you, return to the previous chaper.  

* Tab completion.  To find the list of methods available for a hypothetical object `x`, type `x.[tab]` in Spyder's IPython console -- or in an IPython notebook.  That's referred to as "tab completion." 

* Help.  We can get help for a function or method `foo` by typing `foo?` into the IPython console or `foo` in the Object explorer.  Try each of them with the `type()` function to remind yourself how this works.  

And while we're reviewing:   Save the code file for this chapter in your `Data_Bootcamp` directory and open it in Spyder.  


## Slicing strings and lists 


We can access the elements of strings and lists by specifying the item number in square brackets. This operation is referred to as **slicing**, probably because we're slicing off pieces, like a cake.  The only tricky part of this is remembering that **Python starts numbering at zero**.  


**Exercise.**  Take the string `a = 'some'`.  What is `a[1]`?  


**Slicing strings.** What just happened?  Python starts numbering at zero.  If we want the first item/letter, we use `a[0]`.  If we want the second, we use `a[1]`.  And so on.  We can summarize the numbering convention by writing the word `some` on a piece of paper.  Below them, write the numbers, in order:  0, 1, 2, 3.  Label this row "counting forward."   

We can also count backward, but again Python has its own numbering convention.  If we want the last letter, we use `a[-1]`.  And if we want the one before the last one, we type `a[-2]`.  In this case we get the same answer if we type `a[2]`.  Both give us `'m'`.  

Let's track this "backward" numbering system in our example.  Below the "counting forward" numbers, start another row.  Below the letter `e` write -1.  As we move to the left, we type, -2, -3, -4.  Label this row "counting backward." 


**Exercise.** Take the string `firstname = 'Monty'` and write below it the forward and backward counting conventions.  What is the third letter -- `n` -- in each system?   


**Exercise.** Find the last letter of the string `lastname = 'Python'`.  Find the second to last letter using both the forward and backward counting conventions.  


**Slicing lists.**  We count the same way we did with strings, but the objects here are items in lists rather than characters in strings.  Let's see if we can teach ourselves.  

**Exercise.** Take the list `numberlist = [1, 5, -3]`.  Use slicing to set a variable `first` equal to the first item.  Set another variable `last` equal to the last item.  Set a third variable `middle` equal to the middle item.  


## More slicing 

We've seen how to "slice" (extract) an item from a string or list.  Here we'll show how to slice a range of items. For example, slice the last five characters from the string `c = 'something'`.  

Recall that in Python we start counting at zero. If we want the first letter in `c`, we use `c[0]`.  If we want the second, we use `c[1]`.  

If we want more than a single letter, we need to specify the start and end.  Let's look at some examples and see what they do:  
```python 
c = 'something'
print('c[1] is', c[1])
print('c[1:2] is', c[1:2])
print('c[1:3] is', c[1:3])
print('c[1:] is', c[1:])
```
Let's go through this line by line: 

* The first print statement gives us `o`, the second letter of `something`.  We label it element 1 because we start numbering at zero.  
* The next one does the same.  Why?  The convention is to stop one before the second number, so this goes from 1 to 1, which is the second letter.  
* The following line gives us `om`, the second and third letters.  Why third?  Stick with us now, but here's the logic:  we go from 1 to 2 (one less than the second number), which is the second and third letters (we started counting at zero).  
* The last line has no second number.  By convention it goes to the end.  So the slice `c[1:]` goes from the second letter (the first number 1) to the end, giving us `omething`.  

This is more than a little confusing, so let's summarize.  Take the string `c = 'something'` and write numbers below each letter:  0, 1, 2, 3, 4, 5, 6, 7, 8.  For a slice like `c[n1:n2]`, the counting conventions are:  

* We start at zero, so `n1` is really `n1+1`. That means, for example, that `c[3]` is the fourth character, namely `e`.  
* We end at `n2-1`, so `c[3:7]` includes characters 4, 5, 6, and 7, namely `ethi`.  Remember: `7` refers to the eighth item, but we end one before that.  (Yikes!) 
* If `n1` is missing, we start with the first character.  If `n2` is missing, we end with the last item. Thus `c[3:]` gives us the fourth character to the end, namely `ething`.  And `c[:4]` gives us up to the fourth character, namely `some`.  

Some practice:   

**Exercise.** Set `lastname = 'Python'`. Extract the string `'thon'`. 

**Exercise.** Set `numlist = [1, 7, 4, 3]`. Extract the middle two items and assign them to the variable `middle`. Extract all but the first item and assign them to the variable `allbutfirst`.  Extract all but the last item and assign them to the variable `allbutlast`.  


## Logical expressions (comparisons)

Sometimes we want to do one thing if a condition is true, and another if it's false.  For example, we might want to use observations for which the date is after January 1980, the country is India, or the population is greater than 5 million -- and not otherwise.  

Python -- like all modern programming languages -- has a collection of logical expressions to do things like this.  We refer to such expressions as **comparisons** because they involve the comparison of one thing with another; for example, the date of an observation and the date January 1980.  The result of a comparison is either `True` or `False`.  We refer to true/false variables like this as **Boolean**, a name derived from the 18th century mathematician and logician [George](https://espresso.economist.com/a3e8029408056a0791626262beb1e74d) [Boole](https://en.wikipedia.org/wiki/George_Boole).  


Let's try some simple examples to see what we're dealing with.  Suppose we enter `1 > 0` in the IPython console.  What does this mean?  The input and output look like this:
```python 
In[1]:  1 > 0
Out[1]: True
```
The comparison `1 > 0` is interpretted as a question:  Is 1 greater than 0?  The answer is `True`.  If, instead, we enter `1 < 0` the answer is `False`.  

We might wonder how Python treats such things.  What kind of object are we dealing with?  We can check with the `type()` function; for example, `type(1>0)`.  The answer in this case is `bool` (that is, Boolean), the name we give to expressions that take the values `True` and `False`.  (Actually, it says `<class 'bool'>`, but we'll say `bool` or Boolean.)

Python comes with a list of "operators" we can use in comparisons.  Common ones include `==` (equals), `>` (greater than), `>=` (greater than or equals), and `!=` (not equals).  You can find the complete set in the [Python documentation](https://docs.python.org/3.4/library/stdtypes.html).  We can also reverse comparisons with the word `not`.  For example, `not 1>0` is `False`.  (Think about that for a minute. And remind youself that spaces don't matter in expressions.) 


**Exercise.**  What is `2 >= 1`?  `2 >= 2`?  `not 2 >= 1`? If you're not sure, try them in the IPython console and see what you get.  

**Exercise.**  What is the value of `"Sarah" == 'Sarah'`?  Can you explain why?  

We can do the same thing with variables.  Suppose we want to compare the values of variables `x` and `y`.  Which one is bigger?  To see how this works, run the code 
```python
x = 2*3
y = 2**3 
print('x greater than y is', x > y)
```
Here `x` is 6 and `y` is 8.  The expression `x > y` (`x` greater than `y`) is therefore false.  


We can also assign comparisons to variables.  Here we assign the comparison of `x` and `y` to the variable `test`:  

```python
x = 2*3
y = 2**3 
test = x > y
print('test = ', test)
print('test has type ', type(test))
```
Here we find that `test` is `False` and has type `<class 'bool'>`. 


**Exercise.** What do you think this code produces?  
```python
name1 = 'Chase' 
name2 = 'Spencer' 
check =  name1 > name2 
print(check)
```
Run it and see if you're right.  What type of variable is `check`?  What is its value?  Is Chase "greater than" Spencer?


**Multiple comparisons.**  This is mtwn, but file away for later the idea that we can string together two or more comparisons with the words `and` and `or`.  We'll do something similar when we work with data, but the syntax is a little different.  

Consider the code 
```python 
x = 2/3 
conditiona = x >= 0 
conditionb = x <= 5 
test1 = conditiona and conditionb
test2 = conditiona or conditionb 
```
What are the values of `test1` and `test2`?  The expression `conditiona and conditionb` is true if both conditions are true, false otherwise.  The expression `conditiona or conditionb` is true if either one of the conditions is true. 


**Warning from the future.** We use multiple comparisons most often in Pandas, Python's data management package.  For reasons we won't go into, Pandas uses different syntax:  `&` replaces `and `and `|` replaces `or`.  


## Conditionals (`if` and `else`)

Now that we know how to tell whether a comparision is true or false, we can build that into our code.  "Conditional" statements allow us to do different things depending on the result of a comparison or Boolean variable, which we refer to as a **condition**.  The logic looks like this:  

	if a condition is true, then do something.  
	if a conditions is false, do something else.  

To repeat:  a condition here is a comparison or Boolean variable and is either true or false.  

We use `if` to tell Python what to do if the condition is true, and `else` to do the same if the condition is false.  Picture a decision tree with two branches, one for true, one for false.  If Apple offers us a job, move to California.  If not, stay in New York.  


**`if` statements**  tell the program what to do if the condition is true.  Here's an example with the condition `1>0`.  If the condition is true, which it obviously is, then we print "1 is greater than 0."  If the condition is false, we do nothing. The code to do this is 
```python
if 1 > 0:
    print('1 is greater than 0')
``` 
The syntax here is precise:  

* The `if` statement **ends with a colon**. That's standard Python syntax, we'll see it again.  It's not optional.  
* The "code block" that follows (here one line) is **indented exactly four spaces**.  That's standard, too, and also not optional. Spyder does it automatically.  

Both of these features -- colon at the end of the first line, indent the rest four spaces -- show up in lots of Python code.  It's very compact, and the indentation makes the code easy to read.  


**Exercise.**  Change the code to 
```python
if 1 > 2:
    print('1 is greater than 2')  
``` 
What do you think happens?  Try it and see.  


Here's another example.  Again, we do something if the condition is true, nothing if the condition is false.  In this example, the condition is `x > 6`.  If it's true, we print the number.  If it's false, we do nothing.  The code is 
```python
x = 7       		# we can change this later and see what happens

if x > 6:
    print('x =', x)

print('Done!')
``` 
Here we've set `x = 7`, which makes the condition `x > 6` true.  The `if` statement then directs the program to print `x`.  The blank lines are optional; they make the code easier to read, which is generally a good thing.  The statement `print('Done!')` is just there to tell us that the program ran.  


**Exercise.** What happens if we set `x=4` at the top?  How do we know?  


**`else` statements** tell the program what to do if the condition is false.  If we want to do one thing if a condition is true, and another if it is false, we would use `if` for the first and `else` for the second.  The second part has been missing so far.  We can add it by using an `else` statement.  Here's an example:  
```python 
x = 7

condition = x > 6 

if condition:
    print('x =', x)                         # do if true 
    print(x>6)
else:
    print('x is not > 6 ( x =', x, ')')     # do if false 
    print(x>6)
```
The `else` statement adds the second branch to the decision tree:  what to do if the condition is false.  Try this with `x=4` and `x=7`.  We've added print statements for the condition `x>6` to show what they look like.  


**Exercise.** Start with the assignments
```python 
name1 = 'Dave'
name2 = 'Glenn'
```
(The names on the right can be anything, but let's start with these.)  Write a program using `if` and `else` that prints the name that comes first in alphabetical order.  


## Loops over lists and strings (`for`)

There are lots of times we want to do the same thing many times, either on one object or on many similar objects.  An example of the former is to find an answer to progressively higher degrees of accuracy.  We repeat an operation as many times as we need to get a desired degree of accuracy.  An example of the latter is to print out a list of names, one at a time.  Both situations come up a lot.

Here's an example in which we print all the items in a list, one at a time:  
```python
namelist = ['Chase', Dave', 'Sarah', 'Spencer']

for item in namelist:
   print(item)
```
Let's work through this piece by piece:

* The `for` statement goes through the items in the list one at a time.  As with `if` statements, it ends with a colon.  The variable name `item` is arbitrary.  
* The code block that follows (here one line) is indented exactly four spaces.  

If there's code after this, we would typically leave a blank line in between.  That's convention, not neccessity.  


We say here that we **iterate** over the items in the list and refer to the list as an **iterable**:  that is, something we can iterate over.  The terminology isn't important, but that's what it means if you run across it.  


**Exercise.** What happens if we replace `item` with `banana` in the code above?  


**Example.**  We use a loop to compute the sum of the elements of a list of numbers:
```python
numlist = [4, -2, 5] 
sum = 0
for num in numlist:
    sum = sum + num 
    
print(sum)     
``` 
The answer is 7.  

**Exercise.** Adapt the example to compute the average of the elements of `numlist`.  


We can also run loops over the characters in a string.  This one prints the letters in a word on separate lines:  
```python 
word   = 'anything'
for letter in word:
    print(letter) 
```
(Surely we can think of something more interesting than this!)  


**Example.**  Here's one that combines a `for` loop with an `if` statement to identify and print the vowels in a word:  
```python 
vowels = 'aeiouy'
word   = 'anything'
for letter in word:
    if letter in vowels:
        print(letter)
```
(Adapted from [SciPy lecture 1.2](https://scipy-lectures.github.io/intro/language/control_flow.html#advanced-iteration).)  Describe what each line does as well as the overall result.  


**Example.** What about the consonants?  Note the word `not` below:
```python 
vowels = 'aeiouy'
word   = 'anything'
for letter in word:
    if letter not in vowels:
        print(letter)
```
Extra credit:  How would you change the program to replace the consonants with asterisks?


**Exercise.**  Take the list `stuff = ['cat', 3.7, 5, 'dog']`.   This is somewhat demanding, but give it a try.  

* Write a program that prints the elements of `stuff`.
* Write a program that tells us the `type` of each element of `stuff`.  
* Write a program that goes through the elements of `stuff` and prints only the elements that are strings; that is, the function `type` returns the value `str`.


?? extract vowels, string what's left together.

<!-- See [reddit](http://www.reddit.com/r/Python/comments/35ubwo/newbie_for_programming_i_am_working_on_this/).  -->


**List comprehensions.**  That's a mouthful of jargon, but the idea is that we can use implicit loops.  (This is another thing that doesn't work in Python 2, so make sure you have Python 3 installed.)  Consider, for example, the loop above that prints out the elements of the list {\tt fruit} one at a time.  A list comprehension is a more compact syntax for the same thing:  `[print(item) for item in fruit]`.  As with loops, the variable `item` is a dummy:  we can use any name we wish.  



## Loops over counters 

What does this do?  The variable label `name` here is arbitrary, we can use anything we like.  The expression `range(n)` is new.  It's a built-in Python function that sets up a sequence of integers of length `n`.  With standard Python logic, it goes from zero to `n-1`.  The word `for` tells the program to do the commands that follow for all the values of `number` specified by `range(11)`;  that is, for integer values between zero and ten:  0, 1, 2, 3, ..., 10.  The print statement reports the result.  


Here's an example:  compute and print the squares of whole numbers (integers) up to ten.  ([Paul Ford](http://www.bloomberg.com/graphics/2015-paul-ford-what-is-code/) adds:  "just the sort of practical, useful program that always appears in programming tutorials to address the needs of people who urgently require a list of squares.")   We can do that with a `for` loop:
```python 
for number in range(11):
    square = number**2
    print(square)
```
What does this do?  The variable name `number` is arbitrary, we can use any name we like.   The expression `range(n)` is new.  It's a built-in Python function that sets up a sequence of integers of length `n`.  With standard Python logic, it goes from zero to `n-1`.  The word `for` tells the program to do the commands that follow for all the values of `number` specified by `range(11)`;  that is, for integer values between zero and ten:  0, 1, 2, 3, ..., 10.  The print statement reports the result.  


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
This includes the number zero in the sum, but, of course, that makes no difference in this case.  We can change that if we wish by using `range(1,11)`, which ranges from 1 to 10.  (If this sounds strange to you, remind yourself how numbering works in Python.  Or go back to the subsection on slicing in the previous chapter.)


**Exercise.** Write a loop that computes the sum of integers up to some arbitrary number `n`.  


**Example.**  Consider a bond that pays annual coupons for a given number of years (the maturity) and a principal of 100 at the end.  The yield-to-maturity is the rate at which these payments are discounted.  Given values for the coupon and the yield, the price of the bond is 
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

**Digression.**  When we wrote this code, we used the variable name `yield` instead of `ytm`.  Spyder marked this as "invalid syntax" with a warning sign to the left of the text.  Evidently the name `yield` is reserved for something else.  As general rule, it's a good idea to pay attention to the hints Spyder gives us.  


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

<!--
**Exercise.**  [??] 
-->


## Defining our own functions

It's easy to create our own functions -- experienced programmers do it all the time.  A common view is that you should never copy lines of code.  If you're copying, you're repeating yourself.  What you should do instead is write a function once and use it twice.  More than that, breaking a long program into a small number of functions makes code easier for others to read, which is always a good thing.  

A function has three components:  a name (what we call it), its input (a list of arguments), and its output (what it produces from the input).  Here's a classic example:    
```python 
def hello(firstname):  
    print('Hello,', firstname)    

somename = 'Chase'   
hello(somename) 
```    
The initial `def` statement defines the function, names it `hello`, identifies the input as `firstname`, and ends with a colon (:). The following statements are indented by the usual four spaces and specify what the function does.  In this case, it prints `Hello,` followed by whatever `firstname` hapens to be.  Python understands that the function ends when the indentation ends.  The last two lines in our code block define the string `somename = 'Chase'` and call the function with `somename` as the input argument.  Note that the name in the function's definition and its use need not be the same. 

By convention (but not necessity), Python aficionados put two blank lines before and after function definitions to make then stand out more clearly.  We used one to save space, but would typically use two.  


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


** ?? keyword arguments (sep section?) ?? **


##  More data structures

This whole section is mtwn:  we recommend you skim it and not worry about the details.  We'll review it later as needed when it comes up.  

The term **[data structure][5]** refers to the organization of a collection of data.  A list is a data structure, and we'll run across **dataframes** when we start working with data.  Here are  a couple more basic ones.  

[5]: http://en.wikipedia.org/wiki/Data_structure


**Tuples.** Tuples are collections of things in parentheses separated by commas.  Our primary (only?) use will be dates.  In the datatime module (more coming), the date April 1, 20012 is expressed by the tuple `date = (2012, 4, 1)` (year, month, day). 


**Dictionaries.**   Dictionaries are (unordered) pairs of things defined by curly brackets `{}`, separated by commas, with the items in each pair separated by colon.  They come in handy when you least expect it.  For example, a list of first and last names: 
```python
names = {'Dave': 'Backus', 'Chase': 'Coleman', 'Spencer': 'Lyon', 'Glenn': 'Okun'}
```
If we try `type(names)`, the reply is `dict`, meaning dictionary.  The components of each pair are referred to as the "key" (the first part) and the "value" (the second).  

We access the value from the key with syntax of the form: `dict[key]`.  In the example above, we get Glenn's last name by typing `names['Glenn']`.  

**Exercise.** Construct a dictionary whose keys are names and values are email addresses.  (Three such pairs is enough to make the point.) How would you access your neighbor's email address?  


<!--

## Special Python functions 

This is all mtyn and we don't plan to use any of it.  We include it because we got carried away.  

We can define one-line **lambda functions.** in a streamlined way.  To compute the ever-popular square of a number, we can define the function 
```python
square = lambda x:  x**2
```
We can now compute the square of 8 with `square(8)`.  

There are three functions that do implicit loops of different kinds:

* **map.** The statement `map(function, list)` applies a function to all the elements of a list or similar object, producing another list of the same length.  An example:  
```python
anylist = [2, 'Steelers', [1,2,3]]
m = map(type, anylist)
types = list(m)
```
The last line is needed because `map` produces a "map object," which isn't all that helpful on its own.  So we converted it to a list.  

* **reduce.** The statement `reduce(function, list)` applies a function to the elements of a list and produces a single value.  The idea is that the calculations are connected. For example, we could compute a sum one element at a time:  
```python
from functools import * 
numlist = [4, -2, 5]
sum = reduce(lambda x,y: x+y, numlist)
```
The difference here is that the computations cannot be done separately, they're all connected.  

* **filter.**  Here we apply a logical condition to each element of a list or similar object and keep those for which the condition is true.  Two examples:  
```python 
numlist = [4, -2, 5]
f = filter(lambda x:  x >= 0, numlist) 
newlist = list(f)
anylist = [2, 'Steelers', [1,2,3]]
f = filter(lambda x: type(x) == str, anylist)
newlist = list(f)
```  
The first one has the answer `newlist = [4, 5]`, the second `newlist = ['Steelers']`.  Can you see why?  

[?? talk about each one as an implicit loop?]

Some of us find this kind of syntax obscure and do our best to avoid it.  But similar ideas show up in lots of places.  
--> 


## Assignments and copies

Also mytn, but file away the idea for later.  This is what programmers call a "[gotcha][8]," an unexpected or counterintuitive feature of a language.  This one has gotten all of us at one time or other.  It shows up in the Pandas package, too.  The idea is that if we have (say) a list `x` and set `y = x`, then `y` is attached to `x`.  If we change the components of `x`, then `y` changes along with it.  A lot of other programming languages don't work that way:  the assignment `y = x` creates a new copy of `x`, and we can change `x` all we want without changing `y`.  But not in Python.  


[8]: https://en.wikipedia.org/wiki/Gotcha_(programming)


Python's behavior is similar in this respect to a spreadsheet.  Suppose we put the number 7 in cell A1, then set A2 = A1*10.  We would hope to see the number 70 in A2.  But if we change A1 to 5, then A2 would change to 50 along with it.


Back to Python.  We illustrate the issue with an example adapted from [Stack Overflow](http://stackoverflow.com/a/10844760/804513): 
```python 
x = [1,2,3]
y = x
y[0] = 'WHOA!'
print(x)
```
The output is `['WHOA!', 2, 3]`.  You see what's happened?  We changed the first value of `y`, but when we print `x` we realized it changed, too.  It works the other way, too.  If we change `y`, `x` changes with it:  
```python 
y[2] = 'xyzzy'
print(x)
```
Here we get the output:  `['WHOA!', 2, 'xyzzy']`.  

So that's how it works.  But suppose we want an independent copy of `x`, not simply a different label for it.  what do we do?  The answer is to produce a copy:   
```python 
x = [1,2,3]
y = x.copy()
x[0] = 'WHOA!'
print(y)
```
Here `y` hasn't changed, it's not connected to `x`.  


## Programming style  

Yes, style counts.  We're not only trying to get something done, we're also communicating with others who may look at our code and possibly use it.  A clear style makes that communication more effective.  

* Put import statements at the top.
* Lines should be no longer than 79 characters.
* Skip two lines before and after a function definition. 
* Adopt the style of your group.   

You can find more along these lines in the classic "[PEP8](https://www.python.org/dev/peps/pep-0008/)" and Google's [style guide](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html). 

Some programmers are religious about this.  We'd say simply to make your code readable.  

<!-- 
\url{http://www.reddit.com/r/Python/comments/3639nl/what_is_the_most_beautiful_piece_of_python_code/}
\url{https://github.com/mitsuhiko/werkzeug/blob/master/werkzeug/routing.py}  
--> 


## Resources 

See the resources in the previous chapter, especially the link to [Codecademy](https://www.codecademy.com/tracks/python).  If you work your way up to Advanced Topics, you'll be in good shape for anything that follows.  

Additional resources for specific topics:

* The official [Python Tutorial](https://docs.python.org/3.4/tutorial/controlflow.html) has a nice introduction to "control flow language" that includes comparisons, conditional statements, and loops.  

<!--
* Bernd Klein's [Python Course](http://www.python-course.eu/lambda.php) covers lambda functions, map, reduce, and filter.  The rest of his course is also quite good.  

* Ditto [Python Tips](http://book.pythontips.com/en/latest/), which starts at a level a bit above where we left off.  Lots of cool stuff if you'd like to push further into Python.  
-->

* [CodingBat](http://codingbat.com/python) has a great collection of exercises.  Runs online.  

<!--
* The [Python Challenge](http://www.pythonchallenge.com/) is for people who like puzzles as well as coding.  Not for the faint of heart.  
--> 

<!--
Obscure but cool:  https://github.com/cosmologicon/pywat#python-wats 
--> 
