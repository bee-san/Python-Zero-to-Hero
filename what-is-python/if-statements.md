# If Statements

If statements are one of the most powerful statements in all of programming.

We want to do something _if_ a condition is met.

So for example, if the list is not empty:

```python
x = [6]
if x:
	print("I run!")
```

Because x is non-empty, it has a truthy value. Which means this reads as "If True" and it runs. If it read as "If False" it does not run.

If statements only run if the condition is True.

Now let's see it in action.

We can take user input using the `input()` function \(we'll talk about functions soon\).

```python
name = input("What is your name? ")
```

Now let's say we are a wide bouncer at the TryHackMe Official Pub. We only want to let people in that have a name in our special club.

First, we need to create the list of names. Can you guess what we'll be using for this?

```python
names = ["Skidy", "DorkStar", "Ashu", "Elf"]
```

Great! And now if we have a string, such as Jabba, how do we check if the name is in the list?

```python
"Jabba" in names
# False
```

Now we want to print a special little message if and only if the users inputted name appears in our list. We can do this with:

```python
names = ["Skidy", "DorkStar", "Ashu", "Elf"]

name = input("What is your name? ")

if name in names:
	print("The Wide One has allowed you to come in.")
```

Now, what if their name does not appear in the list of names? We can use an else clause.

```python
names = ["Skidy", "DorkStar", "Ashu", "Elf"]

name = input("What is your name? ")

if name in names:
	print("The Wide One has allowed you to come in.")
else:
	print("The Wide One has not allowed you to come in.")
```

## One Line If Statements

We can also build one line if statements pretty nicely in Python.

```python
age = 12

name = "Jabba" if age == 12 else "Skidy"

print(name)
# 'Jabba'
```

This will be made redundant with the next type of loop, however for things with 2+ pointers \(which happens in many optimal algorithms\) while loops still reign supreme.

For loops are best described how they are read:

```python
names = ["Skidy", "DorkStar", "Ashu", "Elf"]
for name in names:
	print(name)
```

For every name in the list of names, do something \(in this case — print the name\).

For loops can iterate over the elements of any iterable. Let's look at a function which returns an iterable, `range`.

Range returns a list of numbers in a range. So to loop between 1 and 9 we would do:

```python
range(1, 9)
```

Range is inclusive, so 1 and 9 are included.

Now to loop over this:

```python
for i in range(1, 9):
	print(i)
```

Note: We often use i as the variable in a for loop as it stands for "item".

