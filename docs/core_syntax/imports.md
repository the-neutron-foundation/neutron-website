Import Statements
=================
---

The syntax for imports goes something like this:

```neutron
import "package";
```

The string after the `import` keyword is the package/object you wish to import.
Importing will take all the  global objects (classes, functions ...) from the
file you want to import to the file that you have the import statement in.
When looking for files to import, the neutron interpreter looks for the files/
folders relative to the file being run first, then files/folders in the system
path (where the neutron source code is). All path datums are separated by `::`
(double colons). Imports in Neutron are relative.

Example
-------
Say we have the following folder (where `Module` and `SubModule` are folders):

```path
Module:
  --init--.ntn
  SubModule:
    --init--.ntn
    other_file.ntn
```

The module `Module` can be imported by adding `import "Module";` if the
`Module` folder is in the system path or in the same directory as the file being
run. You can also do `import "Module::SubModule";` to import just the `SubModule`
module.

Say the `SubModule/--init--.ntn` file imports `other_file.ntn`, for that to work,
`SubModule/--init--.ntn` would have to include `import "other_file";`. Note, it
does not need to say `import "Module::SubModule::other_file"`. This is what is
meant by "Imports in Neutron are relative".

Using A module
--------------
Say you have a module called `io`, like this:

```path
io:
  --init--.ntn
  print.ntn
    print()
```

Inside the `print.ntn` file you have a `print` function, which is imported in
the `--init--.ntn` file. When importing the `io` module, you are really
importing the `--init--.ntn` file, and anything imported in the `--init--.ntn`
file. With this knowledge, we can import the `print` function with or without a
namespace:

<!-- tabs:start -->
#### ** With Namespace **
```neutron
// With namespace
import "io";
io::print("Hello, World!");
```

#### ** Without Namespace **
```neutron
// Without namespace
import "io::print";
print("Hello, World!");
```
<!-- tabs:end -->

It is recommended to use a namespace if you are using many functions/classes
from the module you are importing from. Only dont use a namespace if you only
intend to use a few functions/classes from the module you are importing.

Note, if there are more modules inside of module (submodules), you can import
them too. If you have a module called `Module`:

```path
Module:
  --init--.ntn
  SubModule:
    --init--.ntn
    other_file.ntn
      print()
```

Then you can import the print functions with the 2 namespace, 1 namespace, or none:

<!-- tabs:start -->
#### ** With 2 Namespaces **
```neutron
// With namespace
import "Module";
Module::SubModule::print("Hello, World!");
```

#### ** With 1 Namespace **
```neutron
// With namespace
import "Module::SubModule";
SubModule::print("Hello, World!");
```

#### ** Without Namespace **
```neutron
// With namespace
import "Module::SubModule::print";
print("Hello, World!");
```
<!-- tabs:end -->

Making A Module
---------------
When creating a module, you can either have it as a single file (e.g. `module.ntn`)
or as a folder. If you have a folder, it must have a `--init--.ntn` file in every
directory. Example of a (useless) `math` module:

```path
math:
  --init--.ntn
  add.ntn
  sub.ntn
  mul.ntn
  div.ntn
```

<!-- tabs:start -->
#### ** --init--.ntn **
```neutron
// --init--.ntn file (no namespace)
import "add::add";
import "sub::sub";
import "mul::mul";
import "div::div";
```

#### ** add.ntn **
```neutron
func add(x, y) {
  return x + y;
}
```

#### ** sub.ntn **
```neutron
func add(x, y) {
  return x - y;
}
```

#### ** mul.ntn **
```neutron
func mul(x, y) {
  return x * y;
}
```

#### ** div.ntn **
```neutron
func div(x, y) {
  return x / y;
}
```
<!-- tabs:end -->

Conclusion
----------
Imports in neutron are like that of python, but they are relative and use
`--init--.ntn` instead of `__init__.py`.
