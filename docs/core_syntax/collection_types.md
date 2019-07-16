Collection Types
================
---

These types store a collection of primitive types, objects, and even
collection types!

`NumpyArray`
------------

This type is the same as the Numpy `ndarray` class. This is built in
and every object in the array is separated by commas. All of that is
around a pair of brackets.

```neutron
(1, 2, 3, 4, 5);  // Evaluates to Numpy Array
```

Arrays can be referenced by indexing them:

```neutron
x = (1, 2, 3, 4, 5);
y = x[1]; // give y the value of 2
```

You can also assign a value to an index of the array like this:

```neutron
x = (1, 2, 3, 4, 5);
x[0] = 20;
x[5] = 399
```

`ListType`
----------

This type is the same as the Python `list` class. This is built in and
every object in the list is separated by commas. All of that is around a
pair of square brackets.

```neutron
[1, 2, 3, 4, 5];  // Evaluates to python list
```

Lists can be referenced by indexing them:

```neutron
x = [1, 2, 3, 4, 5];
y = x[1]; // give y the value of 2
```

You can also assign a value to an index of the list like this:

```neutron
x = [1, 2, 3, 4, 5];
x[0] = 20;
x[5] = 399
```

`TupleType`
-----------

This type is the same as the Python `tuple` class. This is built in and
every object in the tuple is separated by commas. All of that is around
a pair of curly brackets. Tuples are immutable, but you can concatenate
them together.

```neutron
{1, 2, 3, 4, 5};  // Evaluates to python tuple
```

Tuples can be referenced by indexing them:

```neutron
x = {1, 2, 3, 4, 5};
y = x[1]; // give y the value of 2
```

Tuples cannot be changed after assignment, but can be concatonated:

```neutron
x = {1, 2, 3}
y = {4, 5}
x = x + y; // give x the value of {1, 2, 3, 4, 5}
```
