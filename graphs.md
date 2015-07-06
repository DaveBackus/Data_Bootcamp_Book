# Visualizing data


---
**Overview.**

**Python tools.**  Importing packages, graphing with Matplotlib.

**Buzzwords.** Data visualization, 

**Applications.**  Incomes of college majors.??

---

Computer graphics are one of the great advances of the modern world.  Graphs have always been helpful in describing data or concepts, but they're a lot easier to produce now than they were a few decades ago. In fact, we've gotten so good at drawing pictures that we invented a new term:  data visualization**.

That's the good news.  The bad news, or at least a fact of life, is that graphics have lots of moving parts.  ...


## Packages

Packages:  Collections of commands that do more than basic Python.
There are packages that do almost anything, but we'll focus on a couple:
Matplotlib and pandas.  Matplotlib is a graphics package, we'll talk about it
another time.
We touch on pandas --- briefly --- below.

In Python --- and many other languages --- we need to tell Python to make them available.
Here are some options for doing this with a mythical package {\tt xyz}:
\begin{itemize}
\item {\tt from xyz import *}.
This imports all the commands from the package {\tt xyz}.
You can replace the star
with specific commands and import only them.
A command {\tt foo} is then executed by typing {\tt foo}.
\item {\tt import xyz}.  This imports the whole thing.
A command {\tt foo} is then executed by adding {\tt xyz.}
(note the period) before its name:  {\tt xyz.foo}.
\item {\tt import xyz as x} is the most common syntax.
It allows the shorthand {\tt x.foo}.
We'll do this momentarily with the package {\tt pandas}.
\end{itemize}
For more, see the
\href{https://docs.python.org/3.4/tutorial/modules.html}{Section 6}
of the Python tutorial.
This refers to modules, which could be packages, subsets of packages, or even
code you've written yourself.

\item The pandas package:  pandas = (Python Data Analysis Library).
This is the central package for data work,
it allows you to use Python for data management along similar
lines to the program R.
We'll import it typically with the command {\it import pandas as pd}
and execute commands with syntax of the form {\t pd.command}.

\item Reference:  pandas has the usual high-quality
{documentation}
we expect from Python packages.
Search ``python pandas'' or go to
\url{http://pandas.pydata.org/}.
We'll focus here on the input-output tools:
\url{http://pandas.pydata.org/pandas-docs/stable/io.html}.


##  Matplotlib pyplot...



## Object-oriented matplotlib



## Links 

Viz of the Day
Tableau
Viz Wiz

Graphic Detail


# Examples 

http://fivethirtyeight.com/datalab/the-extreme-economic-outlier-that-is-greece-in-7-charts/


