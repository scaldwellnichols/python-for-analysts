Strings[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#strings "Permanent link")
==================================================================================================================================================================================================================

Character symbols[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#character-symbols "Permanent link")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Strings are sequences of character symbols. When stored or processed by a computer, each character symbol will be represented as a sequence of one or more bytes, in accordance with some [character encoding](https://en.wikipedia.org/wiki/Character_encoding) (most commonly [ASCII](https://en.wikipedia.org/wiki/ASCII) or [Unicode](https://en.wikipedia.org/wiki/Unicode)). But for this lesson, we can simply consider character symbols to be the atomic elements of strings. Many programming languages have distinct data types for characters and strings. However, in Python there is no separate data type for characters, a character is just a string of length 1. This seems to work well and avoids the need for type casing between individual characters and strings.

Representation of strings[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#representation-of-strings "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Within a Python program there are several ways to define a string. A string is surrounded by single or double quotes.

```python
'This is a string.'

"So is this!"`
```
The choice of two types of quotation character for demarcating strings makes it easier to write strings that have quotation marks within them.

```python
"This string contains a quote symbol, but it's not the end of the string."
```

To define a string over several lines put three quote marks before and after the string.

```python
"""
Triple quoted strings provide
 - an easy way of incorporating chunks of formatted material
into a program file.
"""
```

Special characters can be included using an **escape character**. For example, `\n` represents a new line.

`"Special characters like 'newlines' \n can be included by use of backslashes"`

Basic Operations on strings[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#basic-operations-on-strings "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

We can add and 'multiply' strings using the same operators as for numerical data types.

| operation | code example | value returned |
| --- | --- | --- |
| `+` | `'cat' + 'fish'` | `'catfish'` |
| `*` | `'Hey!' * 3` | `'Hey!Hey!Hey!'` |

The `in` operator recognises whether one string appears as a substring of another.

| operation | code example | value returned |
| --- | --- | --- |
| `in` | `'tuna' in 'fortunate'` | `True` |
| `in` | `'fun' in 'programming'` | `False` |

And a very useful and common function -- how many characters are in this string?

| operation | code example | value returned |
| --- | --- | --- |
| `len` | `len('antidisestablishmentarianism')` | 28 |

Indices and slices[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#indices-and-slices "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Individual characters and ranges of characters (called sub-strings or slices) can be extracted using a fairly simple but flexible notation. To refer to a character within a string we use an index number, which must be an `int`. The syntax used is illustrated by the following examples:

| operation | code example | value returned | notes |
| --- | --- | --- | --- |
| *use of a string index* | `"Hello"[0]` | `'H'` | the index counts from `0` |
|  | `"Hello"[1]` | `'e'` |  |
| *a negative index* | `"Hello"[-2]` | `'l'` | a negative index counts back from the end |

You can also extract a sub-string (slice) of a string by specifying a range of indices using the : character:

```python
"hello everyone"[6:11]
> 'every'
```

String comparisons[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#string-comparisons "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The same comparison operators that can be applied to numbers can also be applied to strings and return a **Boolean**. Strings are ordered alphabetically (i.e., the order they would appear in a dictionary) so that the string `'abacus'` is considered 'less than' than `'computer'`.

Aside

Comparisons can be used with many other data types as well. When defining a new type of data as a `class`, a programmer may specify conditions for equality and ordering of instances of that class.

String methods[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#string-methods "Permanent link")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Many useful operations on strings are provided in the form of **methods** . A method is essentially just a function that is attached to some particular class.

| method | example code expression | value returned |
| --- | --- | --- |
| `startswith` | `'fundamentals of programming'.startswith('fun')` | `True` |
| `endswith` | `'slaughter'.endswith('laughter')` | `True` |
| `upper` | `'Hello!'.upper()` | `'HELLO!'` |
| `isupper` | `'Hello!'.isupper()` | `False` |
| `title` | `'this is a title'.title()` | `'This Is A Title'` |
| `join` | `'; '.join(['Veni', 'Vidi', 'Vici'])` | `'Veni; Vidi; Vici'` |
| `split` | `'never-to-be-separated'.split('-')` | `[ 'never', 'to', 'be', 'separated']` |

f-strings[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_06_iii_strings/#f-strings "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The syntax for `f-strings` was introduced version 3.6 of the Python language. Although a relatively recent innovation, which does not provide anything that goes beyond what could not be achieved by the string formatting operations provided in earlier Python versions,

`f-strings` provide a very flexible and convenient way of creating strings that is used extensively by many programmers.

The basic idea of `f-strings` is very simple. They enable code to be embedded within a string specification, in order to construct a string where the embedded code is replaced by its value. In most ways, an `f-string` looks just like an ordinary string, but with an `f` attached before the first quote mark. For example, `f"This"` is an `f-string`. It is not a particularly useful one because it does not include any embedded code, so it specifies the same string as just "This". But it is easy to insert code into an f-string. You just enclose it within braces (i.e. `{` `}`).

Here is a simple example, which should give you a good idea of what is possible:

```python
for x in range(10):
    print( f"{x} squared is {x**2}" )
```

Notice that the embedded code does not need to evaluate directly to a string (in the above example the results of both of the embedded code segments will be `int` values). The returned value will be automatically converted to a string representation.

Aside

Every Python object has a `__repr__()` that can be can be used to convert it into a string. For example, try evaluating `[1,2,3].__repr__()` --- you will get a string representation of the list. Within an `f-string`, values returned by embedded code we be converted to strings by implicit use of this method.

Question

What string formatting features were available in earlier versions of Python?

Answer

Early versions of Python provided a `%` operator which could be used to substitute values into a string in similar fashion to string formatting provided in C. (Note: in other contexts, `%` can have a completely different function as a modulus operator).

From Python 3.0 (also back-ported to 2.7) a `format` method was provided for string objects. Although not as concise as the `%` syntax the `format` method is clearer and more flexible.

Question

How can you include actual brace symbols in an f-string, without them being interpreted as enclosing embedded code?

Answer

You can simple double them, using `{{` for an open brace and `}}` for a close brace.

Exercise

To familiarise yourself with f-strings you could do the following:

-   Read up on f-string syntax and the how to use other formatting\
    tricks such as alignment, to make your strings look good.

-   Consider whether you prefer the f-string syntax to the other ways of formatting a string in Python.

-   Can you produce the following output using a short piece of code? You can do it just by printing one fairly simple\
    f-string within a loop statement:

 ```
    1                1                1
    4                4                4
    27               27              27
    256             256             256
    3125            3125           3125
    46656          46656          46656
    823543         823543        823543
    16777216      16777216     16777216
    387420489    387420489    387420489
    10000000000 10000000000 10000000000
```

You will explore string methods further in the next exercise.

In the next section of this lesson you will be introduced to Booleans and logical operators.