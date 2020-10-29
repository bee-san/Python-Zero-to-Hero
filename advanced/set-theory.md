# Set Theory

A set is simply a set of objects. They don't have to be the same type, or have any relation to one another.

```python
set = (apples, pears, oranges)
```

Sets are denoted with parenthesis `( )`. With the separation of elements being a comma. Or sometimes `{ }`.

Sets follow 2 rules:

* Only unique items.

Sets can only contain unique items. It cannot contain the same item twice or more.

* The set is unordered.

There is no order or structure to a set.

The first rule is quite useful. Say, for example we have a list of words from a book:

```python
words = ["hello", "my",  "name", "is", "brandon", "and",
"your", "name", "is", "brandon"]
```

To find all the unique words, we put the words into a set:

```python
words = ["hello", "my",  "name", "is", "brandon", "and",
"your", "name", "is", "brandon"]

unique = set(words)
# {'hello', 'is', 'and', 'brandon', 'my', 'your', 'name'}
```

The 2nd rule ties in nicely with the 1st rule. **A set aims to replicate how we see things in our lives.**

Imagine we are on a road trip with Jahan, Olivia, and Ryan.

Next year, we want to go on a field trip again. It doesn't make much sense to invite Jahan, Olivia, Jahan, Ryan, Jahan.

And it also doesn't make sense to assign an "order" to them. They're people, not elements in an array!

There are other types of sets too. Such as a a [multiset](https://en.wikipedia.org/wiki/Multiset) which allows non-unique elements but no order.

**Note** sets are a computer science / maths topic. I will quickly go over the maths, and we will explore how this is applied in Python,

## 🦁 Cardinality

The cardinality of a set is the length of the set. For the set:

```python
A={1,2,3,4,5,6}
```

The cardinality is

```python
|A|=6
```

## 🚴‍♀️ Equality of Sets

2 sets are equal when all the elements match.

```python
a={1,2,3}
b={3,2,1}
a==b
# True
```

Remember, order doesn't matter - so sets are equal despite being in the 'wrong' order!

## 🚇 Infinite Sets

Some sets are infinite. Such as the set containing all the natural numbers, or all the real numbers.

We can express infinite sets using a little bit of maths. Heard of [list comprehensions](https://skerritt.blog/learn-functional-python-in-10-minutes/)? It looks the same syntactically, but operates infinitely.

The set of all even numbers is:

$$
A={2n:n ∈ Z}
$$

Read this as "for each number, n, in the set of all integers, Z, multiply the number by 2". Which will give us the set of all even numbers.

In a list comprehension, it would look like:

```python
[2 * n for n in naturalNumbers]
```

However, this won't work as Python doesn't allow infinite sets.

## 🐈‍⬛ The Empty Set

The empty set is the set containing nothing at all. It is much like 0. It is nothing, and serves the purpose as a negated value. We don't have 0 apples, we have no apples.

The empty set serves the same purpose. We don't have a set containing all the words, we have nothing.

Its symbol is ∅.

## 🌌 The Universal Set

The Universal Set U is the set which contains all objects, including itself.

If our universe contains only integers, 1, 2, 3, ..., then the universal set is the set of all integers.

## 🏥 Operations

Just like with other data types, sets have operations! Let's start with some operations you may already know.

### ❌ Union

The union is combining 2 sets together \(think addition\). The symbol for the union is ∪. Let's look at an example.

```python
A = {1, 2, 3}
B = {3, 4, 5}
B U A = {1, 2, 3, 4, 5}
```

Notice how when we perform a union, we have two 3's. Since sets only contain unique elements, we simply toss the extra 3 away. Also note, there is no order. So B ∪

A does not result in \(3, 4, 5...\) as the order doesn't exist. We can even say `B ∪ A = {3, 5, 1, 4, 2}`.What if we union an empty set with a non-empty set? Or an empty set with another empty set?

```python
∅∪{1,2,3}={1,2,3}
∅∪∅=∅
```

When we get onto subsets and the likes we'll learn to appreciate the empty set and this simplistic maths.

