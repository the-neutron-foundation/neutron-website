Primitive Types
===============
---

There are many primitive types in neutron, including:
* The `IntType` - for integers (e.g. `1`, `12938`, `9589`)
* The `FloatType` - for floats (e.g. `1.11`, `23.43`, `2.3415325`)
* The `BoolType` - for booleans (`true`, `false`)
* The `NullType` - for null types (`null`)

Note that with the examples below, the code won\'t actually work,
because neutron doesn\'t understand single expression by themselves.

`IntType`
---------

This type implements the python 3 `int` class. It can only include whole
numbers (not decimals). If you divide integers, if results in a decimal,
it rounds down. Note adding an integer to an integer returns an integer.
Here is an example:

```neutron
1 + 1; // Evaluates to 2
3 / 2; // Evaluates to 1 (round down)
2 * 3; // Evaluates to 6
20 - 3; // Evaluates to 17
3 + 2.1; // Error can't add int to float
```

`FloatType`
-----------

This type implements the python 3 `float` class. It can decimals and
whole numbers. Note it must contain a decimal (i.e `1.00`). Adding a
float to a float returns a float. Example:

```neutron
1.0 + 1.2; // Evaluates to 2.2
3.0 / 2.0; // Evaluates to 1.5
2.2 * 3.7; // Evaluates to 8.14
20.0 - 3.2; // Evaluates to 16.8
3.5 + 2; // Error can't add int to float
```

`StringType`
------------

This type implements the python 3 `str` class. You can concatenate
strings in neutron in the same way as python. You may use single
and double quotes.

```neutron
"Hello, " + "World!"; // Evaluates to "Hello, World!"
'Hello, '' + 'World!''; // Also evaluates to "Hello, World!"
```

`BoolType`
----------

This type implements the python 3 `bool` class.

```neutron
true; // Evaluates to true
false; // Evaluates to false
```

`NullType`
----------

This type is a null, and can be used as a placeholder. It is returned when a
function is run and there was no return statement in it, or if you type the
`null` keyword. You cannot do arithmetic with `null`s, if you do, the neutron interpreter
will give you an error. For example:

```neutron
x = null; // Give x a value of null
y = x + null; // Gives error because null + null is invalid
```

**WARNING: Types cannot (and will not) mix (e.g. adding `IntType` and `FloatType`, or adding
`StringType` and `BoolType`)**
