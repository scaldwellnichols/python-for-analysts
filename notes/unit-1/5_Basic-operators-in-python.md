Basic operators in Python[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_05_basic-operations/#basic-operators-in-python "Permanent link")
===========================================================================================================================================================================================================================================================

In this lesson, you will explore the basic operators in Python. You will explore how **variables** and **assignment** are used in Python before exploring how to use **operators**, **functions** and **methods**.

Python is a large and complex language. Only high-level concepts, core programming constructs and a selection of significant concepts will be covered in this lesson. The rest of the module will go into more detail and throughout the course you should refer to other sources to broaden your knowledge.

Learning outcomes

Successful completion of this lesson will help you to:

-   understand how variables and assignment are used in Python
-   understand how operators, functions and methods are used in Python.

Further resources

Some of the sources you could refer to throughout the course include:

-   [Python documentation](https://docs.python.org/3.8/) -- this includes a [tutorial](https://docs.python.org/3.8/tutorial/index.html) for getting started as well as details on all functions, objects and methods in the core Python library.
-   Another introductory Python tutorial with simple interactive code examples is available at [W3schools](https://www.w3schools.com/python/default.asp).
-   [Wikipedia](https://en.wikipedia.org/wiki/Main_Page) is often a good place to start for more information on high-level concepts about programming or software design (not specific to Python).
-   When faced with a tricky bug or problem you may find useful advice at [stackoverflow](https://stackoverflow.com/). Learning how to ask the right questions is an important skill.

Variables and assignment[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_05_basic-operations/#variables-and-assignment "Permanent link")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Before considering particular data types a few other preliminary concepts will need to be understood. You will first be introduced to the idea of a variable and the assignment operator, which are central to the way data is referred to in most programming languages. You will need to use these in order to provide code examples of how data is manipulated by a Python program.

Variables are used in most programming languages. Variables are words in a program's code that are used to stand in place of some value. They may be thought of as referring to or naming their value. A variable can consist of any sequence of letters and digits and can also contain the underscore symbol `_`. Even though variable names can contain digits, the first symbol cannot be a digit. Words used as variables are usually chosen by the programmer so as to give a mnemonic clue about the type of value referred to (for example, variable referring to a number might be `num`).

The value of a variable could be a number or a string (a sequence of characters) or some more complex data item (maybe a list or an image). Unlike names in ordinary language, variables can change their value. This happens when certain commands are executed.

In Python, variables are given values using the `=` symbol. Giving a variable a value is usually called **assignment**. Here is a simple example:

#### Example 1[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_05_basic-operations/#example-1 "Permanent link")

```python
number_A = 4
number_B = 7

# set the variable, total, to the sum of the values stored in these two variables
total = number_A + number_B

# print the value of total
print( total )
```

It is important to realise that the variable names (in this case `number_A`, `number_B` and `total`) have no significance to the execution of the program apart from them being names associated with some value. This is why you would get exactly the same effect by running the following code:

#### Example 2[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_05_basic-operations/#example-2 "Permanent link")

```python
cachucath  = 4
cachucwn   = 7

# set the variable, omemiserum, to the sum of the values stored in these two variables
omemiserum = cachucath + cachucwn

# print the value of total
print( omemiserum )`
```
Question

Although the effect of running the code of either **Example 1** or **Example 2** is the same, most programmers would find **Example 2** far less appealing. Why is this?

After considering the question, share your thoughts using the discussion thread in Minerva. Access the thread for this topic by selecting the **'Discussion'** tab in the side navigation in Minerva and selecting the **'Considering two code examples'** thread for this lesson.

Aside

Although `=` is used to symbolise **assignment** in many programming languages, some consider this to be inappropriate, because the `=` symbol is traditionally used to signify **equality** , but **assignment** is very different from **equality** (both in its ordinary meaning and in mathematics). In some programming languages (for example, Pascal) assignment is written using the symbols `:=`, with `=` being used for the equality relation. If you would like to learn more about the concept of assignment and its notation in various programming languages, you could take a look at the [Wikipedia article on assignment](https://en.wikipedia.org/wiki/Assignment_(computer_science)).

Question

Programmers who are only familiar with **imperative** programming languages, such as Python (and indeed nearly all the most widely used languages), often assume that making assignments to variables must be an essential feature of any programming language. But is assignment essential? Are there any languages that do not have an assignment operation?

You may be interested to find out more about this question, perhaps by reading about [**functional** programming](https://en.wikipedia.org/wiki/Functional_programming#Referential_transparency). Note: this is not a core part of the module but is included for interest.

After considering the question, share your thoughts using the discussion thread in Minerva. Access the thread for this topic by selecting the **'Discussion'** tab in the side navigation in Minerva and selecting the **'Is making assignments to variables an essential feature of any programming language?'** thread for this lesson.

Operators, functions and methods[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_05_basic-operations/#operators-functions-and-methods "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In order to manipulate data, a programming language provides a variety of operations that can be applied to data items to produce new data items. You will need to understand the terminology used to describe such operations and be able to recognise the different ways in which they occur within code.

The terms **operator**, **method** and **function** all describe kinds of manipulation that can be applied to data. Although conceptually similar they have different connotations and correspond to different forms of syntax in Python:

-   **operator** : this term typically refers to the most basic types of manipulation, such as mathematical operations.\
    These are often represented by specific symbols, such as `+`, `*`, `=`, ...

-   **function** : this term generally refers to an operation that is specified using the syntax

    `<function_name>(<arg1>, ..., <argN>)`

    where `<function_name>` is a word describing the function. `<arg1>, ..., <argN>` are values which will be used by the function and can affect its result. The number of arguments depends on the function. In some cases there can be no arguments (for example `print()` --- if given no arguments, the `print()` function will just output a newline character). Most languages, including Python, not only provide a large number of **built-in** functions but also enable the programmer to define new functions. We will see how to do this later in the module.
-   **method** : The term **method** is used in **object oriented** programming languages (including Python) to describe a function that is intimately connected with some specific type of data that has been defined as a **class**.\
    The syntax for a method application takes the form:

    `<object>.<method_name>(<arg1>, .., <argN>)`

    Here, the `<object>` item is an item of a certain **class** (type) and there is a method called `<method_name>` that has been defined for that class.

You should be aware that the words 'operator' and 'function' are not always used with the precise meanings just given. They are sometimes used in a general sense that includes all three types of manipulation. The term **procedure** is also often used as more-or-less equivalent to function. (Historically, in programming the word 'function' was typically used for an operation that returns a result, whereas 'procedure' meant an operation that produced some effect without returning a value. This distinction is not usually made in Python. In fact in Python every function/procedure returns some value, although this could be the special value `None`.)

You will not need to fully understand the way classes and methods can be defined until later in the module. However, some very common and useful built-in data operations are provided in the form of methods by Python, so you need to recognise the syntax and understand the effect of certain method calls. You will see some examples in the next lesson, when we consider the **string** data type.

Lesson complete[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_05_basic-operations/#lesson-complete "Permanent link")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

You have looked at how variables and assignment are used in Python, as well as operators, functions and methods.

In the next lesson you will start to look at basic data types in Python. You will see how mathematical operators and other functions can be used to manipulate number data.