# Functions

One of the principles of writing clean code is DRY:

> Don't Repeat Yourself \(DRY\)

But, inevitably we will repeat ourselves. Since up to now, code is linear. We run code and move onto the next section after it.

This is where functions come in.

Functions are little boxes you put something in and get a result out. They can be used multiple times, preventing us from repeating ourselves if used correctly.

![](../../.gitbook/assets/image%20%287%29.png)

We input something into the box like 2, the box does something with our input and it outputs something like 4.

In this case, the box squares the input number.

If we wanted to square a bunch of numbers, we would have to write something like:

```python
2**2
3**2
4**2
```

But what if, eventually, we wanted to square more numbers? Or if we wanted to square a users input? We cannot possibly cover all cases. So let's put it into a function.

```python
def square(num):
	return num**2
```

Now we can square any number we want with this function.

The function is the black box.

Every function in Python is defined by the keyword `def` \(which means, literally, define\).

After the `def` keyword we name the function. Let's call it Skidy.

```python
def skidy
```

Next up we add the function arguments. Arguments are variables we input into the function.

Remember our magical box? We had inputs into it. The function's arguments are the inputs.

Let's say the function `skidy` returns "Hello, DorkStar" if the name is "dork" else it will return "Goodbye, {name}".

We need one of the inputs to be a name.

```python
def skidy(name)
```

And then finally, as we saw with if statements we need to include a : on the end of the definition. This means that our next line will be tabbed by 4 spaces.

```python
def skidy(name):
	
```

Now we check to see if the name is "dork" and return "Hello, Dorkstar".

```python
def skidy(name):
	if name == "dork":
		return "Hello, DorkStar"
```

Remember the magic box from earlier? It output something. The `return` statement is the output.

Now, we want to return "Hello, {name}" if their name isn't Dork:

```python
def skidy(name):
	if name == "dork":
		return "Hello, DorkStar"
	else:
		return f"Hello, {name}"
```

We now have our function! But you may have noticed something unusual. What's that `f"Goodbye, {name}"`?

This is called an `f-string` in Python. It stands for "Formatted String".

Strings are kinda boring. They don't really convey information. If we rewrote the code:

```python
def skidy():
	return "Hello, Celestron"
```

What if Cmnatic does not run our program? What if it's someone else?

We need a way to take in a variable, and change what we print based on the variable.

We do this with formatted strings.

To make an f-string, start the string with the letter `f`.

```python
f"This is an f-string"
```

And now to use a variable in the string, include it in some curly braces `{`.

```python
name = "Patrick"
f"Hello, this is {name}".
```

Let's go back to our code.

```python
def skidy(name):
	if name == "dork":
		return "Hello, DorkStar"
	else:
		return f"Hello, {name}"
```

This code is messy. Do you know why? Hint: `f-strings`.

Python has a poem called `The Zen of Python` which details what makes Pythonic code.

```text
>>> import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

This code is both nested, complex and isn't the most obvious way.

We can rewrite our code using one line if statements and f-strings like so:

```python
def skidy(name):
	print(f"Hello, {'DorkStar' if name == 'Dork' else name}")
```

To include quotation marks in strings, we have 2 options.

1. We use the other kind of quotation marks. So if we do `print(" 'hi' ")` we would have to use `'`. Same for the other way around.
2. We use triple quotation marks `print("""Hello "this is a good example" """)`.

And now our code is clean!

Refactoring code is a very important part of programming. As the code grows, we'll have new functions and new ways to make the code clean.

How do you think we can call our new function? Hint: we have been using functions from the start. `print()` is a function.

```python
def skidy(name):
	print(f"Hello, {'DorkStar' if name == 'Dork' else name}")

skidy("Dork")
# Hello, DorkStar
skidy("skidy")
# Hello, skidy
```

