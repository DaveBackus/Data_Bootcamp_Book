# Data input: Packages and Pandas 

---
**Overview.**  We introduce "packages" -- collections of tools that extend Python's capabilities -- and explore one of them:  Pandas, the Python package devoted to data management.  We use Pandas to read spreadsheet data into Python and describe the "dataframe" this produces.  

**Python tools.**  Import, Pandas.  

**Buzzwords.**  Package, dataframe, series, csv file.  

**Applications.**  ??? 

**Code.**  [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_pandas_1.py).  

---

**UNDER CONSTRUCTION**

We're ready now to look at some data.  In fact, lots of data.  

You may recall that our typical program consists of data input, data management, and graphics.  We'll spend most of our time here on the first -- data input -- but touch on the second and produce some simple graphs.  Along the way we describe how Python uses collections of tools or plug-ins (**packages**) to address a wide range of applications:  data management (**Pandas**), graphics (Matplotlib), and many other things.  


## Reminders

* Methods and objects.  Recall that we apply the method `justdoit` to the object `x` with `x.justdoit`.  A common example is the `plot()` method, which works for a wide range of data objects.   

* Help.  We get help in Spyder from both the IPython console and the Object inspector.  Remind yourself what these are.  For the hypothetical `x.plot()`, we would type `x.plot?` in the IPython console or `x.plot` in the Object inspector.  

* Data structures.  That's the term we use for specific organizations of data.  Examples are strings, lists, and dictionaries. Each has a specific structure and a set of methods we can apply.   

* ?? more? 


## Python packages

Python is not just a programming language, it's an open source collection of tools that includes both basic Python and a large collection of packages written by different people.  The word "package" here refers to plug-ins or extensions that expand Python's capabilities.  Terminology varies.  What we call a package others sometimes call a "library."  The term "module" typically refers to a subset of basic Python or one of its packages.  You won't go far wrong to use the terms interchangeably.  

The standard Python packages are well written, well documented, and well supported:  they have armies of users who spot and correct problems.  Some of the others less so.  We try to stick to the standard packages, specifically those that come with the Anaconda distribution.  

Some of the leading packages for numerical ("scientific") computation are 

* **[Pandas](http://pandas.pydata.org/).**  The leading package for managing data and our focus in this chapter. 

* **[Matplotlib](http://matplotlib.org/).**  The leading graphics package.  We'll use it extensively.  

* **[NumPy](http://www.numpy.org/).**  Tools for numerical computing.  In Excel the basic unit is a cell, a single number.  In NumPy the basic unit is a vector (a column) or matrix (a table or worksheet).  We won't see much of NumPy here -- maybe a little -- but it's the foundation for Pandas, which we'll use constantly.   

All of these packages come with the [Anaconda distribution](http://docs.continuum.io/anaconda/pkg-docs.html), which means we already have them installed and ready to use.  

Pandas is an essential part of data work in Python.  The authors [describe it](http://pandas.pydata.org/) as "an open source library for high-performance, easy-to-use data structures and data analysis tools in Python."  That's a mouthful.  Suffice it to say that we can do pretty much everything in Pandas that we can do in Excel -- and more.  We can compute sums of rows and columns, generate new rows or columns, construct pivot tables, and lots of other things.  And we can do all this with much larger files than Excel can handle.  

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

In Python we need to tell our program which packages we plan to use.  We do that with an `import` statement.  

**?? terminology:  command?  function?  something else ??**

Here are some examples applied to a mythical package `xyz` and mythical function `foo`:    

* `import xyz as x`.  This imports the package `xyz` under the abbreviation `x`.  A function `foo` in package `xyz` is then executed by typing `x.foo`.  This is the most common syntax and the one we'll use.  With Pandas, for example, the standard import statement is `import pandas as pd`.    

* `import xyz`.  This imports the whole thing as well, but here the command `foo` is executed with the more verbose `xyz.foo`.  

* `from xyz import *`.  This imports all the commands from the package `xyz`, but here the command `foo` is executed simply by typing `foo`.  We don't usually do this, because it opens up the possibility that the same command exists in more than one package, which is virtually guaranteed to create confusion.  If `foo` is the only command we care about, we can use `from xyz import foo` instead. 

The first version of `import` is the one we typically use.  We'll see these examples repeatedly:
```python 
import pandas as pd                  # data package
import matplotlib.pyplot as plt      # graphics package  
```
You might also go through earlier chapters and identify the `import` statements you find.  By convention, they are placed at the top of the program.  What packages or modules have we used?  What do they do?  


Some fine points:  

* What happens if we issue an import statement twice?  Answer:  Nothing, no harm done.  

* Jokes.  These are programmer jokes, which might be a contradiction in terms, but try them and see what happens:   
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

<!--
  (Obscure technical note.  The double underscore often shows up in Python for basic things like this. When we tried to track down the logic, we ran into [this explanation](http://stackoverflow.com/questions/1301346/the-meaning-of-a-single-and-a-double-underscore-before-an-object-name-in-python), which confused us thoroughly. But see also [this one](http://stackoverflow.com/questions/8689964/python-why-do-some-functions-have-underscores-before-and-after-the-functio).)
-->


**Exercise.**  Import Pandas.  What version do you have?  

**Exercise.**  What happens if we import Pandas twice under different names, once with `import pandas as pd` and once with `import pandas as pa`?  Write a short program that tests your conjecture.  (Hint: Use what have we done with Pandas so far.)  


## Data input 1:  reading internet files 

The easiest way to get data into a Python program is to read it from a file -- a spreadsheet file, for example.  The word "read" here means take what's in the file and somehow get it into Python.  Pandas can reads lots of kinds of files:  csv, xls, xlsx, and so on.  The files can be on our computer or on the internet.  We'll start with the internet -- there's less ambiguity about the location of the file -- but the same methods work with files on your computer.  

We prefer **csv files** ("comma separated values"), a standard data format for serious data people.  Their simple structure (entries separated by commas) allows easy and rapid input. They also avoid some of [the problems](http://www.win-vector.com/blog/2014/11/excel-spreadsheets-are-hard-to-get-right/) of translating Excel files.  If we have an Excel spreadsheet, we can always save it as a "CSV (Comma delimited) (*.csv)" file.  Excel will warn us that some features are incompatible with the csv format, but we're generally happy to do it anyway.  Here's an example of a [raw csv file](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/test.csv) (pretty basic, eh?) and this is (roughly) how it's displayed in [Excel](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv).  

Let's read a csv file from our GitHub repository.  We like to read data from internet sources, especially when the data is updated at automatically at the source for us.  That's not the case here, but we'll see how easy it is to get this kind of data into Python.  We read the cleverly-named `test.csv` with the `read_csv` function in Pandas:
```python 
import pandas as pd 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test.csv'
url  = url1 + url2        # location of file 
df = pd.read_csv(url)     # read file and assign it to df 
```
The syntax works like this:  

* `url` is a string that tells Python where to look for the file.  We break it in two because it's too long to fit on one line.  
* `read_csv` is a Pandas function that reads csv files.  The `pd.` before it tells Python it's a Pandas command; we established the `pd` abbreviation in the `import` statement.  
* The `df` on the left makes this an assignment:  we assign what we read to the variable `df`.  

[If the internet is down, or something else goes wrong, we can create the same dataframe from a dictionary:  
```python 
df = pd.DataFrame({'name': ['Dave', 'Chase', 'Spencer'], 
                   'x1': [1, 4, 5], 'x2': [2, 3, 6], 'x3': [3.5, 4.3, 7.8]}) 
```
The details aren't important, we'll do this only when we have to.] 


So what does our read statement give us?  What's in `df`?  We can check its contents by adding the statement `print('\n', df)`.  (The `'\n'` tells the print function to start printing on a new line.)  The result is 
```python
      name  x1  x2  x3
0     Dave   1   2   3
1    Chase   4   3   4
2  Spencer   5   6   7
```
What we have is a table, much like what we'd see in a spreadsheet.  If we compare it to the [source](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv) we see that the first column is new, added somehow by the program, but the others are just as they look online.   

The documentation for `read_csv` in the Object inspector gives us an overwhelming amount of information.  Starting at the bottom, we see that it returns a "dataframe."  More on that shortly.  We also see a long list of "parameters," extra inputs that change how we read the file.  We ignore them unless forced to do otherwise. 



**Exercise.**  Run the code 
```python 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test0.csv'    # note the added 0 
url  = url1 + url2
df = pd.read_csv(url)
```
What do you see?  

**Exercise.** Change the last line of the earlier code to 
```python
dfalt = pd.read_csv(url, nrows=2)
```
What does the argument `nrows=2` do?  


**Example.**  We can identify specific values in a csv file as missing or NA (not available).  We see in the documentation that the parameter na_values takes a list of strings as input.  To treat the number 1 as missing we change the read statement to `read_csv(url, na_values=[1])`.  The result is 
```python
      name  x1  x2   x3
0     Dave NaN   2  3.5
1    Chase   4   3  4.3
2  Spencer   5   6  7.8
```
We see that the number 1 that was formerly at the top of the `x1` column has been replaced by `NaN` -- "not a number."  


**Exercise.** Adapt the code to treat the numbers 1 and 6 as missing.  


We can also read Excel files (xls and xlsx) with Pandas:  use the `read_excel` function.  The code is almost identical: 
```python 
import pandas as pd 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test.xls'
url  = url1 + url2
dfx = pd.read_excel(url)
```
The files are constructed to have identical content.  


**Exercise.** Change the extension `.xls` to `.xlsx` and run the modified code.  What do you get?  



## Properties of dataframes 

Ok, so we read a file and assigned its contents to `df`.  But what is `df`?  What kinds of things can we do with it?  

We can start by finding its type:  use the handy `type()` function and enter `type(df)` in the IPython console.  It responds:  `pandas.core.frame.DataFrame`.  More simply, it's a **dataframe**.  A dataframe is another example of a data structure, like lists and dictionaries, that organize data in a specific way.  A dataframe has three components:  a table of data, column labels, and row labels.  It's the last two that make it distinctive.  

Typically in our data columns are variables and the column labels give us their names.  In our example, the second column has the name `x1` and it values follow below it.  The rows are then observations, and the row labels give us their names.  This is a standard setup and one we'll do our best to conform to.  If the data happen to come in some other form, we'll often convert it.  


**Columns and indexes.**  We can access the column and row labels directly.  For the dataframe `df` we read in earlier, we extract column labels with the method:  `df.columns`.  That gives us the verbose output `Index(['name', 'x1', 'x2', 'x3'], dtype='object')`.  We prefer to have them as a list, which we get by typing `list(df)` in the IPython console.  That gives us the column names as a list:  `['name', 'x1', 'x2', 'x3']`.  If we check the [source](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv), we see that the column labels come from the first row of the file.  


The row labels are referred to as the "index."  We extract them with the method:  `df.index`.  That gives us the verbose output `Int64Index([0, 1, 2], dtype='int64')`.  We can convert it to a list by adding another method, `df.index.tolist()`, which gives us `[0, 1, 2]`.  (Cool!  Two methods strung together!)  In this case, the index is not part of the original; Pandas inserted a counter.  As usual in Python, the counter starts at zero.  


**Exercise.** What does `df.columns.tolist()` do?  How does it compare to `list(df)`?  


<!-- 
**Exercise.** Run the code 
```python 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test.csv'
url  = url1 + url2
df0 = pd.read_csv(url, index_col=0)
```
What is the index in this case?  Can you explain why?  
-->
 

** Column data types.**  Pandas allows every variable (that is, column) to have a different data type, but the type must be the same within a column.  With our dataframe `df`, we get the types with `df.dtypes`:  
```python
name     object
x1        int64
x2        int64
x3      float64
```
Evidently `x1` and `x2` are integers and `x3` is a float.  They're no different from the types of numbers we can across in the previous chapter.  The first column, `name`, is something different.  Object is the name Pandas gives to things it can't turn into numbers -- strings, essentially.  Sometimes, as here, that makes sense:  names like `Dave` and `Spencer` are naturally strings.  But in many cases we've run across, numbers are given the dtype object because there was something in the data that didn't look like a number.  We'll see more of that later on.  


## Working with variables

One of the great things about Pandas is that we can do things with every observation of a variable in one line.  Suppose we want to refer to the varibale `x1`.  

what is this?
df['x1']

construct new variables
df['y1'] = df['x1']/df['x2']
df['y2'] = df['x2'] + df['x3']


## Dataframe methods 


One of the great things about dataframes is that they have lots of methods ready to go.  We'll survey some of the most useful ones.  


* head and tail 

* to_csv and to_excel


**Data output.** If reading is data input, then writing must be output, right?  The functions `write_csv()` and `write_excel()`.  Or we could use methods.  


**Clipboard methods.**  We can read from the clipboard and write to it.  
We're not fans of this, it makes replication hard, but it's awful convenient
and recommended by one of our former students.  `clip = pd.read_clipboard()`

**Setting the index.**

**Data summaries.**  

* mean, std, describe

**Plotting.** 
* plot, bar, hist, box 


**drop columns.** 
df.drop(df.columns[[1, 69]], axis=1, inplace=True) 



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



## Data input 3:  application program interfaces (APIs)

Warning:  subject to change...

This is a motuhful:  application program interface, or API.  What we mean is that some data sources allow access through something more complex than a spreadsheet.  The API is the set of rules for accessing the data.  That's the bad news, the jargon.  The good news is that people have written code to access the APIs that we can use.  And it's easy.  




FRED, World Bank...  etc.  They have API's, which give us better access than even a csv...  










## Data sources:  examples 

Want operator:  graph Greek debt over time, compare to other countries.  


**Example (Penn World Tables).**

What does the data look like?  



**Example (WEO).** 
```python 
url = 'http://www.imf.org/external/pubs/ft/weo/2014/01/weodata/WEOApr2014all.xls'
weo = pd.read_csv(url, sep='\t')    # tab = \t
```

Run the WEO code and list the contents.  What does the file look like?


**Example (PISA education data).**  

Check Susan Chen's notebook 



**Healthcare by location.**
http://www.nytimes.com/interactive/2015/12/18/upshot/19up-healthcosts.html
http://www.nytimes.com/interactive/2015/12/15/upshot/the-best-places-for-better-cheaper-health-care-arent-what-experts-thought.html


**Heart attack data.**
```python 
https://data.medicare.gov/api/views/c7us-v4mf/rows.csv?accessType=DOWNLOAD
https://data.medicare.gov/developers
"""
import pandas as pd
url = 'https://data.medicare.gov/api/views/c7us-v4mf/rows.csv'
df = pd.read_csv(url) 
```


**Example (IMDB).** 
Brandon Rhodes' movie data...  https://github.com/brandon-rhodes/pycon-pandas-tutorial

http://pages.stern.nyu.edu/~dbackus/csv/cast.csv
http://pages.stern.nyu.edu/~dbackus/csv/titles.csv
http://pages.stern.nyu.edu/~dbackus/csv/release_dates.csv 



**Example (movie ratings).** 
http://fivethirtyeight.com/features/fandango-movies-ratings/
https://github.com/fivethirtyeight/data/blob/master/fandango/fandango_score_comparison.csv

Do boxplot to compare, then histogram... 


**Example (Airbnb).** 

http://insideairbnb.com/get-the-data.html

<!--
**Example (Stern teaching data).** 


**Example.** Chetty's income data...  

**Example (Big Mac currency index).**  This is an xls file with multiple sheets.  
http://infographics.economist.com/2015/databank/BMfile2000-Jul2015.xls
 
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/27893 

Papers:  https://scholar.google.com/scholar?hl=en&q=fisman+speed+dating&btnG=&as_sdt=1%2C33
--> 


**Example (age distributions).**  UN data...     


<!--
**Example (Chipotle).** 

**Example (Reinhart-Rogoff).**

http://simplystatistics.org/2013/04/16/i-wish-economists-made-better-plots/ 


**Example (AirBNB).**

http://insideairbnb.com/get-the-data.html

**Example (mortality).** Causes from CDC...  


**Example (bond yields).**


**Example (speed dating).**  download tab delimited data and read it with `read_csv`. 

**Example.** Beer ratings...   
https://github.com/TomAugspurger/PyDataSeattle/blob/master/notebooks/3.%20Indexing.ipynb

--> 


## A taste of what's ahead 

set index 
transpose 

... 



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


## Appendix A:  Creating dataframes

We've generated dataframes with input statements.  Here are some examples that do it explicitly without reference to any external files.  Keep in mind the components of a dataframe:  a table of data, row labels, and column labels.  

**From lists.**  See above.  

**From dictionaries.** 


**From Numpy arrays.**  This is more than a little obscure, but it's often helpful in producing test cases to have a way to generate random numbers.  That's helpful when we want an example we can run without relying on an external data source.  Or if we want to get a sense of how randomness works.  

The Numpy package makes this easy.  (Take example from Quant Econ or documentation.)


## Appendix B:  Copying internet files 


**Example.** 


## Appendix C:  Unzipping files 


**Example.** 

