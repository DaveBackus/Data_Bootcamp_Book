# Installing Python 


---
**Overview.** We install Python, then run a test program to make sure it's working.    

**Python tools.**  Anaconda distribution, Spyder and IPython coding environments.  

**Buzzwords.**  Distribution, environment, mtyn. 

**Code.** [Link](https://raw.githubusercontent.com/DaveBackus/Data_Bootcamp/master/Code/Python/bootcamp_test.py).   

---

There are lots of ways to install Python, but we recommend one:  **Anaconda**.  We show you how to install Anaconda, then run a test program to make sure everything is working.  

Modern programming languages have a number of moving parts.  One part is the program itself, in this case the program that runs Python code.  A second is the collection of packages that do specific things.  Python, for example, has packages that extend Python to manage data, create graphs, perform statistical analysis, and manage web sites. Together, these components are referred to as a **distribution**.  We'll use the Anaconda distribution, which includes Python and some of its more popular packages. The good people at [Continuum Analytics](https://store.continuum.io/cshop/anaconda/) have made sure that all of these parts (usually) work together.  

Another important part of a programming language is the user-interface or **environment** for writing code and executing it.  We'll use two.  **Spyder** is a graphical interface that includes an editor, a button to run code, and windows for experimenting and checking documentation.  An **IPython notebook** is a combination of code, output, and documentation that we can run interactively in **Jupyter**.  Both of these environments call on Python more or less automatically:  press a button and you're good to go.  Even better, both come with the Anaconda distribution. 


## Installing Anaconda 

Follow these instructions.  By which we mean: **follow these instructions exactly!** Creativity is a wonderful thing, but here it will cost you dearly. 
 

**Step 1. Download the Anaconda installer.**  Click [here](http://continuum.io/downloads) to go to the download page.  Click on the logo of your operating system (Windows, Mac OS, or Linux) and "I want Python 3.4" to choose the appropriate version.  Then click on "Python 3.4 Graphical Installer" to download the installer.

**Make sure you get Python 3.4.**  If you accidentally install Python 2.7, or anything other than 3.4, you should uninstall it and start over.  

**Step 2. Run the installer.**  Click on the Anaconda installer you just downloaded to install the Anaconda distribution of Python.  Do what it says.  

**Step 3. Find and run Launcher.**  You should now have Anaconda’s Launcher ready to go.  The trick is finding it.  Look or search wherever programs are on your computer.  In Windows 7, you click on the Start button and go to all programs. You should see an Anaconda folder, which contains (among other things) Launcher. Click on it.  In Windows 8, type “Launcher” into the search box.  On Macs, Finder is similar. 
<!-- more ?? Macs? Windows 9/10 -->

**Pro tip.**  Once you find Launcher, you might put a shortcut in a convenient place so you can find it easily next time.  In Windows, that would be the launchpad or the desktop. 

Once Launcher is running -- be patient, it can take 60 seconds or more -- you should see a teardrop with a snake in the upper left (an anaconda?) followed by the word Launcher.  Also at the top it should say Python 3.4.x.  Below that is a list of apps: programs Launcher can run.  The most important are **ipython-notebook** and **spyder-app**, which are environments for running Python programs.  

You now have Python installed and ready to run.  Congratulations!  


## Coding environments 

Coding environments are pieces of software we use to write and run code.  The best ones make coding easy, even pleasurable, strange as that might sound.  We'll use two:  Spyder and the IPython notebook.  

We access both through Launcher.  If Launcher is open, great.  If not, please start it up (Step 3 above).  It should look (roughly) like [this picture](http://continuum.io/blog/new-launcher).  You will see a list of applications:  

* glueviz 
* ipython-notebook 
* ipython-qtconsole 
* spyder-app 

From here, we can launch our two favorite Python evironments. 


**Spyder.**  Spyder is a graphical environment with an editor for writing programs, a console for trying out one line at a time, and access to help.  It’s our preferred Python environment. Experts often use their own editors, but unless you’re one of them this is where you should start.  

To start Spyder from Launcher, click on the Launch button to the right of spyder-app. We find it a little slow, but it should start up eventually.  Spyder has a number of different windows. The most important are:   

* Editor.  This is on the left.  We can write and edit programs here and save them to our hard drive.  At the top, you'll see green triangles.  The big one runs the whole program (whatever we have in the editor).  The smaller ones run sections of code.  More on this later on.    
* IPython console.  This is on the right at the bottom -- look for the tab with this label.  Here we can write and test single lines of code and see how they work.  Also some other things that we'll touch on later.    
* Object explorer.  This is on the right at the top.  Here we can get documentation on Python commands, which is really useful.  

You can move these windows around by dragging and dropping.  If you mess up and want to revert to the original, look for View at the top and click on "Reset window layout." 


**IPython.**  IPython ("interactive Python") is another graphical environment, one that allows you to combine code, output, words, and graphics.  Lots of people use IPython notebooks to write Python programs and, especially, to present their work. By icnluding text and output along with the code, we can make a notebook look like presentation slides.  We'll use IPython notebooks in class in a few weeks.  In the meantime, here are [two](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/IPython/bootcamp_test.ipynb) [examples](http://nbviewer.ipython.org/github/justmarkham/DAT4/blob/master/notebooks/08_linear_regression.ipynb) and a [more extensive collection](https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks).

To create or run an IPython notebook from Launcher, click on the Launch button to the right of ipython-notebook.  It will open a tab in your default browser.  (If you're not sure what that is, you'll soon find out.)  In the browser tab, you'll see at the top the word "Jupyter," which is the name of this environment.  (It used to say IPython, but now the same environment handles code in Julia, R, and other languages.)  Just below you'll see the words "File, "Edit," "View," etc.  Below that you'll see the directory (folder) structure of your computer.  


**Pro tip.**  Create a directory (folder) on your computer with the name "Data_Bootcamp" and store your programs there.  It will make it easier to find them later.  By way of example, we have set up a Code directory in our [GitHub repository](https://github.com/DaveBackus/Data_Bootcamp) with separate Python and IPython subdirectories.  This is **mtyn** (more than you need), but since we'll be using the repository repeatedly it's worth taking a quick look now. 


## Run test programs 

Let's run a test program -- the same one -- in Spyder and IPython/Jupyter and make sure everything works.  

**Spyder**.  Start up Spyder.  (If you're not sure how to do that, go back to the previous section.) Once you have Spyder up and running:  

* Create a new file.  Click on File (upper left), then New file.  That should give you a new file with some junk at the top that you can ignore or delete.  
* Add code to file.  Enter the following lines of code at the bottom of your file (cut and paste should do it): 

```python 
import sys      # import system module (don't ask) 

print('\nWhat version of Python? \n', sys.version, '\n', sep='') 

if float(sys.version_info[0]) < 3.0:       
    raise Exception('Program halted, old version of Python. \n', 
                    'Sorry, you need to install Anaconda again.')
else:
    print('Congratulations, you have Python 3!')
```

* Comments (mtyn):  (i) Anything following a hashtag (#) is a comment.  (ii) Blank lines are optional here, but they make the code easier to read.  (iii) The rest of the code checks the Python version (`sys.version_info`).  If the version is less than 3.0, it prints an error message (`raise Exception`).  Otherwise it prints the message "Contratulations, etc."
* Save your code.  Click on File at the top left, then Save As, and save in the directory of your choice under the name "bootcamp\_test.py" (Python programs always have the extension py).  We recommend the directory "Data\_Bootcamp" that we suggested earlier. 
* Run it.  Click on the green triangle above the editor and run your program.  

The output appears in the IPython console in the lower right corner.  If you get the message "Congratulations etc," you're all set. Pat yourself on the back and buy yourself a cold drink, you've earned it. If you get the message "Program halted, old version of Python, etc," you need to go back and install Anaconda again, this time **following the instructions exactly**! Yes, we know that's discouraging, but it's better to know now than run into problems later. Have a cold drink anyway and catch your breath.  


**IPython**.  We prefer to write code in an editor and will stick with Spyder for most of the course.  But some people prefer IPython notebooks.  They're good for talks if you want to show both code and output, and intersperse it with text.  They can also be used for reports.  As we've seen from examples, you can read through them more easily than naked code.  Here are [three](https://github.com/ptwobrussell/Mining-the-Social-Web-2nd-Edition/blob/master/ipynb/Chapter%201%20-%20Mining%20Twitter.ipynb) [more](http://nbviewer.ipython.org/url/jakevdp.github.com/downloads/notebooks/XKCD_plots.ipynb) [examples](https://github.com/DaveBackus/Data_Bootcamp/blob/master/Code/SQL/SQL_Intro.ipynb) to make the point.   

To run the same code in an IPython notebook, start up the IPython/Jupyter app in Launcher.  (If you're not sure how to do that, go back to the previous section.) Once you have it up and running:  

* Choose the directory. You should see the directory structure of your computer in Jupyter.  Navigate to the "Data_Bootcamp" directory (folder), whch we hope you created earlier, or some other directory where you'd like to store files for this course.  
* Create a new notebook.  Click on the New menu in the upper right corner and choose Python 3.  This will create a blank notebook and an empty cell, where you can enter words or code.  
* Set the file name.  To the right of the word Jupyter, you'll see the word Untitled.  Change it to bootcamp_test.  
* Enter code.  Click on the menu below the word Help and choose Code.  Then enter the code listed above in the empty cell.  
* Run code.  Click on Cell at the top and choose Run All.    

Output will appear in the same cell below your code.  If it says "Congratulations etc." you're all set.  


## Let's go! 

We're now ready to write and run Python programs in two environments.  That's more than enough for one day.  Take a bow.  


