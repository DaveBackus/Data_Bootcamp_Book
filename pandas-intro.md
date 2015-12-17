# Data input: Packages and Pandas 

---
**Overview.**  We introduce "packages" -- collections of tools that extend Python's capabilities -- and explore one of them:  Pandas, the Python package devoted to data management.  We use Pandas to read spreadsheet data into Python and describe the "dataframe" this produces.  

**Python tools.**  Import, Pandas.  

**Buzzwords.**  Package, dataframe, series, csv file, mtwn.  

**Applications.**  Income by college major, Greek government debt, cell phone penetration by country. 

**Code.**  [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_pandas_1.py).  

---

**UNDER CONSTRUCTION**

We're ready now to look at some data.  We start with getting data into Python, particularly data in spreadsheets.  Along the way we describe how Python uses collections of tools or plug-ins (**packages**) to address a wide range of applications:  data management (**Pandas**), graphics (Matplotlib), and many other things.  

You may recall that our canonical program structure consists of data input, data management, and graphics.  We'll spend most of our time here on the first, but touch on the second and produce a simple plot by finding a suitable method.  

## Reminders

* Data structures are organizations of data.  Examples:  strings, lists, dataframes. 

* Slicing strings and lists.  ..


## Python packages

Python is not just a programming language, it's an open source collection of tools that includes both basic Python and a large collection of packages written by different people.  The word "package" here refers to plug-ins or extensions that expand Python's capabilities.  The terminology varies.  What we call a package others sometimes call a "library."  The term "module" typically refers to a subset of basic Python or one of its packages.  You won't go far wrong to use the terms interchangeably.  

The standard Python packages are well written, well documented, and have armies of users who spot and correct problems.  Some of the others less so.  Our suggestion is to stick to the standard packages, specifically those that come with the Anaconda distribution.  

Some of the leading packages for numerical ("scientific") computation are

* **[Pandas](http://pandas.pydata.org/).**  The leading package for managing and manipulating data and our focus in this chapter. 

* **[Matplotlib](http://matplotlib.org/).**  The leading graphics package for Python.  We'll use it extensively.  

* **[NumPy](http://www.numpy.org/).**  Tools for numerical computing.  In Excel, where the basic unit is a cell, a single number.  In NumPy the basic unit is a vector (a column) or matrix (a table or worksheet).  We won't see much of NumPy here -- maybe a little -- but it's the foundation for Pandas, which we'll use constantly.   

All of these packages come with the [Anaconda distribution](http://docs.continuum.io/anaconda/pkg-docs.html), which means we already have them installed and ready to use.  

<!-- 
Here are some others you might run across:  

* **[Seaborn](http://stanford.edu/~mwaskom/software/seaborn/).** A "wrapper" (isn't that a great term?) for Matplotlib that makes it easier to use.  

* **[Statsmodels](https://pypi.python.org/pypi/statsmodels).**  The basic statistics package. 

* **[Scikit-learn](http://scikit-learn.org/stable/).** A package for "[machine learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/)," which is the name computer scientists give to data work.  CS people have done some cool things with data.  They're also really good at naming things:  machine learning, visualization, support vector machines, random forests.  

* **[NLTK](http://www.nltk.org/).**  The so-called Natural Language Toolkit processes text.  Here "natural language" means "words."  Investors, for example, might process the words used in financial reports to detect mood or sentiment.  One of our students is using NLTK to analyze tweets.  The big-picture idea is that data can be anything, not just numbers.   

* **[Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/)** and **[Scrapy](http://scrapy.org/).**  Extract ("scrape") data from web sites.  

* **[Django](https://www.djangoproject.com/).**  A popular tool for website development.  

We won't use them, but they're in Anaconda, too.  Feel free to give them a try.  If you do, please report back on your experience.  
-->  


## Importing packages 

In Python -- and many other languages, too -- we need to tell our program which packages we plan to use.  We do that with an `import` statement/command.  

Here are some examples applied to a mythical package `xyz` and mythical command `foo`:    

* `import xyz as x`.  This imports the package `xyz` under the abbreviation `x`.  A command `foo` in package `xyz` is then executed by typing `x.foo`.  This is the most common syntax and the one we'll use.  With Pandas, for example, the standard import statement is `import pandas as pd'.    

* `import xyz`.  This imports the whole thing as well, but here the command `foo` is executed with the more verbose `xyz.foo`.  

* `from xyz import *`.  This imports all the commands from the package `xyz`.  The command `foo` is executed simply by typing `foo`.  We don't usually do this, because it opens up the possibility that the same command exists in more than one package, which is virtually guaranteed to give us confusing output.  If `foo` is the only command we care about, we can use `from xyz import foo` instead. 

The first version of `import` is the one we typically use.  We'll see these examples repeatedly:
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
  This can be helpful if we're trying to track down an error.  

  (Obscure note.  The double underscore often shows up in Python for basic things like this. When we tried to track down the logic, we ran into [this explanation](http://stackoverflow.com/questions/1301346/the-meaning-of-a-single-and-a-double-underscore-before-an-object-name-in-python), which confused us thoroughly. But see also [this](http://stackoverflow.com/questions/8689964/python-why-do-some-functions-have-underscores-before-and-after-the-functio).)


**Exercise.**  Import Pandas.  What version do you have?  

**Exercise.**  Suppose you import Pandas twice under different names, once with `import pandas as pd` and once with `import pandas as pa`.  What do you think happens?  Can you write a short program that tests your conjecture?  (This will take a little thought, feel free to consult your neighbor.)  


## The Pandas package 

Pandas is Python's data management package and an essential part of data work in Python.  The authors [describe it](http://pandas.pydata.org/) as "an open source library for high-performance, easy-to-use data structures and data analysis tools in Python."  That's a mouthful.  Suffice it to say that we can do pretty much everything in Pandas that we can do in Excel -- and more.  We can compute sums of rows and columns, generate new rows or columns, compute pivot tables, and lots of other things.  And we can do all this on much larger files than Excel can handle.  

We'll come back to all of these things later in the course, but for now we'll focus on data input:  how to get data into a Python program.  


## Data input 1:  reading internet files    

The easiest way to get data into a Python program is to read it from a file -- a spreadsheet file, for example.  The word "read" here means take what's in the file and somehow get it into Python.  Pandas can reads lots of files:  csv, xls, xlsx, and so on.  The files can be on our computer or on the internet.  We'll start with the internet, because it there's less ambiguity about the location of the file.  

Pandas can read lots of file types, but **csv files** ("comma separated values") are a common format.  Their simple structure (entries separated by commas) allows easy and rapid input. That's a general statement, not a statement about Python.  They also avoid some of [the problems](http://www.win-vector.com/blog/2014/11/excel-spreadsheets-are-hard-to-get-right/) of translating Excel files.  If we have an Excel spreadsheet, we can always save it as a "CSV (Comma delimited) (*.csv)" file.  Excel will warn us that some features are incompatible with the csv format, but we're generally happy to do it anyway.  Here's an example of a [raw csv file](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/test.csv) (pretty basic, eh?) and this is how it's displayed in [Excel](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv).  

Let's read a csv file into Python.  We like to read data from internet sources, especially when the data is updated at automatically at the source for us.  This example doesn't do that, but it shows how easy it is to get data into Python.  We read the cleverly-named `test.csv` with the `read_csv` function in Pandas from our GitHub site:
```python 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test.csv'
url  = url1 + url2
df = pd.read_csv(url)
```
The syntax works like this:  `url` is a string that tells Python where to look for the file.  We break it in two because it's too long to fit on one line.  `read_csv` is a Pandas function that reads csv files.  The `pd.` before it tells Python it's a Pandas command; we established the `pd` abbreviation in the `import` statement.  The `df` on the left makes this an assignment:  we assign what we read to the variable `df`.  

[If the internet is down, or something else goes wrong, we can do this instead:  
```python 
df = pd.DataFrame([['Dave', 1, 2, 3.5], 
                   ['Chase', 4, 3, 4.3], 
                   ['Spencer', 5, 6, 7.8]],
                   columns=['name', 'x1', 'x2', 'x3'])
```
The details aren't important.  If you're curious, we've put the data into rows and added column names.]  

So what does this give us?  We have read data into Python and assigned it to the variable `df`, which we'll now examine.  What's in `df`?  We can check its contents by adding the statement `print(df)`.  Give or take some formatting, it should look like this:  
```python
      name  x1  x2  x3
0     Dave   1   2   3
1    Chase   4   3   4
2  Spencer   5   6   7
```
What we have is a table, much like what we'd see in a spreadsheet.  The first column is new, added by the program, but the others come from the csv file we just read.  


**Exercise.**  Run the code block 
```python 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test0.csv'    # note the added 0 
url  = url1 + url2
df = pd.read_csv(url)
```
The idea is to trigger an error message (the file doesn't exist) so that we know what that looks like.  


## Properties of dataframes 

Ok, so we read a file and assigned the contents to `df`.  What kind of object is `df`?  We can check with the `type()` function.  If we enter `type(df)` into the IPython console, it answers:  `pandas.core.frame.DataFrame` -- dataframe, for short.  A dataframe is a "data structure" -- a specific organization of data -- that includes three things:  the data, column labels, and row labels.  Typically the columns are specific variables and the column labels give us their names.  The rows are observations, and the row labels give us their names.  

We can extract the column labels with the method:  `df.columns`.  That gives us the verbose output `Index(['name', 'x1', 'x2', 'x3'], dtype='object')`.  We prefer to have them as a list, which we get by typing `list(df)` in the IPython console.  That gives us the column names as a list:  `['name', 'x1', 'x2', 'x3']`.  If we check the source (go to the url), we see that the column labels were part of the file we read.  

The row labels are referred to as the "index."  We can extract them with the method:  `df.index`.  That gives us the verbose output `Int64Index([0, 1, 2], dtype='int64')`.  We can convert it to a list by adding another method, `df.index.tolist()`, which gives us `[0, 1, 2]`.  In this case, the index labels were not part of the original, so Pandas inserted a counter.  As usual in Python, the counter starts at zero.  

**Exercise.** What does `df.columns.tolist()` do?  How does it compare to `list(df)`?  

**Exercise.** Run the code 
```python 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test.csv'
url  = url1 + url2
df0 = pd.read_csv(url, index_col=0)
```
What is the index in this case?  Can you explain why?  
 
We'll see one other feature of dataframes in the near future:  the type of each column of data.  Pandas allows every variable (that is, column) to have a different data type, but the type must be the same within a column.  With our dataframe `df`, we get the types from `df.dtypes`:  
```python
name     object
x1        int64
x2        int64
x3      float64
```
Evidently `x1` and `x2` are integers and `x3` is a float.  They're no different from the types of numbers we can across in the previous chapter.  The first column, `name`, is something different.  Object is the name Pandas gives to things it can't turn into numbers -- strings, essentially.  Sometimes, as here, that makes sense:  names like `Dave` and `Spencer` are naturally strings.  But in many cases we've run across, numbers are given the dtype object because there was something in the data that didn't look like a number.  We'll see more of that later on.  


**Exercise.** What does the method `df.mean` do?  `df.describe()`?  `df.T`?  


## Working with variables

what is this?
df['x1']

construct new variables
df['y1'] = df['x1']/df['x2']
df['y2'] = df['x2'] + df['x3']



## Creating and locating files on your computer

Next up:  reading spreadsheet files in Python from your computer.  This is really useful, but there's a catch:  we need to tell Python where to find the file.  That's a small thing in principle, but a tricky one in practice.  It isn't Python, really, but it's an issue we need to address. 


**Prepare test data.**  We'll start with the easy part.  Open a blank spreadsheet in Excel and enter the data:  
```python
name    x1  x2  x3
Dave     1   2   3
Chase    4   3   4
Spencer  5   6   7
```
That is:  four rows with four entries in each one.  

Now save the contents in our `Data_Bootcamp` directory.  Do this three times in different formats:
* As an Excel file.  Save the file as `test.xlsx`.  
* As an old-style Excel file.  Save as an "Excel 97-2003 (*.xls)" file under the name `test.xls`.   
* As a CSV file.  Save as a "CSV (Comma delimited) (*.csv)" file under the name `test.csv`.   
Each of these options show up in Excel when we choose "Save As." 


**Find the file.**  Ok, now where is the file?  We know, it's in the `Data_Bootcamp` directory, but where is that?  We need the complete path so we can tell Python where to look.   

Let's introduce some terms so we can be clear what we're talking about.  The "file name" is something like `test.xlsx`.  In Windows, the "directory" is something like this:  
```
C:\Users\userid\Documents\Data_Bootcamp
```
On a Mac, it is something like
```

```
The (full or absolute or complete) "path" is a combination of the two, with a slash in between:  
```
C:\Users\userid\Documents\Data_Bootcamp\test.csv
```

* Mac OS.  We select (but not open) the file and do "command-i" to get the file's information window.  From the window, we copy the path the follows "Where:."  It looks like we're copying arrows, but they turn into slashes when we paste the path.  

* Windows.  

Windows gives us 
C:\Users\dbackus\Dropbox\Documents\Classes\Data_Bootcamp\Code\Python

Need to reverse the back slashes:  change `\` to `/`.  


```python
path = 'C:/Users/dbackus/Dropbox/Documents/Classes/Data_Bootcamp/Code/Python/test.csv'
```


How do we find it?  On Windows?  Macs?  

Check to see if it's there. 

Fixing mistakes -- "debugging" -- is like solving a mystery. As Sherlock Homes said, the first step is to collect data:   


**Request for help.**  If you find this less than clear, or different on your computer than described here, let us know.  Tell us what to do on your computer and we'll update the text accordingly. 


## Data input 2:  reading files from your computer 



**Read the file.**  We're finally ready to do what we want...  



**Exercise.** 




## More dataframe methods 

**Output,.** We starting by read a can do the reverse


**Clipboard methods.**  We can read from the clipboard and write to it.  
We're not fans of this, it makes replication hard, but it's awful convenient
and recommended by one of our former students.  `clip = pd.read_clipboard()`

**Exercise.** Input `test.csv` from the clipboard and assign it to the dataframe `df_clip`.  


## Data input 3:  internet sources


FRED, World Bank...  etc.  They have API's, which give us better access than even a csv...  


Warning:  subject to change...



We can read other kinds of files in much the same way.  Some examples show how this works:  

A digression on GitHub files.  GitHub has viewers for csv files (also some others) that make them easier to read online.  But they're not the real files.  If we use their urls to access data, we get junk.  The secret is to use the raw files:  click on the raw button above and to the right and you'll get (surprise) the raw file, aka the real thing.  Here's an example to practice on:  

https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv

**Exercise.** Read `test.xlsx` and `test.xls` from the GitHub repo.  The url's are
```python
url1 = 'https://github.com/DaveBackus/Data_Bootcamp/raw/master/Code/Python/test.xls'
url2 = 'https://github.com/DaveBackus/Data_Bootcamp/raw/master/Code/Python/test.xlsx'
``` 
(Note the word "raw" in the address.)  


**drop columns.** 
df.drop(df.columns[[1, 69]], axis=1, inplace=True) 

## Examples 

Want operator:  graph Greek debt over time, compare to other countries.  

**Example (Penn World Tables).**



**Example (incomes of college graduates by major).**    Also:  **Talk about RAW files**


**Example (WEO).** 
```python 
url = 'http://www.imf.org/external/pubs/ft/weo/2014/01/weodata/WEOApr2014all.xls'
weo = pd.read_csv(url, sep='\t')    # tab = \t
```

**down the rabbit hole** 


**Exercise.** Run the WEO code and list the contents.  What does the file look like?

 

**Example (Chipotle).** 


**Example (IMDB).** 
Brandon Rhodes' movie data...  https://github.com/brandon-rhodes/pycon-pandas-tutorial

http://pages.stern.nyu.edu/~dbackus/csv/cast.csv
http://pages.stern.nyu.edu/~dbackus/csv/titles.csv
http://pages.stern.nyu.edu/~dbackus/csv/release_dates.csv 

**Example (Stern teaching data).** 

<!--
**Example.** Chetty's income data...  

**Example (Big Mac currency index).**  This is an xls file with multiple sheets.  
http://infographics.economist.com/2015/databank/BMfile2000-Jul2015.xls
 
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/27893 

Papers:  https://scholar.google.com/scholar?hl=en&q=fisman+speed+dating&btnG=&as_sdt=1%2C33
--> 


**Example (age distributions).**  UN data...     


**Example (Reinhart-Rogoff).**

http://simplystatistics.org/2013/04/16/i-wish-economists-made-better-plots/ 


**Example (AirBNB).**

http://insideairbnb.com/get-the-data.html



**Example (mortality).** Causes from CDC...  


**Example (bond yields).**


**Example (speed dating).**  download tab delimited data and read it with `read_csv`. 

**Example.** Beer ratings...   
https://github.com/TomAugspurger/PyDataSeattle/blob/master/notebooks/3.%20Indexing.ipynb


**Exercise.** 


Education data (PISA)...


## A taste of what's ahead 

set index 
transpose 

... 


## More than we need (mtwn) 1:  Copying internet files 


**Example.** 


## More than we need (mtwn) 2:  Unzipping files 


**Example.** 



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


## Appendix:  creating dataframes

We've generated dataframes with input commands.  Here are some examples that do it explicitly without reference to any external files.  Keep in mind the components of a dataframe:  a table of data, row labels, and column labels.  

**From lists.**  See above.  

**From dictionaries.** 


**From Numpy arrays.**  This is more than a little obscure, but it's often helpful in producing test cases to have a way to generate random numbers.  The Numpy package makes this easy.  (Take example from SS or documentation.)

