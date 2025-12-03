This introduction was created for the NAGT webinar in March 2024. Feel free to check it out!

# Introduction to Python and "thinking algorithmically"

<b>Computation learning objectives:</b>
- Learn about Python and the basics of how to install and run it on your computer 


<b>Geoscience learning objectives:</b>
- Understand the benefits of "thinking algorithmically" in the geosciences

<b>Real-world context:</b>
- Many data tasks can be accomplished more quickly and accurately using coding compared to graphical user interfaces (GUIs) like Excel, ArcGIS, etc. 
- Python is free, meaning your lab or employer can save money if you know how to accomplish tasks with Python

<b>Tips for success:</b>
- read?

## Why me?
I (Joanmarie Del Vecchio) entered Geology via the social sciences and enjoying hikes and fieldwork, and as an undergraduate I did not enjoy the computing aspects of the geosciences. However, in grad school, it became clear to me that nearly all aspects of modern geoscience research either involves, or is being transformed by, computing. Overtime I have come to use and appreciate computing approaches to my research; I now enjoy solving algorithmic "puzzles," figuring out how to tell a computer what I want to do. I also saw many of my friends from grad school deciding against academic careers and instead either leveraging their coding expertise or teaching themselves these skills to pivot to working in industry (and not necessarily geoscience industry). I think my experience can speak to many kinds of geoscientists, especially coding novices. 

## Why now?
1. There is so much data about our Earth being collected at any given moment, but sometimes those datasets are huge or in weird file formats, which means currently relatively few people with the right skills and software can anayze those datasets. This is a problem if we want as many people as possible solving problems in our world associated with climate change, geohazards, and fragile Earth systems.
2. Skills associated with data science are highly transferrable (you can use a few tools to ask a lot of different questions) and employable. Computing opens doors to both research and career success, which means bringing coding into your classroom can make the geosciences more appealing to students traditionally under-represented in or excluded from the geosciences, and improve outcomes for those students if they stick with it. 

# Introduction to Python, conda, and Jupyter Notebooks

## What is Python?
[Python](https://docs.python.org/3/faq/general.html) is a programming language, which helps you deliver commands to a computer (and Ptyhon is a "high-level" language, which means that it looks more like human language instead of computer `beeps` and `boops`, which is good for us scientists). Python is a very popular language for many use cases and fields, and over the past decade it has been increasingly adopted by research scientists who write packages (more on that soon) to do their work (R is another language that scientists also like to use, but its packages have historically focused on statistics). It is also free to download and use, which is great and in contrast to Matlab, which is perhaps the other language that geoscientists may have encountered. It is indeed named after Monty Python's Flying Circus. 

### Why and how would I use Python, philosophically?
This is a good question, and I hope this tutorial helps to answer it. The jargony answer would be "Python facilitates <b>scalable</b> and <b>reproducible</b> scientific research." By "scalable" I mean that the complexity of the research task, and the time it takes to do that task, should not grow with a growing dataset. Doing things "by hand" take a long time and become tedius if repeated over and over again, so the goal of using Python in science research is to automate as many of those tasks we might normally do "by hand" as possible. By "reproducible" I mean that anyone should be able to take your input data, perform the same analyses you did, and get the same result. In the geosciences, this might look like the stream gage example I have in this repository: without Python, we would have to physically click and type to download data from the USGS, bring it into some format for analysis (perhaps Microsoft Excel), type our formulas into cells, make plots, and then save the `.xlsx` file (and hope that no one moves anything around or edits a formula) over and over again. With Python, a single notebook or Python script can download, transform, and plot the data for as many USGS stream gage your heart desires to study. 

### How do I use Python practically?
You need to install Python on your computer to use Python on your computer. When you install a version of Python on your computer, any other software package that uses Python (like `conda` or the package that runs Jupyter Notebooks) will "look" at that version of Python to run that package's software. 

There are a number of ways to <i>execute</i> Python code. The simplest way is to "start up" Python in either the Command Prompt (Windows), Terminal (Mac), or use the [Anaconda Prompt](), and then execute a file that contains Python code that ends in `.py`. For example, if you had a file called `example.py`, you could type this line into your machine's command prompt/terminal and hit enter:
```
python example.py
```
Your computer would then run that script, and it would do whatever it is was contained in the script. This might be the best way to do your science with Python, for example, if you don't have to fiddle and experiment with inputs and code and don't have to look at the results of a calculation until the end. Maybe the contents of `example.py` are just:
```
print("Hello, world!)
```
in which case "Hello, world!" would print to your console. 

But in this tutorial we will be running Python from inside a [Jupyter Notebook](https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/what_is_jupyter.html), which I will describe below, but for now you can think of notebooks as executing individual lines or groups of lines of Python instead of hitting "go" on a whole `.py` file. But in order to run Jupyter Notebooks with Python, we need to build an <i>environment</i> that has <i>packages</i> that help us do that. 

## What are environments and packages, and what is conda?

Borrowing language from Real Python:
"Python modules and Python packages [are] two mechanisms that facilitate modular programming.
Modular programming refers to the process of breaking a large, unwieldy programming task into separate, smaller, more manageable subtasks or modules. Individual modules can then be cobbled together like building blocks to create a larger application."

You install <b>packages</b> that contain <b>modules</b>, and you load or import those modules when you need them in your Python code by typing `import <module_name>` in your script or notebook. 

An <b>environment</b> is a directory that contains a specific collection of packages that you have installed. You can maintain multiple environments if you have different tasks to do that require different software - think of environments as little slices of computers inside your computer that are each running their own software. 

But why not have one environment with all the packages? For various reasons, certain versions of packages or modules might not be compatible with each other, and an environment that has a lot of packages installed might take a really long time to update or fix. Thus we use package managers like <b>[conda](https://docs.conda.io/projects/conda/en/stable/user-guide/getting-started.html)</b> to help us herd these Python package cats. 

There are a few options for installing conda:

![Source: Planemo documentation](https://miro.medium.com/v2/resize:fit:828/format:webp/1*O5Jgl-KFuvUyujAZhXHYlQ.png) from Planemo documentation

Miniconda is a minimal installer provided by Anaconda in that it contains only conda, Python, and the packages they depend upon. The idea is that you will be responsible for installing the packages you need in your own environments to run your scripts.

Anaconda Navigator is a graphical desktop application that enables you to use conda without having to run commands at the command line. You can manage your environments and the packages inside them without scripting. 



## What is a notebook?
A Jupyter Notebook is an interactive computing environment that allows you to create and share documents containing live code, equations, visualizations, and explanatory text.

A Jupyter Notebook consists of cells. There are two main types of cells:

<b>Code</b> cells are used to write and execute code. You can write Python code in these cells and run it by pressing Shift + Enter or clicking the "Run" button in the toolbar.

<b>Markdown</b> cells are used to write text, formatted using Markdown syntax. You can write explanations, documentation, or even LaTeX equations in these cells.

## What is a JupyterHub?
JupyterHub brings the power of notebooks to groups of users. It gives users access to computational environments and resources without burdening the users with installation and maintenance tasks. Users - including students, researchers, and data scientists - can get their work done in their own workspaces on shared resources which can be managed efficiently by system administrators.