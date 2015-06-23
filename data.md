# The data mentality


---
**Overview.**

**Python tools.**  Pandas data input from csv and xls files, general properties of DataFrames.

**Applications.**  Income by college major.??

---

## The data mentality




## Places to look





## Reading data into Python


We'll talk more about packages later, but for now just put these lines above...

```
import pandas as pd
```

**Reading csv files.**
We've found that csv files
are the most useful common data format, far better than xls or xlsx.
Its simple structure (entries separated by commas, tabs, or spaces) allows easy and rapid input.
That's a general statement, not a statement about Python.

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

\item Zip files.  The {\tt zipfile} module (part of basic Python)
lets you do whatever you want with zip files.
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

