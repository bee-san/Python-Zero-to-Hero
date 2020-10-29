# Introduction

Object orientated programming revolves around objects. Don't worry, we won't talk about them for long.

An object can be anything you want.

Imagine a bicycle. The bike is an object with the name "bike".

The wheels of the bike are objects too, which are said to be attributes \(objects can be attributes of other objects in Python\) of the parent class bike.

Let's go right into an example.

```python
class Wheel:
```

We define a class by calling `class <class_name>:`. Our class is called wheel here.

What do wheels have? Well, they have tyres so let's add one.

```python
class Wheel:
	self.tyre = "Michelin"
```

Now our wheel has a Michelin tyre.

Classes are templates for objects. We can build a class such as a wheel, and when we build an object from our class we are saying "every object is based on this one template class".

When we build a new Wheel object:

```python
x = Wheel()
y = Wheel()

x.tyre
# "Michelin"
y.tyre
# "Michelin"
```

It will always have the items in the class definition. In this instance, every single wheel of our bike will always have a Michelin tyre.

Now let's get into magic methods.

Imagine you have a Person class:

```python
class Person:
	def __init__(self, first_name, last_name):
		self.first_name = first_name
		self.last_name = last_name
```

The `__init__` stands for `initialisation`. When we _initialise_ \(create\) an object from this class, this function runs. The function has 3 arguments.

* `self`

Every function \(called a method in OOP\) requires a `self` attribute \(in Python\).

* `first_name`

The first name of the person.

* `last_name`

The last name of the person.

Because we have the argument `self`, we can change the classes _attributes_ \(the values of the object, think back to our wheel example having the attribute that all tyres are "Michelin"\).

So we can do this:

```python
skidy = Person("Skidy", "Shallot")
skidy.first_name
# "Skidy"
skidy.last_name
# "Shallot"
```

What if we have another person, Dark?

```python
dark = Person("Dork", "Star")
```

Now, Dark and Skidy want to get married. In the imaginery land of TryHackMe marriage happens by adding the 2nd persons lastname onto the first. So if Skidy & Dark got married, their combined last name would be `Shallot-Star`.

How do we program this so that any person getting married has a new last name that matches this?

With magic methods!

```python
class Person:
	def __init__(self, first_name, last_name):
		self.first_name = first_name
		self.last_name = last_name

	def __add__(self, person):
		# Adds the 2 strings together and updates our lastname
		self.last_name = self.last_name + "-" + person.last_name
		# Updates 2nd persons last name to match ours
		person.last_name = self.last_name
		return person
```

**Tip: all magic methods follow the format `__X__` with double underscores on either side. They are sometimes called "dunder methods" because of this.**

The way this works is that whenever we do `skidy + dark` where `skidy` and `dark` are objects of the class `Person` we will add Dark's lastname to Skidy's last name, and we will return Dark with their new last name too.

Our code looks like:

```python
skidy = Person("Skidy", "Shallot")
dark = Person("Dork", "Star")

dark = skidy + dark

skidy.last_name
# Shallot-Star
dark.last_name
# Shallot-Star
```

But the real magic here is that we implemented addition for our own code! This is the power of magic methods, and I'll go into much more detail later on. Anyway, back to operators!

### What data structures have magic methods?

Almost all of them implement the basic magic methods which are:

* Addition
* Subtraction

Division / Mod / Comparison \(==, ≠ \(talked about soon\)\) are rarer, but can still be seen in some operators.

