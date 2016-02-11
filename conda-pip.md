# Updating Python:  Conda and Pip  


---
**Overview.**  We describe the tools used to update and install Python packages. 

**Python tools.**  conda, pip.  

**Buzzwords.**  Command line.  

**Applications.**  Seaborn, Quandl.  

---


**Warning:  This is rough in the extreme.** 

There are handy tools for updating Python and installing and updating packages.  We start with **conda**, the tool used to update the components of the Anaconda distribution, then move on to the traditional Python tool, **pip** ("pip installs packages").  

## Getting started 

These tools run on the **command line**, the old-school approach that predates the graphical interfaces we use today (Mac OS, Windows, etc).  

Anaconda:  http://docs.continuum.io/anaconda/pkg-docs 

## Command line 

In Windows.  Either type `cmd` in the search box or use the `Anaconda prompt`.  

In Mac OS:  terminal.  

## Conda 

This is the Anaconda tool, useful for updating and extending Anaconda. Since Anaconda includes most of the packages we use, it's our tool of choice.  

Once you go to the command line, 

Command line... 

conda info 
conda list 

conda update conda 
conda update anaconda 

conda install [package]

For example, we use 

```
conda install quandl 
```

More information:  

* Link:  http://conda.pydata.org/docs/
* Cheat sheet:  http://conda.pydata.org/docs/_downloads/conda-cheatsheet.pdf


## Pip 

Link:  https://pip.readthedocs.org/en/stable/



## Quandl 

Handy access to lots of economic and financial data... 


## Seaborn 

A terrific interface for Matplotlib...  


<!--
## tqdm

Progress bar for data loads...  


## Pyopendata

https://pypi.python.org/pypi/pyopendata/0.0.2

Use to get OECD data?  


## Flappy bird

https://www.youtube.com/watch?v=h2Uhla6nLDU 
https://github.com/Max00355/FlappyBird/blob/master/flappybird.py
--> 

