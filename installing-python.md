# Installing Python 


---
**Overview.** We install Python, then run a test program to make sure it's working.    

**Python tools.**  Anaconda distribution, Spyder and IPython/Jupyter coding environments.  

**Buzzwords.**  Package, distribution, environment, mtwn. 

**Code.** [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_test.py).   

---  


Python is a programming language, but (like other languages) it comes with an ecosystem of related components.  One kind of component is a **package** that extends Python's capabilities.  A good analogy is an operating system, like Windows or Mac OS  You can't do much with either one until you install software "packages" like Word or Excel. Similarly, we will use packages in Python to manage data, create graphs, and compute statistics.  We're going to use a **distribution** called Anaconda, which bundles Python and a bunch of useful packages together in a single download.  

Another kind of component is a user-interface or **environment** for writing code and executing it.  We'll use another analogy here: Word and Google docs are "environments" to produce text documents.  Both work.  We use the one we find more convenient.  The same is true of Python environments.    

We'll use two Python environments in this class: 
 * **Spyder** is a graphical interface that includes an editor, a button to run code, and windows for experimenting and checking documentation.  
 * **Jupyter** is a web-based interface for running **IPython notebooks**, combinations of code, output, and documentation.  

 We will write and execute Python programs in both environments.  Think to yourself:  The environments are analogous to Microsoft Word and the Python program is analogous to a Word document.  

This is a lot of jargon to swallow at one time.  Don't panic, it will become familiar ewith use.  And anything we don't use you can safely ignore.  


## Installing Anaconda 

Follow these instructions.  By which we mean: **follow these instructions exactly!** Creativity is a wonderful thing, but here it will cost you dearly. 

**Step 1. Download the Anaconda installer.** 
* Click **[HERE](http://continuum.io/downloads)** or Google "Anaconda downloads."  
* Scroll to find "Anaconda for Windows" or further down for Macs "Anaconda for OS X."
* Find the option for **Python 3.5.** **NOT** Python 2.7!  If you get 2.7, you'll have to start over.  
* Click the **64-bit Graphical Installer** to start the download. 

**Step 2. Run the installer.**  Click on the Anaconda installer you just downloaded to install the Anaconda distribution of Python.  Do what it says.  

**Step 3. Find and run Launcher.**  Look or search wherever programs are on your computer.    
 * Windows 7 and 8:  Type “Launcher” in your search box.  
 * Macs: Finder, Spotlight Search, and Launchpad all work -- whatever you prefer.    

<!--
**Pro tip.**  Put a shortcut to Launcher in a convenient place so you can find it easily next time.  In Windows, that would be the launchpad or the desktop. 
--> 

Once Launcher is running -- be patient, it can take 60 seconds or more -- you should see something like this:

![Launcher](figs/anaconda_launcher.png "Launcher")

<!--
 * Top left: A teardrop with a snake (an anaconda?) followed by the word Launcher.
 * Top middle: "Python 3.5.x." -- **NOT Python 2.7!!!**
 * Main window:  a list of apps, which are programs Launcher can run.  The most important are **ipython-notebook** and **spyder-app**, which are environments for writing and running Python programs.  
-->


If so, you now have Python installed and ready to run.  Congratulations!  


## Coding environments 

Coding environments are pieces of software we use to write and run code.  The best ones make coding easy, even pleasurable, strange as that might sound.  We'll use two:  **Spyder**  and **Jupyter**.  We access both through Launcher, where Spyder is labelled "spyder-app" and Jupyter is labelled "ipython-notebook".  (Don't ask, it's not worth it.)

If Launcher is open, great.  If not, please start it up (Step 3 above).  

**Spyder.**  Spyder is a graphical environment with an editor for writing programs, a console for trying out one line at a time, and access to help.  It’s our preferred Python environment. Experts often use other editors, but unless you’re one of them this is where you should start.  

To start Spyder from Launcher, **click on the blue Launch button** to the right of spyder-app. We find it a little slow, but it should start up eventually.  You should then see something that looks like this:

![Spyder environment](figs/spyder_plain.png "Spyder")

You see here that Spyder has a number of different components.  It's overwhelming at first, but give it some time.  The most important components are:  

* **Editor.**  This is on the left.  We can write and edit programs here and save them to our hard drive.  
* **Toolbar.** Above the editor, you'll see a row of buttons that we refer to as the toolbar.  Among them are some green triangles.  The big one runs the whole program (whatever we have in the editor).  The smaller ones run sections of code.  More on this later.  Here's a picture:  
![Spyder toolber](figs/spyder_toolbar.png "Spyder's toolbar")
* **IPython console.**  This is on the right at the bottom -- look for the tab with this label.  This is where output from our programs will show up.  On startup you should see something like "Python 3.5.0 |Anaconda 2.4.0 (64-bit)" etc etc, concluding with the line:
```python
in [1]: 
```
We can use the console to write and test single lines of code, get help, and many other things.    
* **Object inspector.**  This is on the right at the top.  We can get Python documentation here, which is really useful.  

We can move these windows around by dragging and dropping.  If we mess up -- it happens to the best of us -- look for "View" at the top and click on "Reset window layout." 


**Jupyter.**  Jupyter is another graphical environment, which we use to create and run **IPython notebooks**. These notebooks combine code, output, words, and graphics.  It's a convenient format for presenting our work to others and can be used as a project report.  We'll use IPython notebooks in class in a few weeks.  In the meantime, here are [two](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_test.ipynb) [examples](http://nbviewer.ipython.org/github/justmarkham/DAT4/blob/master/notebooks/08_linear_regression.ipynb).  

To create or run an IPython notebook from Launcher, **click on the blue Launch button** to the right of the ipython-notebook icon.  It will open a tab in your default browser.  (If you're not sure what that is, you'll soon find out.)  In the browser tab, you'll see something like this:  

![Spyder environment](figs/jupyter_plain.png "Jupyter")

<!--
at the top the word "Jupyter." (It used to say IPython, but now the same environment handles code in Julia, R, and other languages, which called for a [name change](http://ipython.org/#jupyter-and-the-future-of-ipython).)  Just below the word Jupyter you'll see the words "File, "Edit," "View," etc.  Below that you'll see the directory (folder) structure of your computer.  
-->  


**Pro tip.**  Create a directory (folder) on your computer with the name `Data_Bootcamp` and store your programs there.  (And note well:  There is an **underscore** `"_"` between "Data" and "Bootcamp", not a blank space.)  

<!--
By way of example, we have set up a Code directory in our [GitHub repository](https://github.com/DaveBackus/Data_Bootcamp) with separate Python and IPython subdirectories.  This is **mtwn** (more than we need), but since we'll be using the repository repeatedly it's worth taking a quick look now. 

Let's repeat that last part:  We use the acronym **mtwn** to indicate material that is "more than we need," meaning it's safe to ignore.  
--> 


## Run test programs 

Let's run a test program -- the same one -- in Spyder and IPython/Jupyter and make sure everything works.  

**Spyder**.  Start up Spyder.  (If you're not sure how to do that, go back to the previous section.) Once you have Spyder up and running:  

* Create a new file.  Click on "File" (upper left), then "New file."  That should give you a new mostly empty file with some junk at the top that you can ignore or delete. 

* Add code to file.  Enter the following lines of code at the bottom of your file:  

  ```python 
  import sys      # import system module (don't ask) 
  
  print('\nWhat version of Python?\n', sys.version, '\n', sep='') 

  if float(sys.version_info[0]) < 3.0:       
      raise Exception('Program halted, old version of Python. \n', 
                       'Sorry, you need to install Anaconda again.')
  else:
      print('Congratulations, you have Python 3!')
  ```
  [If you're feeling lazy, you can make do with the first two lines on their own, but you won't get the messages we describe below.]   

* Save your code.  Click on File at the top left, then Save As, and save in the `Data_Bootcamp` directory under the name `bootcamp_test.py` (Python programs always have the extension py).  

* Run it.  Click on the green triangle above the editor and run your program.  

The output appears in the IPython console in the lower right corner.  If you get the message "Congratulations etc," you're all set. Pat yourself on the back and buy yourself a cold drink, you've earned it. If you get the message "Program halted, old version of Python, etc," you need to go back and install Anaconda again, this time **following the instructions exactly**! Yes, we know that's discouraging, but it's better to know that now than run into problems later. Have a cold drink anyway and catch your breath.  

**Comment (mtwn).** We use the acronym **mtwn** to indicate material that is "more than we need," meaning it's safe to ignore.  

**More comments.** All of these are mtwn, but we thought they would make the code we just entered less mysterious -- and give us a head start with Python programming.  (i) Anything following a hash (#) is a comment and has no effect on what the program does.  (ii) Blank lines are optional, but they make the code easier to read.  (iii) The rest of the code checks the Python version (`sys.version_info`).  If the version is less than 3.0, it prints an error message (`raise Exception`).  Otherwise it prints the message "Congratulations, etc."  (iv) The statements that begin with `raise` and `print` are indented exactly four spaces.  That's a standard feature of Python.  Anything else generates an error.  


**IPython**.  We prefer to write code in an editor and will stick with Spyder for the first few weeks of the course.  But IPython notebooks are good for talks and reports.  We can read through them more easily than naked code.  Here are [three](https://github.com/ptwobrussell/Mining-the-Social-Web-2nd-Edition/blob/master/ipynb/Chapter%201%20-%20Mining%20Twitter.ipynb) [more](http://nbviewer.ipython.org/url/jakevdp.github.com/downloads/notebooks/XKCD_plots.ipynb) [examples](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/SQL/SQL_Intro.ipynb) to make the point. 

To run the same code in an IPython notebook, start up the IPython/Jupyter app in Launcher.  (If you're not sure how to do that, go back to the previous section.) Once you have it up and running:  

* Choose the directory. You should see the directory structure of your computer in Jupyter.  Navigate to the `Data_Bootcamp` directory (folder) we hope you created earlier.  

* Create a new notebook.  Click on the "New" dropdown menu in the upper right corner and choose Python 3.  This will create a blank notebook and an empty cell, where you can enter words or code.  

* Set the file name.  To the right of the word Jupyter, you'll see "Untitled".  Change it to `bootcamp_test`.  

* Enter code.  Click on the dropdown menu below the word "Help" and choose Code.  Then enter the code listed above in the empty cell.  

* Run the code.  Click on "Cell" at the top and choose Run All.    

Output will appear in the same cell below your code.  If it says "Congratulations etc." you're all set.  


**Exercise.** We have seen two examples of environments for creating Python code files.  Fill in the blanks in this table:

Environment | File 
--- | --- 
MS Word  | Word document
MS Excel | Excel file 
Spyder   | 
        | IPython notebook 

## Let's go! 

We're now ready to write and run Python programs in two environments. Take a bow.  


## Resources 

More on the Anaconda distribution and its contents:

* Anaconda [download](http://continuum.io/downloads) and [package list](http://docs.continuum.io/anaconda/pkg-docs).  
* Spyder [documentation](https://pythonhosted.org/spyder/).  
* IPython [documentation](http://ipython.org/notebook.html).  Look for the [Pybonacci demo](https://youtu.be/H6dLGQw9yFQ), it covers the basics in 5 minutes.  You can also get help in Jupyter:  click on "Help" ar the top and choose "User Interface Tour."
* [Links](https://www.reddit.com/r/Python/comments/2trvyy/resource_or_tutorials_for_anacondaconda/) to documentation and support.  More than you'll ever want or need. 


<!--
## Appendix:  Directory structures 

Complete paths look like this:  
* Windows: `C:\Users\userid\Data_Bootcamp` 
* Mac:  `/Users/userid/Data_Bootcamp`

How to get them?

--> 