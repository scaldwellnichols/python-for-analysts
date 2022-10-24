Introduction to Python[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#introduction-to-python "Permanent link")
===========================================================================================================================================================================================================================================================

In this module, we will be using the Python programming language. This language first appeared in 1991 and was designed by Guido van Rossum.

Python is currently one of the most popular programming languages and is very widely used in scientific applications (especially those involving data analysis). Python is also used in artificial intelligence. It is considered to be one of the best languages to learn as a first programming language, since it supports a wide variety of programming concepts in a fairly straightforward way. This makes Python a good way to acquire a general understanding of programming that is transferable to many other languages.

### Learning outcomes

After completing this lesson you should:

-   understand what a computer program is
-   understand what kind of programming language Python is and its strengths and weaknesses
-   be aware of the different kinds of program development environments that can be used for editing and running programs.

What is a computer program?[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#what-is-a-computer-program "Permanent link")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

As this is an advanced computing course, you may already have a fair idea of what a computer program is. However, briefly consider the general definition and a simple example below, before moving on to the rest of the lesson.

A **computer program** consists of a collection of commands, usually stored in a file (or set of files). Rather than typing out the commands each time we want to execute them we simply run the program. Operating systems provide various ways of running programs, such as via entering a command in a terminal window or clicking on a program icon.

The following is an example of a very simple Python program. When this program runs it will prompt the user to enter three numbers corresponding to the lengths of the three dimensions of a box. It will then calculate and output the volume of the box:

```python
print( "Welcome to the amazing box volume calculator!" )

# Read in box x, y and z values (as strings)
x = input("Enter the length (in cm) of your box: ")
y = input("Enter the width (in cm) of your box: ")
z = input("Enter the depth (in cm) of your box: ")

# multiply lengths in each dimension to get the volume
volume = int(x) * int(y) * int(z)

# The int function converts a string to an integer
print( "The volume of your box is", volume, "cubic centimetres" )
```

This program is **imperative** in style, which means that it consists of a sequence of commands that are to be executed when the program is run. The code illustrates some of the most fundamental ideas in programming. It takes input data (via the `input` commands), performs some calculation (to find the volume) and outputs (using the `print` command) a computed value.

The code also illustrates the use of variables (`x`, `y`, `z` and `volume`), which are assigned values using the `=` symbol. The value of `volume` is calculated by multiplying (using the `*` operator) the three measurement values. Notice that the values of the variables `x`, `y`and `z` will be sequences of characters (called strings) typed in by the user. These character sequences need to be converted to corresponding numbers (integers) by the `int` operator.

### Question

Our general definition characterised a program as a "collection of commands". Consider the following:

-   Do all programs consist of commands?
-   Can definitions, questions or hypotheses be parts of a program?
-   What about data? Is that part of a program?

Try to form an opinion on these questions by conducting your own research. After you have considered the questions, return to Minerva and share your thoughts and findings in the discussion thread. Access the thread for this topic by selecting the **'Discussion'** tab in the side navigation in Minerva and selecting the **'What is a computer program?'** thread for this lesson.

### Hints

-   Find out about the distinction between *imperative* and *declarative* programming languages.
-   Consider that data can be considered to be a declarative part of a program and that structured data may sometimes be used to control the execution of a program.


What kind of programming language is Python?[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#what-kind-of-programming-language-is-python "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

It is difficult to describe Python as a particular kind of programming language. It is not based on any one dominant idea of how to program, and incorporates a wide variety of features which are also found in many other modern programming languages, such as [object orientation](https://en.wikipedia.org/wiki/Object-oriented_programming), [functional programming](https://en.wikipedia.org/wiki/Functional_programming), [exception handling](https://en.wikipedia.org/wiki/Exception_handling) and [meta programming](https://en.wikipedia.org/wiki/Metaprogramming).

Strengths and weaknesses as a programming language[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#strengths-and-weaknesses-as-a-programming-language "Permanent link")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Python has a number of strengths and weaknesses in comparison to other programming languages.

### Strengths[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#strengths "Permanent link")

-   It is easy to learn the basics of Python.
-   Python also enables smooth progression from simple to complex programming.
-   Python is widely used.
-   A huge number of 'packages' are available to support specific types of programming.
-   The Python language provides convenient constructs for many high-level programming ideas.
-   Python strikes a good balance between theoretical elegance and practical utility.

As you can see, Python's strengths are centred around its ease of use and flexibility.

### Weaknesses[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#weaknesses "Permanent link")

-   Python may be too slow or inefficient for certain kinds of applications.
-   Some programmers don't like the use of indentation to specify program structure.
-   Python does not keep track of, or place restrictions on, the type of a variable. For example, we could have phone_number = 01132431751 and phone_number = "0113 2431751" in the same piece of code. Python would not warn you that the same variable was used in one place to reference a number, and in another to reference a string of characters.
-   There are a huge number of different ways to do programming tasks, including very simple ones. Programmers can find this to be a bit disorientating.
-   Python does not enforce modularity (though it does support it). This can potentially lead to maintainability problems, especially in a large system.

Most of these issues can be mitigated by careful and systematic programming.

Slowness is likely to be the most difficult issue to overcome.

Slowness can be an issue for certain kinds of program requirements. For instance, if you wanted to program a system that could process mp4 videos and stream them to a display to produce a real-time video, you would probably not use Python for the processing and streaming. In such cases, greater speed can be achieved by lower level **compiled** languages, whose code gets converted (by **compilation**) into hardware-specific, chip-level instructions that can be executed extremely efficiently.

### Question

What language(s) would you expect to be used to produce code that needs to transform video data from one format to another in order to produce a real-time video stream?

### Answer

You would probably use `C` or `C++` for the following reasons:

-   these low-level languages enable direct manipulation of data at the level of bytes or even individual bits
-   their code can be compiled to run very efficiently (and fast)
-   extensive well-crafted libraries are available for `C` and `C++` that support image and video processing.

Program development environments[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#program-development-environments "Permanent link")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In this module you will develop code primarily using the **Jupyter Notebook** programming environment. This is currently a very popular way of coding, especially in the field of data science. Jupyter has only been around since 2015 and has distinctive differences from other program development tools. Although this module has been designed so that all the exercises and assignments can be done using Jupyter, you should also have some knowledge of other ways that programs can be created.

### Editing programs as text files[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#editing-programs-as-text-files "Permanent link")

Program code is essentially the same as text, except that it must conform to the structure of some programming language. Each programming language has a **syntax**, which determines the range of ways in which character symbols may be combined to produce a valid program. The language also has a **semantics**, which determines what computations will take place when syntactically correct program code is executed.

One way to produce a program is to use a general purpose text editing software tool. Many options exist, including Vim, Emacs, Notepad, Notepad++, Atom, Sublime Text. Most of these provide special editing modes for different types of file which provide convenient functionality for working with files of these types. In particular they usually have a Python mode that facilitates editing Python code.

### Integrated Development Environments (IDEs)[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#integrated-development-environments-ides "Permanent link")

The design of a software tool to support programming can be taken further than just providing editing functions. The term **Integrated Development Environment** (usually abbreviated to IDE) refers to a software tool that is designed to support the whole process of creating programs, including editing, running, and debugging, and also organising and combining different program components.

IDEs vary in complexity from simple combinations of the most useful functionality (e.g. [IDLE](https://docs.python.org/3/library/idle.html)) to extremely complicated systems which offer a huge variety of features (which most users will rarely, if ever, use). Most IDEs are primarily designed for a particular programming language but some support several languages. For example, [Eclipse](https://www.eclipse.org/) was designed for Java, but there is a plugin called [PyDev](https://www.pydev.org/), which enables Eclipse to be used for Python development; and Microsoft's [Visual Studio Code](https://code.visualstudio.com/) can also be used for Python.

One of the simplest and most easily accessible IDEs is [IDLE](https://docs.python.org/3/library/idle.html), which comes with most Python distributions. [Spyder](https://www.spyder-ide.org/) is a popular medium complexity IDE that comes with Anaconda Python and is well-suited for those who would like more features than IDLE but do not want something too elaborate. Somewhat more complex than Spyder, the [PyCharm](https://www.jetbrains.com/pycharm) IDE is very popular with professional Python developers.

The Linux operating system itself can be regarded as a kind of IDE since it provides a platform in which a wide range of tools dealing with all aspects of programming can be quite easily combined to provide a customised programming environment.

### Web based programming[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#web-based-programming "Permanent link")

Instead of using locally installed software, for some purposes it is convenient to write and run code via a web interface. This interface links to a remote server that runs the code. A couple of examples are [Programiz Online Python](https://www.programiz.com/python-programming/online-compiler) and [w3schools Python Tutorial](https://www.w3schools.com/python).

These are more for beginners than for serious developers and may be quite limited with regard to code editing and organisation features. However, they have the advantage of allowing almost instant access to Python programming for anyone with a web browser.

### Notebook programming[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#notebook-programming "Permanent link")

Support for the notebook style of programming is one of the main features of Jupyter, which we will be using throughout the course and will be described in detail in the next lesson. For the purposes of the current lesson you only need to know that notebook programming environments provide a means for combining program code with accompanying documentation.

This documentation can be used by the programmer to present any information relating to the code or to results obtained by running it.

Notebook programming could be seen as similar to a traditional kind of IDE software tool. However, Jupyter is actually implemented as a server program that creates an interface that is accessed via a web-browser. This architecture is very flexible in that the Jupyter server can either be running locally on the same machine as the browser, or it can be running remotely on another machine.

### Collaborative web-based programming environments[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#collaborative-web-based-programming-environments "Permanent link")

Another advantage of server-based implementation of a programming interface is that it allows the possibility that multiple different machines (and people) may connect to the same server and have access to the same code. This means that code can potentially be developed collaboratively. Platforms that support collaborative programming have become very popular recently. Among these are Google's [Colab](https://colab.research.google.com/), Microsoft's [Azure Notebooks](https://notebooks.azure.com/), and [Kaggle](https://www.kaggle.com/), the data science/machine learning community platform. All of these support Python and have interfaces very similar to the Jupyter notebook interface that we shall be using. You could potentially use these platforms for some of your work on this module. However, you will need to submit your assignments in a format that can be loaded and run by Jupyter notebook (i.e. as '.ipynb' files).

### IDLE editor for Python[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#idle-editor-for-python "Permanent link")

In the video below Brandon gives an overview of the IDLE editor for Python. As mentioned above IDLE is a simple IDE (Integrated Development Environment) that comes with most versions of Python and it will be useful for you to see how it works.

[View PDF transcript](https://minerva.leeds.ac.uk/bbcswebdav/xid-18489407_4)\
[Audio file](https://minerva.leeds.ac.uk/bbcswebdav/xid-18468680_4)

### Exercise

Run IDLE and use it to enter and run the code example given above.

In order to run IDLE, you will need to find where the program file is located. If, as recommended, you have installed Anaconda 3, the program should be in a sub-directory of the installation folder that has been created on your machine (probably within your home folder). On Windows the program will probably have a path ending `Anaconda3\Scripts\idle.exe`, whereas on Linux it is likely to be `anaconda3/bin/idle3`.

**NOTE:** Remember that the primary programming environment we are using in this module is **Jupyter Notebooks**. You will be introduced to Jupyter in the next lesson.

Lesson complete[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_02_introduction-to-python/#lesson-complete "Permanent link")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

You have looked at what a computer program is, what kind of programming language Python is and the particular strengths and weaknesses of Python. You have learned about the range of different programming environments (IDEs) that may be used to create code and have experimented with using the IDLE IDE.

In the next lesson you will be introduced to the notebook style of programming. You will also be introduced to Jupyter notebook, which you will use throughout this module.