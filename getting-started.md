# Getting started with Python 


---
**Overview.** We download and install Python, then run some simple test programs.  

**Python tools.**  Anaconda distribution, Spyder and IPython coding environments.  

---

We're going to show you how to install Python.  There are lots of ways to do this, but we'll give you one.  Then we'll run a test program to make sure everything is working.  

Modern programming languages have a number of moving parts.  One part is the program itself.  A second is the collection of packages that do specific things.  Python, for example, has packages that extend Python to manage data, create graphs, and perform statistical analysis. Together, these components are referred to as a **distribution**.  We'll use the Anaconda distribution, which includes Python and some of its more popular packages.  The good people at [Continuum Analytics](https://store.continuum.io/cshop/anaconda/) have made sure that all of these parts work together most of the time.  

Another important part of a programming language is the user-interface or **environment** for writing code and executing it.  We'll use two.  **Spyder** is an editor with a button to run code and windows for experimenting and checking documentation.  An **IPython notebook** is a combination of code, output, and documentation that we can run in **Jupyter**.  


## Downloading Anaconda 

Follow these instructions.  By which we mean:
**FOLLOW THESE INSTRUCTIONS EXACTLY!** Creativity is a wonderful thing, but here it will cost you dearly. 
 

**1. Download the Anaconda installer.**  [Download the installer](http://continuum.io/downloads) appropriate to your computer.  On the download page, click on "I want Python 3.4" and the logo of the operating system you use (Windows, Mac OS, or Linux). 

**Make sure you get Python 3.4.**  If you accidentally install Python 2.7, or anything other than 3.4, you should uninstall it and start over.  

**2. Run the installer.**  Click on the Anaconda installer to install Anaconda.  

**3. Find and run Launcher.**  You should now have Anaconda’s Launcher ready to go.  The trick is finding it.  Look or search wherever programs are on your computer.  In Windows 7, you click on the Start button and go to all programs. You should see an Anaconda folder, which contains (among other things) Launcher. Click on it.  In Windows 8, type “Launcher” into the search box.  On Macs, Finder is similar. 

**Pro tip.**  Once you find Launcher, you might put a shortcut in a convenient place so you can find it easily next time.  In Windows, that might be the launchpad or the desktop. 

Once Launcher is running -- it can take 60 seconds or more -- you should see a teardrop with a snake in the upper left (an anaconda?) followed by the word Launcher.  Also at the top it should say Python 3.4.x.  Below that is a list of apps -- programs Launcher can run.  There's more documentation at [the link](http://docs.continuum.io/anaconda-launcher/index.html). 

**4. Update.**  Once you have Launcher running, it will give you a menu of things you can do with Python.  The most important are ipython-notebook and spyder-app, which are environments for running Python programs.  We'll use both.  If there’s an update button to the right of ipython-notebook, click on it.  [??]

You now have Python installed and ready to run.  Congratulations!  


## Environments

If Launcher is open, great.  If not, please start it up (Step 3 above).  It should look like [this picture](http://continuum.io/blog/new-launcher).  You should see a list of applications:  

* glueviz:  ignore it
* ipython-notebook:  we'll look at this shortly 
* ipython-qtconsole:  ignore it
* spyder-app:  we'll look at this shortly, too

From here, we can launch our two favorite Python evironments, Spyder and Ipython. 


**Spyder.**  Spyder is a graphical environment with an editor for writing programs, a console for trying out one line at a time, and access to help.  It’s our preferred Python environment. Experts often use their own editors, but unless you’re one of them this is a great place to start.  

To start Spyder from Launcher, click on the Launch button to the right of spyder-app. We find it a little slow, but it should start up.  Spyder has a number of different windows. The most important are:   

* The editor.  This is on the left.  You can write and edit programs here and save them to your hard drive.  At the top, you'll see green triangles.  The big one runs the whole program (whatever you have in the editor).  The smaller ones run sections of code.  More later.  
* IPython console.  This is on the right at the bottom -- look for the tab with this label.  Here you can write and test single lines of code and see how they work.  And some other things we'll come back to.  
* Object explorer.  This is on the right at the top.  Here you can get documentation on Python commands.  More on this later, too. 

You can move these tabs around by dragging and dropping.  If you mess up and want to revert to the original, look for View at the top and click on "Reset window layout." 


**IPython.**  IPython is another graphical environment, one that allows you to combine code, output, words, and graphics.  Lots of people use IPython notebooks to write Python programs and, especially, to give presentations about their work.  We'll use them in class once we get going.  Here are [two](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_test.ipynb) [examples](http://nbviewer.ipython.org/url/jakevdp.github.com/downloads/notebooks/XKCD_plots.ipynb); more [here](https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks).

To create or run an IPython notebook from Launcher, click on the Launch button to the right of ipython-notebook.  It will open a tab in your default browser.  (If you're not sure what that is, you'll soon find out.)  In the browser tab, you'll see at the top the word "jupyter," which is the name given to this environment.  (More on this another time.  The short story is that it used to say IPython, but now the same environment handles Julia and R code.)  Below it you'll see the words "File, "Edit," "View," etc.  Below that you'll see the directory (folder) structure of your computer.  


**Pro tip.**  Create a directory (folder) on your computer with a name like "Data_bootcamp" and store your programs there.  It will make it easier to find them later.  


## Run test programs 

Let's see if everything runs as planned.  

We'll start with **Spyder**.  Enter the following lines of code in the editor: 

```
import sys      # this imports some obscure code that allows us to check Python

print('What version of Python? \n', sys.version, '\n', sep='') 

if float(sys.version_info[0]) < 3.0 :       
    raise Exception('Program halted, old version of Python. \n', 
                    'Sorry, you need to install Anaconda again.')
else:
    print('Congratulations, Python is up to date!')
```
Comments:  (i) Anything following a hashtag (#) is a comment.  (ii) Blank lines are optional here, but they make the code easier to follow.  (iii) The rest of this code is hopelessly obscure, don't bother to understand it. We refer to it as mtyn:  more than you need.  We'll run across other things like this, and label them the same way.  


Once you've entered the code, click on File at the top left, then Save As, and save in the directory of your choice under the name bootcamp_text.py (Python programs always have the extension py).  Now click on the green triangle above the code and run it. 

The output appears in the IPython console in the lower right corner.  If you get the message "Program halted, old version of Python, etc," you need to go back and install Anaconda again, this time following the instructions EXACTLY! Yes, we know that's discouraging, but better to know that now than run into problems later.
If you get the message "Congratulations etc," you're all set. Pat yourself on the back. You can close out the program and go back to whatever you were doing.


Next up:  **IPython**.  Here are two ways to run the test code in the IPython/jupyter environment.  

Method 1.  

* Create a blank notebook.  Click on File, then New Notebook, then Python 3.  This will create a blank notebook and a blank cell, a blank area where you can enter words or code.  
* Enter code.  Click on the menu below the word Help and choose Code.  Then enter the code listed above (cut and paste should do).  
* Run.  Click on Cell and choose Run All.  

The output will appear immediately below the code.  

Method 2.  This is more complicated, but it introduces some concepts we'll use later on.  Skip it if you've hit your limit.  

* GitHub.  Go to the course's GitHub site:  https://github.com/DaveBackus/Data_Bootcamp 
* Find test program.  You'll see a directory of files at the top.  Click on Code, then IPython.  There you should find the file bootcamp_test.ipnb.  (IPython notebooks use the extension ipnb.)  If you click on it, you'll see what the notebook looks like:  some code surrounded by text.  
* Download the file/program.  This is the tricky part.  What you see is not the file, but a translation of it that's easier to read.  To download it we need the real file.  To get it, click on the RAW and download [?? use nbviewer??] 



## Wordplay

Python is named for Monty Python, a group of comedians whose humor appeals to the tech crowd.  Idle, a well-know Python editor, is a reference to Python-member Eric Idle.  The [Python Package Index](https://pypi.python.org/pypi), a repository of Python packages, is commonly known as the [Cheese Shop](http://youtu.be/PPN3KTtrnZM), a reference to a famous Monty Python skit.  Anaconda is, of course, a play on the snake theme.   

