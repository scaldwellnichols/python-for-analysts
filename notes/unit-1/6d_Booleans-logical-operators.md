Booleans and logical operators[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iv_booleans-and-logical-operators/#booleans-and-logical-operators "Permanent link")
======================================================================================================================================================================================================================================================================================

Like nearly all programming languages, Python provides a type of value known as Boolean (named after the logician [George Boole](https://en.wikipedia.org/wiki/George_Boole)), which has only two possible values:

-   `True`
-   `False`

These are the only possible values of the type `bool`.

Comparisons[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iv_booleans-and-logical-operators/#comparisons "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

As you saw above Python provides a range of comparison operators, which return Boolean values when evaluated. For example:

-   `3 > 2`

-   `2 + 2 == 5`

-   `input_string == "yes"`

-   `"Hello"[0] == "H"`

These values can be used directly, or assigned to variables, or they occur in the context of **test** operations, which are used to specify **conditionals** (control constructs using `if`) and **loops** (control constructs using `while` or `for`).

Here is a very simple example of code using a test operation within a conditional `if` construct:

```python
if temp > 27 :
    print( "I'm too hot!" )
```

Conditionals and loops are central to the **control logic** of programs, which you will see in a later lesson.

Boolean operators[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iv_booleans-and-logical-operators/#boolean-operators "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Boolean values can be manipulated by means of the Boolean operators: **and**, **or** and **not**:

| Expression | True whenever |
| --- | --- |
| `not test` | test is False |
| `test1 and test2` | both of `test1` and `test2` are `True` |
| `test1 or test2` | either `test1` or `test2` is `True` (or both) |
| `test1 == test2` | `test1` and `test2` have the same value (both `True` or both `False`) |

Since there are only two Boolean values, in all cases where operator does not give the value `True` it gives the value `False`.

You can, of course, combine several Boolean operations together, which enables a complex condition to be defined in terms of combinations of simpler conditions. For example, assuming that the variable `wearing_coat` has been assigned a Boolean value, we might write the following code:

```python
if temp > 27 or (temp > 20 and wearing_coat) :
    print( "I'm too hot!" )
```

In the next section of this lesson you will be introduced to the `None` type.