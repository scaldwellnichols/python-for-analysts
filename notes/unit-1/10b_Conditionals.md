Conditionals[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_ii_conditionals/#conditionals "Permanent link")
================================================================================================================================================================================================================================

Often in life our behaviour depends on, for example, the weather, or other people's actions, or the time of day. The same happens in programming -- we want some piece of code to be executed only in the right circumstances. So just as I might say "**If** it is raining, then I will take an umbrella. **Otherwise, if** it is sunny, I will wear sunglasses.", so Python provides the **if** statement to allow for conditional execution of code.

If[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_ii_conditionals/#if "Permanent link")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The `if` statement provides a way to only execute some statement(s) when a given condition is true.

![Flow diagram of the if flow of logic. Diamond shape labelled condition at top, two arrows tabled true and false create a square. If the true arrow is followed it leads to a box labelled statement.](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/images/PDS_IMG_004.png)

**Figure 1.4:** Diagram of the `if` flow of logic

[View full text description](https://minerva.leeds.ac.uk/bbcswebdav/xid-18459007_4)

To write an `if` statement in Python, first, the `if` keyword, followed by the condition to be checked and then a colon. The colon must be included. The code which will be executed if the condition is met is **indented**, all lines of this section of code have to be indented by the same amount. The indentation is essential, this is how Python knows which bit of code belongs to the `if` block. Other languages might use parentheses or a special ending token to show which part of the code belongs to the `if` block and which code should always be executed, but Python relies entirely on the indentation. Later code is written without this indentation and this is no longer part of the `if` statement so it will be executed in all cases.

```python
if <condition>:
    <code to execute when condition is True>
<code that always executes whether condition is True or False>
```

The expression in `<condition>` can be anything that evaluates to a Boolean (True or False).

### Note

In fact, Python gives some flexibility here because other values are treated as True or False when the context requires a Boolean. For example, the integer 0 is treated the same as the Boolean value False, and all other integers are treated the same as True. The empty string '' evaluates to False, all other strings evaluate to True. Similarly, the empty list `[]` and empty dictionary `{}` both evaluate to False, all other lists and dictionaries evaluate to True.

Sometimes this convenience is really helpful and allows for code that is more readable and succinct, other times it can be a source of bugs. In general, `<condition>` should return a Boolean. If it will return any other type (int, string, float, list...) then remember to check carefully how the different possible values will be interpreted.

Elif[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_ii_conditionals/#elif "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

We might want to check a few different conditions, as in the earlier example "...**Otherwise, if** it is sunny, I will wear sunglasses."

![Flow diagram showing else if flow of logic. This flow diagram links two if flows.](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/images/PDS_IMG_005.png)

**Figure 1.5:** Diagram of the `else` `if` flow of logic

[View full text description](https://minerva.leeds.ac.uk/bbcswebdav/xid-18459008_4)

In Python this is achieved by **elif** (short for "else, if"). The `elif` keyword is used after `if`, it can't be used on its own. The line that starts with `elif` also contains an expression that evaluates to True or False, and must end in a colon, and the next line is indented. Any subsequent lines indented by the same amount also form part of the same block of code belonging to the `elif` statement. When the indentation is reduced again then we're no longer within the `elif` block.

```python
if <condition_1>:
    <code to execute when condition_1 is True>
elif <condition_2>:
    <code to execute when condition_1 is False AND condition_2 is True>
<code that always executes>
```

Notice that the conditions are being checked in order. In our weather example we said "**If** it is raining, then I will take an umbrella. **Otherwise, if** it is sunny, I will wear sunglasses." What should happen if it is both sunny and raining at the same time? Because of the word **otherwise** the logical interpretation is that in this case I will only take an umbrella, I'll only wear sunglasses in the case that it's not raining. In the `if ... elif` structure at most one of the block belonging to the `if` part and the block belonging to the `elif` part can be executed.

Maybe there are many different scenarios to check -- then we just keep adding `elif` statements, there's no limit on how many can be used.

```python
if name == 'John':
    print('my name is John')
elif age < 20 :
    print('my name is not John and I am less than 20 years old')
elif car == 'BMW':
    print('my name is not John, I am at least 20 years old, and I drive a BMW')

# ... other elif statements...

<code that always executes>
```

Maybe it's more sensible that when the weather is both raining and sunny I should take both an umbrella and sunglasses. Then I would say "**If** it is raining, then I will take an umbrella. **If** it is sunny, I will wear sunglasses...". The same works here -- just use multiple, unrelated `if` statements.

```python
if raining:
    print('take an umbrella!')

if sunny:
    print('wear sunglasses!')
```

Else[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_ii_conditionals/#else "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Finally, we may have some default behaviour. For example, "**If** it is past 7am I will get up, **otherwise** I will go back to sleep".

![Flow diagram of the if else flow of logic. Diamond shape labelled condition at top, two arrows tabled true and false create a square. If the true arrow is followed it leads to a box labelled statement 1. If false is followed it leads to a box labelled statement 2.](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/images/PDS_IMG_006a.png)

**Figure 1.6:** Diagram of the `if` `else` flow of logic

[View full text description](https://minerva.leeds.ac.uk/bbcswebdav/xid-18459009_4)

![Flow diagram showing else if flow of logic. This flow diagram links two if else flows.](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/images/PDS_IMG_006b.png)

**Figure 1.7:** Diagram of the `if` `elif` `else` flow of logic

[View full text description](https://minerva.leeds.ac.uk/bbcswebdav/xid-18459010_4)

In Python the default behaviour is identified using the keyword `else`. No condition is needed after `else`, but it must be followed by a colon and the code on the next line(s) should be indented. This indented block of code is executed when none of the conditions in the `if` and `elif` parts evaluated to true.

```python
if <condition_1>:
    <code to execute when condition_1 is True>
elif <condition_2>:
    <code to execute when condition_1 is False AND condition_2 is True>
else:
    <code to execute when condition_1 is False AND condition_2 is False>
<code that always executes>
```

### Aside

It is possible in Python to write conditionals in fewer lines, as below. If the code within an `if` block would have been written over several lines then these statements can be separated with semicolons instead.

```python
if <condition_1>: <code to execute when condition_1 is True>
elif <condition_2>: <code to execute when condition_1 is False AND condition_2 is True>
else: <code to execute when condition_1 is False AND condition_2 is False>
<code that always executes>
```

Don't do this. As you can see, it's much less readable than using separate lines and indentation. Most Python programmers will rarely use this style, and only when the `if` block is extremely simple. It's better to avoid it entirely and get comfortable with using indentation to organise your code blocks.

Nested conditionals[¶](https://minerva.leeds.ac.uk/bbcswebdav/institution/Inter-faculty/ODLC/artificial_intelligence/OCOM5100M_ProgrammingForDataScience/MKDocs_Site/content/unit1/1_10_ii_conditionals/#nested-conditionals "Permanent link")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The code that will be executed as part of an `if` (or `elif`, or `else`) block can contain any valid Python code. In particular, it can contain more `if` statements. Python will understand which code belongs to which `if` block by the indentation.

```python
if sunny:
    print("A beautiful sunny day. Let's go for a walk!")

    if temp < 10:
        # it's sunny AND the temperature is less than 10 degrees
        print("And we should take a good coat on our walk.")

    if temp > 20:
        #  it's sunny AND the temperature is greater than 20 degrees
        print("And don't forget to pack lots of water for the walk.")
```

There is no limit to how deeply nested `if` statements can be, but if you have too many nested statements then the code might become difficult for humans to understand which makes bugs more likely. To avoid having deeply nested conditional statements you could **refactor** your code by defining **functions**. We will see how to do this later in the module.

In the next section of this lesson you will be introduced to loops.