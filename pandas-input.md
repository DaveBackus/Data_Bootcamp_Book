# Data input: Packages and Pandas 

---
**Overview.**  We introduce "packages" -- collections of tools that extend Python's capabilities -- and explore one of them:  Pandas, the Python package devoted to data management.  We use Pandas to read spreadsheet data into Python and describe the "dataframe" this produces.  

**Python tools.**  Import, Pandas.  

**Buzzwords.**  Package, csv file, dataframe, series, index.  

**Applications.**  ??? 

**Code.**  [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_pandas_1.py).  

---

<!--
**UNDER CONSTRUCTION**
-->

We're ready now to look at some data.  Lots of data.  

You may recall that our typical program consists of data input, data management, and graphics.  We'll spend most of our time here on the first -- data input -- but touch briefly on the second and third.  More concretely, we explain how to get spreadsheet data into Python.  Along the way we describe how Python uses collections of tools or plug-ins (**packages**) to address a wide range of applications:  data management (**Pandas**), graphics (Matplotlib), and many other things.  


## Reminders

* Methods and objects.  Recall that we apply the method `justdoit` to the object `x` with `x.justdoit`.  A common example is the `plot()` method, which works for a wide range of data objects.   

* Help.  We get help in Spyder from both the IPython console and the Object inspector.  For the hypothetical `x.plot()`, we would type `x.plot?` in the IPython console or `x.plot` in the Object inspector.  

* Data structures.  That's the term we use for specific organizations of data.  Examples are strings, lists, and dictionaries. Each has a specific structure and a set of methods we can apply.  List are collections of objects between square brackets:  `numberlist = [1, -5, 2]`.  Dictionaries are pairs of items between curly brackets:  `namedict = {'Dave': 'Backus', 'Chase': 'Coleman'}`. The first item in each pair is the "key," the second is the "value."  

* ?? more? 


## Python packages

Python is not just a programming language, it's an open source collection of tools that includes both core Python and a large collection of packages written by different people.  The word "package" here refers to plug-ins or extensions that expand Python's capabilities.  Terminology varies.  What we call a package others sometimes call a "library."  The term "module" typically refers to a subset of core Python or one of its packages.  You won't go far wrong to use the terms interchangeably.  

The standard Python packages are well written, well documented, and well supported.  They have armies of users who spot and correct problems.  Some of the others less so.  We try to stick to the standard packages, specifically those that come with the Anaconda distribution.  

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

Here are some examples applied to a mythical package `xyz` and mythical function `foo`:    

* `import xyz as x`.  This imports the package `xyz` under the abbreviation `x`.  A function `foo` in package `xyz` is then executed by typing `x.foo`.  This is the most common syntax and the one we'll use.  With Pandas, for example, the standard import statement is `import pandas as pd`.    

* `import xyz`.  This imports the whole thing as well, but here the function `foo` is executed with the more verbose `xyz.foo`.  

* `from xyz import *`.  This imports all the functions and methods from the package `xyz`, but here the function `foo` is executed simply by typing `foo`.  We don't usually do this, because it opens up the possibility that the same function exists in more than one package, which is virtually guaranteed to create confusion.  If `foo` is the only function we care about, we can use `from xyz import foo` instead. 

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


**Exercise.**  Import Pandas.  What version do you have?  

**Exercise.**  What happens if we import Pandas twice under different names, once with `import pandas as pd` and once with `import pandas as pa`?  Write a short program that tests your conjecture.  (Hint: Use what have we done with Pandas so far.)  


## Data input 1:  reading internet files 

The easiest way to get data into a Python program is to read it from a file -- a spreadsheet file, for example.  The word "read" here means take what's in the file and somehow get it into Python.  Pandas can reads lots of kinds of files:  csv, xls, xlsx, and so on.  The files can be on our computer or on the internet.  We'll start with the internet -- there's less ambiguity about the location of the file -- but the same methods work with files on your computer.  


We prefer **csv files** ("comma separated values"), a common data format for serious data people.  Their simple structure (entries separated by commas) allows easy and rapid input. They also avoid some of [the problems](http://www.win-vector.com/blog/2014/11/excel-spreadsheets-are-hard-to-get-right/) of translating Excel files.  If we have an Excel spreadsheet, we can always save it as a "CSV (Comma delimited) (*.csv)" file.  Excel will warn us that some features are incompatible with the csv format, but we're generally happy to do it anyway.  Here's an example of a [raw csv file](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/test.csv) (pretty basic, eh?) and this is (roughly) how it's displayed in [Excel](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv).  


It's easy to read csv files with Pandas.  We'll read one from our GitHub repository to show how this works. We like to read data from internet sources like this, especially when the data is updated at automatically at the source.  That's not the case here, but we'll see how easy it is to get this kind of data into Python.  We read the cleverly-named `test.csv` with the equally clever `read_csv` function in Pandas:
```python 
import pandas as pd 
url1 = 'https://raw.githubusercontent.com/DaveBackus'
url2 = '/Data_Bootcamp/master/Code/Python/test.csv'
url  = url1 + url2        # location of file 
df = pd.read_csv(url)     # read file and assign it to df 
```
The syntax works like this:  

* `url` is a string that tells Python where to look for the file.  We break it in two because it's too long to fit on one line.  
* `read_csv` is a Pandas function that reads csv files.  The `pd.` before it tells Python it's a Pandas function; we established the `pd` abbreviation in the `import` statement.  
* The `df` on the left makes this an assignment:  we assign what we read to the variable `df`.  

[If the internet is down, or something else goes wrong, we can create the same dataframe from a dictionary:  
```python 
df = pd.DataFrame({'name': ['Dave', 'Chase', 'Spencer'], 
                   'x1': [1, 4, 5], 'x2': [2, 3, 6], 'x3': [3.5, 4.3, 7.8]}) 
```
The details aren't important, we'll do this only when we have to.] 


So what does our read statement give us?  What's in `df`?  We can check its contents by adding the statement `print('\n', df)`.  (The `'\n'` tells the print function to start printing on a new line, which makes the output look better.)  The result is 
```python
      name  x1  x2  x3
0     Dave   1   2   3
1    Chase   4   3   4
2  Spencer   5   6   7
```
What we have is a table, much like what we'd see in a spreadsheet.  If we compare it to the [source](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv) we see that the first column is new, added somehow by the program, but the others are just as they look online.   

The documentation for `read_csv` in the Object inspector gives us an overwhelming amount of information.  Starting at the bottom, we see that it returns a "dataframe."  More on that shortly.  We also see a long list of optional inputs that change how we read the file.  We ignore them unless forced to do otherwise. 


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


**Exercise.** Change the file extension from `.xls` to `.xlsx` and run the modified code.  What do you get?  


## Properties of dataframes 

Ok, so we read a file and assigned its contents to `df`.  But what is `df`?  What kinds of things can we do with it?  

We can start by finding its type:  Use the handy `type()` function and enter `type(df)` in the IPython console.  It responds:  `pandas.core.frame.DataFrame`.  More simply, it's a **dataframe**.  A dataframe is another example of a data structure, like a list or a dictionary, that organizes data in a specific way.  A dataframe has three components:  a table of data, column labels, and row labels.  

Typically columns are variables and the column labels give us their names.  In our example, the second column has the name `x1` and its values follow below it.  The rows are then observations, and the row labels give us their names.  This is a standard setup and we'll do our best to conform to it.  If the data come in some other form, we'll try to convert it.  


**Dimensions.** We access a dataframe's dimensions -- the numbers of rows and columns -- with the `shape` method:  `df.shape`.  Here the answer is `(3,5)`, so we have 3 rows (observations) and 5 columns (variables).  


**Columns and indexes.**  We access the column and row labels directly.  For the dataframe `df` we read in earlier, we extract column labels with the `columns` method:  `df.columns`.  That gives us the verbose output `Index(['name', 'x1', 'x2', 'x3'], dtype='object')`.  We prefer to have them as a list, which we get by typing `list(df)` in the IPython console.  That gives us the column names as a list:  `['name', 'x1', 'x2', 'x3']`.  If we check the [source](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/Python/test.csv), we see that the column labels come from the first row of the file.  


The row labels are referred to as the **index**.  We extract them with the `index` method:  `df.index`.  That gives us the verbose output `Int64Index([0, 1, 2], dtype='int64')`.  We can convert it to a list by adding another method, `df.index.tolist()`, which gives us `[0, 1, 2]`.  (Cool! Two methods strung together!)  In this case, the index is not part of the original file; Pandas inserted a counter.  As usual in Python, the counter starts at zero.  


**Exercise.** What does `df.columns.tolist()` do?  How does it compare to `list(df)`?  


**Transpose columns and rows.** If we want to rotate the dataframe, exchanging columns and rows, we use the `transpose` method:  `df.transpose` or (more succinctly) `df.T`.  Here's an example:  
```python
dft = df.T
print('\n', dft)
```
The result is 
```
         0      1        2
name  Dave  Chase  Spencer
x1       1      4        5
x2       2      3        6
x3     3.5    4.3      7.8
```
In this case it doesn't make much sense, but in others we'll find it helpful.  

**Column data types.**  Pandas allows every column (typically a variable) to have a different data type, but the type must be the same within a column.  With our dataframe `df`, we get the types with the `dtypes` method; that is, with `df.dtypes`:
```python
name     object
x1        int64
x2        int64
x3      float64
```
Evidently `x1` and `x2` are integers and `x3` is a float.  They're no different from the types of numbers we can across in the previous chapter.  The first column, `name`, is different.  Object is the name Pandas gives to things it can't turn into numbers -- strings, essentially.  Sometimes, as here, that makes sense:  names like `Dave` and `Spencer` are naturally strings.  But in many cases we've run across, numbers are given the dtype object because there was something in the data that didn't look like a number.  We'll see more of that later on.  


## Working with variables

One of the great things about Pandas is that we can do things with every observation of a variable in one statement.  

**Variables = series.**  If we want to refer to the variable `x1`, we write `df['x1']`.  (We can also use `df.x1`, but that runs into problems if `x1` is an existing method.  We won't do it.)  If we ask what type this is, with 
```python
print(type(df['x1']))
```
we find that it's a `pandas.core.series.Series` -- or "series" for short.  A series is simply a dataframe with a single variable, which simplifies the bookkeeping a bit.  


**Constructing new variables from old ones.** Now that we know how to refer to a variable, we can construct others from them.  We construct two with 
```python 
df['y1'] = df['x1']/df['x2']
df['y2'] = df['x2'] + df['x3']
```
The first line computes the new variable `y1` as the ratio of `x1` to `x2`.  The second computes `y2` as the sum of `x2` and `x3`.  

The dataframe now includes both of these variables.  The statement `print('\n', df)` gives us 
```python 
       name  x1  x2   x3        y1    y2
0     Dave   1   2  3.5  0.500000   5.5
1    Chase   4   3  4.3  1.333333   7.3
2  Spencer   5   6  7.8  0.833333  13.8
```

## Dataframe methods 


One of the great things about dataframes is that they have lots of methods ready to go.  We'll survey some of the most useful ones at high speed and come back to them when we have more interestng data.  

**Data output.** If reading is data input, then writing must be output, right?  The functions `write_csv()` and `write_excel()` produce csv and Excel files, respectively.  Or we could use the methods `df.to_csv()` and `df.to_excel()` to do the same thing.  We'll hold off on them until we've addressed files on our computer.  


**Clipboard methods.**  We can read from the clipboard and write to it.  Suppose we open a spreadsheet and copy a section of it into the clipboard.  We can paste it into a dataframe with the statement
```python
df_clip = pd.read_clipboard()`
```
We're not fans of this, it makes replication hard if we need to do this again, but it's awful convenient.  We heard about it from one of our former students.  


**Setting the index.**  We're not stuck with the index in our dataframe, we can make it whatever we want.  If we want to use `name` as the index, associating observations with the `name` variable, we use the `set_index()` method:  
```python
df = df.set_index(['name']) 
```
That gives us 
```python
         x1  x2   x3        y1    y2
name                                
Dave      1   2  3.5  0.500000   5.5
Chase     4   3  4.3  1.333333   7.3
Spencer   5   6  7.8  0.833333  13.8
```
with `name` now used as the index.  

We did something else here that's important:  We assigned the result back to `df`.  That keeps what we've done in the dataframe `df`.  Without this, `df` would remain unchanged with a counter as its index.  


**Exercise.** Set `name` as the index as just described.  Use the `index` method to extract it and verify that `name` is, in fact, the index.  

**Exercise.**  Apply the `reset_index()` method to our new dataframe.  What does it do?  What is the index of the new dataframe?  


**Statistics.**  We can compute the mean, the standard deviation, and other statistics for all the variables at once with 
```python
df.mean()
df.std()
df.describe()
```
The first line gives us the means, the second the standard deviations.  The third line gives us a collection of statistics, including the mean, the standard deviation, the min, and the max.  


**Exercise.** The statement `print(df.mean())` gives us the means of each variable in a column.  How would we produce the same output as a row? 

**Exercise.** What kind of object does `df.mean()` produce?  


**Plotting.**  We have a number of plot methods avaialble.  The most basic is simply `.plot()`, which plots all of the variables against the index.  Try this and see what it looks like:  
```python
df.plot()
```
You should see lines for each of the variables plotted against the index `name`.  


**Exercise.**  Produce a bar chart of the same data with the statement 
```python
df.plot(kind='bar')
```
What happens if you change `bar` to `barh`?  


**Rename or delete variables.**  Suppose we want to give `x1` the more intuitive name `sales`.  We can do that with the statement 
```python 
df.rename(columns={'x1': 'sales'})
```
Note the use of a dictionary that associates the "key" `x1` with the "value" `sales`.  

If we want to delete `x1` instead, we use the `drop` method:  
```python
df.drop(['x1'], axis=1)
```
This method will drop either observations (`index=0`) or variables (`axis=1`).  


**Exercise.** Drop the initial observation from `df`, the one with the index `'Dave'`.    

<!-- df.drop(['Dave'], axis=0) --> 


**The top and bottom of a dataframe.** We commonly work with much larger dataframes in which it's unwieldy, and perhaps impossible, to print the whole thing.  So we often look at either the top or bottom:  the first few few or last few observations.  The statement `df.head(n)` extracts the top `n` observations.  If we use `df.head()` it extracts 5 observations.  This creates a new dataframe, as we can see here:  
```python
h = df.head(2)
print(type(h))
print(h)
```
The second print statement gives us the first 2 observations, which is what we requested.  


`df.tail(2)` does the same for the bottom of the dataframe `df`:  the last 2 observations.  


## Data input 2:  reading files from your computer 


Next up:  reading spreadsheet files in Python from your computer's hard drive.  This is really useful, but there's a catch:  we need to tell Python where to find the file.  That's a small thing in principle, but a tricky one in practice.  It's not a Python problem, really, but it's one we need to address. 


**Prepare test data.**  We start with the easy part.  Open a blank spreadsheet in Excel and enter the data:  
```python
name    x1  x2  x3
Dave     1   2   3
Chase    4   3   4
Spencer  5   6   7
```
That is:  four rows with four entries in each one.  

Now save the contents in your `Data_Bootcamp` directory.  Do this three times in different formats:

* Excel file.  Save the file as `test.xlsx`.  
* Old-style Excel file.  Save as an "Excel 97-2003 (*.xls)" file under the name `test.xls`.   
* CSV file.  Save as a "CSV (Comma delimited) (*.csv)" file under the name `test.csv`.   

Each of these options show up in Excel when we choose "Save As." 


**HELP!!**


**Find the file.**  Ok, now where is the file?  We know, it's in the `Data_Bootcamp` directory, but where is that?  We need the complete path so we can tell Python where to find it.   

Let's introduce some terms so we can be clear what we're talking about.  The "file name" is something like `test.csv`.  The format of the "directory" or folder address depends on the operating system.  On a Windows computer, it's something like  
```python
C:\Users\userid\Documents\Data_Bootcamp 
```
On a Mac, it looks like 
```python 
/Users/userid/Data_Bootcamp  
```
The complete (or full or absolute) "path" is a combination of the two, with a slash in between.  In Windows:  
```python 
C:\Users\userid\Documents\Data_Bootcamp\test.csv
```
In Mac OS:  
```python 
/Users/userid/Data_Bootcamp/test.csv 
```
Note that they use different kinds of slashes.    


How did we find these addresses or paths?  

* Windows.  In thw Windows ??
* Mac OS.  We select (but not open) the file and do "command-i" to get the file's information window.  From the window, we copy the path that follows "Where:."  It looks like we're copying arrows, but they turn into slashes when we paste the path.  


**Reading data with the complete path.**  Once we have the complete path, we simply tell Python to read the file at that location.  Again, this varies with the operating system.  

* In Windows, we take the complete path and -- **this is important** -- change all the backslashes `\` to double backslashes `\\`.  Then we read the file from the path, just as we read it from a url earlier:
```python
path = 'C:\\Users\\userid\\Documents\\Data_Bootcamp\\test.csv'
df = read_csv(path)
```

* In Mac OS we don't need to change the slashes: 
```python
path = '/Users/userid/Data_Bootcamp/test.csv'
df = read_csv(path)
```

Try the appropriate one on your computer to make sure it works.  Let us know if it doesn't.  


**Reading from the current working directory.** An alternative is to set the current working directory (cwd).  How we do that depends on our environment, which is why we prefer the other approach:  It works in all environments.  In Spyder, the path of the cwd is in a textbox at the top on the right side.  (Take a look, make sure you can find it.)  If the cwd is where our data file is, skip the next part.  If not, we can reset it in two steps:  

* Find the folder icon to the right of the cwd textbox.  We know we have the right one if a text bubble pops up that says "Browse a working directory".  Click on the icon and navigate to the folder/directory that contains our data file, namely `Data_Bootcamp`.  Then click on "Select Folder" to choose it.  

* Next we click on the red arrow to the right of the folder icon, the one with the text bubble that says "Set as current console's working directory".  That should set the cwd to `Data_Bootcamp`. 

Once this is done, we can read the file with 
```python
file = 'test.csv'
df = read_csv(file)
```
If this doesn't work, go back to the complete path.  


**Request for help.**  If you have difficulty, or find that this works differently on your computer, let us know.  




## Data input:  examples 

Here are some spreadsheet datasets we've found interesting.  In each one, we descibe the data using the `shape`, `columns`, and `head` methods.  Where it makes sense, we also produce a simple plot.  


**Penn World Table.**  The [PWT](http://www.rug.nl/research/ggdc/data/pwt/?lang=en), as we call it, is a standard database for comparing the incomes of countries.  It includes annual data for GDP, GDP per person, employment, hours worked, capital, and many other things.  The variables are measured on a comparable basis, with GDP measured in  2005 US dollars.  

The data is in an [Excel spreadsheet](http://www.rug.nl/research/ggdc/data/pwt/v81/pwt81.xlsx).  If we open it, we see that it has three sheets.  The third one is the data and is named `Data`.  We read it in with the code:  
```python
import pandas as pd 
url = 'http://www.rug.nl/research/ggdc/data/pwt/v81/pwt81.xlsx'
pwt = pd.read_excel(url, sheetname='Data')
```
So what does that give us?  

* `pwt.shape` returns `(10357, 47)`:  the dataframe `pwt` contains 10,357 observations of 47 variables.  
* `list(pwt)` gives us the variable names, which include `countrycode`, `country`, `year`, `rgdpo` (real GDP), and `population`.  
* `pwt.head()` shows us the first 5 observations, which refer to Angola for the years 1950 to 1954.  If we look further down, we see that countries are stacked on top of each other in roughly alphabetical order.  

The data are in our standard format:  Each column is a variable, each row is an observation.  But if we were to plot one of the variables, it wouldn't make much sense.  The observations string together countries, one after the other.  What we'd like to do is compare countries, which this isn't set up to do -- yet.  

**Exercise.** Change the input in the last line of code to `sheetname=2`.  Why does this work?  


**Example (WEO).**  Another good source of macroeconomic data for countries is the IMF's World Economic Outlook or WEO.  It comes out twice a year and includes annual data from 1980 to roughly 5 years in the future (forecats, evidently).  It includes the usual GDP, but also government debt and deficits, interest rates, and exchange rates.  

This one gives us some idea of the challanges we face dealing with what looks like ordinary spreadsheet data.  The file extension is `xls`, which suggests it's an Excel lspreadsheet, but in fact it's a tab-delimited file.  Essentially a csv, but with tabs rather than commas separating entries.  We read it in with 
```python 
import pandas as pd
url = 'https://www.imf.org/external/pubs/ft/weo/2015/02/weodata/WEOOct2015all.xls'
weo = pd.read_csv(url, sep='\t')    # tab = \t
```

**Exercise.** How big is the dataframe `weo`?  What variables does it include?  Use the statement `weo[[0, 1, 2, 3, 4]].head()` to see what the first five columns contain.  

Like the PWT, this dataset doesn't come in the standard format, with columns as variables and rows as observations.  Instead, each row contains observations for all years for some variable and country combination.  If we want to work with it, we'll have to change the structure.  


**PISA education data.**  PISA stands for [Program for International Student Assessment](http://www.oecd.org/pisa/).  It's an international effort to collect information about educational performance that's comparable across countries.  We read about it every few years when newspapers print stories about how poorly American students are doing.  PISA collects data on student performance, teacher quality, and many other things, and post both summaries and individual data.  

We use data from a summary table in an [OECD report](http://www.oecd.org/pisa/keyfindings/pisa-2012-results-volume-I.pdf); note the data link at the bottom of Table 1.A.  This codes reads the data from the link:  
```python 
import pandas as pd
url = 'http://dx.doi.org/10.1787/888932937035'
pisa = pd.read_excel(url, 
                     skiprows=18,       # skip the first 18 rows 
                     skipfooter=7,      # skip the last 7 
                     parse_cols=[0,1,9,13],   # select columns of interest 
                     index_col=0,       # set the index as the first column
                     header=[0,1]       # set the variable names 
                     )
pisa = pisa.dropna()                    # drop blank lines 
pisa.columns = ['Math', 'Reading', 'Science']   # simplify variable names 
```
There are a number of new things in the read statement:  

* We've spread the read statement over several lines to make it easier to read.  Python understands that the line doesn't end until we reach the right paren ).  That's common Python syntax.  
* We skip rows at the top and bottom that do not contain data.  
* We set the index and column labels.  

We can clean this up further if we drop blank lines and simplify the variable names:  
```python 
pisa = pisa.dropna()                    # drop blank lines 
pisa.columns = ['Math', 'Reading', 'Science']   # simplify variable names 
pisa['Math'].plot(kind='barh')
```
The plot at the bottom is virtually impossible to read, but we'll work on that later.  


**Incomes by college major.** Nate Silver's outfit, the [538 blog](http://fivethirtyeight.com/), does a lot of good data journalism and often posts its data online.  This one comes from their analysis of [income by college major](http://fivethirtyeight.com/features/the-economic-guide-to-picking-a-college-major/).  The data comes from the American Community Survey but they've done the work of organizinfg it for us.  

Here's the code:  
```python
url1 = 'https://raw.githubusercontent.com/fivethirtyeight/data/master/'
url2 = 'college-majors/recent-grads.csv'
url = url1 + url2
df538 = pd.read_csv(url)
```

**Exercise.** What variables does this data contain?  

**Exercise.** Set the index as `Major`.  (Ask yourself:  What method should I use?)  

**Exercise.** Create a horizontal bar chart using the `plot()` method.  


**Internet Movie Database (IMDb).**  We love this one, a list of roles in IMDb's movie database that we got from [Brandon Rhodes](https://github.com/brandon-rhodes/pycon-pandas-tutorial).  We read it with this code:  
```python
url  = 'http://pages.stern.nyu.edu/~dbackus/csv/cast.csv'
cast = pd.read_csv(url, encoding='utf-8')
```
Don't panic if nothing happens, this takes a couple minutes.  

**Exercise.** Since we're all experts by now, we'll leave this one to you:  

* How large is the dataframe?  
* What variables does it include?   
* Try these statements:     
```python
ah = cast[cast['title']=='Annie Hall']
gc = cast[cast['name']=='George Clooney']
```
This goes beyond what we've done so far, but what do you think they do?  What do the dataframes `ah` and `gc` contain?  

<!-- 
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


**Example (Airbnb).** Chase likes this one.  Someone posted a bunch of Airbnb data online.  

http://insideairbnb.com/get-the-data.html

--> 

<!--
**Example (Stern teaching data).** 


**Example.** Chetty's income data...  

**Example (Big Mac currency index).**  This is an xls file with multiple sheets.  
http://infographics.economist.com/2015/databank/BMfile2000-Jul2015.xls
 
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/27893 

Papers:  https://scholar.google.com/scholar?hl=en&q=fisman+speed+dating&btnG=&as_sdt=1%2C33
--> 

<!--
**UN population projections by age**  We tend to have pretty good demographic data:  counts of people, their ages, how many children they have, what they die of, and so on.  A good international source is the [United Nations' Population Division](http://esa.un.org/unpd/wpp/Download/Standard/Population/).  

This code reads in estimates of past and projections of future population by age for many countries:\
--> 


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


## Data input 3:  APIs


APIs are application program interfaces.  That's a mouthful.  A dataset with an API allows access through some method other than a spreadsheet.  The API is the set of rules for accessing the data.  The bad news is the jargon.  The good news is that people have written code to access the APIs.  And it's easy to use, which is the point.  

Pandas has what they call a set of [remote data access tools](http://pandas.pydata.org/pandas-docs/stable/remote_data.html).  They break now and then, tupically when the underlying data changes, but when they work they're great.  This part of Pandas is undergoing a transition (see the link), but for now this is how it works.  


**FRED.** The St Louis Fed has put together a large collection of time series data that they refer to as [FRED](https://research.stlouisfed.org/fred2/):  Federal Reserve Economic Data.  They started with the US, but now include data for many countries.  

The Pandas [Remote Data Access docs](http://pandas.pydata.org/pandas-docs/stable/remote_data.html) describe how to access FRED with Pandas.  Here's an example that reads in quarterly data for US real GDP and real consumption and produces a simply plot: 
```python
import pandas as pd 
import pandas.io.data as web    # package to access FRED 
import datetime                 # package to handle dates 

start = datetime.datetime(2010, 1, 1)
codes = ['GDPC1', 'PCECC96']    # real GDP, real consumption 
fred  = web.DataReader(codes, 'fred', start) 
fred = fred/1000                # convert billions to trillions

fred.plot()
```
The graph is a little clunky, but we'll show how to fix it up next week.  


**World Bank.** The World Bank's data covers economics and social statistics for most countries in the world.  Variables include GDP, population, education, and infrastructure.  Here's an example:  
```python
import pandas as pd                 
from pandas.io import wb            # World Bank api

var = ['NY.GDP.PCAP.PP.KD']         # GDP per capita 
iso = ['USA', 'FRA', 'JPN', 'CHN', 'IND', 'BRA', 'MEX']  # country codes 
year = 2013
wb = wb.download(indicator=var, country=iso, start=year, end=year)
```
If we look at the dataframe `wb`, we see that it has a double index, `country` and `year`.  By design, all of the data is for 2013, so we kill off that index with the `reset_index` method and plot what's left as a horizontal bar chart:  
```python
wb = wb.reset_index(level='year', drop=True)
wb.plot(kind='barh') 
```

These are worth thinking about, but do not have clear answers:  

**Exercise.** What would you like to change in this graph?  Keep a list for next time we run into this one.  

**Exercise.** This data is similar to the PWT, in the sense that we have observations for dates and countries.  In the PWT, 


**Fama-French.**  Gene Fama and Ken French post lots of data on equity returns on [Ken French’s website](http://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html).  The data are zipped text files, which we can easily read into Excel.  The Pandas tool is even better.  Here's an example:  
```python
import pandas.io.data as web

ff = web.DataReader('F-F_Research_Data_factors', 'famafrench')[0]
ff.columns = ['xsm', 'smb', 'hml', 'rf']      # rename variables 

ff.describe()
```
The data is monthly, 1926 to present.  Returns are expressed as percentages; multiply by 12 to get a rough approximation of an annual return.  The returns refer to

* xsm:  the return on the market minus the riskfree return
* smb:  the return on small firms minus the return on big firms 
* hml:  the return on value firms minus the return on growth firms 
* rf:  the riskfree rate 

We use the `describe()` method to compute statistics.  Evidently `xsm` has the largest mean.  It also has the largest standard deviation.  A couple plot methods show us more about the distribution:  
```python 
ff.plot()
ff.boxplot()
```
What do you see?  


## Resources 

See also our list of common [data sources](http://databootcamp.nyuecon.com/bootcamp_data/).


<!-- 
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

--> 

<!--
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
-->