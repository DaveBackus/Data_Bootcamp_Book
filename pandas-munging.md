# Emerging market indicators 

---
**Overview.** We often get data in one form and want to change it to another.  Pandas has an exceptional collection of tools for doing this, but it takes us out of our Excel mindset.  

**Python tools.**  Pandas, data frames, index, columns, transpose...  

**Buzzwords.**  Want operator, selection (filtering), 

**Applications.** 

---

The idea is to get going, cover details later. 

The idea is to start with what we want the end product to be:  to apply, in the words of a colleague, the **want operator**.   

Applications:  growth by decade, debt, ... 


## Reminders

Methods...

DataFrames

Series 


## Variable types 

dtypes 

conversion 

## Pandas as Excel 


## Selection 

aka filtering 


## Indexes 



## Columns 

transpose 




## Merging


We'll talk more about packages later, but for now just put these lines above...

```python 
import pandas as pd
```

https://realpython.com/blog/python/working-with-large-excel-files-in-pandas/


Methods to cover

describe
value_counts
set_index  --- and  .sort_index() to speed up selection 
also multiindexes:  df.set_index(['var1', 'var2'])
reset_index -- puts index into varlist 

df.loc['var1'].loc['var2']
df.loc['var1', entry]

groupby -- sorts automatically 
size, sum, mean, max, min 

data types for variables (info?)

## Missing values 


## Stack and unstack...  


unstack... (Rhodes 1:34) 

unstack:  Brandon Rhodes at 2:00 
 

## Pivot tables 

https://en.wikipedia.org/wiki/Pivot_table 

Rhodes:  You can all of it and more with set_index, sort_index, and unstack.  2:10m



## Merging dataframes 

merge:  Brandon Rhodes at 2:10 

Evidently Pandas is smart... 


## Examples 

Auto safety:  http://www.nhtsa.gov/NCSA


## References 

Brandon Rhodes.  This is great.  
https://youtu.be/5JnMutdy6Fw
https://github.com/brandon-rhodes/pycon-pandas-tutorial/

https://en.wikipedia.org/wiki/Pivot_table

Other 

* Groupby:  http://pandas.pydata.org/pandas-docs/stable/groupby.html
* stack and unstack:  http://pandas.pydata.org/pandas-docs/stable/reshaping.html

Kaggle example:  http://blog.kaggle.com/2013/01/17/getting-started-with-pandas-predicting-sat-scores-for-new-york-city-schools/ 

Lots of examples:  
http://tomaugspurger.github.io/
http://nbviewer.ipython.org/github/TomAugspurger/PyDataSeattle/tree/master/notebooks/

SQL intro https://www.khanacademy.org/computing/hour-of-code/hour-of-sql/v/welcome-to-sql 

SQL and Pandas:  https://www.youtube.com/watch?v=1uVWjdAbgBg 

http://www.gregreda.com/2013/10/26/intro-to-pandas-data-structures/ 
http://www.gregreda.com/2013/10/26/working-with-pandas-dataframes/

http://manishamde.github.io/blog/2013/03/07/pandas-and-python-top-10/ 