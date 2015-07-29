
# More working with data 

---
**Overview.** 

**Python tools.**  

**Buzzwords.**  

---

## Reminders

Methods...

DataFrames

Series 


## Pandas as Excel 


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

unstack:  Brandon Rhodes at 2:00 
 

**Pivot tables.** You can all of it and more with set_index, sort_index, and unstack.  2:10m



## Merging dataframes 

merge:  Brandon Rhodes at 2:10 

Evidently Pandas is smart... 



## References 

Brandon Rhodes.  This is great.  
https://youtu.be/5JnMutdy6Fw
https://github.com/brandon-rhodes/pycon-pandas-tutorial/
