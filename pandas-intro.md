# Managing data 1 

---
**Overview.**  We introduce packages (collections of tools that extend Python's capabilities) and explore one of them:  Pandas, the Python package devoted to data management.  We use Pandas to read spreadsheet data into Python and describe the "dataframe" this produces.  

**Python tools.**  Import, Pandas.  

**Buzzwords.**  Package, dataframe, series, csv files.  

**Application.**  Income by college major. 

**Code.**  [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_pandas_1.py).  

---

We're ready now to look at some data.  We start with getting data into Python, particularly data in spreadsheets.  Along the way we describe how Python uses collections of tools or plug-ins (**packages**) to address a wide range of applications:  data management (**Pandas**), graphics (Matplotlib), and many other things.  

You may recall that our canonical program structure consists of data input, data management, and graphics.  We'll spend most of our time here on the first, but touch on the second and produce a simple plot by finding a suitable method.  


## Reminders 

Some things we'll use repeatedly:

* Lists and strings.  Strings are collections of characters in quotes:  `'this is a string'`.  Lists are collections of things in square brackets:  `[1, 'help', 3.14159]`.   

* The `type()` function.  The command `type(x)` tells us what kind of object `x` is.  Past examples include integers, floating point numbers, and lists.  

* Methods and objects.  It's common in Python to work with objects using methods.  (If these words are confusing, go back to the previous chapter.)  We apply the method `bar` to the object `foo` by typing `foo.bar`.  

* Tab completion.  To find the list of methods available for a hypothetical object `x`, type `x.[tab]` in Spyder's IPython console -- or in an IPython notebook -- to get a list.  That's referred to as "tab completion." 

* Help.  We can get help for a function or method `foo` by typing `foo?` into the IPython console or `foo` in the Object explorer.  Try each of them with the `type()` function to remind yourself how this works.  

And while we're reviewing:   Save the code file for this chapter in your `Data_Bootcamp` directory and open it in Spyder.  


## Python packages

Python is not just a programming language, it's an open source collection of tools that includes both basic Python and a large collection of packages written by different people.  The terminology varies.  What we call a package others sometimes call a **library**.  The term **module** typically refers to a subset of basic Python or a package.  

The standard packages -- which we'll talk more about in a minute -- are well written, well documented, and have armies of users who spot and correct problems.  Some of the others less so.  Our suggestion is to stick to the standard packages, specifically those in the Anaconda distribution, until you're reasonably comfortable with Python.

Some of the leading packages for numerical ("scientific") computation  are

* **[Pandas](http://pandas.pydata.org/).**  The leading package for managing and manipulating data and our focus in this chapter. 

* **[Matplotlib](http://matplotlib.org/).**  The leading graphics package for Python.  We'll use it extensively.  

* **[NumPy](http://www.numpy.org/).**  Tools for numerical computing, including linear algebra. Compare this to Excel, where the basic unit is a cell, a single number.  In NumPy the basic unit is a vector (a column) or matrix (a table or worksheet).  In this respect, it's a direct competitor to Matlab.  We won't see much of NumPy here -- maybe a little -- but it's the foundation for Pandas, which we'll use constantly.   

All of these packages come with the [Anaconda distribution](http://docs.continuum.io/anaconda/pkg-docs.html).  We'll use all of them a bit, and Matplotlib and Pandas constantly.  

Here are some others you might run across:  

* **[Seaborn](http://stanford.edu/~mwaskom/software/seaborn/).** A "wrapper" (isn't that a great term?) for Matplotlib that makes it easier to use.  

* **[Statsmodels](https://pypi.python.org/pypi/statsmodels).**  The basic statistics package. 

* **[Scikit-learn](http://scikit-learn.org/stable/).** A package for "[machine learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/)," which is the name computer scientists give to data work.  CS people have done some cool things with data.  They're also really good at naming things:  machine learning, visualization, support vector machines, random forests.  

* **[NLTK](http://www.nltk.org/).**  The so-called Natural Language Toolkit processes text.  Here "natural language" means "words."  Investors, for example, might process the words used in financial reports to detect mood or sentiment.  One of our students is using NLTK to analyze tweets.  The big-picture idea is that data can be anything, not just numbers.   

* **[Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/)** and **[Scrapy](http://scrapy.org/).**  Extract ("scrape") data from web sites.  

* **[Django](https://www.djangoproject.com/).**  A popular tool for website development.  

We won't use them, but they're in Anaconda, too.  Feel free to give them a try.  If you do, please report back on your experience.  


## Importing packages 

In Python -- and many other languages -- we need to tell our program which packages we plan to use.  We do that with the `import` command.  

Here are some examples applied to a mythical package `xyz` and mythical command `foo`:    

* `from xyz import *`.  This imports all the commands from the package `xyz`.  A command `foo` is then executed by typing `foo`.  We don't usually do this, because it opens up the possibility that the same command exists in more than one package, which is virtually guaranteed to give us confusing output.  If `foo` is the only command we care about, we can use `from xyz import foo` instead.    

* `import xyz`.  This imports the whole thing as well, but the language or syntax changes.  Here the command `foo` is executed by adding `xyz.` (note the period) before it:  `xyz.foo`.

* `import xyz as x`.  This is the most common syntax.  It allows the shorthand `x.foo`, which saves us the effort of typing `xyz`.  Many packages have standard abbreviations.  We use them ourselves and recommend the same, it makes code clearer to others.   


The last version of `import` is the one we typically use.  We'll see these examples repeatedly:
```python 
import pandas as pd
import matplotlib.pyplot as plt 
```
You might also go through earlier examples and identify the `import` statements you find.  By convention, they are placed at the top of the program.  What packages or modules have we used?  What do they do?  


Some fine points:  

* What happens if we issue an import statement twice?  Answer:  Nothing, no harm done.  

* Jokes.  These are programmer jokes, which might be a contradiction in terms, but try these and see what happens:   
  ```python 
  import this
  import antigravity 
  ```

* We can check the version number of a package with the `__version__` method.  To check the version of Pandas, try 
  ```python 
  import pandas as pd 
  print('Pandas version ', pd.__version__)   	# these are double underscores 
  ```
  This can be helpful if we're trying to track down an error.  Stack Overflow typically asks for the version number when you post a question.  

  (Obscure note.  The double underscore often shows up in Python for basic things like this. When we tried to track down the logic, we ran into [this explanation](http://stackoverflow.com/questions/1301346/the-meaning-of-a-single-and-a-double-underscore-before-an-object-name-in-python), which confused us thoroughly. But see also [this](http://stackoverflow.com/questions/8689964/python-why-do-some-functions-have-underscores-before-and-after-the-functio).)


**Exercise.** Import Pandas.  What version are you running?  

**Exercise.**  Suppose you import Pandas twice under different names, once with `import pandas as pd` and once with `import pandas as pa`.  What do you think happens?  Can you write a short program that tests your conjecture?  (This will take a little thought, feel free to consult your neighbor.)  

## The Pandas package 

Pandas is Python's data management package and an essential part of data work in Python.  The authors [describe it](http://pandas.pydata.org/) as "an open source library for high-performance, easy-to-use data structures and data analysis tools in Python."  That's a mouthful.  Suffice it to say that we can do pretty much everything in Pandas that we can do in Excel -- and more.  We can compute sums of rows and columns, generate new rows or columns, compute pivot tables, and lots of other things.  And we can do all this on much larger files than Excel can handle.  

We'll come back to all of these things later in the course, but for now we'll focus on data input:  how to get data into a Python program.  

## Preparing test input 

The simplest way to get data into a Python program is to read it from a file -- a spreadsheet file, for example.  The word "read" here means take what's in the file and somehow get it into Python.  Pandas can read lots of such files:  csv, xls, xlsx, and so on.  

We'd like to read all of these files into Python.  The first step is to prepare some test files we can use.  Start Excel or the equivalent (did we really say that?) and open a new blank spreadsheet.  In column one ("A") put x1 at the top and the numbers 1, 4, and 5 below it.  In column two ("B") put x2, 2, 3, and 6.  In column three ("C") put x3, 3, 4, and 7.  

Now save the contents three times as, respectively, csv, xls, and xlsx files with filenames `test.csv`, `test.xls`, and `test.xlsx`.  Put all three in your `Data_Bootcamp` directory. 


## Reading csv files

We've found that **csv files** ("comma separated values") are the most useful common data format.  Their simple structure (entries separated by commas) allows easy and rapid input. That's a general statement, not a statement about Python.  They also avoid some of [the problems](http://www.win-vector.com/blog/2014/11/excel-spreadsheets-are-hard-to-get-right/) of translating Excel into other formats.  


Let's read the file `test.csv` into Python.  We do that with the cleverly-named `read_csv` function in Pandas:
```python 
import pandas as pd
file = 'test.csv'
df = pd.read_csv(file)
```
The syntax works like this:  `read_csv` is a Pandas function that reads csv files.  The `pd.` before it tells Python it's a Pandas command; we established the `pd` abbreviation in the `import` statement.  

Since we're positive people, let's assume this runs without error.  If so, we can check the contents by adding the statement `print(df)`.  It should look like the file we contructed earlier.  

--- 

**Digression.** Prepare yourself for a long digression about the **current working directory** (cwd), the directory (folder) where Python looks for things.  If the code above generated an error, the most common reason is that Python looked for the file in the wrong place.  If that's the case, we have some work to do.  

Fixing mistakes -- "debugging" -- is like solving a mystery. As Sherlock Homes said, the first step is to collect data:   

* Check the cwd. We do that by running this mysterious code:  
  ```python 
  import os         # operating system module 
  print('Current working directory: ', os.getcwd())
  ```  
  This tells us the cwd.  If it's the directory where the file is, we're all set.  

* List the files in the cwd:  
  ```python 
  print('List of files in working directory:', os.listdir())
  ```
  If our file is there, we're good to go.   


If `test.csv` isn't there, we need to change the current working directory (cwd).  In Spyder, the cwd is in a textbox in the upper right corner.  We follow these steps to change it:

* Find the folder icon to the right of the cwd textbox.  We know which one because a text bubble pops up that says "Browse a working directory."  When we click on the icon, we'll be able to browse our directories until we find the one we want, probably the one labelled `Data_Bootcamp`.  Once we find it, we click on Select to choose it.  

* Now we click on the red arrow to the right, the one with the text bubble that says "Set as console's current working directory."  You can check using `os.getcwd`.  If we get the right directory, we can stop.  If not -- and "not" is our experience -- one more step will do it.  Click out of Spyder and restart.  Yes, we know that's ugly, but [it's not our fault](https://github.com/spyder-ide/spyder/issues/1702).  

End of digression.  

--- 

We hope, by now, that we (meaning you) have been able to read the csv file into Python.  

**Exercise.**  Run the code block 
```python 
import pandas as pd
file = 'test0.csv'
df = pd.read_csv(file)
```
The idea is to trigger an error message (the file `test0.csv` doesn't exist) so that we know what that looks like.  


## Properties of dataframes 

Ok, now we have a dataframe -- what's in it?  What can we do with it?  

If you try `type(df)` you'll find that it's a DataFrame, the standard object type in pandas.
It's a table of numbers, much like a sheet in a spreadsheet program,
with labels for rows (the index) and columns (the variables).  

`df.[tab]` 

Get labels:  df.columns, df.index...  

Look at it:  df.head(), df.head(7), df.tail().  

These are dfs too.  head = df.head(), type(head)

Other methods we could try:  

* df.columns.tolist() (the column labels as a list),
* df.describe() (summary statistics)
* df.corr() (correlations between variables)
* df.dtypes() (variable types)
* df.info() (information about the form of the data).
* Transpose df.T

**Exercise.** Find another method with tab completion.  What does it do?  ??


dtypes pretty good.  

For object, get list of entries:  entries = df['var'].drop_duplicates()

value counts 

**Sorting.**

## Other data input    

We can read other kinds of files in much the same way.  Some examples show how this works:  

* **Online csv's.**  Pandas will read data from online csv's as well, we just put the url (internet address) in the function.  This example reads `test1.csv` from our GitHub repository (an online collection of files associated with the course):  
  ```python 
  url1 = 'https://raw.githubusercontent.com/DaveBackus/'
  url2 = 'Data_Bootcamp/master/Code/Data/test1.csv'
  url = url1 + url2
  df = pd.read_csv(url)
  ```
  Run the code and print `df` to see what you get.  


* **xls and xlsx files.**  
```python 
file = '../Data/test2.xlsx'
xls = pd.read_excel(file)       # default is first sheet
```

**more on xls's**  Get list of sheets so we know what we're dealing with... 
Also read a few rows, see what they look like... 

A digression on GitHub files.  GitHub has viewers for csv files (also some others) that make them easier to read online.  But they're not the real files.  If we use their urls to access data, we get junk.  The secret is to use the raw files:  click on the raw button above and to the right and you'll get (surprise) the raw file, aka the real thing.  Here's an example to practice on:  

https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv

**Exercise.** Read `test.xlsx` and `test.xls` from the GitHub repo.  The url's are
```python
url1 = 'https://github.com/DaveBackus/Data_Bootcamp/raw/master/Code/Python/test.xls'
url1 = 'https://github.com/DaveBackus/Data_Bootcamp/raw/master/Code/Python/test.xlsx'
``` 
(Note the word "raw" in the address.)  

* **Clipboard.**  Copy from clipboard.
We're not fans of this, it makes replication hard, but it's awful convenient
and recommended by one of our former students.  `clip = pd.read_clipboard()`


**Exercise.** Input `test.csv` from the clipboard and assign it to the dataframe `df_clip`.  


## Modifying dataframes:  column methods

Referring to variables

Renaming variables... 

Single variables (series)

New variables ... 

Logs (np!) 

Subsets of variables 

Saving results:  assigne or `inplace=true'.  


**Transpose**  Switch rows and columns... 


## Modifying dataframes:  row methods

Selecting the rows we want...  



## Accessing data from internet sources


FRED, World Bank...  etc.  They have API's, which give us better access than even a csv...  


Warning:  subject to change...


## Application:  Greek government debt in WEO

Want operator:  graph Greek debt over time, compare to other countries.  

**Example (WEO).** 
```python 
url = 'http://www.imf.org/external/pubs/ft/weo/2014/01/weodata/WEOApr2014all.xls'
weo = pd.read_csv(url, sep='\t')    # tab = \t
```


**Exercise.** Run the WEO code and list the contents.  What does the file look like?



**Example (incomes of college graduates by major).**    Also:  **Talk about RAW files** 


**Example (Chipotle).** 


**Example (IMDB).** 
Brandon Rhodes' movie data...  https://github.com/brandon-rhodes/pycon-pandas-tutorial

http://pages.stern.nyu.edu/~dbackus/csv/cast.csv
http://pages.stern.nyu.edu/~dbackus/csv/titles.csv
http://pages.stern.nyu.edu/~dbackus/csv/release_dates.csv 

**Example (Stern teaching data).** 


**Example.** Chetty's income data...  

**Example (Big Mac currency index).**  This is an xls file with multiple sheets.  
http://infographics.economist.com/2015/databank/BMfile2000-Jul2015.xls


**Example (speed dating).**  download tab delimited data and read it with `read_csv`. 
 
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/27893 

Papers:  https://scholar.google.com/scholar?hl=en&q=fisman+speed+dating&btnG=&as_sdt=1%2C33

**Example.** Beer ratings...   
https://github.com/TomAugspurger/PyDataSeattle/blob/master/notebooks/3.%20Indexing.ipynb


**Exercise.** 

## More...  

Talk about using Stata or SAS programs, shows up in CPS and MEPS, probably others.  


## Output methods

 to_excel, to_csv ...


## More about data frames

Referring to series...  


Creating new series 
(This is great, all done at once.  Loop somewhere.)  


plot methods...  


## Resources 

* Brandon Rhodes' exceptionally good [PyCon video](https://github.com/brandon-rhodes/pycon-pandas-tutorial).  Two and a half hours will rarely be better spent.  

* xlrd:  http://tech.novus.com/augmenting-your-excel-workflow-with-python/  In Anaconda.  See [here](https://www.reddit.com/r/Python/comments/3fbdur/augmenting_your_excel_workflow_with_python/) for comments on similar packages.  Several of them, including xlrd, are in [Anaconda](http://docs.continuum.io/anaconda/pkg-docs).  

https://realpython.com/blog/python/working-with-large-excel-files-in-pandas/ 

Kaggle example:  http://blog.kaggle.com/2013/01/17/getting-started-with-pandas-predicting-sat-scores-for-new-york-city-schools/ 

Chipotle data from NYT:  
http://www.nytimes.com/interactive/2015/02/17/upshot/what-do-people-actually-order-at-chipotle.html?_r=0
https://raw.githubusercontent.com/TheUpshot/chipotle/master/orders.tsv
http://www.danielforsyth.me/pandas-burritos-analyzing-chipotle-order-data-2/ 

http://pandas.pydata.org/pandas-docs/stable/cookbook.html#data-in-out
http://pandas.pydata.org/pandas-docs/stable/io.html 

History of debt (see data link on left):  http://www.imf.org/external/ns/cs.aspx?id=262 


http://www.alfredo.motta.name/data-manipulation-primitives-in-r-and-python/ 

http://www.gregreda.com/2013/10/26/intro-to-pandas-data-structures/ 

Cookbook:  http://pandas.pydata.org/pandas-docs/stable/tutorials.html#pandas-cookbook 

Pandas plotting methods:  http://pandas.pydata.org/pandas-docs/version/0.10.1/visualization.html#autocorrelation-plot

Another intro:  http://efavdb.com/pandas-tips-and-tricks/