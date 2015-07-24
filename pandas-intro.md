
# Working with data 

---
**Overview.** 


**Python tools.**  Importing packages, reading csv and xls files into Pandas.  


**Buzzwords.**  


**Applications.**  GDP ??

---

Ok, let's look at some data, see what we can make of it.  


Along the way we describe how Python uses collections of tools (**packages**) to address a wide range of applications:  graphics (Matplotlib), data management (Pandas), and many other things.  


## Reminders 

Methods... ??


## Python packages

Python is not just a program, it's an open source collection of tools that includes both basic Python and a large collection of packages written by different people.  The terminology varies.  What we call a package others sometimes call a **library**.  The term **module** typically refers to a subset of basic Python or a package.  

The standard packages -- which we'll talk more about in a minute -- are well written, well documented, and have armies of users who spot and correct problems.  Some of the others less so.  Our suggestion is to stick to the mainstream packages, specifically those in the Anaconda distribution, until you're reasonably comfortable with Python.

Some of the leading mainstream packages for numerical ("scientific") computation  are

* **[Matplotlib](http://matplotlib.org/).** The leading graphics package for Python and our focus in this chapter.

* **[NumPy](http://www.numpy.org/).**  Tools for numerical computing, including linear algebra. Compare this to Excel, where the basic unit is a cell, a single number.  In NumPy the basic unit is a vector (a column) or matrix (a table or worksheet).  In this respect, it's a direct competitor to Matlab.  We won't see much of NumPy here -- maybe a little -- but it's the foundation for Pandas, which we'll use constantly.   

* **[Pandas](http://pandas.pydata.org/).**  The leading package for managing and manipulating data.  The basic unit is a DataFrame, which is a table of data (like a worksheet) with labels for observations and variables.  If you've used R, you'll be familiar with the idea.  If not, you'll be familiar with it in the near future.  

All of these packages come with the [Anaconda distribution](http://docs.continuum.io/anaconda/pkg-docs.html).  We'll use all of them a bit, and Matplotlib and Pandas constantly.  

Here are some others you might run across:  

* **[Seaborn](http://stanford.edu/~mwaskom/software/seaborn/).** A "wrapper" (isn't that a great term?)for Matp[lotlib that makes it easier to use.  

* **[Statsmodels](https://pypi.python.org/pypi/statsmodels).**  The basic statistics package. 

* **[Scikit-learn](http://scikit-learn.org/stable/).** A machine learning, which is essentially the name computer scientists give to statistics.  CS people have done some cool things; they're also really good at naming things (visualization, machine learning).  

* **[NLTK](http://www.nltk.org/).**  The so-called Natural Language Toolkit processes text.  Here "natural language" means "words."  Investors, for example, might process the words used in financial reports to detect the mood or sentiment.  One of our students is using NLTK to analyze tweets.  The big-picture idea is that data can be anything, not just numbers.   

* **[Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/)** and **[Scrapy](http://scrapy.org/).**  Extract ("scrape") data from web sites.  

* **[Django](https://www.djangoproject.com/).**  A popular tool for website development.  

We won't use them, but they're in Anaconda, too.  Feel free to give them a try.  If you do, please report back on your experience.  


## Importing packages 

In Python -- and many other languages -- we need to tell our program which packages we plan to use.  We do that with the `import` command.  

Here are some examples applied to a mythical package `xyz` and mythical command `foo`:    

* `from xyz import *`.  This imports all the commands from the package `xyz`.  A command `foo` is then executed by typing `foo`.  We don't usually do this, because it opens up the possibility that the same command exists in more than one package, which is virtually guaranteed to give us confusing output.  If `foo` is the only command we care about, we can use `from xyz import foo` instead.    

* `import xyz`.  This imports the whole thing as well, but the language or syntax changes.  Here the command `foo` is executed by adding `xyz.` (note the period) before it:  `xyz.foo`.

* `import xyz as x`.  This is the most common syntax.  It allows the shorthand `x.foo`, which saves us the effort of typing ``xyz`.  Many packages have standard abbreviations.  We use them ourselves and recommend the same, it makes code clearer to others.   


The last version of `import` is the one we typically use.  We'll see these examples repeatedly:
```
import pandas as pd
import matplotlib as mpl ??
```
You might also go through earlier examples and identify the `import` statements you find.  By convention, they are placed at the top of the program.  What packages or modules have we used?  What do they do?  


Some fine points:  

* What happens if we issue an import statement twuice?  No problem, no harm is done.  

* Jokes.  These are programmers jokes, which might be a contradiction in terms, but try these and see what happens:   
  ```
  import this
  import antigravity 
  ```


* We can check the version number of a packages with the `__version__` method.  For example, to check the version of Pandas, we can use 
  ```
  import pandas as pd 
  print('Pandas version ', pd.__version__)   	# these are double underscores 
  ```
  this is frequently helpful if a program once worked and now doesn't.  Perhaps something changed between versions.  Stack Overflow typically asks for the version number and your operating system when you post a question.  


**Exercise.** Suppose we import Pandas twice under different names, once as `import pandas as pd` and once as `import pandas as pa`.  What do you think happens?  Can you write a short program that checks?  (This will take a little thought, feel free to consult your neighbor.)


## Reading data into Python 1


We'll talk more about packages later, but for now just put these lines above...

```
import pandas as pd
```

We'll talk more later about how to import packages that extend Python's capabilities.  Pandas is the data management package... as [they say](http://pandas.pydata.org/):  "open source library for high-performance, easy-to-use data structures and data analysis tools in Python."




**Reading csv files.**
We've found that csv files
are the most useful common data format, far better than xls or xlsx.
Its simple structure (entries separated by commas, tabs, or spaces) allows easy and rapid input.
That's a general statement, not a statement about Python.`

Suppose you have (as we do) a csv file you'd like to input into Python.
We can read it with the ``read_csv`` command in pandas:

```
import pandas as pd
file = 'test1.csv'
df = pd.read_csv(file)
```

This reads the file {\tt test1.csv} into {\tt df}.
If you try {\tt type(df)} you'll find that {\tt df} is a DataFrame,
the standard object type in pandas.
It's a table of numbers, much like a sheet in a spreadsheet program,
with labels for rows (the index) and columns (the variables).  

What do we get?  Try type.  DataFrame!  What's that?  A table of numbers with labels for rows and columns.  

df.head()
df.tail()

These are dfs too.  head = df.head()...  


## Spreadsheet and csv files 

http://www.win-vector.com/blog/2012/12/please-stop-using-excel-like-formats-to-exchange-data/
http://www.win-vector.com/blog/2014/11/excel-spreadsheets-are-hard-to-get-right/ 


## Data frames 

Some of the methods you could try:
{\tt df.columns} (the column labels),
{\tt df.columns.tolist()} (the column labels as a list),
{\tt df.index} (the row labels),
{\tt df.head(2)} (the top two rows),
{\tt df.tail()} (the bottom five rows), 
{\tt df.tail(2)} (the bottom two rows),
{\tt df.describe()} (summary statistics),
and {\tt df.info()} (information about the form of the data).
There are only three rows in this one, so you could simply
print the whole thing, but with large data sets this is very useful.

{\bf Comment.}
The tricky part of this is setting the working directory,
where Python looks for things.
More on this another time.

%[??  Check to see if file is there ??]

\item ?? mention {read table}

\item Reading csv's from url's.
Even better, {\tt read\_csv} also reads from url's.
The same file is in our GitHub repository (talk about how to find it,
and the Raw button).
We can read it with
\begin{verbatim}
import pandas as pd     # this is redundant if we've already imported it
url1 = 'https://raw.githubusercontent.com/DaveBackus/'
url2 = 'Data_Bootcamp/master/Code/Data/test1.csv'
url = url1 + url2
df = pd.read_csv(url)
\end{verbatim}
Or we could read the World Economic Outlook (WEO) database from the IMF.
This reads in the whole thing:
\begin{verbatim}
url = 'http://www.imf.org/external/pubs/ft/weo/2014/01/weodata/WEOApr2014all.xls'
weo = pd.read_csv(url, sep='\t')    # tab = \t
\end{verbatim}
%{\bf Exercise.}
Try this and list the contents.
What does the file look like?

\item Spreadsheets.  They have a more complex structure and the possibility
of more than one sheet.
Most programmers avoid these files when they can:  they create technical problems
that are hard to predict.
See, for example, this
\href{http://www.win-vector.com/blog/2014/11/excel-spreadsheets-are-hard-to-get-right/}{blog post}.

Neverthless, spreadsheets are extremely common in the business world and elsewhere,
so we need to be able to work with them.
Here's an example that reads in the first sheet:
\begin{verbatim}
file = '../Data/test2.xlsx'
xls = pd.read_excel(file)       # default is first sheet
\end{verbatim}
% ***********  ?? more at some point


\item Copying from url's.
Here's an example that copies a file from a url:
\begin{verbatim}
import urllib.request           # this is a module from the package urllib
file = 'foo.csv'
urllib.request.urlretrieve(url, file)
\end{verbatim}
This way you can copy the file to your own computer and read it in from there.
This does the same thing, courtesy of Sarah:
\begin{verbatim}
f = urllib.request.urlopen(url)
file = 'foo_sbh.csv'
with open(file, 'wb') as local_file:
    local_file.write(f.read())
\end{verbatim}

\item {\bf Exercise.}  Create a spreadsheet and save it as both csv and xlsx.
Write code to read them into Python.


\item Copy from clipboard.
We're not fans of this, it makes replication hard, but it's awful convenient
and recommended by some of our former students.

\begin{verbatim}
clip = pd.read_clipboard()
\end{verbatim}


Brandon Rhodes' movie data...  https://github.com/brandon-rhodes/pycon-pandas-tutorial


## Examples 

WEO 

Gelman's speed dating data:  http://www.stat.columbia.edu/~gelman/arm/examples/speed.dating/

Stern teaching data 

Movie data from Rhodes 

Chetty 100 x 100 data 


## Exporting data

write as csv or xls 


## More

unstack... (Rhodes 1:34) 


## Reading zipped files 

The `zipfile` module (part of basic Python) lets you do whatever you want with zip files.
Some examples:

```
import pandas as pd
import urllib
import zipfile
import os

url  = 'http://databank.worldbank.org/data/download/WDI_csv.zip'
file = os.path.basename(url)            # strip out file name
urllib.request.urlretrieve(url, file)   # copy to disk

# see what's there
print(['Is zipfile?', zipfile.is_zipfile(file)])
zf = zipfile.ZipFile(file, 'r')
print('List of zipfile contents (two versions)')
[print(file) for file in zf.namelist()]
zf.printdir()

# extract a component
csv = zf.extract('WDI_Data.csv')        # copy to disk
df1 = pd.read_csv('WDI_Data.csv')       # read
print(df1.columns)                      # check contents

# alternative:  open and read
csv = zf.open('WDI_Data.csv')
df2 = pd.read_csv(csv)
print(df3.columns)
```

For more, see the section of the Python tutorial that describes the
\href{https://docs.python.org/3.4/library/zipfile.html#module-zipfile}{zipfile module}.

Big Mac index
http://infographics.economist.com/2015/databank/BMfile2000-Jul2015.xls

https://realpython.com/blog/python/working-with-large-excel-files-in-pandas/ 

Kaggle example:  http://blog.kaggle.com/2013/01/17/getting-started-with-pandas-predicting-sat-scores-for-new-york-city-schools/ 

http://www.win-vector.com/blog/2014/11/excel-spreadsheets-are-hard-to-get-right/