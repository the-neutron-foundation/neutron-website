Embedded Python Code
=============
---

Putting Python Code
-------------------

It is possible to make functions that have python functionality by
putting embedded python code. This is how the `io` packages were written.

To put embedded python code into your Neutron code, use the backtick ```.
You can use python code anywhere as an expression, or just pure python
code.

Example of pure embedded python code:

```neutron
`print("Hello, Neutron!")
x = "how are you?"
a_python_function_here();
```

Example of python code being used as an expression:

```neutron
a_neutron_function(`python_function(10)`, `20`, 30); // Use python code as positional arguments
x = `len("Hello World!")`; // len is 12
```

In order to get variables, or make them, you must do it in a special
way. To make a variable, use the namespace `var` for local variables and
`gvar` for global variables. Example:

```neutron
`var.local_variable = "foo"
gvar.global_variable = "This is a global variable"`;
```

To reference to a variable, just use the namespace `var` for local
variables and `gvar` for global variables, and don\'t assign them to
anything. Note that getting the variable from the namespace only returns
a class, not the value python equivalent value. In order to get the
value, you must use the `.value` attribute. Example:

```neutron
var.local_variable # get value of variable
gvar.global_variable`;
```

To get an attribute from a class in a method, get the variable `this` and get the `.objects` attribute from it:

```
class test {
  def --init--(this, arg) {
    this::arg = arg;
    `print(var.this.objects["arg"])`
  }
}
```

To get the python equivalent value, use the `.value` attribute. For
example:

```neutron
local_variable = true;
`print(var.local_variable) # prints "true"
print(var.local_variable.value) # prints "True"`;
```

Making Types
------------

To make a variable, you cannot just simply assign a variable. You must
make the appropriate class for the appropriate type you are assigning a
variable to. For example, to make an integer 10, you must use the
`bt.IntType` and use the python `10`, and make the `enter_value` keyword
argument `True`. Example:

```neutron
`var.foo = bt.IntType(10, enter_value=True)
var.foo = bt.StringType("this is a string", enter_value=True)
var.foo = bt.NumpyArray(np.array(1, 2, 3, 4), enter_value=True)`;
```

Note that in this case, `bt` is short for builtin types.

**NOTE: you no not need to do this with expressions. Instead, with expressions,
you just need to write the normal python `int`, and neutron will make a
`bt.IntType` type.** For example:

```
x = `10+10`; // maps to bt.IntType(10+10, enter_value=True)
y = `None`; // maps to bt.NullType()
```

`Builtin Types` List
--------------------

The builtin type available are:

`bt.IntType` - for integers (maps to `int` in python)

`bt.FloatType` - for floats (maps to `float` in python)

`bt.StringType` - for strings (maps to `str` in python)

`bt.BoolType` - for booleans (maps to `bool` in python)

`bt.NumpyArray` - for Numpy arrays (maps to `ndarray` in python)

`bt.ListType` - for python-like lists (maps to `list` in python)

`bt.TupleType` - for python-like tuples (maps to `tuple` in python)

`bt.NullType` - for a null type similar to the python None type (no
arguments) (maps to `None` in python)
